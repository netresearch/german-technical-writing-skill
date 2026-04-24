# Examples — Bad vs. Good

Real paired cases from past Jira tickets and team-chat announcements. Each pair shows the anglicism-laden original, the rewrite, and why the rewrite works.

## Case 1 — The opening incident

**Bad (OROSPD-692 comment, 2026-04-24):**

> Ein bare get würde mit BadMethodCallException zur Laufzeit brechen. Ein Regressionstest führt den Provider durch den Decorator, damit ein Rename in die Falle zurück von Unit-Tests gefangen wird.

**Problems:**

1. *"ein bare get"* — *bare* is not a German word in this sense. Use *"ein unqualifiziertes `get`"* or *"ein nacktes `get`"*.
2. *"würde … brechen"* — Konjunktiv II without counterfactual + *brechen* for "break code". Should be Indikativ *"wirft"* (*the unqualified call does throw at runtime — not hypothetically*).
3. *"in die Falle zurück"* — garbled calque of "back into the trap". German has no equivalent idiom here.
4. *"gefangen"* — literal "caught". Tests *erkennen*, *decken auf*, or *fangen ab*.

**Good:**

> Ein unqualifiziertes `get` wirft zur Laufzeit eine `BadMethodCallException`. Der Regressionstest schickt den Provider durch den Decorator, damit ein späterer Rename direkt in den Unit-Tests auffliegt — ohne Decorator würde ein Umbenennen erst im Behat-Lauf sichtbar.

**Why it works:**

- Indikativ for fact (*wirft*), Konjunktiv II only for the explicit counterfactual ("ohne Decorator würde ...")
- *unqualifiziertes* is the technical term for method calls without context
- *auffliegt* is idiomatic German for "a bug gets caught" in colloquial tech speech — alternative: *erkannt wird*
- The *ohne Decorator würde ...* clause provides the missing motivation that the original garbled away

## Case 2 — Test failure description

**Bad:**

> Der Test ist gefailt weil die Fixture empty war und das System in einen bad state endete.

**Problems:**

- *gefailt* — pure anglicism
- *empty* — untranslated English
- *bad state* — untranslated English
- *endete* — *enden* is literal for "end up"

**Good:**

> Der Test ist fehlgeschlagen, weil die Fixture leer war und das System in einem inkonsistenten Zustand landete.

**Why:**

- *fehlgeschlagen* — canonical verb for test failure
- *leer* — German word exists, use it
- *inkonsistenter Zustand* — established technical phrasing for "bad state"
- *landen* — the idiomatic verb when a process arrives somewhere unintended

## Case 3 — Jira comment: fix explanation

**Bad:**

> Der Bug ist gefixt wo die Exception gecatched wurde aber nicht rethrown, sodass der Error silent war. Ich habe das gehandled indem ich den Handler refactored habe.

**Problems:**

- Stacked Denglisch with no reason: *gefixt*, *gecatched*, *rethrown*, *silent*, *gehandled*, *refactored*
- First person (*"Ich habe"*) in a Jira comment that belongs in shared ticket history
- *"wo"* as relative pronoun for a thing is colloquial and wrong here
- *silent* applied to *Error* — English idiom that doesn't transfer

**Good:**

> Die Exception wurde zwar abgefangen, aber nicht erneut geworfen — der Fehler blieb dadurch unsichtbar. Der Handler ist umgestellt, sodass die Exception nach dem Logging weitergereicht wird.

**Why:**

- *abgefangen* (proper verb), *erneut geworfen* (re-throw), *unsichtbar* (silent → invisible, the natural equivalent)
- Impersonal — no *"ich"*
- Describes the outcome (*"der Handler ist umgestellt"*), not the author's process
- *weitergereicht* is the established verb for passing an exception up the stack

## Case 4 — Jira description problem statement

**Bad:**

> Das Issue ist dass der Service immer null returned wenn die DB empty ist, was einen NullPointer trigger im Frontend bedeutet. Wir müssen das handeln.

**Problems:**

- *returned*, *empty*, *trigger*, *bedeutet* (calqued from "means")
- *Issue* is fine as loanword but *das Problem* would also work
- *handeln* = "to trade/act", not "to handle errors"
- First person (*"Wir müssen"*) in a problem statement

**Good:**

> Der Service gibt bei leerer Datenbank `null` zurück. Im Frontend löst das eine `NullPointerException` aus. Die Fehlerbehandlung muss ergänzt werden.

**Why:**

- *gibt … zurück* — canonical German for *return*
- *löst … aus* — canonical German for *trigger*
- Three short sentences instead of one rambling one
- Impersonal *"muss ergänzt werden"* instead of first-person *"Wir müssen"*

## Case 5 — Release note bullet

**Bad:**

> * Wir haben die Pipeline gefixed, sodass Tests auch bei flaky Conditions green bleiben.

**Problems:**

- First person in release notes — always wrong
- *gefixed*, *flaky Conditions*, *green* — Denglisch salad

**Good:**

> * Pipeline stabilisiert: Tests bleiben auch bei instabilen Bedingungen grün.

**Why:**

- Noun-phrase header (*"Pipeline stabilisiert"*) is natural release-note form
- Colon-then-explanation structure is German release-note convention
- *grün* is accepted for CI status — keeps the domain language
- *instabile Bedingungen* is the clean technical rendering of "flaky"

## Case 6 — Status update comment

**Bad:**

> Update: Ich habe heute das Issue debugged und gefunden dass der Root Cause die DataProviderDecorator Regex ist. Der bare get Name wird gerejected. Ich fixe das jetzt indem ich die Method zu getPimField renamen.

**Problems:**

- First person throughout
- *debugged*, *gerejected*, *bare*, *renamen*, *Root Cause* unsteady
- *"Ich fixe das jetzt indem ich ... renamen"* — verb placement + infinitive mix
- Stream-of-consciousness structure; not scannable

**Good:**

> *Status-Update:* Die Ursache liegt in der Regex `/^(get|has|is)(.+)$/i` des `DataProviderDecorator` — der unqualifizierte Methodenname `get` wird abgelehnt. Fix: Methode wird auf `getPimField` umbenannt.

**Why:**

- Impersonal passive throughout
- Concrete detail (the actual regex pattern) replaces vague "Root Cause"
- Two sentences: *diagnosis*, then *fix*. Scannable.
- Italic *"Status-Update:"* as a lead-in works in Jira wiki markup

## Case 7 — Deployment announcement

**Bad:**

> Heads up: Der neue Release geht heute abend live. Wer noch MRs am draft hat sollte merged haben bis 18 Uhr sonst slippt das in die nächste Deploy Window.

**Problems:**

- *Heads up*, *slippt*, *Window* — English idioms breaking rhythm
- *"gerne"* missing — announcements like this tend to be clipped to the point of rudeness
- Mixed sentence structure

**Good:**

> *Hinweis:* Das nächste Release geht heute Abend live. Offene MRs müssen bis 18:00 Uhr gemergt sein, sonst verschieben sie sich auf den nächsten Deploy.

**Why:**

- *Hinweis* is the German equivalent of "heads up" in an announcement register
- *verschieben sich* replaces *slippt* — proper German
- *"nächsten Deploy"* — *Deploy* is accepted loanword, use it without *Window*

## Meta-observation

Across these cases, the repeating failure modes are:

1. **First person slipping into artifacts** — chat habits bleeding into persistent text
2. **Verb-cognate translation** — grabbing the first German verb that sounds like the English one, instead of the established technical one
3. **Idiom calquing** — translating an English idiom word-for-word when German has no equivalent (the idiom has to be dropped or reformulated)
4. **Untranslated adjectives** — *empty*, *silent*, *bare*, *flaky*, *green* — German has all of these, the writer just forgot to switch
5. **Konjunktiv II for non-hypotheticals** — adding *würde* to soften when the sentence should be blunt Indikativ

When reviewing your own German draft, scan for these five patterns specifically. One pass is usually enough.
