# Anti-Patterns — False Friends in German Technical Writing

Catalogue of literal English→German translations that read as anglicisms in professional German technical prose, paired with the natural technical phrasing.

## How to use

Search by English concept or by the wrong-form you're tempted to write. Each row explains **why** the wrong form reads as anglicism — grammatical but foreign — and which form is established in German dev writing.

## Verbs — Exceptions & Errors

| EN concept | ❌ Wrong | ✅ Right | Why |
|---|---|---|---|
| throw | schmeißen | werfen | "schmeißen" is colloquial/regional; technical German uses *werfen* for exceptions. |
| catch | fangen / catchen | abfangen | Bare *fangen* means "catch" in the animal/ball sense. Exceptions get *abgefangen* (the *ab-* prefix is not optional). |
| code breaks | brechen (alone) | fehlschlagen / abbrechen / eine Exception werfen | Code does not *brechen*; a process can *abbrechen* (abort) or *scheitern*, a call can *fehlschlagen*. |
| trigger error | triggern | auslösen | *Triggern* exists colloquially but sounds amateurish in written tech prose. *Auslösen* is the canonical verb. |
| hit an error | hitten / auf Fehler hitten | auf einen Fehler stoßen / einen Fehler treffen | *Hitten* is pure Denglisch. *Auf X stoßen* is idiomatic. |
| raise an exception | anheben | werfen / auslösen | German has no "raise" idiom for exceptions; collapse to *werfen*. |
| handle error | handeln | behandeln | *Handeln* means "to act/trade"; errors get *behandelt*. |
| recover from | erholen von | sich erholen von / zurückkehren aus | Technical contexts prefer *nach einem Fehler zurückkehren* or *sich erholen* (reflexive, not bare). |

## Verbs — Tests & Builds

| EN | ❌ | ✅ | Why |
|---|---|---|---|
| test passes | passt | besteht / geht durch | *Passen* = to fit. Tests *bestehen*. |
| test fails | failt / failed | schlägt fehl / fällt durch | *Failen* is pure anglicism; *fällt durch* mirrors exam language. |
| test is green / red | grün / rot (OK) | grün / rot | This usage is accepted. |
| build fails | Build failt | Build schlägt fehl / bricht ab | Build *schlägt fehl* or *bricht ab*; never *failt*. |
| caught by tests | gefangen | erkannt / aufgedeckt / abgefangen | *Gefangen* = captured (in the prisoner sense). Tests *erkennen* or *decken auf*. |
| run tests | runnen | ausführen / laufen lassen | *Ausführen* is the canonical verb; *laufen lassen* is colloquial but acceptable. |
| skip test | skippen (OK colloquial) | überspringen / auslassen | Written form prefers *überspringen*. |
| cover code | covern | abdecken | *Covern* is music-industry German. Tests *decken Code ab*. |
| assert | asserten | zusichern / prüfen | *Asserten* is Denglisch; *eine Assertion* (noun) is fine, verb form prefers *prüfen* or *zusichern*. |

## Verbs — Data Flow & Control

| EN | ❌ | ✅ | Why |
|---|---|---|---|
| return null | returnen | zurückgeben | *Returnen* is pure anglicism. |
| call method | callen | aufrufen | *Callen* is Denglisch. |
| pass argument | passen | übergeben | *Passen* is wrong (see tests); parameters get *übergeben*. |
| fall back to | zurück in … fallen | auf … zurückfallen / auf … ausweichen | Preposition+particle order: *auf X zurückfallen*, not *zurück in X fallen*. |
| end up in state | in Zustand … enden | in Zustand … landen / … erreichen | *Enden* is literal. Processes *landen* in a state. |
| fix bug | fixen (OK informal) | beheben / beseitigen / fixen | *Fixen* is acceptable in chat and commit messages; Jira descriptions prefer *beheben*. |
| parse input | parsen | parsen / auswerten | *Parsen* is accepted Denglisch. *Auswerten* is more formal. |
| check condition | checken (OK informal) | prüfen | Written form prefers *prüfen*. |
| resolve | resolven | auflösen / ermitteln | *Resolven* is Denglisch. |

## Verbs — Git & VCS

| EN | ❌ | ✅ | Why |
|---|---|---|---|
| merge | mergen (OK) | mergen / zusammenführen | Both accepted. Pure German sounds stilted but is correct. |
| rebase | rebasen (OK) / umbasen | rebasen | *Umbasen* is not a word. *Rebasen* is accepted. |
| cherry-pick | cherry-picken (OK) | cherry-picken / übernehmen | Accepted loanword. |
| squash | squashen (OK) | squashen / zusammenfassen | Accepted loanword. |
| revert | reverten (OK) | reverten / zurücknehmen / rückgängig machen | Accepted loanword. |
| rename | renamen | umbenennen / renamen (colloquial) | *Renamen* acceptable in chat; written form prefers *umbenennen*. *Ein Rename* as noun is widely accepted. |
| checkout | auschecken / checkouten (OK) | auschecken / auf X wechseln | Accepted. |
| push | pushen (OK) | pushen | Accepted. |
| pull | pullen / ziehen (OK) | pullen / abholen | Accepted; *abholen* slightly dated. |

## Nouns & Adjectives

| EN | ❌ | ✅ | Why |
|---|---|---|---|
| the test | die Test | der Test | Gender mistake — *der Test* (masc). |
| bare X | ein bare X | ein unqualifiziertes X / ein nacktes X | *Bare* is not a German adjective. |
| vanilla (default) | vanilla | unverändert / Standard- | Calque; in tech contexts *unverändert* works. |
| low-hanging fruit | niedrig hängende Frucht / low-hanging Fruit | leicht erreichbare Verbesserung / einfache Gewinne | Dead metaphor in German; prefer description. |
| end of the day | am Ende des Tages (as idiom) | letztlich / am Ende / unter dem Strich | *Am Ende des Tages* as idiom is calqued; only use literally. |
| on the same page | auf derselben Seite | einer Meinung / auf demselben Stand | Literal translation; cut it. |
| nice to have | nice-to-have (OK) | wünschenswert / angenehm, aber optional | Accepted loanword; pure form less stilted than calque. |
| happy path | happy path (OK) | Glücksfall / Normalfall / Standardablauf | Accepted loanword in design contexts. |

## Sentence structure

| Pattern | Problem | Fix |
|---|---|---|
| "Wenn X, dann Y, was Z macht" | Calqued relative clause stacking | Split into two sentences. |
| "Der Code, der X macht, ist wichtig" | Over-nested subordinate | Flatten: "Der Code für X ist wichtig." |
| "Es ist wichtig, dass ..." | Weak opener | Start with the subject: "X muss ..." |
| "würde werfen" ohne Hypothese | Konjunktiv without counterfactual | Use Indikativ: "wirft". |
| Überlange Substantivketten (Produkt-Konfigurations-Attribut-Validierungs-Service) | Noun-stacking beyond 3 elements | Split with *des/für/bei*: "Validierungs-Service für Produkt-Konfigurations-Attribute" |

## Pseudo-anglicisms to avoid

These are German "English" words that don't exist in English or mean something else:

- **Handy** for mobile phone — acceptable in general German but never in tech writing (use *Smartphone*)
- **Beamer** for projector — avoid in tech writing (use *Projektor*)
- **Shooting** for photo session — marketing-speak, not tech
- **Oldtimer** for vintage car — irrelevant but beware the pattern

## When to break the rules

Use anglicisms deliberately when:

- Quoting someone else's exact words
- Writing chat messages to a team that already uses the term
- In code-adjacent contexts where English identifier names need context ("the `callback` wird gecallt" sounds less weird than "der `callback` wird aufgerufen" if the discussion is heavily about the literal identifier)

But always flag it consciously — not as a default.
