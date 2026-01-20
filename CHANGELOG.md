# Changelog

Alle vesentlige endringer i dette prosjektet dokumenteres her.

Formatet er inspirert av *Keep a Changelog*, og prosjektet følger semantisk versjonering der det er praktisk.

## [Unreleased] – Fase 3: Kvoter & Misbruksvern

### Høydepunkter
- Nytt **kvote- og brukssporingssystem** med atomisk Postgres RPC for å forhindre race conditions.
- **Rate limiting** via Upstash Redis for anti-spam beskyttelse (graceful fallback hvis ikke konfigurert).
- **Felles utilities** i `_shared/utils.ts` for auth, allowlist, kvote-reservering og brukslogging.
- Alle **9 Edge Functions** refaktorert med ny pipeline: Auth → Allowlist → RateLimit → Quota → AI → Finalize.

### Added
- **Database-migrasjon (`supabase/migrations/20260120_quota_system.sql`)**:
  - `entitlements` tabell: Bruker-tier, limits (JSONB), features (JSONB)
  - `usage_counters` tabell: Rollup for rask kvote-sjekk per bruker/dag
  - `usage_events` tabell: Append-only audit log for alle AI-kall
  - RLS policies: Users kan kun lese egne rader, service role kan skrive
  - `quota_reserve()` RPC: Atomisk check-and-increment for kvotereservasjon
  - `quota_finalize()` RPC: Logger bruk til audit log
  - `get_user_entitlements()` RPC: Henter brukers tier og limits
- **Shared Utilities (`supabase/functions/_shared/`)**:
  - `utils.ts`: `reserveQuota()`, `finalizeUsage()`, `createServiceRoleClient()`, `checkRateLimit()` re-export
  - `rateLimit.ts`: Upstash Redis sliding window rate limiting (10 req/60s per bruker)
- **Edge Function Refaktorering**: Alle 9 funksjoner har nå full pipeline:
  - `ai-suggest-settings`, `ai-plan`, `ai-generate-section` (streaming)
  - `ai-image` (bruker `ai_images_per_day` kvote)
  - `ai-tts` (bruker `ai_tts_chars_per_day` kvote)
  - `ai-mermaid-fix`, `ai-summarize`, `ai-analyze-file`, `url-analyze`

### Changed
- **Edge Functions**: Byttet fra inline auth-kode til shared utilities.
- **Kvotetyper**:
  - `ai_requests_per_day`: 100 (default)
  - `ai_images_per_day`: 20 (default)
  - `ai_tts_chars_per_day`: 30000 (default)

### Filer berørt
- `supabase/migrations/20260120_quota_system.sql` (NEW)
- `supabase/functions/_shared/utils.ts` (utvidet)
- `supabase/functions/_shared/rateLimit.ts` (NEW)
- Alle 9 Edge Functions under `supabase/functions/`

---

## [Previous] – EPUB Eksport + PowerPoint + Lydoptimalisering

### Added
- **EPUB Eksport (`services/export/epub.ts`)**:
  - Full EPUB 3-struktur (mimetype, container.xml, content.opf, nav.xhtml)
  - Markdown → XHTML konvertering med inline formatting
  - Cover og kapittelillustrasjoner embedded
  - Mermaid-diagrammer rendret til PNG
  - Ren CSS-styling for e-lesere
  - Tilgjengelig for alle kategorier (fiction + non-fiction)
- **PowerPoint Eksport (`services/export/pptx.ts`)**:
  - AI-oppsummering av kapitler til 3-5 bullet points
  - Tittelslide med cover og sammendrag
  - Agenda-slide med alle kapitler
  - Per-kapittel slides med tekst og illustrasjon
  - Dedikerte diagram-slides med dynamisk skalering
  - Kun synlig for non-fiction kategorier

### Changed
- **MP3 Eksport (`services/export/mp3.ts`)**:
  - Bitrate redusert fra 128kbps til 64kbps for TTS-tale
  - Halverer filstørrelse uten hørbar kvalitetsforringelse

### Filer berørt
- `services/export/epub.ts` (NEW)
- `services/export/pptx.ts` (NEW)
- `services/ai/summarize.ts` (NEW)
- `services/export/mp3.ts` (bitrate endring)
- `services/export/index.ts`
- `components/ui/DownloadModal.tsx`
- `landing/index.html`, `landing/style.css`

---

## [Previous] – Eksport- og render-overhaling + “Suggest Prompt”

### Høydepunkter
- Ny **Suggest Prompt**-knapp som forbedrer/utvider *Core Idea* direkte i Story Engine (med Undo), for mer treffsikre genereringer.
- Stor oppgradering av **video-eksport**: stabil typografi og strukturert parsing av Markdown for bedre lesbarhet på skjerm.
- Ny/utbedret **interaktiv nettside-eksport** (ZIP) med mørkt tema, responsiv layout og innebygd avspilling for lyd/bilder.

### Added
- **Suggest Prompt (Core Idea)**:
  - Én-knapps forbedring av korte/enkle input-prompter til mer profesjonell og presis *Core Idea*.
  - Undo-funksjon for å gå tilbake til original tekst.
- **Interaktiv nettside-eksport**:
  - Genererer en komplett nettside i ZIP-format med navigasjon/innholdsfortegnelse, mørkt tema og støtte for lyd/bilde.

### Changed
- **Video-eksport (services/export/video.ts)**:
  - Innført strukturert “smart split”/normalisering for å hindre tekst-klumping/overlapp.
  - Forbedret håndtering av Markdown-elementer:
    - Overskrifter, labels, lister, horisontale linjer og nested blockquotes.
    - Kodeblokker vises monospaced og line-for-line på skjerm.
    - Markdown-tabeller detekteres som blokker og renderes som tydelige tabeller i video (grid).
  - Skille mellom “taletekst” og “videotekst” for bedre synk og mindre støy.
- **Kapittel-addons / TTS-løype (services/ai/chapters.ts)**:
  - Rens/strukturering for TTS slik at uegnede elementer (diagrammer/tabeller/kode) ikke skaper støy i opplesning.
  - Konsistent bruk av displayLine vs line for video vs tale.

### Fixed
- Hindret at sitatblokker “sluker” påfølgende avsnitt i video-rendering.
- Redusert visuell støy og økt lesbarhet i video ved bedre spacing og mer robust parsing.
- Bedre robusthet i render-pipeline gjennom konsekvent normalisering av tekststruktur.

### Filer berørt
- `components/views/IntroView.tsx` (Suggest Prompt UI + Undo)
- `services/ai/plan.ts` / `services/prompts.ts` (Core Idea enhancement prompt/flow)
- `services/export/video.ts` (stor render-overhaling + tabell-grid + callouts)
- `services/export/website.ts` (interaktiv eksportpipeline)
- `services/export/docx.ts`, `components/ui/ContentRenderer.tsx`, `components/views/CompleteView.tsx`, `README.md`
