# Verständlichkeit — was der Leser rekonstruieren muss

Comprehension is not a word count. A text is hard to read when the reader has to reconstruct what the writer left out: an antecedent three paragraphs up, a self-minted abbreviation, a condition that was dropped while shortening. A slightly longer explanation that stands on its own beats a terse one full of back-references.

This reference resolves conflicts with the brevity and variation rules in `typografie-rhythmus.md` and `register.md`.

## Priority

**Fachliche Richtigkeit und eindeutiges Verständnis haben Vorrang vor Kürze, stilistischer Abwechslung und dem Ziel, weniger maschinell zu klingen.**

Where a rule from another reference would cost a condition, an exception, a negation or an unambiguous reference, that rule yields. Shortening that loses meaning is a defect, not a saving.

## Bezüge müssen ohne Rücksprung auflösbar sein

*dies*, *damit*, *dadurch*, *Letzteres*, *siehe oben* are usable only where the referent is the nearest plausible candidate. Otherwise repeat the term. Repeating four words is cheaper for the reader than scrolling back one screen — and in Jira, where comments are read out of order and quoted in isolation, the referent is often no longer on the page at all.

❌ *„Dadurch ist das weiterhin möglich. G3 bleibt ebenfalls offen."*

✅ *„Der automatische Merge verhindert keine doppelten IDs. Auch die Anforderung, bestehende Einträge vor Änderungen zu schützen, bleibt unerfüllt."*

The second version is longer and needs no back-reference.

## Erklärung einmal, notwendiger Kontext erneut

`typografie-rhythmus.md` forbids re-explaining a mechanism. That rule targets padding, not every repetition:

- **Explain once** — a mechanism, a cause, a design decision gets one full explanation, where it matters most.
- **Repeat what a section needs to stand on its own** — the term, the ticket key, the one-clause context. A section that forces a jump backwards is the defect the brevity rule was meant to prevent.

The test is not „steht das schon irgendwo", but „muss der Leser zurückspringen, um diesen Absatz zu verstehen".

## Erfundene Kürzel gibt es nicht

*G2*, *Option B3*, *Variante 2* as labels for things that have names are the writer's shorthand, not the reader's. Use the speaking name (*die Merge-Guard-Anforderung*), or introduce the abbreviation once explicitly and only when it recurs often enough to earn the introduction.

Real identifiers are the opposite case and stay verbatim: ticket keys (*NRS-4763*), MR/PR numbers, commit SHAs, field names, class names. Never paraphrase, renumber or „vereinfache" them away.

## Konkret schlägt bildhaft, wo etwas erklärt wird

`SKILL.md` and `anti-patterns.md` want idiomatic dev speech (*ins Gehege kommen*, *läuft voll*, *fliegt auf*) — sterile German reads more machine-written, not less. That stays true. It is narrowed in one place:

> Natürliches Deutsch ist erwünscht. Wo eine Aussage einen Fehler, eine Ursache, eine Handlung oder eine Entscheidung erklärt, haben konkrete Beschreibungen Vorrang vor Redewendungen.

- ❌ *„Doppelte IDs fliegen damit auf."* — in the sentence that states what the test does
- ✅ *„Der Test erkennt doppelte IDs."*
- ✅ *„Der Speicher läuft voll"* — description of a symptom, nothing is replaced

The question is never whether the wording is colloquial, but whether the idiom stands in place of information the reader needs: which component, which condition, which consequence.

## Satzbau prüfen, nicht Wörter zählen

The 10–15 / 25 / 35 figures in `register.md` are a warning signal, not the check. A short sentence can be unreadable: *„Damit gilt dies dort ebenfalls nicht."* passes every word count and says nothing.

Three questions per sentence:

1. Is it unambiguous who does what?
2. Does each condition sit next to the statement it restricts?
3. Must the reader hold several insertions or references in mind at once?

A sentence that fails one of these gets split or rebuilt — however short it is. A long sentence that passes all three may stay.

Variation is subordinate to this. Where several items are genuinely parallel — acceptance criteria, a list of findings, three checks of the same kind — parallel phrasing is the clearer form. Do not break symmetry that carries meaning just to sound less machine-written; break the symmetry that only decorates.

## Fachbegriffe nach Zielgruppe

`typografie-rhythmus.md` forbids glossing terms the audience coined. That holds for established terminology in front of the audience that uses it — a backend developer needs no definition of *Race Condition*.

It does not cover two cases:

- **A term outside the reader's field.** A mixed audience (PM, QA, customer) is not the dev audience the rule assumes. Explain what that audience cannot be assumed to know — once, at first relevant use.
- **Project-internal coinages.** A name invented in this project or this ticket is not known just because it sounds technical. Introduce it at first use.

Same facts for every audience, different amount of explanation. Never simplify to beginner level and never drop technical depth for it.

## Kürzen darf keine Bedingung kosten

When shortening, conditions, exceptions, negations and hedges are the first things to fall out — and they are the load-bearing parts.

- *„kann"* must not become *„wird"*, *„sollte nicht mehr auftreten"* must not become *„ist ausgeschlossen"* (see `typografie-rhythmus.md`, Aussagen über künftiges Verhalten).
- *„außer bei … "*, *„nur wenn … "*, *„es sei denn … "* stay, even when the sentence then breaks the word budget.
- Keep measured fact, conclusion and assumption distinguishable. Where a statement is an assumption, it says so.

Cut filler, self-praise and summaries that add nothing. Do not cut the qualifier.

## Bei Unsicherheit

Decide ordinary style questions yourself. Never invent a missing fact. Ask only where an ambiguity would change the technical statement and the available context cannot resolve it.

## Selbstcheck

After composing: does any *dies / damit / Letzteres / siehe oben* have a referent the reader must search for? An abbreviation you minted yourself? A real identifier that got paraphrased? An idiom standing where a mechanism should be? A sentence whose subject you have to hunt for, short or not? A condition, exception or hedge that the shortening pass ate? A project-internal coinage used unintroduced, or a term glossed for people who coined it? If yes — fix before posting.
