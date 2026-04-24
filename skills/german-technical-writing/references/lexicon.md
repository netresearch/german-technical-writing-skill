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
| compile error | der Kompilierungsfehler | native | *Compile-Fehler* accepted colloquially. |
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
| fixture | die Fixture | accepted | plural: *die Fixtures*. |
| mock | der Mock | accepted | verb: *mocken*. |
| stub | der Stub | accepted | plural: *die Stubs*. |
| spy | der Spy | accepted | plural: *die Spys / die Spies*. |
| assertion | die Assertion | accepted | plural: *die Assertions*. |
| test passes | der Test besteht | native | never *der Test passt*. |
| test fails | der Test schlägt fehl / fällt durch | native | never *der Test failt*. |
| skip | überspringen / skippen | both | written: *überspringen*; chat: *skippen*. |
| test coverage | die Testabdeckung / die Test Coverage | both | |
| regression | die Regression | accepted | plural: *die Regressionen*. |
| flaky | flaky / instabil / flatterhaft | both | *flaky* dominant in team chat. |

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
| pull request / MR | der Pull Request / der PR / der MR / die Merge Request | accepted | **In git.netresearch.de always use MR / Merge Request** (per team convention). |
| push | pushen | accepted | |
| pull | pullen / abholen | both | |
| fetch | fetchen / abholen | both | |
| checkout | auschecken / checkouten / auf X wechseln | both | *auf X wechseln* most native. |
| diff | der Diff | accepted | |
| conflict | der Konflikt | native | |
| reset | der Reset / zurücksetzen | both | |
| blame | blamen / blame (Tool-Name) | accepted | usually just *git blame* as tool-call. |

## CI / CD / Build

| EN | DE | Register | Notes |
|---|---|---|---|
| pipeline | die Pipeline | accepted | plural: *die Pipelines*. |
| build (noun) | der Build | accepted | plural: *die Builds*. |
| deploy (noun) | das Deploy / das Deployment | accepted | |
| deploy (verb) | deployen / ausrollen | both | |
| rollout | der Rollout / die Ausrollung | accepted | *Rollout* dominant. |
| rollback | der Rollback | accepted | |
| staging | das Staging / die Staging-Umgebung | accepted | |
| production | die Produktion / die Produktivumgebung / Prod | native | |
| release (noun) | das Release / die Veröffentlichung | both | |
| release (verb) | releasen / veröffentlichen | both | |
| hotfix | der Hotfix | accepted | |
| patch | der Patch | accepted | |
| feature flag | das Feature Flag / der Feature-Schalter | accepted | |
| canary | das Canary / das Canary-Release | accepted | |
| smoke test | der Smoke-Test | accepted | |

## HTTP / APIs

| EN | DE | Register | Notes |
|---|---|---|---|
| request | der Request | accepted | plural: *die Requests*. |
| response | die Response | accepted | plural: *die Responses*. |
| endpoint | der Endpoint / der Endpunkt | both | |
| payload | das Payload | accepted | |
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
| component | die Komponente / das Component | both | native preferred. |
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
| token | der Token | accepted | |
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
| injection | die Injektion / das Injecten | accepted | |
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
| to profile | profilen / das Profiling durchführen | |
| to optimize | optimieren | |
| to deprecate | als veraltet markieren / deprecaten | |
| to document | dokumentieren | |

## Articles for ambiguous loanwords

These get mistakes most often. Fix the article first:

- **der** Commit, **der** Rebase, **der** Merge, **der** Branch, **der** Build, **der** Bug, **der** Fix, **der** Patch, **der** Hook, **der** Mock, **der** Stub, **der** Wrapper, **der** Decorator, **der** Provider, **der** Service, **der** Controller, **der** Token, **der** Header, **der** Callback, **der** Listener, **der** State, **der** Request, **der** Endpoint, **der** Cache, **der** Index, **der** Timeout (or *das*), **der** Retry
- **die** Pipeline, **die** Exception, **die** Fixture, **die** Assertion, **die** Response, **die** Session, **die** Migration, **die** Query, **die** Prop, **die** Factory, **die** Komponente, **die** Schnittstelle
- **das** Interface, **das** Feature, **das** Event, **das** Ticket, **das** Issue, **das** Template, **das** Deployment, **das** Staging, **das** Logging, **das** Monitoring, **das** Framework, **das** Caching, **das** Routing, **das** Rendering, **das** Payload, **das** Refactoring, **das** Repository, **das** Schema

## When no entry exists

If a term isn't here:

1. Check whether it's in the Duden online (duden.de) — if yes, use that gender/spelling
2. Check how the Microsoft German Style Guide handles it
3. If still unclear, prefer the native German form in written text, the loanword in chat
4. If truly ambiguous, ask the user
