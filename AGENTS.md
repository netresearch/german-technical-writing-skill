# German Technical Writing Skill

Natural German technical register for Jira comments, internal German docs, release notes, and team-chat to German-speaking colleagues. Catches literal English→German anglicisms and enforces the canonical technical lexicon.

## Repo Structure

```
├── .claude-plugin/plugin.json              # Plugin manifest
├── skills/german-technical-writing/
│   ├── SKILL.md                            # Trigger description, process, top-anti-patterns
│   ├── references/
│   │   ├── anti-patterns.md                # ~60 false-friends catalogue
│   │   ├── lexicon.md                      # Technical term lexicon with gender
│   │   ├── register.md                     # Tense/voice/person, artifact conventions
│   │   └── examples.md                     # 7 paired bad-vs-good cases
│   └── evals/evals.json                    # 15 trigger-eval queries with assertions
├── .github/workflows/                      # CI: lint, security, release, eval-validate, harness-verify, auto-merge-deps
├── composer.json                           # type: ai-agent-skill
├── LICENSE-MIT, LICENSE-CC-BY-SA-4.0       # Dual license: code (MIT), prose (CC-BY-SA-4.0)
└── README.md                               # Installation + features
```

## Scope

Skill triggers for German prose ≥ 1 sentence in German-audience artifacts: Jira tickets and comments, internal German wiki/spec/RFC pages, release notes for German audiences, team-chat (Slack/Matrix/Teams) to German-speaking colleagues.

**Out of scope:** commit messages and MR/PR descriptions are written in English at Netresearch and most agencies delivering customer projects, regardless of the team's native language.

## Extending

- **Anti-pattern entry** → `skills/german-technical-writing/references/anti-patterns.md`. Required: English concept, ❌ literal form, ✅ preferred form, **why** the literal reads as anglicism.
- **Lexicon entry** → `skills/german-technical-writing/references/lexicon.md`. Required: English term, preferred German form (with article), register tag, gotchas.
- **Worked example** → `skills/german-technical-writing/references/examples.md`. New `## Case N` block with bad text, problems list, rewritten good text, and explanation. Drawn from real Jira history preferred over synthetic.
- **Eval query** → `skills/german-technical-writing/evals/evals.json`. Each entry needs ≥ 2 expectations and ≥ 2 assertions per the validator.

## Compatibility

Agent Skill format — works with Claude Code, Cursor, GitHub Copilot, and any [skills.sh](https://skills.sh)-compatible agent.

## License

Code [MIT](LICENSE-MIT) · Prose [CC-BY-SA-4.0](LICENSE-CC-BY-SA-4.0)
