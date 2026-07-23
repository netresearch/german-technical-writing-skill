# Technical Lexicon — Preferred German Forms

Table of technical terms with gender, preferred form, and usage notes. Use this when you need to pick between two candidate phrasings for a concept.

## How this list is organized

- **EN term** — the English concept
- **DE form** — preferred form with article (where noun)
- **Register** — *accepted Denglisch loanword* (use as-is), *native German* (preferred in formal writing), *both* (either works)
- **Notes** — gotchas, gender, pluralization

## Exceptions & Error Handling

| EN | DE | Register | Notes |
|---|---|---|---|
| exception | die Exception | accepted loanword | plural: *die Exceptions*. Never *der/das Exception*. |
| throw | werfen | native | "eine Exception werfen" — canonical. *schmeißen* is colloquial. |
| catch | abfangen | native | "eine Exception abfangen". Never bare *fangen*. |
| re-throw | erneut werfen / rethrow | both | *rethrow* acceptable in code comments. |
| stack trace | der Stacktrace | accepted loanword | plural: *die Stacktraces*. |
| runtime error | der Laufzeitfehler | native | preferred over *Runtime Error*. |
| compile error | der Kompilierfehler | native | *Kompilierungsfehler* also correct but longer; *Compile-Fehler* accepted colloquially. |
| type error | der Typfehler | native | preferred. |
| null pointer | der Nullpointer / NullPointerException | both | when quoting the Java exception, use the loanword. |
| fatal error | der fatale Fehler / der schwerwiegende Fehler | native | *fataler Fehler* is dominant. |

## Tests

| EN | DE | Register | Notes |
|---|---|---|---|
| test | der Test | both | plural: *die Tests*. Never *die Test* (feminine is wrong). |
| unit test | der Unit-Test | accepted | plural: *die Unit-Tests*. Hyphen preferred. |
| integration test | der Integrationstest | native | no hyphen; *der Integration-Test* also seen. |
| functional test | der Funktionstest | native | |
| end-to-end test / e2e test | der End-to-End-Test / der E2E-Test | accepted | |
| fixture | die/das Fixture | accepted | plural: *die Fixtures*. Gender split (*das* by analogy with *das Feature*); pick one per text. |
| mock | der Mock | accepted | verb: *mocken*. |
| stub | der Stub | accepted | plural: *die Stubs*. |
| spy | der Spy | accepted | plural: *die Spys / die Spies*. |
| assertion | die Assertion | accepted | plural: *die Assertions*. |
| test passes | der Test läuft durch / ist grün / geht durch | native | never *der Test passt*. Not *der Test besteht* — subjectless *bestehen* reads as "the test exists"; the code under test *besteht* the tests (*der Code besteht die Tests*), the test itself *läuft durch*. |
| test fails | der Test schlägt fehl | native | *fällt durch* is colloquial. Written: *schlägt fehl*; chat: *failt* is widespread and tolerable there. |
| skip | überspringen / skippen | both | written: *überspringen*; chat: *skippen*. |
| test coverage | die Testabdeckung / die Test Coverage | both | |
| regression | die Regression | accepted | plural: *die Regressionen*. |
| flaky | flaky / instabil / unzuverlässig | both | *flaky* dominant in team chat; *wackelig* colloquial. NEVER *flatterhaft* — that describes a fickle person, not a test. |

## Version Control & Git

| EN | DE | Register | Notes |
|---|---|---|---|
| commit (noun) | der Commit | accepted | plural: *die Commits*. |
| commit (verb) | committen | accepted | *einchecken* is dated. |
| branch | der Branch | accepted | plural: *die Branches*. |
| merge (noun) | der Merge | accepted | |
| merge (verb) | mergen / zusammenführen | both | |
| rebase (noun+verb) | der Rebase / rebasen | accepted | |
| cherry-pick | cherry-picken / übernehmen | both | |
| squash | squashen / zusammenfassen | both | |
| revert (verb) | reverten / zurücknehmen / rückgängig machen | both | |
| rename (noun) | der Rename / die Umbenennung | both | *Rename* widely accepted. |
| rename (verb) | umbenennen / renamen | both | written: *umbenennen*; chat: *renamen*. |
| pull request / MR | der Pull Request / der PR / der Merge Request / der MR | accepted | masculine — *Request* is *der* (never *die Merge Request*). **In git.netresearch.de always use MR / Merge Request** (per team convention). |
| push | pushen | accepted | |
| pull | pullen | accepted | *abholen* reads as translation German — devs say *pullen*. |
| fetch | fetchen | accepted | same — *abholen* uncommon in dev speech. |
| checkout | auschecken / auf X wechseln | both | *auf X wechseln* most native; *checkouten* clunky, avoid. |
| diff | der Diff | accepted | |
| conflict | der Konflikt | native | |
| reset | der Reset / zurücksetzen | both | |
| blame | git blame (Tool-Name) | accepted | *ein git blame machen* / *git-blamen*. Never bare *blamen* — collides with *sich blamieren* (to embarrass oneself). |

## CI / CD / Build

| EN | DE | Register | Notes |
|---|---|---|---|
| pipeline | die Pipeline | accepted | plural: *die Pipelines*. |
| build (noun) | der Build | accepted | plural: *die Builds*. |
| deploy (noun) | das Deployment / der/das Deploy | accepted | gender of *Deploy* unstable — both attested; pick one per text. |
| deploy (verb) | deployen / ausrollen | both | |
| apply (verb) | ausrollen / anwenden / ausführen | native | Terraform/CI: *den Plan ausrollen*. NOT *applyen* / *ich applye*. |
| apply (noun) | der Apply / der Apply-Job | accepted | the CI job. plural: *die Applies* / *die Apply-Jobs*. |
| rollout | der Rollout / die Ausrollung | accepted | *Rollout* dominant. |
| rollback | der Rollback | accepted | |
| staging | das Staging / die Staging-Umgebung | accepted | |
| production | die Produktion / die Produktivumgebung / Prod | native | |
| release (noun) | das Release / die Veröffentlichung | both | |
| release (verb) | releasen / veröffentlichen | both | |
| hotfix | der Hotfix | accepted | |
| patch | der Patch | accepted | |
| feature flag | das Feature Flag / der Feature-Schalter | accepted | |
| canary | das Canary-Release / das Canary-Deployment | accepted | standalone *das Canary* uncommon — use the compound. |
| smoke test | der Smoke-Test | accepted | |

## HTTP / APIs

| EN | DE | Register | Notes |
|---|---|---|---|
| request | der Request | accepted | plural: *die Requests*. |
| response | die Response | accepted | plural: *die Responses*. |
| endpoint | der Endpoint / der Endpunkt | both | |
| payload | die/das Payload | accepted | gender unstable — *die* (die Nutzlast) at least as common as *das*; pick one per text. |
| header | der Header | accepted | |
| body | der Body | accepted | |
| query param | der Query-Parameter | accepted | |
| status code | der Statuscode | native | |
| timeout | das Timeout / der Timeout | accepted | gender unstable; *das* more common. |
| retry | der Retry / der erneute Versuch | both | |
| rate limit | das Rate Limit / die Drosselung | accepted | |

## Frontend / UI

| EN | DE | Register | Notes |
|---|---|---|---|
| component | die Komponente | both | native preferred; as loanword *die Component* (feminine like *die Komponente*). |
| render | rendern | accepted | |
| hook | der Hook | accepted | |
| state | der State / der Zustand | both | React-Kontext: *State*; allgemein: *Zustand*. |
| prop | die Prop | accepted | |
| event | das Event / das Ereignis | both | |
| listener | der Listener / der Zuhörer | accepted | *Zuhörer* too literal. |
| callback | der Callback / die Rückruffunktion | accepted | |
| selector | der Selector / der Selektor | both | |
| layout | das Layout | accepted | |
| template | das Template / die Vorlage | both | |

## Data / Persistence

| EN | DE | Register | Notes |
|---|---|---|---|
| database | die Datenbank | native | |
| query | die Query / die Abfrage | both | |
| migration | die Migration | accepted | |
| schema | das Schema | accepted | |
| index | der Index | accepted | |
| cache | der Cache | accepted | |
| cache invalidation | die Cache-Invalidierung | native | |
| transaction | die Transaktion | native | |
| rollback (DB) | der Rollback | accepted | |
| commit (DB) | der Commit | accepted | |
| session | die Session / die Sitzung | both | |
| token | der/das Token | accepted | both widespread (*das Token* very common in auth contexts); pick one per text. |
| serialize | serialisieren | native | |
| deserialize | deserialisieren | native | |

## Architecture / Patterns

| EN | DE | Register | Notes |
|---|---|---|---|
| service | der Service | accepted | |
| controller | der Controller | accepted | |
| provider | der Provider | accepted | |
| decorator | der Decorator / der Dekorator | both | |
| wrapper | der Wrapper | accepted | |
| factory | die Factory | accepted | |
| repository | das Repository | accepted | |
| interface | das Interface / die Schnittstelle | both | |
| abstract | abstrakt | native | |
| inheritance | die Vererbung | native | |
| composition | die Komposition | native | |
| dependency | die Abhängigkeit / die Dependency | both | native usually preferred in formal docs. |
| injection | die Dependency Injection / die Injektion | accepted | verb: *injizieren*. Never *das Injecten*. |
| refactoring | das Refactoring | accepted | *Refaktorierung* sounds bureaucratic. |
| bug | der Bug | accepted | |
| feature | das Feature | accepted | |
| ticket / issue | das Ticket / das Issue | accepted | |
| roadmap | die Roadmap | accepted | |

## Common verbs — technical register

| EN | DE | Notes |
|---|---|---|
| to execute | ausführen | "Code ausführen", "Befehl ausführen" |
| to run (tests/code) | ausführen / laufen lassen | |
| to invoke | aufrufen | |
| to validate | validieren / prüfen | |
| to parse | parsen | accepted loanword |
| to serialize | serialisieren | |
| to configure | konfigurieren | |
| to initialize | initialisieren | |
| to instantiate | instanziieren / erzeugen | |
| to override | überschreiben | |
| to implement | implementieren | |
| to extend | erweitern | |
| to refactor | refactoren / umgestalten | |
| to debug | debuggen | |
| to profile | ein Profiling machen / profilieren (Messung) | bare *profilen* is awkward (collides with *sich profilieren*); usually rephrased via the noun. |
| to optimize | optimieren | |
| to deprecate | deprecaten / als deprecated markieren | *als veraltet markieren* reads as stiff paraphrase in dev register — keep the loanword. |
| to document | dokumentieren | |

## Articles for ambiguous loanwords

These get mistakes most often. Fix the article first:

- **der** Commit, **der** Rebase, **der** Merge, **der** Branch, **der** Build, **der** Bug, **der** Fix, **der** Patch, **der** Hook, **der** Mock, **der** Stub, **der** Wrapper, **der** Decorator, **der** Provider, **der** Service, **der** Controller, **der** Header, **der** Callback, **der** Listener, **der** State, **der** Request, **der** Merge Request, **der** Endpoint, **der** Cache, **der** Index, **der** Retry, **der** Apply, **der** Apply-Job, **der** Stack-Frame
- **die** Pipeline, **die** Exception, **die** Assertion, **die** Response, **die** Session, **die** Migration, **die** Query, **die** Prop, **die** Factory, **die** Komponente, **die** Schnittstelle, **die** Callsite, **die** Baseline
- **das** Interface, **das** Feature, **das** Event, **das** Ticket, **das** Issue, **das** Template, **das** Deployment, **das** Staging, **das** Logging, **das** Monitoring, **das** Framework, **das** Caching, **das** Routing, **das** Rendering, **das** Refactoring, **das** Repository, **das** Schema
- Genuinely unstable — both attested, pick one and stay consistent within a text: **der/das** Timeout, **der/das** Token, **der/das** Deadlock, **der/das** Deploy, **die/das** Payload, **die/das** Fixture, **der/das** Breaking Change

Morphology shortcut: *-ing*/*-ment* nominalizations are always **das** (das Refactoring, das Deployment, das Logging); person nouns take natural gender (der/die Admin).

## Plural & case of loanwords

- Default plural is *-s*: die Commits, die Branches, die Deployments.
- *-y* just takes *-s*, no y→ies: die Proxys, die Librarys (or use *die Libraries* as full English plural — never mix).
- *-er* loans follow the German zero plural: die Server, die Manager, die Listener (never *die Servers*).
- Loanwords inflect like German nouns: *des Servers*, *auf diesen Servern*, *dem Branch*.
- Genitive: plain *-s* where valid (*des Commits*, *des Builds*); never an English apostrophe-s (*Sebastians Branch*, not *Sebastian's Branch*).

## Debugging / Postmortem / Analysis

These are the terms most prone to the calque-overcorrection trap. Native German engineers say all of these as English loanwords; translating them produces DeepL-output that no developer would speak.

| EN | DE | Register | Notes |
|---|---|---|---|
| root cause | die Root Cause | accepted loanword | NEVER *Wurzelursache* (calque) or *Hauptursache* (works in formal text but uncommon in dev). Postmortems, code reviews, Jira: *Root Cause* verbatim. Plural: *die Root Causes*. |
| root-cause analysis | die Root-Cause-Analyse | accepted | Hyphenated compound. *Wurzelursachen-Analyse* is wrong. |
| caller | der Caller | accepted | Stack-trace + debugging context. *Aufrufer* technically correct but stilted in dev jargon. |
| callsite / call site | die Callsite / die Aufrufstelle | both | feminine (*die Website*, *die Stelle*). Loanword dominant; native form acceptable in formal docs. |
| call stack | der Call Stack / der Aufruf-Stack | both | |
| stack frame | der Stack-Frame | accepted | masculine — *der Frame* (der Rahmen). |
| edge case | der Edge Case | accepted loanword | NEVER *Randfall* in software-engineering register. *Randfall* belongs to math/stats. Plural: *die Edge Cases*. |
| corner case | der Corner Case | accepted | Same logic as Edge Case. |
| code path | der Code-Pfad | accepted | *Ausführungspfad* possible but uncommon. |
| hot path | der Hot Path | accepted | Performance-Kontext; loanword only. |
| happy path | der Happy Path | accepted | Already in `anti-patterns.md`. |
| code path / execution path | der Code-Pfad | accepted | |
| race condition | die Race Condition | accepted loanword | NEVER *Wettlaufbedingung* (academic-CS textbook). |
| deadlock | der/das Deadlock | accepted | gender unstable, *der* at least as common (*einen Deadlock*). NEVER *Verklemmung*. |
| memory leak | das Memory Leak | accepted | NEVER *Speicherleck*. |
| stack overflow | der Stack Overflow | accepted | NEVER *Stapelüberlauf*. |
| garbage collection | die Garbage Collection / GC | accepted | NEVER *Müllabfuhr*. *Speicherbereinigung* is academic. |
| heap | der Heap | accepted | NEVER *Haldenspeicher*. |
| thread | der Thread | accepted | NEVER *Faden*. |
| trace | der Trace | accepted | |
| trace logging | das Trace-Logging | accepted | |
| stack trace | der Stacktrace / der Stack-Trace | accepted | Already in Exceptions section. |
| reproducer / repro | der Reproducer | accepted | NEVER *Reproduktionsbeispiel*. *Repro* rare in German dev speech, gender unsettled — prefer *Reproducer*. |
| postmortem | das Postmortem | accepted | |
| breaking change | das Breaking Change / der Breaking Change | accepted | Gender unstable; both attested. NEVER *brechende Änderung*. |
| dry-run | der Dry-Run | accepted | NEVER *Trockenlauf* (mechanical-engineering term). |
| smoke test | der Smoke-Test | accepted | Already in CI/CD section. |
| diff | der Diff | accepted | Already in VCS section. |
| flag (boolean attribute) | das Flag | accepted | NEVER *die Flagge*. |

### Calque check

Before writing a German compound noun in tech prose, ask: *would I say this German word out loud in a code review with a German-speaking team?* If the answer is "no, I'd say the English term," keep the loanword. The litmus test isn't dictionary existence — Duden has translations for nearly everything. The test is everyday-engineering-speech use.

## When no entry exists

If a term isn't here:

1. Check whether it's in the Duden online (duden.de) — if yes, use that gender/spelling
2. Check how the Microsoft German Style Guide handles it
3. If still unclear, prefer the native German form in written text, the loanword in chat
4. If truly ambiguous, ask the user
