# German Technical Writing Skill

Natural German technical register for Jira comments, GitLab/GitHub MR/PR descriptions, commit messages, release notes, and team-facing documentation.

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

- **Anti-pattern detection**: ~60 literal-translation false friends catalogued — `brechen` (break), `gefangen` (caught), `returnen` (return), `failen` (fail), `triggern` (trigger), `hitten` (hit), plus calqued idioms ("in die Falle zurück", "am Ende des Tages", "auf derselben Seite")
- **Technical lexicon**: preferred German forms for Exceptions, Tests, Builds, Git, CI/CD, HTTP, Frontend, Data, Architecture — with gender, compound-noun rules, and `der/die/das` for ambiguous loanwords
- **Register enforcement**: Präsens-Indikativ default, impersonal voice, no first-person in artifacts, sentence-length limits, compound-noun stacking rules, ß/ä/ö/ü orthography
- **Artifact-specific conventions**: dedicated guidance for Jira descriptions, Jira comments, MR descriptions, commit messages, release notes
- **Worked examples**: 8 paired bad-vs-good cases from real Jira history with annotations

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

This skill is automatically triggered when composing German-language prose longer than one sentence for a persistent or team-facing artifact:

- Writing a Jira comment, description, or ticket summary in German
- Writing a GitLab MR / GitHub PR description or title in German
- Writing a commit message in German
- Writing release notes, changelog entries, or RFC/spec documents in German
- Writing Matrix / Slack / Teams messages to colleagues in German
- Producing any other German artifact that colleagues or reviewers will read

The skill is **not** triggered for:

- Conversational German chat replies to the user
- Internal reasoning or thinking
- Single-line acknowledgements (`"Ok"`, `"Danke"`, `"Fertig"`)
- English artifacts that happen to contain German names or identifiers

### Example queries

- "schreib bitte einen Jira-Kommentar auf OROSPD-692: der cart-merge-on-login Test failt weil ..."
- "can you write a German MR description for git.netresearch.de explaining we're removing the legacy SOAP adapter"
- "commit message auf deutsch bitte: wir haben den DataProviderDecorator regex bug gefixed"
- "release notes eintrag auf deutsch schreiben für den neuen cart-merge-on-login fix"

### What the skill does

1. Compose directly in German — don't translate from an English mental draft
2. Self-review each sentence against the anti-pattern list
3. Apply the technical lexicon (canonical verbs, preferred gender for loanwords)
4. Match the register to the artifact type (tense, voice, person)
5. If two phrasings seem plausible and the author can't decide, ask — don't guess

## What's inside

```
skills/german-technical-writing/
├── SKILL.md              # Trigger description, process, quick-reference
├── references/
│   ├── anti-patterns.md  # ~60 false-friends catalogue with explanations
│   ├── lexicon.md        # Technical term lexicon with gender
│   └── register.md       # Tense/voice/person, artifact conventions
└── examples/
    └── bad-vs-good.md    # 8 paired real-world cases with annotations
```

## External references

The skill builds on these authoritative sources:

- [Microsoft German Localization Style Guide](https://download.microsoft.com/download/e/f/9/ef9f6d8e-cd8b-420c-8696-afd98b4a367d/deu-deu-StyleGuide.pdf) — canonical source for tone, formality, and technical German conventions
- [Microsoft Learn Schnellstart-Leitfaden (de-de)](https://learn.microsoft.com/de-de/contribute/content/style-quick-start) — Microsoft's own German technical-writing quick reference
- [Weka: Technische Dokumentation Styleguides](https://www.weka.de/produktsicherheit/nutzen-oeffentlich-zugaenglicher-styleguides/) — overview of German technical-documentation style guides
- [dictaJet: Grundlagen der Technischen Dokumentation — Styleguide](https://www.dictajet.de/styleguide/) — practical style-guide elements for German technical writing
- [IT-Business: Anglizismen in der IT](https://www.it-business.de/anglizismen-in-der-it-a-167154/) — catalogue of anglicisms in German IT with native alternatives
- Duden online — final arbiter for orthography and case/gender when no project convention exists

## License

- **Code** (`composer.json`, `plugin.json`, scripts): [MIT](LICENSE-MIT)
- **Prose** (`SKILL.md`, references, examples, README): [CC-BY-SA-4.0](LICENSE-CC-BY-SA-4.0)

## Contributing

Issues and pull requests welcome at <https://github.com/netresearch/german-technical-writing-skill/issues>.

When proposing new anti-pattern entries or lexicon additions, please include:

1. The English concept
2. The literal-translation form to avoid
3. The preferred technical German form
4. A brief explanation of **why** the literal form reads as anglicism

See `skills/german-technical-writing/examples/bad-vs-good.md` for the style of explanation we expect.
