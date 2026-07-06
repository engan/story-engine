# Story Engine Roadmap

Dette dokumentet beskriver fremtidig arbeid og prioriterte oppfølgingsspor for
Story Engine.

Roadmapen skal ikke være en liste over alt som allerede er levert. Ferdige
features, historiske beslutninger og release-notes ligger i `CHANGELOG.md`,
`README.md` og arkiverte planer under `docs/plans/archived/`.

Sist ryddet: 2026-07-06.

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
- Final Quality Pass / Final Review / targeted Revise som hovedkvalitetsflyt.
- Evidence safety, fact-lock, source repair og verified source metadata som
  operative kvalitetsmekanismer.
- Dashboard, Billing, Monitoring, Model & Pricing og Quality Queue V1 som
  admin-/operatorflater.
- Public FAQ, pricing, privacy, terms og cookies routes.
- PDF/DOCX Mermaid-kontrastnormalisering.
- GPT Image 2 / Gemini image-katalog, TTS-valg og multimodal output-baseline.

Se `CHANGELOG.md` for kurert historikk.

---

## Prioritet 1: Launch- og driftsklarhet

### Vertex / Gemini auth-key cleanup

**Status:** aktivt migreringsspor
**Planer:**

- `docs/plans/active/gemini-auth-key-migration-plan-2026-06-19.md`
- `docs/plans/active/generativelanguage-to-vertex-phase2.md`
- `docs/plans/active/vertex-phase2-canary-runbook.md`
- `docs/plans/active/vertex-phase2-wave1-reentry-checklist.md`

**Hvorfor:** Redusere avhengighet til standard Gemini API keys, samle mer
produksjonstrafikk på Vertex/service-account-routing og ha trygg rollback per
funksjon.

**Neste steg:**

- Fullfør credential inventory uten å lagre hemmeligheter i repoet.
- Avklar hvilke gjenstående Gemini Developer API-flows som skal til auth key
  og hvilke som skal flyttes til Vertex.
- Hold `GEMINI_API_KEY` fallback aktiv til canary- og smoke-data er gode nok.
- Ikke aktiver flere Vertex text flags før Monitoring viser stabilitet for
  forrige bølge.

### Paid launch margin og kreditt-økonomi

**Status:** aktiv launch-readiness
**Planstatus:** lokal draftplan finnes, men er ikke versjonert i repoet ennå.

**Hvorfor:** Før bred betalt lansering må inkluderte credits, top-ups,
providerkost, Stripe-fees, fallback/retry og margin kunne vurderes per tier og
operasjon.

**Neste steg:**

- Deploy/verify oppdatert `ai-quota-sync` før produksjonsdata forventes i
  margin-snapshot.
- Fullfør per-user, billing-cycle og resolved-model drilldown.
- Definer hard stop/admin-review terskler for providerkost.
- Avklar årsabonnementenes effektive credit-verdi og tax/VAT-behandling.

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

### Authoritative-first source repair planning

**Status:** backlog / pending follow-up
**Planstatus:** lokal draftplan finnes, men er ikke versjonert i repoet ennå.

**Hvorfor:** Source Authority Registry brukes allerede i verifisering og
ranking. Neste kvalitetsløft er å bruke authority-signaler tidligere i
source-repair query planning, uten å la registry-medlemskap alene lukke et
evidence-gap.

**Neste steg:**

- Klassifiser topic/risk/context fra eksisterende metadata.
- Velg relevante trusted source packs som advisory signal.
- Generer preferred-domain queries før bred fallback.
- Legg til tester som beviser at broad fallback fortsatt virker og at
  topic-spesifikk hardkoding ikke sniker seg inn.

### Final Quality Pass hardening

**Status:** kontinuerlig hardening / operator-runbook
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

### GPT-5.6 Sol/Terra/Luna evaluation

**Status:** aktiv vurderingsplan, ikke produksjonsbytte
**Planstatus:** lokal draftplan finnes, men er ikke versjonert i repoet ennå.

**Hvorfor:** Nye OpenAI review/revision-modeller kan bli relevante, men bare
hvis offisiell API-tilgang, pricing, caching, avtalevilkår, evals og
marginobservabilitet er verifisert.

**Neste steg:**

- Ikke endre defaultmodeller før offisiell tilgang og pricing er bekreftet.
- Bruk admin-only/offline/shadow eval før eventuell pilot.
- Krev flaggbasert rollback og ingen svekking av source/evidence-policy.

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

### Radio Play med Lyria/musikk/ambience

**Status:** konsept / senere produktspor
**Plan:** `docs/plans/lyria-radio-play-integration.md`

**Hvorfor:** Radio Play kan bli sterkere med egen audio-plan, Gemini-TTS for
dialog/narrator, musikk/ambience beds og enkel miksing med ducking.

**Neste steg:**

- Ikke bind v1 til udokumentert Lyria 3 request-kontrakt.
- Bruk kapabilitetsadapter for Lyria/alternativ musikkmodell.
- Hold lydregi i egen pass etter tekst/script, ikke i fiction-prompten.
- La brukeren regenerere lydlag uten å regenerere tekst.

### Persistent media storage

**Status:** planned / later-track
**Plan:** `docs/plans/persistent-storage-strategy.md`

**Hvorfor:** Prosjekttekst lagres allerede, men varig media-storage må styres
av kost, retention, tier-politikk og on-demand lasting.

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
- Flytt nye untracked planfiler inn i riktig status når de skal versjoneres:
  aktiv, backlog eller arkivert.
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
