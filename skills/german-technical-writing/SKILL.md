---
name: german-technical-writing
description: "Use when writing German-language prose longer than one sentence for Jira tickets, internal German wiki/spec docs, or team-chat to German-speaking colleagues (Slack, Matrix, Teams). Invoke BEFORE composing, not after. Covers anglicism verbs (failt, triggern, returnen), calqued collocations and idioms (blockiert auf, macht Sinn, in 2026), Denglisch-loanword lexicon with genders (der Commit, die Pipeline), register per artifact type (impersonal for Jira/wiki, ich/du for chat), German typography (Gedankenstrich –, „Anführungszeichen“, Durchkopplung), and AI-typical rhythm (restatement padding, symmetric paragraphs, summary closers). Skip for commit messages, MR/PR descriptions, release notes (English by team convention), conversational chat replies, internal reasoning, single-line acknowledgments ('Ok', 'Danke'), or English artifacts containing German identifiers. If you catch yourself thinking 'my German is probably fine here' for anything longer than a sentence — invoke this skill."
license: "(MIT AND CC-BY-SA-4.0). See LICENSE-MIT and LICENSE-CC-BY-SA-4.0"
compatibility: "Language-only skill. No runtime dependencies."
metadata:
  author: Netresearch DTT GmbH
  version: "1.3.0"
  repository: https://github.com/netresearch/german-technical-writing-skill
allowed-tools: Read
---

# German Technical Writing

Natural German technical register for German-audience artifacts. Prevents English-first composition plus phrase-by-phrase translation that reads as DeepL-output to natives.

## Process

1. **Compose in German directly**, not by translating. Restart if you catch yourself drafting English first.
2. **Self-review each sentence** against `references/anti-patterns.md` — verbs, collocations, idioms, Amtsdeutsch.
3. **Apply the lexicon** — canonical verbs and loanword gender: `references/lexicon.md`.
4. **Match register per artifact** — impersonal Präsens-Indikativ for Jira/wiki, ich/du for chat: `references/register.md`.
5. **German typography, human rhythm** — Gedankenstrich –, „Anführungszeichen“, Durchkopplung; every fact once, varied sentence shapes, no summary closer: `references/typografie-rhythmus.md`.
6. **No editorializing** — say what changed, not how good/careful the work is; no self-praise or narrating the expected: `references/no-editorializing.md`.
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

Full ~60-entry catalogue plus pseudo-anglicisms and idiom calques in `references/anti-patterns.md`. Worked pair-examples in `references/examples.md`.

## Three traps — apply all three disciplines

Over-applying one drives you into another:

1. **Anglicism** (verb-level): keeping English when German is canonical. *Test failt* → *schlägt fehl*. *Fehler triggern* → *Fehler auslösen*. The table above and `anti-patterns.md` target this.
2. **Calque / overcorrection** (nouns, collocations, idioms): translating English when the loanword or a different German structure is canonical. *Wurzelursache* → *Root Cause*. *blockiert auf X* → *wartet auf X*. *macht Sinn* → *ist sinnvoll*. See `anti-patterns.md` and `lexicon.md` ("Debugging / Postmortem / Analysis").
3. **Amtsdeutsch over-polish**: fleeing both traps into stiff officialese and AI-symmetric structure — *Datenbestand* for DB, *Es handelt sich um*, passive chains, every paragraph built alike, facts restated per section. See `anti-patterns.md` ("Amtsdeutsch over-polish") and `references/typografie-rhythmus.md`. Idiomatic dev speech (*ins Gehege kommen*, *läuft voll*, *fliegt auf*) is wanted, not a violation.

Decision rule for nouns: if a native German developer would *say* the term verbatim in a review or stand-up, keep it English. The test isn't "does a German equivalent exist?" but "do German engineers actually say it?" A German form that sounds like a textbook title is a calque.

"German verbs" without "keep loanword nouns" produces DeepL-grade output; both without the third discipline produce correct-but-machine-stiff output. Apply all three.

## Scope note

Commit messages, MR/PR descriptions, release notes and internal IT-project tickets (NRS, NRT, SRV\*, IO\*, LIC) are English — skip them. This skill governs *how* to write German, never *whether* German is the right choice.
