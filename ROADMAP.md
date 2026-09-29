# Story Engine Roadmap

Dette dokumentet beskriver fremtidig arbeid og prioriterte oppfølgingsspor for
Story Engine.

Roadmapen skal ikke være en liste over alt som allerede er levert. Ferdige
features, historiske beslutninger og release-notes ligger i `CHANGELOG.md`,
`README.md` og arkiverte planer under `docs/plans/archived/`.

Sist gjennomgått: 2026-09-29. Daterte produksjonsbevis og åpne unntak står i
[produktstatus](docs/operations/product-status.md); planene nedenfor eier
akseptansekriteriene. «Implementert», «deployet» og «akseptert» er ulike porter.

---

## Prinsipper

- Story Engine skal forbli språk-, land- og objektagnostisk.
- Roadmap-punkter skal beskrive gjenbrukbare produkt- eller driftskapabiliteter,
  ikke hardkode konkrete prosjekter, personer, land, steder eller temaer.
- Fullførte features skal ikke ligge som aktive roadmap-løfter.
- Operasjonelle runbooks kan være aktive uten at de er produkt-roadmap.
- Edge Function-deploy er bare relevant når tilhørende function-filer endres.

---

## Nåværende produktbaseline

Disse områdene regnes som levert og fjernes derfor fra aktiv roadmap:

- PDF, DOCX, PPTX, EPUB, TXT, website, audio og MP4-eksport.
- MP4 video med 16:9 og 9:16-format.
- Simple / Custom startmodus.
- Project save/load, Projects view, Revise og Variant-grunnflyt.
- Language variants med review-inheritance når evidenskontrakten bevares.
- Final Quality Pass / Final Review / targeted Revise som implementert
  hovedflyt; representativ Core-kvalitet er fortsatt under akseptanse.
- Evidence safety, fact-lock, source repair og verified source metadata som
  operative kvalitetsmekanismer.
- Dashboard, Billing, Monitoring, Model & Pricing og Quality Queue V1 som
  admin-/operatorflater.
- Public FAQ, pricing, privacy, terms og cookies routes.
- PDF/DOCX Mermaid-kontrastnormalisering.
- Bilde- og TTS-valg samt multimodal output-baseline. Sunburst er global
  bildestandard, med naturlig kvalitets-/kostobservasjon fortsatt åpen.

Se `CHANGELOG.md` for kurert historikk.

---

## Prioritet 1: Launch- og driftsklarhet

### Core-akseptanse for kildebasert Final Quality Pass

**Status:** historisk teknisk baseline 9/9; Core-A 0/4 og Core-B 0/2
komplette kvalitetsmålinger per 29. september. Core-C ordinær brukerflyt og
Core-D release-beslutning er åpne. R2/direct-source er av.

**Plan:** `docs/plans/active/final-review-closure-completeness-evidence-semantics-plan-2026-08-31.md`

**Neste steg:**

- Mål hosted Review-discovery etter deployet, providerfritt verifisert
  CPU-retting i én særskilt godkjent Case-1-kjøring. Siste betalte Case 1
  stoppet før Review-providerstart og er terminalt avstemt.
- Fullfør frosne Core-A/B-kvalitetsmålinger, source/evidence-audit,
  kost/oppgjør, save/reload og ordinær bruker-/rollback-kontroll.
- Behold 18-seksjoners støtte tilgjengelig; egen long-form-kvalitetstest er
  senere R&D og blokkerer ikke denne Core-beslutningen.

### Vertex / Gemini auth-key cleanup

**Status:** nøkkelmigrering avsluttet 16. september; Vertex fase 2 er aktiv
som plan, men ny produksjonscanary er gated.

**Planer:**

- `docs/plans/archived/gemini-auth-key-migration-plan-2026-06-19.md`
- `docs/plans/active/generativelanguage-to-vertex-phase2.md`
- `docs/plans/active/vertex-phase2-canary-runbook.md`
- `docs/plans/active/vertex-phase2-wave1-reentry-checklist.md`

**Hvorfor:** Redusere avhengighet til standard Gemini API keys, samle mer
produksjonstrafikk på Vertex/service-account-routing og ha trygg rollback per
funksjon.

**Neste steg:**

- Avklar hvilke gjenstående Gemini Developer API-flows som senere skal flyttes
  fra den fungerende auth-nøkkelen til Vertex.
- Frys gjeldende modell, prompt, provider og kost per operasjon før canary.
  Source Harvest og Source Repair har egne grunnings-/billingporter.
- Verifiser funksjonsvis rollback og skill providerbytte fra modellbytte.

### Paid launch margin og kreditt-økonomi

**Status:** aktiv launch-readiness
**Plan:** `docs/plans/active/subscription-included-credit-margin-launch-readiness-plan-2026-07-03.md`

**Hvorfor:** Før bred betalt lansering må inkluderte credits, top-ups,
providerkost, Stripe-fees, fallback/retry og margin kunne vurderes per tier og
operasjon.

**Neste steg:**

- Fullfør logisk operasjonskost, faktisk providerfaktura og kundekreditt-
  avstemming før pris- eller marginbeslutning.
- Definer hard stop/admin-review ved providerkost og avklar årsabonnement,
  tax/VAT og Stripe live-oppfølging i egne planer.
- Behandle rapportert margin som observasjon til datagrunnlaget er komplett.

### Supabase auth custom domain

**Status:** aktiv/pending operasjonell plan
**Planstatus:** lokal draftplan finnes, men er ikke versjonert i repoet ennå.

**Hvorfor:** Google-login bør vise et seriøst produktdomene i stedet for
Supabase project-ref hosten.

**Neste steg:**

- Velg endelig `auth.<produktdomene>` eller tilsvarende custom domain.
- Bekreft Supabase add-on, DNS-eierskap og Google OAuth callback-strategi.
- Behold gammel Supabase-host som bakoverkompatibel fallback.
- Verifiser login, session restore, Edge Functions, QR-login, billing og
  storage etter bytte.

---

## Prioritet 2: Kvalitet, evidens og modellvalg

### Final Quality Pass hardening

**Status:** implementert flyt, men representativ kilde-/kvalitetsakseptanse
føres i Core-sporet ovenfor. Operatørrutiner og regresjonsvern er løpende.

**Planer:**

- `docs/plans/active/final-review-operator-runbook.md`
- `docs/plans/archived/final-quality-pass-flat-revision-hardening-plan-2026-06-19.md`

**Hvorfor:** Final Quality Pass er levert, men publikasjonssensitive
review-/revision-flows må fortsette å ha regresjonsvern, evidence guards og
klare operatorrutiner.

**Neste steg:**

- Hold smoke-dekning for final quality, source repair og export warnings aktiv.
- Behandle nye reelle svikt som generiske mekanismeforbedringer, ikke som
  emne- eller landspesifikke patches.
- Oppdater runbooks når operatorflyten endres.

### Gemini 3.8 Flash og GPT-6 Sol/Luna

**Status:** kandidatspor under evaluering; ingen produksjonsbytte.
**Planer:**

- `docs/plans/active/gemini-3-8-flash-evaluation-migration-and-retirement-plan-2026-09-02.md`
- `docs/plans/active/gpt-6-sol-luna-review-revision-evaluation-plan-2026-09-23.md`
- `docs/plans/active/sak4-and-model-transition-review-2026-09-23.md`

**Hvorfor:** Produksjon bruker fortsatt Gemini 3.6/3.7/3.1 per operasjon og
GPT-5.6 Terra/Luna i Review/Revision. En nyere modell i katalogen er ikke en
godkjent serverrute.

**Neste steg:**

- Bekreft API-tilgang, kanonisk ID, pricing/caching og vilkår med Story Engines
  serveridentitet. Frys incumbent-input og kjør separate, kontrollerte
  sammenligninger for hver operasjon.
- Mål kvalitet, kilde-/kontraktssikkerhet, tid, feil, kost, kredittføring og
  recovery. Core-A baseline må være komplett før produksjonspromotering.
- Behold dagens ruter som testet rollback til resultat og eierbeslutning er
  dokumentert.

---

## Prioritet 3: Input- og research-utvidelser

### Social media link analysis

**Status:** backlog, høy produktverdi
**Plan:** `docs/plans/social-media-link-analysis-plan.md`

**Hvorfor:** `Analyze Link` bør kunne hente meningsfullt innhold fra offentlige
video- og sosiale lenker, ikke bare vanlige HTML-sider.

**Første bølge:**

- YouTube transcript extraction med tydelig fallback når captions mangler.
- X/Twitter oEmbed for enkel post-tekst.
- `sourceType` og metadata i responsen.

**Senere bølger:**

- Meta oEmbed hvis app-token og juridisk/operasjonelt oppsett er avklart.
- Gemini multimodal videoanalyse for korte offentlige videoer der tekst ikke er
  tilgjengelig.

### Category / genre taxonomy review

**Status:** backlog / reference plan
**Plan:** `docs/plans/category-genre-taxonomy-review-plan-2026-06-09.md`

**Hvorfor:** Dagens 158 kombinasjoner dekker mye, men intern metadata kan gi
bedre routing, evidence policy, source readiness og Final Review uten å legge
flere valg på normalbrukeren.

**Neste steg:**

- Legg til sidecar metadata for format, audience, risk, evidence posture og
  output intent.
- Vurder noen få høyverdige business-, research- og training-formater.
- Bevar aliases og bakoverkompatibilitet for eksisterende prosjekter.

---

## Prioritet 4: Brukeropplevelse og internasjonalisering

### UI localization / i18n

**Status:** draft / not started
**Plan:** `docs/plans/ui-localization-i18n-plan-2026-05-15.md`

**Hvorfor:** Story Engine skiller allerede mellom output language og UI language
i praksis, men app-UI er fortsatt stort sett hardkodet på engelsk.

**Neste steg:**

- Innfør key-basert UI-translation layer separat fra dokument-/export-labels.
- Start med `en` og `nb`.
- Legg UI language preference i konto/localStorage uten å overstyre output
  language.
- Migrer Workspace, Complete, Download, Projects, Review, Revise og Variant før
  dypere adminflater.

### Nedlastbar nettside og AI-design

**Status:** BASE print-/fokus-/kontrastretting deployet; ti historiske ZIP-er
statisk revalidert. Lokal `file://`-, offline-, print- og viewportakseptanse
og betalt AI-design er åpne.

**Plan:** `docs/plans/downloadable-website-design-plan-2026-09-01.md`

**Neste steg:**

- Godkjenn faktiske ZIP-er lokalt med tastatur, print og flere viewportbredder.
- Kjør AI-design bare etter separat kost- og kvalitetsport; bevar fungerende
  BASE-eksport som rollback.

### Visitor og product analytics

**Status:** later-track plan
**Plan:** `docs/plans/visitor-analytics-plan.md`

**Hvorfor:** Story Engine har sterk intern usage/billing-telemetri, men mangler
lettvekts trafikk- og produktfunnel-innsikt.

**Neste steg:**

- Hold visitor/product analytics separert fra `usage_events`.
- Vurder Plausible/Umami for traffic analytics.
- Bruk egen Supabase-tabell for produktanalytics hvis app-funnel skal spores.
- Start med få operatornyttige counters, ikke tung BI.

---

## Prioritet 5: Audio, media og nye produksjonsflater

### Enhanced Radio Play Audio

**Status:** kode og lokal mediekontrakt finnes; produksjonspilot er pauset.
Pilotbrytere og ordinær dialogue-only-atferd må avklares og verifiseres.

**Plan:** `docs/plans/active/lyria-radio-play-integration.md`

**Hvorfor:** Lyria, ambience, SFX og miks krever sluttlytting, trygg
produksjonskobling og korrekt mediegjenoppretting før bred bruk.

**Neste steg:**

- Avklar pilotflagg og miljø mens utviklingen er pauset.
- Verifiser ordinær brukersti, lydkvalitet, gjenopptakelse, eksport,
  lineage og kost før ny produksjonsaktivering.

### Gemini 3.8 TTS-migrering

**Status:** forberedelse; ingen produksjonsaktivering. Første kontrollkall
stoppet med HTTP 400 og ga ingen lydfil; årsak og faktisk fakturakost er åpne.

**Plan:** `docs/plans/active/gemini-3-8-tts-evaluation-migration-and-legacy-retirement-plan-2026-09-24.md`

**Neste steg:**

- Avklar request-/providerfeilen, faktisk pris, API-tilgang og isolert
  evalidentitet før ny betalt prøve.
- Sammenlign tale, varighet, språk, single-/multi-speaker, kost, billing,
  retry og eksport med dagens TTS-rute. Bevar 3.1 som eksplisitt rollback
  til migreringen er verifisert.

### Persistent media storage

**Status:** planned / later-track
**Plan:** `docs/plans/persistent-storage-strategy.md`

**Hvorfor:** Prosjekttekst og cover lagres i skyen, mens seksjonsbilder og lyd
fortsatt er lokale. Varig cloud-media må styres av kost, retention,
tier-politikk og on-demand lasting.

**Neste steg:**

- Behold media-persist som feature-flagget kapabilitet.
- Avklar storage retention per tier.
- Unngå at cloud-media blir et skjult kostsluk før pricing og quotas er klare.

### Video Studio / image-to-video

**Status:** long-term concept
**Plan:** `docs/plans/future-plan-video-music-generation.md`

**Hvorfor:** AI-video kan bli en fremtidig premiumflate, men krever
asynkron jobbstyring, storage, cost controls og moden API-kvalitet.

**Neste steg:**

- Vent på stabil API-tilgjengelighet, akseptabel kost per sekund og god nok
  karakter-/stil-konsistens.
- Ikke start før storage og video-credit/kostmodell er avklart.

---

## Prioritet 6: Operator- og evalverktøy

### Operator voice agent

**Status:** aktiv ideplan, ikke startet
**Plan:** `docs/plans/operator-voice-agent-plan-2026-05-21.md`

**Hvorfor:** En admin-only voice agent kan hjelpe founder/operator med demo,
produktstatus og roadmap-spørsmål uten å bli en normal sluttbrukerchat.

**Neste steg:**

- Velg realtime-provider via spike.
- Hold all tilgang admin-gated og protected.
- Ikke gi agenten direkte tilgang til secrets eller autonome kodeendringer.

### LLM-as-judge quality monitoring

**Status:** concept / later-track
**Plan:** `docs/plans/llm-as-judge-plan.md`

**Hvorfor:** Automatisk kvalitetsmonitorering kan gi trenddata for prompt- og
modellendringer, men må unngå judge-bias og ukontrollert kostvekst.

**Neste steg:**

- Start som sampled/admin-only eval, ikke per-generering default.
- Bruk eksplisitte rubrics og bias-mitigering.
- Ikke bland dette med kundevendt Final Review uten egen produktbeslutning.

---

## Planhygiene

Aktive planer skal holdes aktive bare når de faktisk styrer implementering,
operasjonell verifikasjon eller nær oppfølging.

Nærliggende cleanup:

- Oppdater active master checklist slik den ikke peker på planer som allerede
  ligger i `docs/plans/archived/`.
- Versjoner nye planfiler i riktig status: aktiv, backlog eller arkivert.
- Hold `ROADMAP.md` kortere enn planfilene; detaljer skal ligge i planene.

---

## Ikke lenger roadmap

Følgende er historikk, ikke fremtidig roadmap:

- EPUB Export
- PowerPoint Export
- Video Export med MP4 og 9:16
- Auto-detect language
- Basic website export
- Basic audio/TTS export
- Simple project persistence
- Billing/Dashboard/Monitoring grunnflater
- Final Review v1 og Revise v1

Disse skal bare tilbake på roadmapen hvis det gjelder en ny generasjon av
kapabiliteten, ikke fordi den opprinnelige leveransen finnes.
