---
name: german-technical-writing
description: "Use when writing ANY German-language prose longer than one sentence for Jira comments and descriptions, internal German-language wiki or spec documents, release notes aimed at a German-speaking audience, or team-chat messages (Slack, Matrix, Teams) to German-speaking colleagues. Invoke BEFORE composing German text, not after. Enforces natural German technical register by catching literal English→German translation anglicisms (brechen, gefangen, returnen, triggern, failen, die Test, hit, end up) and substituting canonical technical verbs (werfen, abfangen, zurückgeben, auslösen, fehlschlagen, der Test, auf … stoßen, landen). Also enforces present-indicative tense, impersonal voice, and a consistent Denglisch-loanword lexicon (der Commit, die Pipeline, der Branch, die Exception — accepted; 'der Rename in die Falle zurück gefangen werden' — not accepted). Do NOT invoke for commit messages or MR/PR descriptions (at Netresearch and most agencies delivering customer projects, those are English by team convention regardless of native language), conversational German chat replies to the user, internal reasoning or thinking, single-line acknowledgments ('Ok', 'Danke', 'Fertig'), or English artifacts that happen to contain German identifiers. If you catch yourself thinking 'my German is probably fine here' while writing anything longer than a sentence for a Jira ticket or German-audience artifact — that's the moment to invoke this skill, because that thought is exactly when anglicisms slip through."
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

Commit messages and MR/PR descriptions are English at Netresearch and most agencies delivering customer projects — this skill does not apply to them.
