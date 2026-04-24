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

## Why this skill exists

Claude's default German composition pattern in a mostly-English session is English-first: draft mentally in English, translate phrase-by-phrase. Grammar stays correct, but technical **register** breaks. Verbs like *brechen* (break), *gefangen* (caught), *returnen* (return), *failen* (fail) are false friends that read fluently as English idioms rendered in German syntax — but native German technical writers never use them. The reader experiences the text as DeepL-without-post-editing: mechanically correct, unmistakably foreign.

This is a **register problem, not a grammar problem**. Correcting it requires:

1. Composing in German directly instead of translating
2. Using the established German technical verb lexicon (*werfen*, *abfangen*, *zurückgeben*, *auslösen*, *fehlschlagen*)
3. Accepting ecosystem-standard Denglisch loanwords where they already exist (*der Commit*, *die Pipeline*, *die Exception*) while rejecting ad-hoc anglicisms (*brechen*, *gefangen*, *failen*)

The cost of a bad Jira comment is high — colleagues read it, it persists in issue history, and the author-reviewer relationship suffers when the text reads as sloppy. The cost of loading this skill's reference tables before composing is trivial.

**Note on scope:** this skill targets German-audience artifacts. At Netresearch and most agencies that deliver projects to customers, commit messages and MR/PR descriptions are written in English by team convention regardless of the native language of authors and reviewers — do not invoke this skill for those.

## Process

Follow these steps in order. Do not skip. The last step is the most important.

### 1. Compose directly in German

When you catch yourself mentally forming an English sentence and then translating, **stop**. Close the English thought. Restart by asking: "Wie würde ein deutscher Senior-Developer diesen Sachverhalt in einem Jira-Kommentar formulieren?"

The difference is between:

- *(English-first)* "Code breaks with an exception" → *(literal)* "Code bricht mit einer Exception"
- *(German-first)* "Was passiert? Eine Exception wird geworfen." → "Der Code wirft zur Laufzeit eine Exception"

### 2. Self-review each sentence against the anti-pattern list

Before posting, read every sentence and ask: "Klingt das wie übersetztes Englisch?" The tells:

- Verb is a literal-cognate translation (*brechen* for break, *gefangen* for caught, *returnen* for return, *failen* for fail, *triggern* for trigger, *hitten* for hit)
- Preposition-follows-verb pattern copies English ("fall back into" → "zurück in … fallen")
- Sentence structure mirrors English subject-verb-object exactly instead of using German's flexibility (verb-second, verb-final in subordinate clauses)
- Idiom is a calqued English idiom ("in die Falle zurück gefangen werden" is calqued from "caught in the trap")

For the top-20 anti-patterns inline, see the Quick Reference below. For the full catalogue, load `references/anti-patterns.md`.

### 3. Apply the technical lexicon

For domain-standard terms, use the established German phrasing rather than inventing one. See `references/lexicon.md` for the full table. Top entries:

- **Exception** → werfen / abfangen (never *schmeißen*, *catchen*, *fangen*)
- **Test** → bestehen / fehlschlagen (never *passen*, *failen*)
- **Build** → bricht ab / schlägt fehl (never *brechen* alone, never *failt*)
- **null** → zurückgeben (never *returnen*)
- **Fehler** → auslösen / werfen / stoßen auf (never *triggern*, *hitten*)
- **State** → in Zustand X landen / Zustand X erreichen (never *enden in*)

### 4. Match register to artifact type

German-language Jira tickets, internal wiki pages, and release notes expect a specific register:

- **Tense**: Präsens-Indikativ für Fakten. *"Der Provider wirft eine Exception"* — nicht *"würde werfen"* außer im echten Konjunktivfall (Hypothese, nicht-Real-Szenario).
- **Voice**: Aktiv bevorzugt bei handelnden Subjekten (*"Der Test erkennt die Regression"*); Passiv für Systemverhalten (*"Die Exception wird geworfen"*).
- **Person**: Keine erste Person in Artefakten. Kein "ich", kein "wir" in Jira-Beschreibungen oder Wiki-Seiten. Stattdessen impersonal/passiv.
- **Länge**: Kurze Sätze, technische Präzision vor literarischer Eleganz.

Details in `references/register.md`.

### 5. If unsure, ask — don't guess

When two phrasings seem plausible and you can't decide which is natural, **ask the user**:

> "Bevor ich den Kommentar poste — Formulierung A ("Die Exception wird zur Laufzeit geworfen") oder B ("Der Code wirft zur Laufzeit eine Exception")?"

This is not failure — it's the fallback that protects the artifact. Native speakers have sub-second intuitions about register; forced guessing produces the exact anglicism patterns this skill exists to prevent.

## Quick Reference — Top 20 Anti-Patterns

| English idea | ❌ Wrong (literal) | ✅ Right (technical) |
|---|---|---|
| code breaks | bricht | schlägt fehl / wirft eine Exception / bricht ab |
| caught by tests | gefangen | erkannt / aufgedeckt / abgefangen |
| throw exception | Exception schmeißen / fangen | Exception werfen / abfangen |
| return null | null returnen | null zurückgeben |
| test passes | Test passt | Test besteht / geht durch |
| test fails | Test failt | Test schlägt fehl / fällt durch |
| build fails | Build failt | Build schlägt fehl / bricht ab |
| hit an error | auf Fehler hitten | auf einen Fehler stoßen / einen Fehler treffen |
| fall back to | zurück in … fallen | auf … zurückfallen / auf … ausweichen |
| trigger error | Fehler triggern | Fehler auslösen |
| end up in state | in Zustand … enden | in Zustand … landen / … erreichen |
| refresh cache | Cache frisch machen | Cache neu aufbauen / invalidieren |
| fix the bug | den Bug fixen | den Bug beheben / beseitigen (fixen akzeptabel in Team-Kontext) |
| handle error | Fehler handeln | Fehler behandeln |
| call method | Methode callen | Methode aufrufen |
| parse input | Input parsen | Eingabe parsen (parsen akzeptabel) |
| run tests | Tests runnen | Tests ausführen / laufen lassen |
| check condition | Bedingung checken | Bedingung prüfen (checken akzeptabel mündlich, schriftlich lieber prüfen) |
| merge branch | Branch mergen | Branch mergen (akzeptiert) / zusammenführen |
| rename variable | Variable renamen | Variable umbenennen |

## Accepted Denglisch loanwords

These are ecosystem-standard in Germany's dev community and should **not** be translated to avoid sounding stilted or 1990s-style:

*der Commit, der Branch, der Merge, der Rebase, der Pull Request / MR, das Deploy / Deployment, die Pipeline, der Build, die Exception, der Test, die Fixture, der Hook, der Mock, der Stub, die Assertion, der Request, die Response, das Refactoring, die Regression, der Bug, das Feature, der Fix, der Patch, der Rollout, der Rollback, das Staging, das Logging, das Monitoring, die CI, das Framework, das Interface, der Service, der Controller, der Provider, der Decorator, der Wrapper, das Caching, das Routing, das Rendering, der Token, die Session, das Payload.*

Use articles consistently (*die Pipeline*, not *das Pipeline*). See `references/lexicon.md` for the full list with gender.

## Anti-patterns that aren't about words

Not every register problem is a single word. Watch for these patterns:

- **Overlong subordinate clauses with verb-stranding**: German allows long clauses, but Jira comments need them short. Split.
- **Noun-stacking beyond 3 elements**: *"Produkt-Konfigurations-Attribut-Validierungs-Service"* — split with *des/für/bei*.
- **Konjunktiv II without a hypothetical**: *"würde werfen"* only if you're describing a counterfactual. For "this throws", use *"wirft"*.
- **Calqued English idioms**: *"am Ende des Tages"* (at the end of the day), *"auf derselben Seite"* (on the same page), *"Low-hanging Fruit"* in a German sentence. Cut them.

## When to load references

Load these files into context as needed:

- `references/anti-patterns.md` — full false-friends catalogue (~60 entries with explanations)
- `references/lexicon.md` — technical term lexicon with gender, domain, and usage notes
- `references/register.md` — deep dive on tense/voice/person, artifact-specific conventions (Jira ticket, Jira comment, release notes, wiki)

## Examples

See `examples/bad-vs-good.md` for real paired cases from past Jira comments with annotations on what went wrong and how to fix it.

## External references

Authoritative sources this skill builds on:

- [Microsoft German Localization Style Guide (deu-deu-StyleGuide.pdf)](https://download.microsoft.com/download/e/f/9/ef9f6d8e-cd8b-420c-8696-afd98b4a367d/deu-deu-StyleGuide.pdf) — canonical source for tone, formality, and technical German conventions in IT products
- [Microsoft Learn Schnellstart-Leitfaden (de-de)](https://learn.microsoft.com/de-de/contribute/content/style-quick-start) — Microsoft's own German technical-writing quick reference
- [Weka: Technische Dokumentation Styleguides](https://www.weka.de/produktsicherheit/nutzen-oeffentlich-zugaenglicher-styleguides/) — overview of German technical-documentation style guides (tekom, Siemens, etc.)
- [dictaJet: Grundlagen der Technischen Dokumentation — Styleguide](https://www.dictajet.de/styleguide/) — practical style-guide elements for German technical writing
- [IT-Business: Anglizismen in der IT](https://www.it-business.de/anglizismen-in-der-it-a-167154/) — catalogue of anglicisms in German IT with native alternatives
- Duden online — final arbiter for orthography and case/gender when no project convention exists

## Failure anchor

**Real incident, 2026-04-24.** A Jira comment on OROSPD-692 contained this sentence:

> "Ein bare get würde mit BadMethodCallException zur Laufzeit brechen. Ein Regressionstest führt den Provider durch den Decorator, damit ein Rename in die Falle zurück von Unit-Tests gefangen wird."

Three failures in one sentence: *brechen* (literal break), *in die Falle zurück* (garbled calque), *gefangen* (literal caught). The rewrite:

> "Ein unqualifiziertes `get` wirft zur Laufzeit eine `BadMethodCallException`. Ein Regressionstest schickt den Provider durch den Decorator, damit ein späterer Rename direkt in den Unit-Tests auffliegt — ohne Decorator würde ein Umbenennen erst im Behat-Lauf sichtbar."

That is the class of fix this skill exists to produce **before the post button is clicked**.
