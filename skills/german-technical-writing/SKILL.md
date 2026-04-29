---
name: german-technical-writing
description: "Use when writing German-language prose longer than one sentence for Jira tickets, internal German wiki/spec docs, or team-chat to German-speaking colleagues (Slack, Matrix, Teams). Invoke BEFORE composing, not after. Enforces natural German technical register by catching English→German anglicisms (brechen, gefangen, returnen, triggern, failen, die Test, hit, end up) and substituting canonical verbs (werfen, abfangen, zurückgeben, auslösen, fehlschlagen, der Test, auf … stoßen, landen). Also enforces present-indicative tense, impersonal voice, and Denglisch-loanword lexicon (der Commit, die Pipeline, der Branch, die Exception). Skip for commit messages, MR/PR descriptions, release notes (English by team convention), conversational chat replies, internal reasoning, single-line acknowledgments ('Ok', 'Danke'), or English artifacts containing German identifiers. If you catch yourself thinking 'my German is probably fine here' for anything longer than a sentence — invoke this skill."
license: "(MIT AND CC-BY-SA-4.0). See LICENSE-MIT and LICENSE-CC-BY-SA-4.0"
compatibility: "Language-only skill. No runtime dependencies."
metadata:
  author: Netresearch DTT GmbH
  version: "1.0.0"
  repository: https://github.com/netresearch/german-technical-writing-skill
allowed-tools: Read
---

# German Technical Writing

Natural German technical register for German-audience artifacts. Prevents English-first composition plus phrase-by-phrase translation, which produces grammatically correct German that reads as DeepL-output to native readers.

## Process

1. **Compose in German directly**, not by translating. Restart if you catch yourself drafting English first.
2. **Self-review each sentence** against `references/anti-patterns.md`.
3. **Apply the lexicon** — canonical verbs and loanword gender: `references/lexicon.md`.
4. **Match register** — Präsens-Indikativ, impersonal voice, no first-person: `references/register.md`.
5. **If unsure, ask — don't guess.**

## Top anti-patterns

| ❌ | ✅ |
|---|---|
| code bricht | schlägt fehl / wirft Exception |
| gefangen | erkannt / abgefangen |
| null returnen | null zurückgeben |
| Test failt | schlägt fehl / fällt durch |
| Fehler triggern | Fehler auslösen |
| auf Fehler hitten | auf Fehler stoßen |

Full ~60-entry catalogue plus pseudo-anglicisms and idiom calques in `references/anti-patterns.md`. Worked pair-examples in `references/examples.md`.

## Scope note

Commit messages, MR/PR descriptions, and release notes are English at Netresearch and most agencies delivering customer projects — this skill does not apply to them.
