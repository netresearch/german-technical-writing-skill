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
- **Register enforcement**: Präsens-Indikativ default, impersonal voice, no first-person in artifacts, sentence-length and compound-noun rules, ß/ä/ö/ü orthography
- **Artifact-specific conventions**: Jira ticket descriptions, Jira comments, internal German wiki/spec pages
- **Worked examples**: 6 paired bad-vs-good cases with annotations

## Installation

### Marketplace (Recommended)

Add the [Netresearch marketplace](https://github.com/netresearch/claude-code-marketplace) once, then browse and install skills:

```bash
# Claude Code
/plugin marketplace add netresearch/claude-code-marketplace
/plugin install german-technical-writing
```

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
│   ├── anti-patterns.md  # ~60 false-friends catalogue with explanations
│   ├── lexicon.md        # Technical term lexicon with gender
│   ├── register.md       # Tense/voice/person, artifact conventions
│   └── examples.md       # 6 paired real-world cases with annotations
└── evals/
    └── evals.json        # 15 trigger-eval queries with assertions
```

## Contributing

Issues and pull requests welcome at <https://github.com/netresearch/german-technical-writing-skill/issues>.

When proposing new anti-pattern entries or lexicon additions, please include:

1. The English concept
2. The literal-translation form to avoid
3. The preferred technical German form
4. A brief explanation of **why** the literal form reads as anglicism

See `skills/german-technical-writing/references/examples.md` for the style of explanation we expect.

## License

- **Code** (`composer.json`, `plugin.json`, configs): [MIT](LICENSE-MIT)
- **Prose** (`SKILL.md`, references, README): [CC-BY-SA-4.0](LICENSE-CC-BY-SA-4.0)
