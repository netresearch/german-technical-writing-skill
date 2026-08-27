---
name: german-technical-writing
description: "Use when writing German-language prose longer than one sentence for Jira tickets, internal German wiki/spec docs, or team-chat to German-speaking colleagues (Slack, Matrix, Teams). Invoke BEFORE composing. Covers anglicism verbs (failt, triggern, returnen), calqued collocations and idioms (blockiert auf, macht Sinn, in 2026), loanword genders (der Commit, die Pipeline), per-artifact register (impersonal for Jira/wiki, ich/du for chat), German typography (Gedankenstrich, Anführungszeichen, Durchkopplung), and AI-typical rhythm (restatement, symmetric paragraphs, summary closers). Skip for commit messages, MR/PR descriptions, release notes (English by team convention), conversational chat replies, or single-line acknowledgments. If you catch yourself thinking 'my German is probably fine here' for anything longer than a sentence — invoke this skill."
license: "(MIT AND CC-BY-SA-4.0). See LICENSE-MIT and LICENSE-CC-BY-SA-4.0"
compatibility: "Language-only skill. No runtime dependencies."
metadata:
  author: Netresearch DTT GmbH
  version: "1.5.0"
  repository: https://github.com/netresearch/german-technical-writing-skill
allowed-tools: Read
---

# German Technical Writing

Natural German technical register for German-audience artifacts — not English-first composition phrase-translated into DeepL-German.

## Process

1. **Compose in German directly**, not by translating. Restart if you catch yourself drafting English first.
2. **Self-review each sentence** against `references/anti-patterns.md` — verbs, collocations, idioms, Amtsdeutsch.
3. **Apply the lexicon** — canonical verbs and loanword gender: `references/lexicon.md`.
4. **Match register per artifact** — impersonal for Jira/wiki, ich/du for chat: `references/register.md`.
5. **Typography & rhythm** — Gedankenstrich, Durchkopplung; every fact once, varied sentence shapes: `references/typografie-rhythmus.md`.
6. **No editorializing** — say what changed, not how good the work is: `references/no-editorializing.md`.
7. **If unsure, ask — don't guess.**

## Top anti-patterns

| ❌ | ✅ |
|---|---|
| code bricht | schlägt fehl / wirft Exception |
| gefangen | erkannt / abgefangen |
| null returnen | null zurückgeben |
| Test failt | schlägt fehl |
| Fehler triggern | Fehler auslösen |
| auf Fehler hitten | auf Fehler stoßen |
| blockiert auf X | wartet auf X / hängt an X |

Full catalogue in `references/anti-patterns.md`; worked examples in `references/examples.md`.

## Three traps — apply all three disciplines

Over-applying one drives you into another:

1. **Anglicism** (verb-level): English where German is canonical. *Test failt* → *schlägt fehl*. Targeted by the table above and `anti-patterns.md`.
2. **Calque** (nouns, collocations, idioms): word-by-word translation where the loanword or another German structure is canonical. *Wurzelursache* → *Root Cause*; *blockiert auf X* → *wartet auf X*; *macht Sinn* → *ist sinnvoll*. See `anti-patterns.md` and `lexicon.md`.
3. **Amtsdeutsch over-polish**: fleeing both traps into stiff officialese and AI-symmetric structure — *Datenbestand*, *Es handelt sich um*, passive chains, facts restated per section. See `anti-patterns.md` and `typografie-rhythmus.md`. Idiomatic dev speech (*ins Gehege kommen*, *läuft voll*, *fliegt auf*) is wanted, not a violation.

Noun rule: if a native German developer would *say* the term verbatim in a review or stand-up, keep it English — a German form that sounds like a textbook title is a calque.

## Scope note

Commit messages, MR/PR descriptions, release notes and internal IT-project tickets (NRS, NRT, SRV\*, IO\*, LIC) are English — skip them. This skill governs *how* to write German, not *whether*.
