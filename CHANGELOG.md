# Changelog

Alle vesentlige, brukersynlige og driftskritiske endringer i dette prosjektet dokumenteres her.

Formatet er inspirert av *Keep a Changelog*. Story Engine bruker datert
releasehistorikk der semantisk versjonering ikke er praktisk.

> Retrospektiv notis: Perioden februar-juli 2026 ble etterfylt 2026-07-06
> basert på git-historikk og README-snapshots. Dette er en kuratert
> releasehistorikk, ikke en linje-for-linje commit-indeks. Bruk `git log` for
> komplett teknisk commit-spor.

## [Unreleased]

### Documentation
- README og den kuraterte releasehistorikken er ajourført gjennom juli 2026,
  med en egen seksjon for produksjonsendringene som ble committet 1. august.

---

## [2026-08-01] - Produksjonsruter, Radio Play og lokal v2-aktivering

### Added
- Radio Play fikk en delt, språkagnostisk narrator-kontrakt som normaliserer
  vanlige fortelleraliaser uten å slå sammen eksplisitt navngitte karakterer.
- Casting og voice preview fikk tydeligere kanonisk forteller, rolleveiledning og
  smoke-dekning for alias-dedupe, navngitte turer og TTS-stemmefordeling.
- En aktiv implementeringsplan ble lagt til for å gjøre Final Quality Pass helt
  profil-uavhengig før media, med quality gate, lineage og billing-recovery uten
  å endre video-/website-tekstmarkering.

### Changed
- Gemini 3.1 Flash TTS-planen ble arkivert etter produksjons-smoke av 2.5 Pro
  TTS, tidligere 3.1 Flash TTS-variantbruk, preview-lyd og Dashboard-metrikk.
- Planlegging, source harvest og støtteoperasjoner bruker Gemini 3.6 Flash;
  Gemini 3 Flash er fjernet fra aktive produksjonsruter etter utvidet evaluering.
- Final Review bruker GPT-5.6 Terra/`high` og Final Revision GPT-5.6 Luna/`xhigh`.
  Flag-off recovery holder seg i GPT-5.6-familien, mens GPT-5.4 og GPT-5.5 er
  deaktivert som runtime-, fallback- og rollback-ruter.
- Kvalifiserte førstegenereringer med illustrasjoner eller lyd kan utsette media
  til den review-first text-first-kjeden er ferdig, slik at media bygges fra den
  ferdigstilte teksten. Profil-/serverkrav gjelder fortsatt.
- Local Persistence V2 ble aktivert som standard på `localhost` og
  `story.neoweb.no` etter juli-hardening og produksjonsreadback.
- Modellpromotering krever nå dokumentert incumbent/candidate-evaluering,
  kvalitet/source/contract-gater, kost/latens/billing-kontroll og testet recovery.

### Fixed
- Local media attention ble gjort mindre påtrengende og mer handlingsrettet;
  brukbare medier vises grønt, mens manglende, ufullstendige og stale medier
  forklares i detaljpanelet fremfor gjentatte globale varsler.
- Legacy lokale utkast forblir synlige i read-only recovery etter New Project og
  refresh til brukeren laster ned backup eller rydder dem eksplisitt.
- Production Report summerer logiske TTS-jobber fra den autoritative parent-raden
  uten å dobbelttelle de underliggende provider-segmentene.

---

## [2026-07-31] - Modellreadiness, persistence-verktøy og prisgrunnlag

### Added
- Local Persistence V2 fikk prosjektindikatorer, trygg lokal backup/restore,
  eksplisitt cleanup av media og hele prosjektdata samt IndexedDB-transaksjonstester.
- Gemini 3.6- og GPT-5.6-canarymetadata ble bevart gjennom navigasjon og gjort
  fail-closed ved arm-/readback-mismatch.
- Gjentakende karakterer fikk sterkere visuelle identity anchors på tvers av
  cover- og seksjonsbilder.

### Changed
- GPT-5.6 provider-priser, Final Review/Revision-kreditter og OpenAI image-priser
  ble oppdatert for korrekt margin- og Production Report-grunnlag.
- Source harvest fikk rikere evidence-metadata og tydeligere dekning/readback før
  videre Gemini 3.6-evaluering.
- Prosjekt- og dokumentflater fikk jevnere framing, spacing, sideikoner og
  tydeligere tomtilstand når et kvalitetspass ikke finnes.

### Fixed
- Final Revision fikk strengere synlig ordgrense, bedre omission detection,
  bevaring av diagrammer/kilder og kontrollert Luna `xhigh -> high` recovery
  etter bekreftet timeout.
- Lav kredittsaldo stopper planlegging før nye betalte provider-kall og forklarer
  hvordan en bevart pause kan gjenopptas.

---

## [2026-07-23] - Local-first fundament, GPT-5.6 canary og billing recovery

### Added
- Local Persistence V2 etablerte owner/project-scoped IndexedDB-records,
  separate Blob-medier, content hashes, writer lease, atomiske checkpoints,
  safe resume, storage health og read-only legacy recovery bak rollout-gaten.
- GPT-5.6 Terra/Luna fikk separate eval-/canary-armer, observability,
  sikkerhetsidentifikatorer og eksplisitte globale promotion-gates.
- Billing reconciliation fikk kø, pending-varsel og atomisk resolution for
  providerutfall som ikke kan bekreftes sikkert i samme forespørsel.

### Changed
- Den uvirksomme `Registry Publish Control`-flaten, API-et, Edge Function-en og
  tabellene ble fjernet. Modellkatalogen er fortsatt beskrivende pris-/statusdata,
  men kan ikke fremstilles som en produksjonsbryter.
- Annual subscriptions fikk månedlig refill av inkluderte credits, mens kjøpte
  credits bevares når et abonnement avsluttes.

### Fixed
- Final quality output-kontrakter, aktiv reasoning effort og timeout-recovery ble
  strammet inn uten å svekke structured outputs eller kildebevaring.

---

## [2026-07-17] - Logiske TTS-jobber og evidence-hardening

### Added
- TTS fikk én idempotent reserve/finalize-livssyklus per logisk jobb, separate
  child-segmenter, observerte varigheter, tegnproxy og usage-/rapport-scope.
- TTS-batching fikk en eksplisitt plan for providergrenser, Radio Play-turer,
  segmentering, retry og kredittestimat.
- Bildegenerering fikk målrettet Image Fact QA med validering, korrigering og
  inkludert sluttpass uten ekstra kundekreditter.

### Changed
- Deep research/source harvest fikk strengere provenance, coverage, source
  boundaries, non-fiction-metode og kildeanskaffelse før final quality.
- Prosjektets TTS-usage bevares og forsones i rapporter på tvers av save/load.

### Fixed
- Grounded seksjonsgenerering fikk bounded timeout under Supabase-grensen og
  tydelig pause når providerutfallet er ukjent, fremfor automatisk å duplisere
  et mulig betalt kall.
- Svake eller utdaterte image/source-fallback-kontrakter feiler lukket, mens
  explainer-kvalitet og gyldige eksisterende medier bevares.

---

## [2026-07-06] - Variant, eksportlesbarhet og lanseringsvern

### Added
- README fikk språk- og objektagnostiske badges, oppdatert variant-/eksportstatus og månedlig changelog-inndeling.
- Stripe live-mode gates, eksplisitte public app origins, QR-login origin config og Vercel security headers ble lagt til som lanseringsvern.

### Changed
- Språkvarianter som bevarer kildegrunnlag og evidenskontrakt kan arve `strong`/baseline-lagret Final Review-status fra kildeprosjektet og lagres som publiseringsklare egne prosjekter.
- `ai-translate-plan` parser flere JSON-kandidater og response-parts, tåler vanlige JSON-artefakter og retryer streng JSON før feltvis fallback brukes.
- Cover og seksjonsbilder for språkvarianter regenereres med valgt skriftspråk når språkbytte faktisk krever nye visuelle leveranser.
- Audio-only-varianter kan oppdatere samme prosjekt uten å regenerere eller miste eksisterende seksjonsbilder når `Illustrations` ikke er valgt.
- Variant add-on preflight skiller script-line hard minimum fra anbefalt buffer for audio-estimat.
- Dashboard Recent Activity grupperer ledger-hendelser fra et dypere usage-vindu slik at tette media-batcher ikke skjuler historikken.

### Fixed
- PDF/DOCX-eksport normaliserer Mermaid SVG-tekst per node før PNG-rendering, slik at diagrammer med blandede lyse og mørke noder forblir lesbare.
- Variant-mediaflyten fikk bedre repair/missing-media-håndtering og guard mot partial reused audio.

---

## [2026-06-30] - Evidence, quality, public routes og monitoring

### Added
- Public routes for `/faq`, `/pricing`, `/privacy`, `/terms` og `/cookies` ble lagt til med samme designlinje som landingssiden.
- Monitoring fikk `Quality Queue V1`, en lazy-loaded adminflate for read-only kvalitetskandidater med deterministisk `risk_score`, bounded vindu og paginering.
- En objektagnostisk trusted source authority registry ble lagt til for offisielle, statistiske, helse-, standard- og fact-check-kilder.
- Source authority registry og source repair fikk egne eval-/smoke-sjekker.

### Changed
- `Upload Files`, `Final Quality Pass` og kreditt-preflight fikk kortere og mer lesbare hjelpetekster i Simple og Custom.
- `ai-analyze-file` fikk en generell high-stakes media guard for bilde, lyd og video.
- Utkast med ulukket kildestatus kan vise samme lokaliserte kildestatus-varsel i workspace preview og eksporterte formater.
- Export warning-tekstene ble flyttet til delt i18n-lag.
- `Repair Sources` kan forsøke å finne sterkere kilder for QA-gap før revisjon, bære ulukkede gap inn i revisjonsflyten og kvalifisere dem før ny review.
- Quality Autopilot ble hardnet med `strong_stop`, scoped revise, staged long-document execution, guarded broad fallback, post-review, `qualityChain`-metadata og eksplisitte stop reasons.
- Kvalifiserte audio/radio-førstegenereringer kan kjøre initial Final Quality Pass før TTS/radio-medier bygges.
- Imagen 4-IDer ble migrert til Gemini image-kompatibilitetsaliaser for gamle prosjekter.
- Prosjektbadges, stale publication warnings, source display titles, URL-labels og high-assurance source repair ble kalibrert uten emne- eller domenespesifikk hardkoding.

### Fixed
- Mermaid-rendering i website/export ble stabilisert med lokal Mermaid-asset og bedre kontrast uten å tvinge website-diagrammer til PNG der det ikke trengs.
- Source repair- og evidence-prune-flyter fikk bedre guards mot stale metadata, gjentatte repair-looper og usikre fallback-stater.
- Export href-sanitization og workspace markdown-tabeller ble strammet inn.

---

## [2026-05-30] - Simple start, verified sources, billing og model monitoring

### Added
- `Simple` startmodus ble lagt til for førstegenerering, med skjulte avanserte kontroller og automatisk `Suggest Settings` ved `Create Project`.
- `Model & Pricing` i Monitoring viser provider-katalog, server registry, credit value, registry publish control, pricing simulator, model catalog, mismatch findings og flow-matrise.
- Website-zip pakker lokale Mermaid- og KaTeX-assets med stabile filnavn og lisensnotis.
- TXT-eksporten skiller mellom kundevendt kreditt-/ledger-rapport og admin-only intern produksjonsrapport.

### Changed
- Seksjonsvis post-check ble pensjonert til fordel for review-first quality gate, targeted/broad revision, QA Memo, QA-historikk, review-delta og QA-prefilled revise-briefs.
- `ai-plan` normaliserer Core Idea-URL-er, opplastede dokumenter, Google Search-kilder og produkt-/konfiguratorlenker til én kildepool.
- `ai-plan` produserer rik `verifiedCitations`-metadata med source tiers, safe-fetch/SSRF-beskyttelse, bounded reads, soft404/mismatch-signaler og fallback til enkel citation-kontrakt.
- Story Engine-filen kan eksportere kildepool, faktakandidater, primary facts, rejected/conflict facts og source-backed status i frontmatter når fact-lock er aktiv.
- Offisielle kildesider kan bidra med `source_visual_references` til cover og seksjonsbilder.
- Betalte AI-flyter bruker reserve/commit/cancel, pricing snapshots, operation-gate metadata og replay-beskyttelse mot doble provider-kall.
- TTS-billing lagrer usage source, observert varighet der det er trygt, billed minutes og fallback til `character_proxy`.

### Fixed
- Verified source title handling, source link display og source ranking ble strammet inn.
- Runtime evidence og model registry mismatch-funn ble gjort mer presise.
- Vite dynamic import warnings og Mermaid app-shell preload-risiko ble redusert.

---

## [2026-04-30] - Revise, variants, visual references og usage ledger

### Added
- `Revise` ble samlet som primær flyt for tekstforbedring, med støtte for å oppdatere samme prosjekt eller lagre en revisjonsgren.
- `ai-translate-plan` og `ai-translate-markdown` etablerte server-side språkvariantflyt.
- Admin Users fikk prosjektvolum, review health, revision branches og siste prosjektaktivitet via paginert `ai-admin-user-projects`.
- Gemini 3.1 Flash TTS ble lagt til, med mer robust lang audio-segmentering.
- `gpt-image-2` og `gpt-image-2-hd` ble lagt til som hovedvalg for bildegenerering.
- Usage ledger og image credit reservations ble lagt til som grunnlag for mer presis produksjonsrapportering.

### Changed
- Lagret QA-memo og prioriterte tiltak kan prefylles i `Revise`.
- `Variant` fikk egen save-target-logikk og samme låste profil-kontrakt som importert Story Engine-fil.
- Prosjektkort og prosjektåpning ble komprimert og tydeliggjort med fargekodet status, bedre neste-steg-guidance og admin-skjult advanced mode.
- Core Idea-flyten for opplastede visuelle referanser ble mer robust.
- Final Review/Revision ble flyttet til GPT-5.5 medium som review-standard, med hybrid pricing defaults og provider-prising i Production Report.
- Prompt-, heuristikk- og normaliseringsgrunnlaget for Suggest Settings ble samlet i delt lag med fast-path, fallback og strengere genre-/opsjonsnormalisering.

### Fixed
- Final revision timeout- og batching-problemer ble redusert.
- Project cover image preservation, language auto-detection og selected section count i final review ble forbedret.
- Legacy daily TTS quota-tekst ble erstattet med kredittbasert billingtekst.

---

## [2026-03-31] - Final Review, Projects triage og quota monitoring

### Added
- Vertex quota monitor dashboard og `ai-quota-sync` ble lagt til.
- Admin workspace fikk quota health, final review memo og rikere subscription state.
- Dashboard fikk billing snapshots, billing status warnings, activity filters og review activity visibility.
- Projects fikk routing observability, import state, review-risk triage, saved QA memo snapshots, review-delta sammenligning, family navigation og operator guidance.
- Final Review fikk review lineage, round tracking, editorial memory, guided patch preview og seedede remake goals.
- Quota health alerting ble utvidet med Slack/email/dedup.

### Changed
- Billing v1 packages og subscription state ble låst tettere mot admin-/dashboardflater.
- Daglige request caps ble fjernet fra tekstflyter der kreditt-/billingmodellen er primær kontroll.
- Gemini quota failures og frontend edge-function requests fikk tydeligere feilhåndtering.
- Projects simple/advanced mode ble redesignet med bedre diagnostikk og collapsible panels.
- Section generation ble hardnet med bedre continuity, prompt diagnostics og runtime logging.

### Fixed
- Imported project state, routing import drift og legacy routing snapshots ble synliggjort i workspace og Projects.
- Cover generation timeout og image retry-håndtering ble forbedret.
- Final review timeout budget og review freshness states ble strammet inn.

---

## [2026-02-28] - Billing, QR login, grounding og export hardening

### Added
- Billing view, Stripe checkout/portal flows, credit packages og split mellom included/purchased credits ble lagt til.
- QR mobile authorization flow ble lagt til.
- Admin/dashboard credit health og monthly capacity display ble utvidet.
- Credit preflight warnings før skriving ble lagt til.
- Codex post-check edge function og non-fiction post-check flow ble lagt til som tidlig kvalitetsmekanisme.
- Practical-guides taxonomy, sub-options og section propagation ble lagt til.
- AI plan tuning presets og avansert source harvest/timeout tuning ble lagt til.
- Mermaid repair preview og apply-to-project flow ble lagt til.

### Changed
- Prompt source ble samlet på tvers av frontend og edge.
- Video-export ble migrert til MP4-default med 9:16-støtte og bedre video-/TTS-håndtering.
- Image model policy, image pricing og Gemini 3.1 Flash Image Preview-støtte ble oppdatert.
- Plan generation, grounding source harvest og citation handling ble hardnet mot timeout, hallucinerte URLs og proxy-URL-er.
- Dashboard Recent Activity ble utvidet og filtrerer bort irrelevante shadow events.
- Mermaid layout og export-responsivitet ble forbedret for preview, PDF, EPUB og PPTX.
- Character/arc labels og flere eksporttekster ble lokalisert.

### Fixed
- Insecure API key injection og client-side grounding fallback ble fjernet fra produksjonsflyt.
- Stripe, admin og QR login fikk bedre CORS/auth-håndtering.
- TTS-modellvalg, image fallback, cover retry, usage metrics persistence og project language display ble stabilisert.
- Mermaid parsing ble hardnet mot `End` node IDs, uavsluttede code blocks, subgraph-title overlap og falske auto-closures.
- Export links i PDF/EPUB fikk bedre wrapping og sources-kapittel.

---

## [2026-01-20] - Fase 3: kvoter og misbruksvern

### Added
- Nytt kvote- og brukssporingssystem med atomisk Postgres RPC for å forhindre race conditions.
- Rate limiting via Upstash Redis for anti-spam-beskyttelse, med graceful fallback hvis ikke konfigurert.
- Felles utilities i `_shared/utils.ts` for auth, allowlist, kvote-reservering og brukslogging.
- Database-migrasjon for `entitlements`, `usage_counters`, `usage_events`, RLS policies og RPC-ene `quota_reserve()`, `quota_finalize()` og `get_user_entitlements()`.

### Changed
- Alle daværende 9 Edge Functions ble refaktorert til pipeline: Auth -> Allowlist -> RateLimit -> Quota -> AI -> Finalize.
- Kvotetyper ble standardisert for request-, image- og TTS-bruk.

---

## [2026-01-10] - EPUB, PowerPoint og lydoptimalisering

### Added
- EPUB 3-eksport med strukturert `mimetype`, `container.xml`, `content.opf`, `nav.xhtml`, embedded cover/kapittelillustrasjoner og Mermaid-diagrammer rendret til PNG.
- PowerPoint-eksport for non-fiction med AI-oppsummerte bullet points, tittelslide, agenda, kapittelslides og dedikerte diagram-slides.

### Changed
- MP3-eksport for TTS-tale ble optimalisert til lavere bitrate for mindre filer.

---

## [2025-12-24] - Eksport, rendering og Suggest Prompt

### Added
- `Suggest Prompt`-knapp for å forbedre/utvide Core Idea direkte i Story Engine, med Undo.
- Interaktiv website-eksport som ZIP med navigasjon, mørkt tema og støtte for lyd/bilde.

### Changed
- Video-eksport fikk strukturert smart split/normalisering for å hindre tekstklumping og overlapp.
- Markdown-elementer som overskrifter, labels, lister, horisontale linjer, nested blockquotes, kodeblokker og tabeller fikk bedre video-rendering.
- TTS-løypen skiller bedre mellom taletekst og videotekst.

### Fixed
- Sitatblokker sluker ikke lenger påfølgende avsnitt i video-rendering.
- Render-pipelinen ble mer robust gjennom konsekvent tekstnormalisering.
