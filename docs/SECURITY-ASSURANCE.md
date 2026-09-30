# Security assurance case

This document states what a user of the German Technical Writing Skill can and cannot expect in terms of security, and why. Every claim names the file that supports it. Organisation-wide policies (vulnerability reporting, findings handling, secret management) are linked from the README section "Governance and policies" and are not repeated here.

## What the repository ships

- Markdown prose: `skills/german-technical-writing/SKILL.md` and the seven files under `skills/german-technical-writing/references/`. An AI agent reads them as instructions for writing German text.
- Eval definitions: `skills/german-technical-writing/evals/evals.json`. Only the validators in CI read them; no agent or grader in this repository runs them.
- Package metadata: `composer.json`, `package.json`, `plugin.json`, `.claude-plugin/plugin.json`.
- Repository tooling: `.pre-commit-config.yaml`, `renovate.json`, lint configuration, and the workflows under `.github/workflows/`.

The skill contains no program, script or hook; the only executable line in the repository's package metadata is the `prepare` script in `package.json` (see Limits). `SKILL.md` declares `compatibility: "Language-only skill. No runtime dependencies."` and `allowed-tools: Read`, and none of the skill files contains a command for the agent to run.

## Security requirements

1. Loading the skill must not cause the agent to run commands, fetch network resources or read secrets.
2. The content a user installs must be the content maintained in this repository.
3. Released archives must be verifiable as built by the release workflow from a signed tag.
4. The repository's CI must not grant its token more permissions than each job needs, and must not run pull-request code with a write token.

## Actors and trust boundaries

| Boundary | Trusted side | Untrusted or less-trusted side |
|----------|--------------|--------------------------------|
| Contribution | Maintainers listed in the organisation access roster | Pull requests from any GitHub user |
| CI | The reusable workflows the callers use, pinned to `main` of netresearch/.github, netresearch/skill-repo-skill and netresearch/typo3-ci-workflows; the `pull_request_target` workflows (`labeler.yml`, `auto-merge-deps.yml`), which run as defined on `main` | Pull-request content, including the pull request's own copy of the calling workflow files, which GitHub runs for `pull_request` events (with a read-only token for pull requests from forks) |
| Distribution | This repository, its signed release tags and release assets | Mirrors, forks, and channels that fetch from this repository (marketplace, Packagist, npm `github:` installs, skills.sh) |
| Use | The user who installs and invokes the skill | The text the user asks the agent to write or rewrite |

## Threats and countermeasures

**Malicious instructions added to the skill prose.** An agent follows the Markdown it loads, so a change that told it to run a command or exfiltrate data would reach every user after the next release. Countermeasures: changes arrive through pull requests; Betterleaks secret scanning, zizmor and the skill validator run on every pull request to `main` (`.github/workflows/security.yml`, `.github/workflows/lint.yml`); the skill contains no instruction to run a command, and its front matter lists only `Read` under `allowed-tools`. That field pre-approves tools while the skill is active; it does not take away tools the agent session already has, so it is not a barrier against a malicious instruction. Reviewing the prose itself for such instructions is a human review step, not an automated check.

**Tampered release archives.** The release workflow `.github/workflows/release.yml` calls `netresearch/skill-repo-skill/.github/workflows/release.yml`. That reusable refuses to run unless the pushed `v*` tag is annotated and its signature verifies on GitHub, builds zip and tar.gz archives, signs `SHA256SUMS.txt` keyless with Cosign, and attests the archives and the checksum file with SLSA build provenance (`actions/attest-build-provenance`). A user can verify an archive with `gh attestation verify` and the checksum signature with `cosign verify-blob`.

**Compromised or over-privileged CI.** Every workflow sets `permissions: {}` at the top and grants each job only the permissions its reusable needs (all files under `.github/workflows/`). The two `pull_request_target` workflows, `labeler.yml` and `auto-merge-deps.yml`, call reusables that do not check out pull-request code; each carries a `zizmor: ignore[dangerous-triggers]` comment stating that reason. `auto-merge-deps.yml` passes two named secrets instead of `secrets: inherit`. zizmor analyses the workflows on pull requests to `main` (`security.yml`), and the OpenSSF Scorecard runs weekly and on pushes to `main` (`scorecard.yml`).

**Vulnerable or malicious dependencies.** The package has no runtime dependency of its own. `composer.json` requires `netresearch/composer-agent-skill-plugin` (constraint `*`), the Composer plugin that registers the skill; `package.json` declares `@netresearch/agent-skill-coordinator` only as a peer dependency. Dependency review and Composer Audit run on pull requests to `main` (`security.yml`), and Renovate keeps the pinned pre-commit hook revisions current (`renovate.json` enables its `pre-commit` manager).

**Secrets committed to the repository.** Betterleaks scans pushes to `main` and pull requests to `main` (`security.yml`). The package itself reads and stores no credentials.

## Secure design principles applied

- **Least privilege:** `SKILL.md` pre-approves no tool other than `Read`; every workflow sets `permissions: {}` and grants each job only what it needs.
- **Economy of mechanism:** the skill is prose with no runtime code, so there is no parser, network client or file writer to get wrong.
- **Complete mediation of releases:** every release goes through the reusable release workflow, which checks the tag signature before it builds anything.
- **Open design:** all content, workflows and release attestations are public.

## Common weaknesses

The OWASP Top 10 and CWE Top 25 categories concern software that accepts input, stores data, authenticates users or builds queries and commands. The package does none of this: it has no code path that parses input, no output sink, no authentication and no storage. The weaknesses that apply are supply-chain ones (tampered artefacts, compromised CI, vulnerable dependencies), countered as described above.

## Limits

- The skill cannot restrict which tools the agent has. `allowed-tools: Read` only pre-approves reading; what the agent does with other tools its session holds is outside this package.
- The skill's advice concerns wording. Text the agent writes with it can still contain confidential information the user supplied; the skill does not filter content.
- npm runs the `prepare` script of a package installed from git ([npm scripts documentation](https://docs.npmjs.com/cli/using-npm/scripts#life-cycle-scripts)), so installing with `github:netresearch/german-technical-writing-skill` runs the `prepare` script in `package.json`, which calls `pre-commit install --install-hooks` when `pre-commit` is on the `PATH` and otherwise does nothing. The Composer route runs `netresearch/composer-agent-skill-plugin` in the consumer's project once the consumer allows that plugin.
- Which checks are required before a merge is set in the repository's branch protection, not in this tree.
