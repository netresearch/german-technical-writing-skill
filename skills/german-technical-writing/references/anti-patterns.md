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
| hit an error | hitten / auf Fehler hitten | auf einen Fehler stoßen | *Hitten* is pure Denglisch. *Auf X stoßen* is idiomatic; *einen Fehler treffen* is itself a calque. |
| raise an exception | anheben | werfen / auslösen | German has no "raise" idiom for exceptions; collapse to *werfen*. |
| handle error | handeln | behandeln | *Handeln* means "to act/trade"; errors get *behandelt*. |
| recover from | erholen von | sich erholen von / zurückkehren aus | Technical contexts prefer *nach einem Fehler zurückkehren* or *sich erholen* (reflexive, not bare). |

## Verbs — Tests & Builds

| EN | ❌ | ✅ | Why |
|---|---|---|---|
| test passes | passt / besteht | läuft durch / geht durch / ist grün | *Passen* = to fit. *Der Test besteht* reads as "the test exists" (the code *besteht* the tests, not the test itself). |
| test fails | failt / failed | schlägt fehl | *Failen* is pure anglicism in written artifacts (tolerable in chat); *fällt durch* colloquial. |
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
| pull | pullen / ziehen (OK) | pullen | Accepted loanword; *abholen* reads as translation German, not dev speech. |

## Nouns & Adjectives

| EN | ❌ | ✅ | Why |
|---|---|---|---|
| the test | die Test | der Test | Gender mistake — *der Test* (masc). |
| bare X | ein bare X | ein unqualifiziertes X | *Bare* is not a German adjective; *ein nacktes X* only colloquially. |
| vanilla (default) | vanilla | unverändert / Standard- | Calque; in tech contexts *unverändert* works. |
| low-hanging fruit | niedrig hängende Frucht / low-hanging Fruit | leicht erreichbare Verbesserung / einfache Gewinne | Dead metaphor in German; prefer description. |
| end of the day | am Ende des Tages (as idiom) | letztlich / am Ende / unter dem Strich | *Am Ende des Tages* as idiom is calqued; only use literally. |
| on the same page | auf derselben Seite | einer Meinung / auf demselben Stand | Literal translation; cut it. |
| waiting on you / the ball is in your court | es steht auf dir / der PR steht auf dir | es liegt bei dir / du bist am Zug / der PR wartet auf dich | In the responsibility sense *steht auf dir* is not idiomatic; German uses *liegt bei* or *am Zug sein*. (*Auf jemanden stehen*, accusative, is a real idiom — it means to fancy someone, which is why the calque misreads.) |
| it is on me / my turn | das ist mein Zug (in a status report) | ich bin am Zug / das liegt bei mir | *Am Zug sein* is the idiom for whose turn it is. *Mein Zug* is correct in a board-game context, so in prose about work it reads as the game or the train. |
| nice to have | nice-to-have (OK) | wünschenswert / angenehm, aber optional | Accepted loanword; pure form less stilted than calque. |
| happy path | Glückspfad / Glücksfall | der Happy Path | Accepted loanword — keep it English (see compound-calque table below). *Glücksfall* means a lucky break, not a code path. |

## Collocation & preposition calques (the „blockiert auf“ trap)

The subtlest failure mode: every word is German, but the verb+preposition or verb+object pairing is mapped 1:1 from English. Natives read these as machine output even when they can't name why. Check the German collocation, never transfer the English preposition.

| EN pattern | ❌ Calque | ✅ Natural | Why |
|---|---|---|---|
| blocks on X | blockiert auf X | wartet auf X / wird durch X blockiert / hängt an X | *blockieren auf* does not exist in German. |
| runs into timeouts | läuft in Timeouts | es kommt zu Timeouts / läuft in einen Timeout | plural *in Timeouts laufen* is Denglisch; the singular idiom is marginal, *es kommt zu* is safe. |
| traffic occurs / there is traffic | Traffic entsteht | es gibt genug Traffic / genug Last kommt zusammen | *entstehen* doesn't collocate with Traffic/Last. |
| produce this timing | dieses Timing erzeugen | dieses Timing treffen / sich zeitlich überschneiden | timing isn't *erzeugt*; describe the overlap. |
| run closely together | eng nebeneinander laufen | zeitlich eng ineinandergreifen / sich zeitlich überschneiden | parallel processes don't run *nebeneinander* in German. |
| assertion on X | die Assertion auf X | die Prüfung von X / die Assertion, dass … | *auf* is the English *on*; rephrase. |
| silently swallows | stillschweigend verschluckt | verschluckt / unterdrückt | *verschlucken* is already silent — *stillschweigend* doubles it. |
| marked as deprecated | als veraltet markiert | deprecatet / als deprecated markiert | stiff paraphrase; dev register keeps the loanword. |
| the right fix | der richtige Fix | der eigentliche Fix / der saubere Fix | *richtig* implies the workaround was *wrong* rather than provisional. |
| migrate to X | auf/nach X migrieren | zu X migrieren | |
| compatible with X | kompatibel zu X | kompatibel mit X | |
| integration with X | die Integration mit X | die Integration in X | |
| change X to Y | X auf Y ändern | X in Y ändern | |
| on the internet/web | auf dem Internet/Web | im Internet / im Web | |
| report to sb. | an jdn. berichten | jdm. berichten | dative, no preposition. |

## Idiom & discourse calques

| EN | ❌ Calque | ✅ Fix | Why |
|---|---|---|---|
| makes sense | macht Sinn | ist sinnvoll / ergibt Sinn | *Sinn machen* still marked in written register; *ist sinnvoll* is safest. |
| in 2026 | in 2026 | 2026 / im Jahr 2026 | German drops the preposition with bare years. High-frequency error. |
| address a problem | ein Problem adressieren | angehen / lösen / behandeln | *adressieren* = to put an address on something. |
| realize (notice) | realisieren, dass | merken / feststellen, dass | German *realisieren* = to implement/make real. |
| I'm fine with it | Ich bin fein damit | passt für mich / einverstanden | pure calque. |
| no idea | keine Idee | keine Ahnung | *Idee* = a creative idea, not ignorance. |
| it takes two X | es braucht zwei X | dafür sind zwei X nötig | rising anglicism, still marked in written register. |
| once more | einmal mehr | erneut / wieder einmal | |
| do a good job | einen guten Job machen | gute Arbeit leisten | (*einen guten Job machen* is common speech, marked in writing) |
| for several minutes | für mehrere Minuten | mehrere Minuten lang | *für* + duration is English. |
| billion | die Billion (as 10⁹) | die Milliarde | German *Billion* = 10¹². Numeric error, not style. |

## Sentence structure

| Pattern | Problem | Fix |
|---|---|---|
| "Wenn X, dann Y, was Z macht" | Calqued relative clause stacking | Split into two sentences. |
| "Der Code, der X macht, ist wichtig" | Over-nested subordinate | Flatten: "Der Code für X ist wichtig." |
| "Es ist wichtig, dass ..." | Weak opener | Start with the subject: "X muss ..." |
| "würde werfen" ohne Hypothese | Konjunktiv without counterfactual | Use Indikativ: "wirft". |
| Überlange Substantivketten (Produkt-Konfigurations-Attribut-Validierungs-Service) | Noun-stacking beyond 3 elements | Split with *des/für/bei*: "Validierungs-Service für Produkt-Konfigurations-Attribute" |

## Filler & meta-commentary (the „ehrlich gesagt“ trap)

Empty throat-clearing that prefaces a statement by asserting its own sincerity, or re-announces what was already said. Pure calque of English *to be honest (with you)* / *frankly* / *I'll be straight with you*. German technical prose states the fact directly — honesty is the baseline of the exchange, so the preface is redundant, reads as translated American register, and distracts from the content. Cut it.

| EN filler | ❌ Calque | ✅ Fix | Why |
|---|---|---|---|
| to be honest / honestly / frankly | ehrlich gesagt / um ehrlich zu sein / ganz ehrlich / offen gesagt | *(cut — state the fact directly)* | Sincerity is assumed; in technical prose the preface is filler. *Ehrlich gesagt* exists colloquially but adds nothing here. The multi-clause form (*„ich sage dir lieber ehrlich …, statt zu verschleiern“*) is egregious — a reader asks "so otherwise you *don't*?" |
| to be fair | fairerweise muss man sagen (as filler) | *(cut, or „allerdings“ / „andererseits“)* | Calqued concessive hedge. |
| as I said / like I said | wie (bereits) gesagt — *as filler* | *(cut, unless it genuinely points back to a specific earlier statement)* | Filler unless a real back-reference. |
| I have to say / I must admit | ich muss sagen / ich muss zugeben | *(cut — drop the meta-frame)* | First-person meta-commentary; also breaks the impersonal-voice rule in artifacts. |

Applies in chat to colleagues too, not only in formal artifacts — and the English originals are just as unwelcome, so do not fall back to *"to be honest, …"* either.

## Hollow antithesis (the „X, nicht Y“ trap)

A statement followed by the negation of an alternative that was never in question.
Rhetorically an *Antithese*; where the positive half is already unambiguous it is also
a *Pleonasmus*, because the second half excludes nothing. The surface forms are
„X, nicht Y“ and „nicht X, sondern Y“, and they are among the most reliable tells of
machine-written prose.

| ❌ | ✅ | Why |
|---|---|---|
| „deine Arbeit, nicht meine“ | „Die Commits stammen von dir.“ | *Deine* already excludes *meine*. |
| „Das ist ein Fehler, kein Feature.“ | „Das ist ein Fehler.“ | Nobody proposed *Feature*. |
| „Ich habe es gemessen, nicht geschätzt.“ | „Gemessen über 100 gemergte MRs: …“ | Replace the claim of rigour with the measurement. |

**Why it creeps in:** the negation fends off an objection nobody raised, and the
balanced pair *sounds* considered while carrying no additional thought. It is hedging
disguised as precision — and it often drags the writer into a sentence that was about
someone else.

**Keep the construction only when the excluded alternative was genuinely on the
table** — when a reader would otherwise land on it, or when it was the previous,
wrong assumption:

> ✅ „Die Ursache liegt im TER, nicht in tailor.“ — both had been suspected; naming
> the loser *is* the finding.

The test: delete the negated half. If nothing is lost, it was never doing work. When
in doubt, cut it and spend the words on the positive statement instead — say who,
what and why, rather than what it is not.

## Compound-noun calques (the „Wurzelursache“ trap)

These are the **opposite** of the verb-level anglicisms above. Writers who internalize "use German verbs" tend to over-correct and start *translating* English compound technical terms that should stay as loanwords. The result is grammatically perfect German that sounds like DeepL output to a native engineer because no German developer ever utters those translations.

| EN | ❌ Calque | ✅ Loanword | Why |
|---|---|---|---|
| root cause | Wurzelursache / Hauptursache | Root Cause | *Wurzelursache* is unused in German engineering speech. Postmortems, code reviews, Jira: *Root Cause* verbatim. Plural: *Root Causes*. |
| root-cause analysis | Wurzelursachen-Analyse | Root-Cause-Analyse | Same; hyphenated compound. |
| caller (stack-trace) | der Aufrufer | der Caller | *Aufrufer* technically correct, but stilted in dev jargon. Stack-Trace + Debugging: *Caller*. *Aufrufstelle* OK as alternative. |
| callsite | die Aufrufstelle (in dev jargon) | der Callsite | Same logic; *Aufrufstelle* OK in formal docs. |
| edge case | der Randfall | der Edge Case | *Randfall* works in math/stats register but is unused in software-engineering speech. Plural: *Edge Cases*. |
| corner case | der Eckfall | der Corner Case | Same logic. |
| race condition | die Wettlaufbedingung | die Race Condition | *Wettlaufbedingung* is academic-CS textbook; engineering register is *Race Condition*. |
| memory leak | das Speicherleck | das Memory Leak | *Speicherleck* exists but engineers say *Memory Leak*. |
| stack overflow | der Stapelüberlauf | der Stack Overflow | Engineering register keeps the loanword; *Stapelüberlauf* is OS-textbook. |
| garbage collection | die Müllabfuhr / die Speicherbereinigung | die Garbage Collection | *Müllabfuhr* is colloquial waste-disposal — never use in tech. *Speicherbereinigung* exists but is academic; engineers say *GC* or *Garbage Collection*. |
| deadlock | die Verklemmung | das Deadlock | *Verklemmung* is OS-textbook; engineering register is *Deadlock*. |
| heap | der Haldenspeicher | der Heap | Same trap. |
| thread | der Faden | der Thread | *Faden* is purely literal/textile. |
| code path | der Ausführungspfad | der Code-Pfad | Native form possible but uncommon; *Code-Pfad* dominant. |
| hot path | der heiße Pfad | der Hot Path | Performance-Kontext; loanword only. |
| happy path | der Glückspfad | der Happy Path | Already noted above. |
| reproducer | das Reproduktionsbeispiel | der Reproducer | Engineering shorthand. |
| trace | die Spur | der Trace | *Spur* is the Duden translation but engineers say *Trace*. |
| timeout | die Zeitüberschreitung (in dev jargon) | das Timeout / der Timeout | *Zeitüberschreitung* is Duden-perfect but reads bureaucratic. |
| stub | der Platzhalter | der Stub | *Platzhalter* exists but is for general placeholders, not test doubles. |
| mock | das Imitat | der Mock | Same logic. |
| pull request | die Zugverlangung | der Pull Request / der MR | *Zugverlangung* is a parodic backformation that should not exist in any document. |
| merge conflict | der Verschmelzungskonflikt | der Merge Conflict | *Verschmelzung* is metallurgy. |
| breaking change | die brechende Änderung | das Breaking Change / der Breaking Change | *Brechende Änderung* is calque from "breaking"; gender on the loanword unstable, both *das* and *der* attested. |
| dry-run | der Trockenlauf | der Dry-Run | *Trockenlauf* exists in mechanical engineering, not in software. |

### Decision rule

If a native German developer would *say* the term verbatim in a code review or stand-up, keep it English. The litmus test isn't "does a German equivalent exist?" — Duden has German for nearly everything. The test is: "does any German engineer actually use the German equivalent in everyday speech?" If the German form sounds like a textbook chapter title, it's a calque.

**Align to the product's German UI** — the same litmus from the other side. When a tool ships a German interface, use *its* term, not the English word you would say in English. Confluence: *Entwurf* (not „Draft“), *Veröffentlichen* / *veröffentlichen* (not „publizieren“). And avoid vague English umbrella-nouns where a precise German term is standard — *Schnittstelle* / *Anbindung*, not „Connector“. A German user of the German UI says „Entwurf“, so „Draft“ reads as untranslated: here the loanword is *not* the verbatim term, the German one is.

### Identifiers are values, not vocabulary

The decision rule above sorts words into "keep the loanword" and "use the German
term". Machine-readable strings belong to neither: field names, API values, status
constants, flags, exit codes, branch names. They are quoted material, and translating
one invents something the system never emits — the reader who searches for it finds
nothing.

Set them as values, in code style, and let the German sentence carry the meaning
around them:

| ❌ | ✅ | Why |
|---|---|---|
| „CLEAN, 20 Checks bestanden“ | „`mergeStateStatus: CLEAN`, 20 Prüfungen bestanden“ | `CLEAN` is a GitHub field value; „Checks“ is an everyday word with *Prüfungen* ready to hand. Translating the value would produce a state the API has no name for. |
| „der Job ist FAILED“ | „der Job steht auf `failed`“ | The value stays literal, the sentence supplies the grammar. |
| „setze das Flag auf WAHR“ | „setze `--force` auf `true`“ | Neither the flag nor its value is German vocabulary. |

The two errors are opposite and both easy: dropping an English word in where German
has a plain one (*Checks*, *Threads*, *Head*), and translating a literal that has to
stay verbatim.

### Do not invent a term where a plain word or a sentence exists

The Amtsdeutsch trap below is over-translation into officialese. Its livelier cousin
is over-*translation into invention*: minting a German term for a technical concept
because the literal rendering feels flat, or because no established word exists. The
coinage carries associations the subject does not have, or none at all, and no reader
can look it up.

It comes in two shapes, and the second is the one that slips through — because the
self-check asks about imagery, and the second shape has none.

**The vivid one.** „Torlage“ for a merge gate — built from *Tor* = gate, but *Torlage*
in German is a scoring chance in football. It was used repeatedly in status reports
before anyone asked what it meant. „Alle Bedingungen fürs Zusammenführen“ says it and
needs no decoding.

**The dry one.** „Intent-Defekt“ for a piece of code that did nothing while its comment
claimed it protected something. Sober, technical-looking, built from two real words —
and empty: it names no defect anyone can act on, and the reader's answer was „ich
verstehe es nicht“. What it was standing in for took three plain sentences: *Der Code
hat nicht getan, was der Kommentar behauptet. Das Ergebnis war trotzdem richtig. Falsche
Beschreibung, kein falsches Verhalten.* Length is not the measure — those three
sentences are readable, the one compound was not.

Abstract compounds are the natural landing spot when a concept has no German name, and
German makes them frictionless to build, so the urge is strongest exactly where the idea
is hardest. That is the moment to write the sentence instead.

If a term has no established German form, use the English one or describe the thing in
ordinary words. Invention is the one option that leaves the reader worse off than
either.

## Amtsdeutsch over-polish (the „Datenbestand“ trap)

The third failure mode: avoiding anglicisms so hard that the text lands in bureaucratic officialese no developer writes. Grammatically perfect, register-dead. The fix is always the plain dev word or an active verb.

| ❌ Amtsdeutsch | ✅ Dev register | Why |
|---|---|---|
| der Datenbestand | die Datenbank / die DB | *Datenbestand* is Behördensprache. |
| In dieser Konstellation | dann / in dem Fall | |
| Es handelt sich um X | Das ist X / just name X | translation filler ("it is a matter of"). |
| Zu beachten ist, dass X | state X directly, or *Achtung:* | instruction-manual German. |
| perspektivisch | langfristig / später | consultant buzzword. |
| Die Prüfung erfolgt durch X / X wird einer Prüfung unterzogen | X prüft | Funktionsverbgefüge — use the verb. Same for *zur Anwendung bringen* → *anwenden*, *zum Einsatz kommen* → *einsetzen*, *eine Durchführung erfolgt* → any active verb. |
| partiell / obsolet (as filler formality) | teilweise / veraltet | plain word over formal word when both fit. |
| Unterstützung bieten | unterstützen / helfen | |

Deliberately idiomatic dev speech is *welcome*, not a violation: *sich ins Gehege kommen*, *der Speicher läuft voll*, *das fliegt in den Unit-Tests auf*, *läuft eh knapp am Limit*, *den Cache wegziehen*. Sterilizing these into formal German makes text read more machine-written, not less.

### Four failure modes — keep them straight

This file catalogues **four distinct failure modes**, and over-applying one drives you into another:

1. **Anglicism (verbs):** keeping English when German is canonical. *Test failt* → *schlägt fehl*. *Fehler triggern* → *Fehler auslösen*. The verb tables above target this.
2. **Calque (compound nouns, collocations, idioms):** translating English word-by-word when the loanword or a different German structure is canonical. *Wurzelursache* → *Root Cause*. *blockiert auf* → *wartet auf*. The calque tables above target this.
3. **Amtsdeutsch over-polish:** fleeing both traps into stiff officialese (*Datenbestand*, *Es handelt sich um*, Funktionsverbgefüge, passive chains). The table above targets this.
4. **Translating what has to stay literal:** field names, API values, flags and status constants are quoted material, not vocabulary — rendering `CLEAN` as *FERTIG* names a state the system never emits. „Identifiers are values, not vocabulary“ above targets this, together with its twin, inventing a term (*Torlage*, *Intent-Defekt*) where a plain description would do.

All four disciplines apply simultaneously. The first three form a chain of over-correction: writers who absorb only the first drift into the second, and those who absorb the first two drift into the third. The fourth is independent of that chain — it catches writers who have learned to translate well and then translate something that was never language to begin with.

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
