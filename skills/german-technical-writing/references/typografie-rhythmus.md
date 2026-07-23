# Typografie & Rhythmus — was Text als maschinell entlarvt

Two rule sets. Typography is mechanical — apply it verbatim. Rhythm rules describe the *shape* natural German prose has; produce that shape rather than policing individual words. These are the loudest AI tells in otherwise correct German — native readers spot them before any vocabulary issue.

## Typografie

**Gedankenstrich.** German uses the Halbgeviertstrich `–` with spaces on both sides — never the English em-dash `—`. Budget: at most one Gedankenstrich-Einschub per paragraph; the default separators are comma, colon, and full stop. Number and date ranges take `–` without spaces: *S. 22–24*, *28.–29. Februar*.

**Anführungszeichen.** German quotes open low, close high: `„…“` (inner: `‚…‘`). Guillemets `»…«` are the valid alternative; pick one convention per document. A comma meeting a closing quote goes after it: *„fertig“,* not *„fertig,“*. Straight `"…"` only inside code spans.

**Durchkopplung.** A multi-word English term inside a compound couples with hyphens throughout: *End-to-End-Test*, *Continuous-Integration-Pipeline*, *Cart-Merge-Feature*. The most common mistake is coupling only the last joint (*Social Media-Plattform* → *Social-Media-Plattform*). A bare English phrase not forming a compound keeps its spacing (*Machine Learning*), but couples fully the moment it takes another element (*Machine-Learning-Modell*). Don't invent compounds where a prepositional phrase is what a dev would say: *bei mehreren Consumern*, not *im Mehr-Consumer-Betrieb*.

**Zahlen, Datum, Uhrzeit.** Decimal comma, thousands point: *1.234,56*, *199,95 €*. Time with colon plus *Uhr*: *18:00 Uhr*. Date *23.07.2026* or ISO *2026-07-23*; with month name no leading zero (*7. März*). Units keep a space: *512 MB*, *2 GB*.

**Groß-/Kleinschreibung.** Loanword nouns are capitalized like German nouns (*das Feature*, *der Commit*), including nominalized verbs (*beim Mergen*, *das Deployen*). Headings follow German sentence case, never English Title Case. Genitive with plain *-s*, never apostrophe-s (*Sebastians Branch*).

## Rhythmus & Struktur

**Jeder Mechanismus wird genau einmal erklärt.** State a cause, a mechanism, or a fact once, where it matters most; later sections reference it (*siehe oben*, *dadurch*) instead of re-explaining. Re-explanation padding is the fastest way to make a Jira comment read machine-generated. Likewise, one statement per fact: if two adjacent sentences say the same thing in different words, keep the better one.

**Satzlängen variieren.** Natural prose mixes a short verdict sentence with a longer explanatory one. A run of same-length, same-structure main clauses (Behauptung → Ausführung → Konsequenz, repeated per paragraph) is the signature AI rhythm — break it. The same goes for matched parallel verdicts across items (*„Löst X nicht." / „Verschiebt X nur."*): vary the build.

**Aufzählungen haben die Länge ihres Inhalts.** Three symmetric items, three arguments, three adjectives (*sicher, schnell und zuverlässig*) is the AI default shape. Use the number of points the content actually has, and prose where prose reads better than bullets.

**Fachbegriffe werden nicht selbst glossiert.** Writing *„… wächst unbegrenzt (Memory Leak)"* to a dev audience explains a term the reader knows — drop the gloss and use the term directly, or the plain description alone.

**Aussagen über künftiges Verhalten bleiben relativiert.** Devs write *„sollte damit nicht mehr auftreten"* / *„damit tritt das Leak nicht mehr auf"* — not datasheet absolutes like *„Damit ist X ausgeschlossen"*. Reserve absolute claims for things actually proven.

**Der Text endet mit dem letzten Fakt oder der nächsten Aktion.** No summary paragraph, no *„Zusammenfassend lässt sich sagen"*, no restating the opening. Openers state the subject immediately — no *„Es ist wichtig zu beachten, dass"*, no scene-setting.

**Ein Begriff pro Konzept.** The entity introduced as *der Service* stays *der Service* for the whole text — never alternate with *der Dienst* for elegant variation. Terminology consistency beats stylistic variety in technical prose.

**Verben statt Substantivketten.** *X prüft* instead of *die Prüfung erfolgt durch X*. Watch for *-ung* noun chains and *erfolgen/durchführen/vornehmen* carriers (see the Amtsdeutsch table in `anti-patterns.md`).

**Schlichte Konnektoren.** Natural German connects with *außerdem, deshalb, also, aber, trotzdem* — or starts the next sentence with no connector at all. Density of *zudem, darüber hinaus, ferner, nichtsdestotrotz, im Zuge dessen* marks generated text. Same for adjective inflation (*nahtlos, essenziell, robust, umfassend, entscheidend*): the plain word or no adjective.

**Chat hat Partikeln.** In Du-Form chat, modal particles carry the collegial register: *eh, halt, mal, eben, ja, doch* (*„läuft eh knapp am Limit", „schau mal in Zeile 84"*). Their total absence reads translated. In formal artifacts (Jira descriptions, wiki specs) they stay out.

## Selbstcheck

A quick scan after composing: any `—`? More than one `–`-Einschub in a paragraph? English quotes? An uncoupled English compound? The same fact stated twice? Three symmetric anything? A term glossed for people who coined it? A *„Damit ist … ausgeschlossen"*? A closing summary? Two names for one thing? If yes — fix before posting.
