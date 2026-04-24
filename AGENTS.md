# German Technical Writing Skill

Natural German technical register for Jira comments and descriptions, internal German-language documentation, release notes, and team-chat messages to German-speaking colleagues.

## Repo Structure

```
├── .claude-plugin/
│   └── plugin.json                       # Plugin manifest (points at ./skills/german-technical-writing)
├── skills/german-technical-writing/
│   ├── SKILL.md                          # Trigger description, process, quick-reference
│   ├── references/
│   │   ├── anti-patterns.md              # ~60 false-friends catalogue
│   │   ├── lexicon.md                    # Technical term lexicon with gender
│   │   └── register.md                   # Tense/voice/person, artifact conventions
│   └── examples/
│       └── bad-vs-good.md                # Paired real-world cases with annotations
├── composer.json                         # Composer package manifest (type: ai-agent-skill)
├── LICENSE-MIT                           # MIT license for code and config
├── LICENSE-CC-BY-SA-4.0                  # CC-BY-SA-4.0 license for prose (SKILL.md, references, examples)
└── README.md                             # Installation, usage, features
```

## What this skill does

Detects and prevents literal English→German translation anglicisms in persistent team artifacts. Targets the **register** problem, not grammar — text produced by English-first composition is grammatically correct but uses false friends (`brechen`/`gefangen`/`returnen`) that a native technical writer would never choose.

The skill enforces:

1. German-first composition (not phrase-by-phrase translation from English)
2. The canonical German technical verb lexicon (`werfen`, `abfangen`, `zurückgeben`, `auslösen`, `fehlschlagen`)
3. Present-indicative tense, impersonal voice, no first-person in artifacts
4. Accepted ecosystem Denglisch (`der Commit`, `die Pipeline`, `die Exception`) while rejecting ad-hoc anglicisms (`brechen`, `gefangen`, `failen`)

## When the skill triggers

Skill fires for German prose longer than one sentence aimed at a German-speaking audience: Jira comments and descriptions, internal German-language wiki/spec pages, RFC documents, release notes for German audiences, and team-chat messages (Slack, Matrix, Teams) to German-speaking colleagues.

Skill does **not** fire for: commit messages or MR/PR descriptions (English by team convention at Netresearch and most agencies delivering customer projects), conversational German chat replies, internal reasoning, single-word acknowledgements, English artifacts that merely contain German identifiers.

## Extending the skill

### Adding an anti-pattern

Open `skills/german-technical-writing/references/anti-patterns.md` and add to the relevant section (Verbs — Exceptions, Tests, Data Flow, Git, Nouns, Sentence Structure, Pseudo-anglicisms). Every entry needs:

- English concept
- ❌ Literal-translation form
- ✅ Preferred technical form
- **Why** the literal form reads as anglicism (often a register mismatch or false friend)

### Adding a lexicon entry

Open `skills/german-technical-writing/references/lexicon.md` and add to the relevant domain section (Exceptions & Error Handling, Tests, Version Control, CI/CD, HTTP, Frontend, Data, Architecture). Every entry needs:

- English term
- Preferred German form (with article where noun)
- Register tag (*accepted loanword*, *native German*, or *both*)
- Notes on gender, pluralization, or usage gotchas

### Adding a paired example

Open `skills/german-technical-writing/examples/bad-vs-good.md` and add a new `## Case N` block with: bad text, explicit list of problems, rewritten good text, explanation of why the rewrite works. Drawn from real Jira/MR history preferred over synthetic examples.

## Compatibility

Agent Skill format — works with Claude Code, Cursor, GitHub Copilot, and any [skills.sh](https://skills.sh)-compatible agent.

## License

- Code: [MIT](LICENSE-MIT)
- Prose: [CC-BY-SA-4.0](LICENSE-CC-BY-SA-4.0)
