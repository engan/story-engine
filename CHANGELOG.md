# Changelog

Alle vesentlige, brukersynlige og driftskritiske endringer i dette prosjektet dokumenteres her.

Formatet er inspirert av *Keep a Changelog*. Story Engine bruker datert
releasehistorikk der semantisk versjonering ikke er praktisk.

> Retrospektiv notis: Perioden februar-juli 2026 ble etterfylt 2026-07-06
> basert på git-historikk og README-snapshots. Dette er en kuratert
> releasehistorikk, ikke en linje-for-linje commit-indeks. Bruk `git log` for
> komplett teknisk commit-spor.

## [Unreleased]

- Ingen åpne release-notes er samlet her ennå.

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
- Audio/radio-prosjekter kjører initial Final Quality Pass før TTS/radio-medier bygges.
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
