# Register — Tense, Voice, Person, and Artifact-Specific Conventions

Register is the biggest single driver of whether German technical prose reads as native or translated. Use this reference when composing longer artifacts (Jira description, MR description, release notes, RFC).

## Tense

**Default: Präsens-Indikativ.** Use it for describing what code does, what a system behaves like, what a ticket is about.

- ✅ "Der Service wirft bei fehlendem Feld eine Exception."
- ❌ "Der Service würde bei fehlendem Feld eine Exception werfen." (Konjunktiv II without counterfactual — calqued from English "would throw")

**Konjunktiv II only for real hypotheticals.** Counterfactuals, proposals, "if we did X", forward-looking plans:

- ✅ "Wenn wir die Cache-TTL auf 10 Minuten senken würden, würde der ES-Index seltener neu aufgebaut."
- ✅ "Ohne den Decorator-Layer würde ein Rename erst im Behat-Lauf sichtbar." *(counterfactual — the Decorator layer exists, we're describing the absence case)*

**Perfekt for completed work done:** Acceptance criteria, status updates, commit messages in the perfective sense.

- ✅ "Die Lock-Datei ist aktualisiert, die Pipeline läuft grün."
- ✅ "Wir haben den Import-Pfad umgestellt; die alte Klasse ist entfernt."

**Präteritum almost never in tech writing.** It's literary/narrative. Never use it in Jira or MR text.

- ❌ "Der Test schlug fehl, weil die Fixture leer war." *(sounds like a novel)*
- ✅ "Der Test ist fehlgeschlagen, weil die Fixture leer war." *(Perfekt — natural tech prose)*

## Voice

**Active preferred when an actor is identifiable.** Pick it when you're describing what a specific service/test/user does.

- ✅ "Der PricingStorageIsolator rebuildet die Combined-Price-Lists aus den raw-Rows."
- ✅ "Das Fixture-Loader liest die YAMLs aus `tests/Fixtures/`."

**Passive for system behavior where the actor is irrelevant or diffuse.** Jira descriptions often benefit from passive because they describe outcomes, not actors.

- ✅ "Die Exception wird zur Laufzeit geworfen."
- ✅ "Die PriceListToCustomer-Rows werden beim PricingStorageIsolator-Lauf neu aufgebaut."

**Avoid mixing active and passive in a single flow.** Pick one per paragraph for parallelism.

**Never use "man" in technical writing for a concrete actor.** It's acceptable in generic statements ("man kann X auch über Y erreichen") but clunky when a subject is identifiable.

- ❌ "Man muss das Behat-Baseline neu aufbauen."
- ✅ "Das Behat-Baseline muss neu aufgebaut werden."

## Person

**No first person in artifact text.** Ever. "Ich", "wir", "uns" belong in chat, review comments, and 1:1 communication — not in Jira descriptions, MR descriptions, or release notes.

- ❌ "Wir haben den Bug gefixt."
- ✅ "Der Bug ist behoben." (Perfekt-Passiv)
- ✅ "Der Fix ist enthalten in Commit abc1234." (if you need to name it)

**Second person only in user-facing documentation aimed at a reader.** Use Sie-Form in product-facing documentation, Du-Form in internal wiki/team docs (HMKG team uses Du).

- ✅ *(HMKG team wiki)* "Achte darauf, dass der Branch auf `develop` basiert, bevor du merged."
- ✅ *(external customer docs)* "Melden Sie sich unter /admin an und navigieren Sie zu ..."

## Artifact-Specific Conventions

### Jira Issue Description

Structure:

```
h2. Problem
[What is broken/missing/needed. Impersonal, present tense, 2-4 sentences max.]

h2. Ziel
[What the solution should achieve. Impersonal, present or future, 1-2 sentences.]

h2. Akzeptanzkriterien
* [Bullet list, each item passive or imperative infinitive]
* [...]

h2. Out of Scope
* [What this ticket explicitly does NOT cover]

h2. Abhängigkeiten
* Benötigt: [ticket keys]
* Blockiert: [ticket keys]
* Parent Epic: [key]
```

Style:
- Impersonal throughout — no "ich/wir"
- Present tense for the problem description (it *is* broken now)
- Bullets in parallel grammatical form (all noun phrases or all imperative verbs, not mixed)

### Jira Comment

- Start with context in one line (MR link, CI status, commit SHA)
- Use `h3.` headings, not `h2.` (comments are sub-content)
- Tables for feature/test enumerations (`|| Column || Column ||` header, `| cell | cell |` rows)
- Code elements in `{{monospace}}`
- Closing: facts + next action, no hedging ("Hoffen wir mal", "Scheint zu funktionieren" — cut)

### GitLab MR Description

- **Title**: `TICKET-KEY: Short imperative summary in English or German` (team convention: titles usually English on git.netresearch.de even when description is German)
- **Body in German**: Problem / Lösung / Impact. One screen max.
- Avoid the "what I did today" narrative — reviewers don't read a journal. They want: **what changed, why, how to verify**.
- Link the Jira ticket in the body, not just implicitly via branch name

### Commit Message

- First line: `TICKET-KEY: Imperative summary, ≤72 chars`
- Language follows team convention — HMKG uses English for commits per global CLAUDE.md
- When writing German commits (other projects): imperative mood (*"Fixture-Chain um PriceListToCustomer erweitern"*), not narrative (*"Ich habe die Fixture-Chain erweitert"*)
- Body (optional): why the change is needed, not what the diff shows

### Release Notes

- Bullet list, one line per user-visible change
- Start each bullet with a noun or verb phrase, not "Wir haben..."
- Group by: Features / Fixes / Breaking Changes / Deprecations
- No marketing language, no hedging

## Sentence Length

German allows longer sentences than English, but technical prose in Jira/MR contexts should stay **short**. Rule of thumb:

- Ideal: 10–15 words per sentence
- Acceptable: up to 25 words
- Hard stop: 35+ words means split it

The reason: Jira/MR readers skim. Long Verbalketten-Sätze are where anglicisms hide because the writer loses the thread halfway through.

## Compound Nouns

German loves compound nouns. Technical writing leverages this, but beware overstacking:

- ✅ "Produkt-Konfigurations-Attribut" *(3 elements, readable)*
- ⚠️ "Produkt-Konfigurations-Attribut-Validierung" *(4 elements, starting to strain)*
- ❌ "Produkt-Konfigurations-Attribut-Validierungs-Service" *(5 elements — split with prepositions)*
  - → "Service zur Validierung von Produkt-Konfigurations-Attributen"
  - → "Validierungs-Service für Produkt-Konfigurations-Attribute"

**Hyphenation rule:** connect with `-` when at least one component is a loanword (*Exception-Handler*, *PriceList-Rebuild*, *CI-Pipeline*). Pure German compounds can omit hyphens (*Konfigurationsattribut*) but hyphens are always safe for readability.

## Orthography Minimums

Never substitute these with ASCII:

- **ß** — "weiß", "Fuß", "groß", "Maß". Never write "weiss", "Fuss". (exception: Swiss German drops ß — not our context)
- **ä ö ü** — "Qualität", "Überprüfung", "Änderung". Never "ae/oe/ue" in normal text.
- **„…"** — German quotation marks. In Jira markup or code contexts, straight quotes `"..."` are fine. In plain prose, use `„…"` for nested quotes.

Capitalization:
- All nouns capitalized (the default German rule — don't forget)
- Verbs used as nouns capitalized: *"das Rebuilden der Combined-Price-Lists"*
- Adjectives normally lowercase unless nominalized: *"das Wichtigste ist X"* (nominalized), *"der wichtige Schritt"* (attribute)

## Checklist — self-review pass

Before posting any German artifact longer than one sentence, read through it once and ask:

1. ☐ Is every verb drawn from the German technical lexicon, not translated from English?
2. ☐ Is the tense Präsens-Indikativ (default) or justified Konjunktiv/Perfekt?
3. ☐ Is there any first-person ("ich", "wir") that should be impersonal?
4. ☐ Is every sentence under 25 words?
5. ☐ Are compound nouns split at ≤3 elements or with prepositions beyond that?
6. ☐ Are ß/ä/ö/ü intact?
7. ☐ Does any sentence contain a calqued English idiom ("am Ende des Tages", "low-hanging fruit", "auf derselben Seite")?
8. ☐ If bullet points: are they in parallel grammatical form?

If any check fails, fix it before posting.
