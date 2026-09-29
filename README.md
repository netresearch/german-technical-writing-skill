# German Technical Writing Skill

Natural German technical register for Jira comments and descriptions, internal German-language wiki/spec pages, and team-chat messages to German-speaking colleagues.

Catches literal English→German anglicisms (`brechen`, `gefangen`, `returnen`, `triggern`, `failen`) and substitutes the canonical technical lexicon (`werfen`, `abfangen`, `zurückgeben`, `auslösen`, `fehlschlagen`) while accepting ecosystem-standard Denglisch loanwords (`der Commit`, `die Pipeline`, `die Exception`).

## 🔌 Compatibility

This is an **Agent Skill** following the [open standard](https://agentskills.io) originally developed by Anthropic and released for cross-platform use.

**Supported Platforms:**
- ✅ Claude Code (Anthropic)
- ✅ Cursor
- ✅ GitHub Copilot
- ✅ Other skills-compatible AI agents

> Skills are portable packages of procedural knowledge that work across any AI agent supporting the Agent Skills specification.

## Features

- **Anti-pattern detection**: ~60 false-friends catalogued — `brechen`, `gefangen`, `returnen`, `failen`, `triggern`, `hitten`, plus calqued idioms (*am Ende des Tages*, *Low-hanging Fruit*) and pseudo-anglicisms (`Handy`, `Beamer`)
- **Technical lexicon**: preferred German forms with gender for Exceptions, Tests, Git, CI/CD, HTTP, Frontend, Data, and Architecture domains
- **Register enforcement**: Präsens-Indikativ default, impersonal voice, no first-person in artifacts, sentence-length and compound-noun rules
- **Artifact-specific conventions**: Jira ticket descriptions, Jira comments, internal German wiki/spec pages
- **Comprehension over brevity**: unambiguous references instead of *siehe oben*, conditions and exceptions kept while shortening, sentence structure checked rather than words counted
- **Worked examples**: 8 paired bad-vs-good cases with annotations

## Installation

### Marketplace (Recommended)

Add the [Netresearch marketplace](https://github.com/netresearch/claude-code-marketplace) once, then browse and install skills:

```bash
# Claude Code
/plugin marketplace add netresearch/claude-code-marketplace
/plugin install german-technical-writing@netresearch-claude-code-marketplace
```

### Without a marketplace

Since Claude Code 2.1.157 a plugin directory under your personal skills directory loads on its own:

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/netresearch/german-technical-writing-skill.git \
  ~/.claude/skills/german-technical-writing
```

It loads as `german-technical-writing@skills-dir` on the next session. Update with `git -C ~/.claude/skills/german-technical-writing pull` and start a new session; remove it by deleting the directory. This route has no `claude plugin update`.

### npx ([skills.sh](https://skills.sh))

Install with any [Agent Skills](https://agentskills.io)-compatible agent:

```bash
npx skills add https://github.com/netresearch/german-technical-writing-skill --skill german-technical-writing
```

### Download Release

Download the [latest release](https://github.com/netresearch/german-technical-writing-skill/releases/latest) and extract to your agent's skills directory.

### Git Clone

```bash
git clone https://github.com/netresearch/german-technical-writing-skill.git
```

### Composer (PHP Projects)

```bash
composer require netresearch/german-technical-writing-skill
```

Requires [netresearch/composer-agent-skill-plugin](https://github.com/netresearch/composer-agent-skill-plugin).

### npm (Node Projects)

```bash
npm install --save-dev \
  @netresearch/agent-skill-coordinator \
  github:netresearch/german-technical-writing-skill
```

Requires [@netresearch/agent-skill-coordinator](https://github.com/netresearch/node-agent-skill-coordinator), which discovers the skill in `node_modules` and registers it in `AGENTS.md` via a `postinstall` hook. For pnpm, also allowlist the coordinator's postinstall:

```json
{
  "pnpm": {
    "onlyBuiltDependencies": ["@netresearch/agent-skill-coordinator"]
  }
}
```


## Usage

The skill triggers automatically when composing German prose longer than one sentence for a German-audience artifact — Jira tickets and comments, internal German wiki/spec pages, or team-chat messages to German-speaking colleagues.

Example queries:

- *"schreib bitte einen Jira-Kommentar auf OROSPD-692: der cart-merge-on-login Test failt weil ..."*
- *"HMKG-2202 ticket beschreibung muss neu geschrieben werden — problem/ziel format auf deutsch"*
- *"kurze Slack-Ankündigung ans HMKG team auf deutsch: Pipeline CI-383 ist grün"*
- *"drei-satz blurb auf deutsch fürs internal-wiki über das MeyerBaselineBundle"*

The skill does **not** trigger for commit messages, MR/PR descriptions, release notes (all English at Netresearch and most agencies delivering customer projects), conversational chat replies, single-word acknowledgements, or English artifacts that happen to contain German identifiers.

## Structure

```
skills/german-technical-writing/
├── SKILL.md              # Trigger description, process, top-anti-pattern table
├── references/
│   ├── anti-patterns.md            # ~60 false-friends catalogue with explanations
│   ├── lexicon.md                  # Technical term lexicon with gender
│   ├── register.md                 # Tense/voice/person, artifact conventions
│   ├── typografie-rhythmus.md      # Typography and the AI-rhythm tells
│   ├── cognitive-accessibility.md  # Comprehension priority over brevity
│   ├── no-editorializing.md        # Inform, don't sell
│   └── examples.md                 # 8 paired cases with annotations (Case 8 synthetic)
└── evals/
    └── evals.json                  # 27 evals; newer entries carry self-check samples
```

## Contributing

Issues and pull requests welcome at <https://github.com/netresearch/german-technical-writing-skill/issues>.

When proposing new anti-pattern entries or lexicon additions, please include:

1. The English concept
2. The literal-translation form to avoid
3. The preferred technical German form
4. A brief explanation of **why** the literal form reads as anglicism

See `skills/german-technical-writing/references/examples.md` for the style of explanation we expect.

### Tests and checks

The repository ships no executable code: the skill is Markdown prose plus `evals/evals.json`, and `SKILL.md` requests only the `Read` tool. What runs on a change are validators, not a behavioural test suite.

| Check | What it verifies | CI workflow |
|-------|------------------|-------------|
| `validate-skill.sh` | SKILL.md front matter and description, layout of the reference files, README sections and install targets | `lint.yml` (Skill Validation) |
| markdownlint, yamllint, actionlint, JSON syntax, version parity | File syntax; the version in `plugin.json`, `.claude-plugin/plugin.json` and SKILL.md `metadata.version` agrees | `lint.yml` (Skill Validation) |
| `validate-evals.sh` | Structure of every eval in `evals/evals.json`; for evals that carry `samples`, each assertion is run against `samples.passing` (must be accepted) and `samples.failing` (at least one must be rejected) | `eval-validate.yml` (Eval Validation) |
| AGENTS.md checks | AGENTS.md exists, stays under 150 lines, and has no dead links | `harness-verify.yml` (Harness Verification) |

All four run on pull requests; Harness Verification runs only for pull requests to `main`. The validators come from [netresearch/skill-repo-skill](https://github.com/netresearch/skill-repo-skill) at `main`.

Run them locally:

```bash
pre-commit install --install-hooks   # once; the hooks mirror the lint checks
pre-commit run --all-files

git clone https://github.com/netresearch/skill-repo-skill.git /tmp/skill-repo-skill
bash /tmp/skill-repo-skill/skills/skill-repo/scripts/validate-skill.sh .
bash /tmp/skill-repo-skill/skills/skill-repo/scripts/validate-evals.sh skills/german-technical-writing/evals/evals.json
```

`validate-evals.sh` prints one `PASS:`, `WARN:` or `FAIL:` line per check (plus `INFO:` context lines) and ends with `Results: N passed, N failed, N warnings`; it exits non-zero when any line is `FAIL:`. A `FAIL:` naming a sample means the assertion regex is inverted or does not match the answer it should accept. `validate-skill.sh` prints `ERROR:`, `WARNING:` and `OK:` lines, ends with an `Errors:` and a `Warnings:` count, and exits non-zero on errors only.

A new eval, or an eval whose assertions change, needs `samples` (a `passing` answer and `failing` answers): in pull requests the validator compares against the copy on `main` and fails an eval that lacks them. See [AGENTS.md](AGENTS.md) for what each kind of contribution must contain.

## Governance and policies

This repository follows the Netresearch organisation policies:

- [Governance](https://github.com/netresearch/.github/blob/main/GOVERNANCE.md): who owns and maintains the project, the roles, how decisions and disputes are settled.
- [Roadmap](https://github.com/netresearch/.github/blob/main/ROADMAP.md): planned and excluded work for the coming year.
- [Handling of dependency and code analysis findings](https://github.com/netresearch/.github/blob/main/SECURITY.md#handling-of-dependency-and-code-analysis-findings): thresholds, deadlines and exceptions for dependency and static-analysis findings.
- [Secret management](https://github.com/netresearch/.github/blob/main/SECURITY.md#secret-management): how CI and release credentials are stored, accessed and rotated.
- [Access roster](https://github.com/netresearch/.github/blob/main/docs/access-roster.md): the people and teams with admin, maintain and write access to this repository.

Checks that run on pull requests here: Skill Validation (`lint.yml`) and Eval Validation (`eval-validate.yml`) on every pull request; for pull requests to `main` also Betterleaks secret scanning, zizmor workflow analysis, dependency review, Composer Audit with an Opengrep static-analysis scan (all `security.yml`), Harness Verification (`harness-verify.yml`) and Template Drift (`check-template-drift.yml`).

## License

- **Code** (`composer.json`, `plugin.json`, configs): [MIT](LICENSE-MIT)
- **Prose** (`SKILL.md`, references, README): [CC-BY-SA-4.0](LICENSE-CC-BY-SA-4.0)
