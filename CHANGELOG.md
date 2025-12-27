# Changelog

Alle vesentlige endringer i dette prosjektet dokumenteres her.

Formatet er inspirert av *Keep a Changelog*, og prosjektet følger semantisk versjonering der det er praktisk.

## [Unreleased] – Eksport- og render-overhaling + “Suggest Prompt”

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
