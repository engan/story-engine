# Story Engine
### Den AI-drevne publiseringsplattformen.

![React](https://img.shields.io/badge/React-00599C?style=for-the-badge&logo=react&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Gemini 3.x Pro](https://img.shields.io/badge/Gemini_3.x_Pro-8E75B2?style=for-the-badge&logo=google&logoColor=white)
![Vertex AI](https://img.shields.io/badge/Vertex_AI-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white)
![Made in Norway](https://img.shields.io/badge/Made_in_Norway-A63A3A?style=for-the-badge&logo=flag-icon&logoColor=white)

![Story Engine Infographic](public/infographic.png)

> **Story Engine effektiviserer produksjonen av innhold og sikrer fakta ved hjelp av avanserte AI-agenter. Fra én idé til ferdig dokument, lydbok og video – kvalitetssikret.**

---

## 🚀 Nøkkelfunksjoner

*   ✍️ **Smart Prompt-utvidelse**: Usikker på hvordan du skal formulere deg? Ett klikk forvandler enkle stikkord til en rik, detaljert prosjektbeskrivelse optimalisert for at AI-en skal gi best mulig resultat.

*   ✨ **AI-anbefalte innstillinger**: Få forslag til kategori, sjanger/format (158 kombinasjoner), søk, kreativitet og diagram-frekvens - automatisk tilpasset din idé.

*   📄 **Native Dokumentgenerering**: Skaper ekte PDF, DOCX og MP3-filer direkte i nettleseren uten eksterne konverteringstjenester.

*   🌐 **Interaktiv Nettside**: Eksporter prosjektet ditt som en komplett, responsiv nettside (.zip) med mørkt tema, innholdsfortegnelse, og integrert lyd/bilde-avspilling. Åpnes enkelt direkte i nettleseren.

*   🎬 **Smart Video-produksjon**: Genererer videoer per kapittel med synkronisert lyd og tekst. Eksporterer som **MP4** (H.264/AAC) i **16:9** eller **9:16** (vertikal) format. Bruker "Smart Split"-teknologi for å sikre perfekt typografi.

*   📊 **PowerPoint-eksport (Non-Fiction)**: AI-genererte presentasjoner med oppsummerte bullet points, kapittelillustrasjoner og Mermaid-diagrammer på dedikerte slides.

*   📚 **EPUB E-bok**: Eksporter som universell e-bok med cover, kapittelnavigasjon og bilder – klar for Apple Books, Kobo, Kindle og andre e-lesere.

*   📂 **Analyser hva som helst**: Start prosjektet ditt med en lydfil, video, bilde, dokument, kodefil eller et helt .zip-arkiv. AI-en forstår innholdet og skriver "Core Idea" for deg.

*   🛠️ **AI-verktøykasse for spesialoppgaver**: Utfør avanserte oppgaver med ett klikk – konverter lydfiler til undertekster (.srt), generer en komplett README.md fra et .zip-arkiv, eller trekk ut et profesjonelt sammendrag fra et langt dokument.

*   🌍 **Full språk-kontroll**: Velg mellom auto-deteksjon eller spesifiser nøyaktig hvilket språk historien skal skrives på. Inkluderer nå oversettelse av eksisterende prosjekter.

*   📊 **Dynamisk Diagram-frekvens**: Kontroller den visuelle tettheten med presisjon - velg hvor ofte AI-en skal generere flytskjemaer, tidslinjer og grafer.

*   📝 **Regenerer fra fil**: Last opp en tidligere generert Story Engine-fil (.txt) for å lage nye formater som lyd, video eller nettside med den originale teksten eller oversett til et annet språk.

*   ⚙️ **Automatisk struktur**: La AI-en bestemme det optimale antallet seksjoner for historien din basert på kompleksitet og tema, eller velg antall seksjoner selv.

*   🎙️ **Velg din stemmekvalitet**: Bytt mellom to kraftige Text-to-Speech modeller for lydbøker – Gemini 2.5 Flash (rask og effektiv) eller Pro (maksimal kvalitet).

*   🤖 **Multi-Agent System**: Orkestrerer planlegging, skriving og faktasjekk gjennom spesialiserte AI-agenter som samarbeider.

*   🧼 **Vaskemaskinen (Sanitizer)**: Automatisk rensing og validering av kode, Markdown og Mermaid-diagrammer før visning. "Self-healing" Mermaid-diagrammer som fikser syntaksfeil automatisk.

*   🔍 **Final Review (QA Memo)**: Helhetlig kvalitetsvurdering av ferdig genererte dokumenter. En dedikert AI-agent leser hele dokumentet etter generering og returnerer et strukturert QA-memo med verdict (`strong` / `acceptable` / `needs_revision`), prioriterte forbedringsforslag, og seksjonsspesifikke issues – uten å endre selve dokumentet.

*   🧭 **Intelligent Model Routing**: Automatisk valg av optimal AI-modell basert på prosjektets `category`, `genre`, `creativity`-nivå, og om det er fiction eller non-fiction. Routing-logikken lever i `shared/routing/` og brukes av alle Edge Functions.

*   📊 **Quota Health Monitoring**: Sanntids-dashboard for Google Cloud API-kvoter (Gemini, Imagen, Vertex AI) med automatisk synkronisering, helseberegning, og trendvisning. Eget admin-view (`QuotaHealthView`).

*   💳 **Billing & Tier-system**: Komplett abonnement- og kredittløsning med Stripe-integrasjon. Fire tier-nivåer (Free, Starter, Pro, Enterprise) med ulike månedlige inkluderte kreditter, generasjonsgrenser og feature-flagg. Konfigurert i `shared/billing/`.

---

## 🚀 Se Story Engine i aksjon

### 🧪 Prøv Appen (Beta)
Story Engine kan nå testes på midlertidig server her:
👉 **[https://story.neoweb.no](https://story.neoweb.no)** 

### 🌐 Live demoer
- **Story Engine showcase (landing/index.html):**  
  [https://neoweb.no/se-walkthrough/index.html](https://neoweb.no/se-walkthrough/index.html)  
  Viser leveranseuniverset med video, lyd og eksporteksempler.

- **Interaktiv nettside-eksport (website/index.html):**  
  [https://neoweb.no/se-walkthrough/website/index.html](https://neoweb.no/se-walkthrough/website/index.html)  
  Ferdig eksportert nettside generert fra Story Engine.

<p>
  <a href="https://neoweb.no/se-walkthrough/website/index.html">
    <img src="https://neoweb.no/se-walkthrough/infographic.png" width="900" alt="Story Engine Showcase"/>
  </a>
  <br/>
  <a href="https://neoweb.no/se-walkthrough/index.html"><strong>Åpne Showcase ➔</strong></a>
  &nbsp;|&nbsp;
  <a href="https://neoweb.no/se-walkthrough/website/index.html"><strong>Åpne Nettside-eksport ➔</strong></a>
</p>

---

### 🗺️ Videogjennomgang
> 💡 **Klikk på bildene for å se videoene direkte fra vår server**

<table>
  <tr>
    <td>
      <strong>Seksjon 1: Hva Story Engine er i dagens versjon</strong><br/>
      <a href="https://neoweb.no/se-walkthrough/section-1.mp4">
        <img src="https://neoweb.no/se-walkthrough/section-1.png" width="420" alt="Seksjon 1"/>
      </a><br/>
      Plattformens kjerne, mål og hvorfor pipeline-basert produksjon gir bedre leveringssikkerhet.
    </td>
    <td>
      <strong>Seksjon 2: Arbeidsflyt i praksis (input, styring og regenerering)</strong><br/>
      <a href="https://neoweb.no/se-walkthrough/section-2.mp4">
        <img src="https://neoweb.no/se-walkthrough/section-2.png" width="420" alt="Seksjon 2"/>
      </a><br/>
      Startmodi, Suggest-flyter, Story Engine-fil import og hvilke innstillinger som bevisst forblir justerbare.
    </td>
  </tr>
  <tr>
    <td>
      <strong>Seksjon 3: Leveranser, add-ons og formatstrategi</strong><br/>
      <a href="https://neoweb.no/se-walkthrough/section-3.mp4">
        <img src="https://neoweb.no/se-walkthrough/section-3.png" width="420" alt="Seksjon 3"/>
      </a><br/>
      Hvordan ett prosjektgrunnlag gjenbrukes til dokument, presentasjon, web, video, lyd og e-bok.
    </td>
    <td>
      <strong>Seksjon 4: Teknologi, sikkerhet, kostkontroll og administrasjon</strong><br/>
      <a href="https://neoweb.no/se-walkthrough/section-4.mp4">
        <img src="https://neoweb.no/se-walkthrough/section-4.png" width="420" alt="Seksjon 4"/>
      </a><br/>
      Edge-first arkitektur, server-side kredittlogikk, prompt-SSOT og adminverktøy for brukerstyring.
    </td>
  </tr>
</table>

### 🖥️ Visuell Omvisning App
Møtet med brukeren – rent, moderne og inviterende.

![Landingsside](public/app-hero-eng.png)

<details>
<summary><strong>Klikk for å se Story Engine app</strong></summary>

### Startside app
Etter landingssiden – moderne og stilrent panel.

![Startside app](public/story-engine.png)

### Alternativt smal skjermbredde
Skriv inn dine nye ideer umiddelbart på din telefon. 

![Alternativt smal skjermbredde](public/story-engine-small.png)
</details>

<details>
<summary><strong>Klikk for å se genereringen i sanntid</strong></summary>

### Generation Progress
Noen trinn før genereringen, her foregår researchingen.

![Generation Progress](public/processing.png)

Hvor magien skjer. Her ser brukeren innholdet bli skapt i sanntid, med levende oppdateringer.

![Generation Progress](public/generation-progress.png)

Her kan man følge skrivingen seksjon for seksjon etter hvert som den skrives.

![Generation Progress](public/generation-progress-2.png)
</details>

<details>
<summary><strong>Klikk for å se eksportformater</strong></summary>

### Eksport og leveranseformater
Story Engine er bygget for å gjøre ett prosjektgrunnlag om til flere ferdige leveranser. Her kan brukeren eksportere til blant annet lesbare dokumentformater, nettside, presentasjon, lyd og video, avhengig av hvilken type prosjekt som er generert.

På lydsiden vises det to ulike formater i den øverste bryteren: klassisk fortelleropplesning og en mer dramatisert variant som radio play / lyddrama. Det gjør at samme tekstgrunnlag kan brukes enten som ren narrasjon eller som en mer scenisk lydopplevelse.

På videosiden vises det også to ulike varianter i den andre øverste bryteren: vanlig bredformatvideo og en vertikal videoversjon tilpasset mobil og sosiale flater. Dette gjør eksporten mer praktisk når samme innhold skal brukes både som tradisjonell video og i mer korte, mobile formater.

I tillegg viser denne visningen hvordan innholdet kan tas videre til flere konkrete leveranser, som dokumenteksport, webformat og andre sluttprodukter. Målet er å gjøre Story Engine til mer enn bare en skriveflate: det er også et system for å pakke samme prosjekt ut i flere brukbare formater.

![Eksportformater](public/story-engine-format.png)
</details>

<details>
<summary><strong>Klikk for å se Projects</strong></summary>

### Projects
Prosjektoversikten samler alle lagrede prosjekter på ett sted. Her kan brukeren åpne tidligere arbeid, starte en remake fra eksisterende grunnlag, og holde kontroll på hele arbeidsflyten uten å miste historikk.

![Projects](public/projects.png)
</details>

<details>
<summary><strong>Klikk for å se Dashboard</strong></summary>

### Dashboard
Dashboardet gir et raskt overblikk over konto, aktivitet og status. Det er her brukeren ser hva som nylig er generert, hvilke funksjoner som er brukt, og hvordan prosjektarbeidet utvikler seg over tid.

![Dashboard](public/dashboard.png)
</details>

<details>
<summary><strong>Klikk for å se Billing</strong></summary>

### Billing
Billing-siden samler abonnement, kredittsaldo, top-ups og betalingsstatus i ett tydelig grensesnitt. Målet er at brukeren alltid skal forstå hva som er inkludert, hva som er kjøpt, og hva som er neste steg.

![Billing](public/Billing.png)
</details>

<details>
<summary><strong>Klikk for å se Monitoring</strong></summary>

### Quota Health
Monitoring viser levende status for AI-kvoter, forbruk og operasjonell helse. Dette er admin-flaten som gjør det mulig å oppdage kapasitetsproblemer, lese runtime-flagg og vurdere neste rollout-steg før noe faktisk går galt.

![Quota Health](public/monitoring-quota-health.png)

### Runtime & Config
Her vises hvilke runtime-flagg og fallback-mekanismer som faktisk er aktive. Det gjør overvåkningen konkret, og kobler konfigurasjon direkte til hvordan systemet oppfører seg i produksjon.

![Runtime & Config](public/monitoring-runtime.png)

### Phase 2 Readiness
Readiness-visningen samler signalene som trengs før neste Vertex-bølge kan vurderes. Den gjør canary-beslutninger mer synlige og mindre avhengige av manuell tolkning på tvers av flere paneler.

![Phase 2 Readiness](public/monitoring-phase2.png)

### Operational Risks
Dette panelet løfter frem de viktigste operative risikopunktene i et format som er lett å bruke i hverdagen. Målet er å gjøre oppfølging konkret, ikke bare informativ.

![Operational Risks](public/monitoring-operational-risks.png)
</details>

<details>
<summary><strong>Klikk for å se Users</strong></summary>

### Users
Admin-brukerlisten gir full oversikt over brukere, tier, kreditter og abonnementsstatus. Dette gjør support- og driftsarbeid raskere, tryggere og langt mindre avhengig av å slå opp data flere steder.

![Users](public/admin-users.png)
</details>

---

## 🏗️ Teknisk Arkitektur

### Dataflyt (Input → Eksport)

Dataflyten er delt i to separate diagrammer for bedre lesbarhet.

<details>
<summary><strong>Klikk for å se Dataflyt Del 1 (Input → Generering)</strong></summary>

### Dataflyt Del 1: Input → Generering

Dette diagrammet dekker input, analyse, planlegging og innholdsgenerering fram til ferdig generert payload.
```mermaid
graph TD
    Entry((("🚀 App Start")))
    Entry --> LandingPage["🏠 Landing Page<br/><i>LandingPage.tsx</i>"]
    LandingPage --> UserStart((("👤 Bruker")))

    subgraph InputSources ["📥 INPUT KILDER"]
        direction TB
        IdeaInput["📝 Core Idea"]
        FileInput["📁 Fil Upload"]
        URLInput["🌐 URL Analyse"]
        PlanFile["📄 .txt Plan"]
    end
    UserStart -->|"Velger kilde"| InputSources

    subgraph Analysis ["🔍 ANALYSE & ANBEFALINGER"]
        direction TB
        CoreIdea["💡 Core Idea"]
        UI["🎨 IntroView"]
        AIRecommend["🤖 getRecommendedSettingsHybrid()"]
        SuggestPrompt["✨ enhanceUserIdeaHybrid()"]
        FileAnalyzer["⚙️ fileExtract.ts"]
        URLAnalyzer["🔗 api.ts"]
        FileParser["📑 fileParser.ts"]
        SharedPromptSuggest["🧩 shared/prompts<br/><i>suggest builders</i>"]
        EdgeSuggestPrompt["⚙️ ai-suggest-prompt"]
        EdgeSuggestSettings["⚙️ ai-suggest-settings"]
        EdgeAnalyzeFile["⚙️ ai-analyze-file"]
        EdgeUrlAnalyze["⚙️ url-analyze"]
        GeminiAnalyze["🤖 Gemini API<br/><i>3.x flash/pro</i>"]
    end

    IdeaInput --> AIRecommend
    IdeaInput --> SuggestPrompt
    SuggestPrompt --> EdgeSuggestPrompt
    EdgeSuggestPrompt --> SharedPromptSuggest
    EdgeSuggestPrompt --> GeminiAnalyze
    CoreIdea --> AIRecommend
    AIRecommend --> EdgeSuggestSettings
    EdgeSuggestSettings --> SharedPromptSuggest
    EdgeSuggestSettings --> GeminiAnalyze
    GeminiAnalyze --> CoreIdea
    EdgeSuggestSettings --> UI

    FileInput --> FileAnalyzer
    FileAnalyzer --> EdgeAnalyzeFile
    EdgeAnalyzeFile --> GeminiAnalyze
    URLInput --> URLAnalyzer
    URLAnalyzer --> EdgeUrlAnalyze
    EdgeUrlAnalyze --> GeminiAnalyze
    PlanFile --> FileParser --> PlanReady["📋 NovelPlan<br/><i>fra fil</i>"]

    subgraph Planning ["📐 PLANLEGGING"]
        direction TB
        PlanningLogic{"🤔 Har vi plan?"}
        PlanGenerator["📝 generateNovelPlanHybrid()"]
        SharedPromptPlan["🧩 shared/prompts<br/><i>planPrompt.ts</i>"]
        EdgePlan["⚙️ ai-plan"]
        ModelRouter["🧭 shared/routing<br/><i>decision.ts</i>"]
        GeminiPlan["🤖 Gemini API<br/><i>3.x pro (via Vertex/Dev)</i>"]
        SearchDecision{"🔎 Google Search?"}
        SearchAPI["🌍 Grounding + Citations"]
        PlanCoverAttempt["🖼️ ai-plan cover attempt<br/><i>(Imagen 4.x)</i>"]
    end

    UI --> PlanningLogic
    PlanningLogic -->|"Ja"| PlanReady
    PlanningLogic -->|"Nei"| PlanGenerator
    PlanGenerator --> SharedPromptPlan
    SharedPromptPlan --> EdgePlan
    EdgePlan --> ModelRouter
    ModelRouter --> GeminiPlan
    EdgePlan --> SearchDecision
    SearchDecision -->|"Ja"| SearchAPI --> EdgePlan
    SearchDecision -->|"Nei"| EdgePlan
    EdgePlan --> PlanCoverAttempt --> EdgePlan
    EdgePlan --> PlanReady

    subgraph ContentFlow ["✍️ GENERERING + SANITIZE + ADD-ONS"]
        direction TB
        CoverDecision{"🖼️ Cover fra ai-plan?"}
        EdgeImageCover["⚙️ ai-image (cover fallback)"]
        ImageGen["🎨 Imagen 4.x"]
        PlanWithCover["📖 Plan + coverImageUrl"]
        ChapterGen["📚 generateChapterBatch()"]
        PromptService3["📋 Request assembly<br/><i>chapters.ts</i>"]
        SharedPromptSection["🧩 shared/prompts<br/><i>sectionPrompt.ts</i>"]
        EdgeSection["⚙️ ai-generate-section<br/><i>SSE</i>"]
        RoutingSection["🧭 shared/routing"]
        GeminiSection["🤖 Gemini Streaming<br/><i>Vertex AI / Dev API</i>"]
        StreamHandler["📡 chapters.ts"]
        RawMD["📄 Rå MD"]
        CodexDecision{"🧠 Codex post-check?"}
        EdgeCodex["⚙️ ai-codex-postcheck"]
        CodexModel["🧠 OpenAI Codex"]
        Fix1["🔧 ContentSanitizer"]
        Fix2["✅ mermaidFixer"]
        MermaidDecision{"📊 Mermaid OK?"}
        EdgeMermaidFix["⚙️ ai-mermaid-fix"]
        SharedPromptFix["🧩 mermaidFixPrompt.ts"]
        GeminiFix["🤖 Mermaid fix"]
        CleanMD["✨ Ren MD"]
        AddOnProcessor["⚡ processChapterAddOns()"]
        EdgeImageChapter["⚙️ ai-image (chapter)"]
        EdgeScript["⚙️ ai-script-convert"]
        EdgeTTS["⚙️ ai-tts"]
        FinalChapter["📖 GeneratedChapter"]
        GenerationPayload["💾 Payload til Del 2"]
    end

    PlanReady --> CoverDecision
    CoverDecision -->|"Ja"| PlanWithCover
    CoverDecision -->|"Nei"| EdgeImageCover
    EdgeImageCover --> ImageGen
    ImageGen --> EdgeImageCover
    EdgeImageCover --> PlanWithCover
    PlanWithCover --> ChapterGen
    ChapterGen --> PromptService3
    PromptService3 --> SharedPromptSection
    SharedPromptSection --> EdgeSection
    EdgeSection --> RoutingSection
    RoutingSection --> GeminiSection
    GeminiSection --> EdgeSection
    EdgeSection --> StreamHandler
    StreamHandler --> RawMD
    RawMD --> CodexDecision
    CodexDecision -->|"Ja (non-fiction)"| EdgeCodex
    EdgeCodex --> CodexModel
    CodexModel --> EdgeCodex
    EdgeCodex --> Fix1
    CodexDecision -->|"Nei / fallback"| Fix1
    Fix1 --> Fix2
    Fix2 --> MermaidDecision
    MermaidDecision -->|"Ja"| CleanMD
    MermaidDecision -->|"Nei"| EdgeMermaidFix
    EdgeMermaidFix --> SharedPromptFix
    SharedPromptFix --> GeminiFix
    GeminiFix --> EdgeMermaidFix
    EdgeMermaidFix --> Fix2
    CleanMD --> AddOnProcessor
    AddOnProcessor --> EdgeImageChapter
    AddOnProcessor --> EdgeScript
    EdgeScript --> EdgeTTS
    AddOnProcessor --> FinalChapter
    EdgeImageChapter --> FinalChapter
    EdgeTTS --> FinalChapter
    FinalChapter --> GenerationPayload
    PlanWithCover --> GenerationPayload

    classDef userNode fill:#fef3c7,stroke:#d97706,stroke-width:3px,color:#92400e
    classDef landingNode fill:#fce7f3,stroke:#be185d,stroke-width:2px,color:#9d174d
    classDef apiNode fill:#dbeafe,stroke:#2563eb,stroke-width:2px,color:#1e40af
    classDef processNode fill:#f3e8ff,stroke:#7c3aed,stroke-width:2px,color:#5b21b6
    classDef serviceNode fill:#e0e7ff,stroke:#4f46e5,stroke-width:2px,color:#3730a3
    classDef stateNode fill:#dcfce7,stroke:#16a34a,stroke-width:3px,color:#166534
    classDef decisionNode fill:#fff7ed,stroke:#ea580c,stroke-width:2px,color:#c2410c
    classDef sanitizerNode fill:#e0f2fe,stroke:#0284c7,stroke-width:2px,color:#075985

    class Entry,UserStart userNode
    class LandingPage landingNode
    class GeminiAnalyze,GeminiPlan,SearchAPI,ImageGen,GeminiSection,GeminiFix apiNode
    class SuggestPrompt,AIRecommend,PlanGenerator,ChapterGen,StreamHandler,AddOnProcessor processNode
    class PromptService3,FileAnalyzer,URLAnalyzer,FileParser,EdgeSuggestPrompt,EdgeSuggestSettings,EdgeAnalyzeFile,EdgeUrlAnalyze,EdgePlan,SharedPromptSuggest,SharedPromptPlan,SharedPromptSection,EdgeSection,EdgeImageCover,EdgeImageChapter,EdgeMermaidFix,SharedPromptFix,EdgeScript,EdgeTTS,EdgeCodex,ModelRouter,RoutingSection serviceNode
    class CoreIdea,PlanReady,PlanWithCover,FinalChapter,GenerationPayload,UI stateNode
    class PlanningLogic,SearchDecision,CoverDecision,CodexDecision,MermaidDecision decisionNode
    class RawMD,Fix1,Fix2,CleanMD sanitizerNode
    class CodexModel apiNode
```
</details>

<details>
<summary><strong>Klikk for å se Dataflyt Del 2 (State → Eksport)</strong></summary>

### Dataflyt Del 2: State → Eksport

Dette diagrammet dekker state/sporing, visning og alle eksportformatene.
```mermaid
graph TD
    %% ═══════════════════════════════════════════
    %% 📱 STORY ENGINE - DEL 2 (STATE → EKSPORT)
    %% Oppdatert: Mars 2026
    %% ═══════════════════════════════════════════

    GenerationPayload["📥 Fra Del 1<br/><i>Plan + Chapters + Audio + Images</i>"]
    QuotaUsage["💳 Credits/Kvoter<br/><i>Edge _shared/utils.ts</i>"]

    subgraph StateTracking ["💾 STATE & SPORING"]
        direction LR
        AppState[("App State<br/><i>React</i>")]
        UsageMetrics["📊 UsageMetrics<br/><i>Tokens/Images/Audio</i>"]
    end

    GenerationPayload --> AppState
    GenerationPayload -.-> QuotaUsage
    QuotaUsage --> UsageMetrics
    AppState --> UsageMetrics

    Viewer["🖥️ ContentRenderer<br/><i>react-markdown + Mermaid</i>"]
    Screen["📺 GenerationView<br/><i>Live + Yellow text</i>"]
    UserEnd((("👤 Bruker")))
    DownloadBtn["⬇️ DownloadModal<br/><i>Format + Progress</i>"]
    FormatChoice{"📁 Format?"}

    AppState --> Viewer --> Screen
    UserEnd -.->|"Ser dokument"| Screen
    UserEnd -->|"Last Ned"| DownloadBtn --> FormatChoice

    subgraph FinalReviewFlow ["🔍 FINAL REVIEW (QA MEMO)"]
        direction TB
        ReviewDecision{"🔍 Kjør Final Review?"}
        EdgeFinalReview["⚙️ ai-final-review"]
        ReviewModel["🤖 Pro Model<br/><i>Gemini/GPT/Opus</i>"]
        QAMemo["📋 QA Memo<br/><i>verdict + issues</i>"]
    end

    AppState -->|"Ferdig dokument"| ReviewDecision
    ReviewDecision -->|"Ja"| EdgeFinalReview
    EdgeFinalReview --> ReviewModel
    ReviewModel --> EdgeFinalReview
    EdgeFinalReview --> QAMemo
    ReviewDecision -->|"Nei / Ikke tilgjengelig"| DownloadBtn

    subgraph ExportService ["📤 EKSPORT SERVICE"]
        direction TB
        DLService["🔧 downloadService"]
        ContentParse["📑 ContentParser<br/><i>MD → Blokker</i>"]
        ExportModules["📦 Export Modules<br/><i>docx/pdf/video/website</i>"]
        FullMD["📄 Full Markdown<br/><i>YAML + Innhold</i>"]
        DLService --> ContentParse
        DLService --> ExportModules
        DLService --> FullMD
    end

    AppState -->|"NovelPlan + Chapters"| DLService
    UsageMetrics -->|"Produksjonsrapport"| DLService

    subgraph ExportFormats ["💾 EKSPORT FORMATER"]
        direction TB
        ExportTXT["📄 .txt<br/><i>YAML + Markdown</i>"]
        GeneratePDF["📕 PDF Generator<br/><i>jsPDF + Bold/Italic</i>"]
        ExportPDF["📕 .pdf<br/><i>A4 + Mermaid PNG</i>"]
        GenerateDOCX["📘 DOCX Generator<br/><i>docx + Numbered lists</i>"]
        ExportDOCX["📘 .docx<br/><i>Native Word</i>"]
        GenerateMP3["🎵 Audio Processor<br/><i>MP3/WAV valg</i>"]
        ExportMP3["🎵 .zip<br/><i>MP3 (64kbps) eller WAV</i>"]
        GenerateWebM["🎬 Video Processor<br/><i>MP4 H.264/AAC</i>"]
        ExportWebM["🎬 .zip<br/><i>MP4 (16:9 / 9:16)</i>"]
        GenerateWebsite["🌐 Web Generator<br/><i>HTML/CSS/JS Bundle</i>"]
        ExportWebsite["🌐 .zip<br/><i>Interaktiv side</i>"]
        GeneratePPTX["📊 PPTX Generator<br/><i>AI Summarize + PptxGenJS</i>"]
        ExportPPTX["📊 .pptx<br/><i>Non-Fiction presentasjon</i>"]
        GenerateEPUB["📚 EPUB Generator<br/><i>XHTML + Cover</i>"]
        ExportEPUB["📚 .epub<br/><i>Universell e-bok</i>"]
    end

    FormatChoice -->|"TXT"| ExportTXT
    FullMD --> ExportTXT

    FormatChoice -->|"PDF"| GeneratePDF
    ContentParse --> GeneratePDF
    GeneratePDF --> ExportPDF

    FormatChoice -->|"DOCX"| GenerateDOCX
    ContentParse --> GenerateDOCX
    GenerateDOCX --> ExportDOCX

    FormatChoice -->|"MP3"| GenerateMP3
    AppState -->|"audioContent"| GenerateMP3
    GenerateMP3 --> ExportMP3

    FormatChoice -->|"MP4 Video"| GenerateWebM
    AppState -->|"audio + image"| GenerateWebM
    GenerateWebM --> ExportWebM

    FormatChoice -->|"Nettside"| GenerateWebsite
    AppState -->|"Plan + Chapters"| GenerateWebsite
    GenerateWebsite --> ExportWebsite

    FormatChoice -->|"PPTX"| GeneratePPTX
    AppState -->|"Plan + AI Summary"| GeneratePPTX
    GeneratePPTX --> ExportPPTX

    FormatChoice -->|"EPUB"| GenerateEPUB
    ContentParse --> GenerateEPUB
    GenerateEPUB --> ExportEPUB

    classDef userNode fill:#fef3c7,stroke:#d97706,stroke-width:3px,color:#92400e
    classDef apiNode fill:#dbeafe,stroke:#2563eb,stroke-width:2px,color:#1e40af
    classDef processNode fill:#f3e8ff,stroke:#7c3aed,stroke-width:2px,color:#5b21b6
    classDef serviceNode fill:#e0e7ff,stroke:#4f46e5,stroke-width:2px,color:#3730a3
    classDef stateNode fill:#dcfce7,stroke:#16a34a,stroke-width:3px,color:#166534
    classDef exportNode fill:#fce7f3,stroke:#db2777,stroke-width:2px,color:#9d174d
    classDef decisionNode fill:#fff7ed,stroke:#ea580c,stroke-width:2px,color:#c2410c
    classDef viewNode fill:#f5f3ff,stroke:#7c3aed,stroke-width:2px,color:#5b21b6
    classDef metricsNode fill:#fef9c3,stroke:#ca8a04,stroke-width:2px,color:#854d0e

    class UserEnd userNode
    class Viewer,Screen viewNode
    class DLService,ContentParse,ExportModules serviceNode
    class AppState,GenerationPayload stateNode
    class QuotaUsage,UsageMetrics metricsNode
    class FormatChoice decisionNode
    class ExportTXT,ExportPDF,ExportDOCX,ExportMP3,ExportWebM,ExportWebsite,ExportPPTX,ExportEPUB,GeneratePDF,GenerateDOCX,GenerateMP3,GenerateWebM,GenerateWebsite,GeneratePPTX,GenerateEPUB,FullMD,DownloadBtn exportNode
    classDef reviewNode fill:#ecfdf5,stroke:#059669,stroke-width:2px,color:#065f46
    class EdgeFinalReview,ReviewModel,QAMemo reviewNode
    class ReviewDecision decisionNode
```
</details>

<details>
<summary><strong>Klikk for å se Sekvensdiagram (Interaksjon)</strong></summary>

### Sekvensdiagram (Interaksjon)

Hvordan frontend kommuniserer med AI-modellene og håndterer asynkrone strømmer.

```mermaid
%%{init: {
  'theme': 'base',
  'themeVariables': {
    'primaryColor': '#6366f1',
    'primaryTextColor': '#ffffff',
    'primaryBorderColor': '#4f46e5',
    'secondaryColor': '#10b981',
    'tertiaryColor': '#f0f9ff',
    'lineColor': '#6366f1',
    'noteTextColor': '#1e293b',
    'noteBkgColor': '#fef3c7',
    'noteBorderColor': '#f59e0b',
    'actorTextColor': '#1e293b',
    'actorBkg': '#e0e7ff',
    'actorBorder': '#6366f1',
    'activationBkgColor': '#c7d2fe',
    'activationBorderColor': '#4f46e5',
    'sequenceNumberColor': '#ffffff'
  },
  'sequence': {
    'mirrorActors': false,
    'messageAlign': 'center',
    'width': 180,
    'useMaxWidth': true
  }
}}%%

sequenceDiagram
    autonumber
    
    box rgba(99, 102, 241, 0.1) 🎯 KLIENT
        participant User as 👤 Bruker
        participant FE as 🖥️ Frontend
        participant San as 🧼 Sanitizer
        participant DL as 📦 Download/Export
    end
    
    box rgba(16, 185, 129, 0.1) ☁️ EDGE
        participant Edge as ⚙️ Supabase Edge Functions
    end
    
    box rgba(245, 158, 11, 0.1) 🧠 MODELLER
        participant Gemini as ⚡ Gemini API
        participant OpenAI as 🧠 OpenAI (Codex)
        participant Search as 🔍 Google Search
        participant Imagen as 🎨 Image Model (Imagen/Gemini)
    end

    Note over User,Imagen: 🎯 FASE 1: Input & AI-anbefalinger
    
    User->>+FE: 📝 Input: idé, fil eller URL
    alt Filanalyse
        FE->>+Edge: POST ai-analyze-file
        Edge->>+Gemini: Multimodal analyse
        Gemini-->>-Edge: Analyse-resultat
        Edge-->>-FE: Core Idea / sammendrag
    else URL-analyse
        FE->>+Edge: POST url-analyze
        Edge-->>-FE: Innhold / sammendrag
    end
    FE->>+Edge: POST ai-suggest-settings
    Edge->>Gemini: Prompt fra shared/prompts
    Gemini-->>Edge: Settings-forslag
    Edge-->>-FE: category/genre/creativity/grounding

    Note over User,Imagen: 📐 FASE 2: Planlegging og cover
    
    User->>FE: ✅ Godkjenn innstillinger
    FE->>+Edge: POST ai-plan
    Note over Edge: buildPlanPrompt() fra shared/prompts
    
    alt Grounding aktivert
        Edge->>+Search: Hent kilder/fakta
        Search-->>-Edge: Grounded data
    end
    
    Edge->>+Gemini: Generer plan JSON
    Gemini-->>-Edge: NovelPlan + citations
    opt ai-plan forsøker cover
        Edge->>Imagen: Generer cover (Gemini/Imagen)
        Imagen-->>Edge: Base64 bilde eller feil
    end
    Edge-->>-FE: Plan-respons (+ optional coverImageUrl/status)
    opt ai-plan cover feilet (ett fallback-forsøk)
        FE->>+Edge: POST ai-image (cover fallback)
        Edge->>+Imagen: Generer cover
        Imagen-->>-Edge: Base64 bilde
        Edge-->>-FE: coverImageUrl
    end

    Note over User,Imagen: ✍️ FASE 3: Seksjonsgenerering (SSE)
    
    loop Per seksjon
        FE->>+Edge: POST ai-generate-section (stream)
        Note over Edge: buildGenerateSectionPrompt() fra shared/prompts
        Edge->>+Gemini: streamGenerateContent
        loop Per chunk
            Gemini-->>Edge: Markdown chunk
            Edge-->>FE: SSE event chunk
            FE-->>User: Live oppdatering
        end
        Gemini-->>-Edge: Seksjon ferdig
        Edge-->>-FE: DONE event
        opt Non-fiction post-check (Codex)
            FE->>+Edge: POST ai-codex-postcheck
            Edge->>+OpenAI: Responses API (Codex)
            OpenAI-->>-Edge: Revidert tekst / fallback
            Edge-->>-FE: Post-check resultat
        end
        FE->>San: Rens + valider Mermaid
        opt Mermaid krever AI-fiks
            San->>+Edge: POST ai-mermaid-fix
            Edge->>Gemini: Fix-prompt (shared/prompts)
            Gemini-->>Edge: Fikset diagram
            Edge-->>-San: Valid Mermaid
        end
        San-->>FE: Ren output
    end
    
    Note over User,Imagen: 🎁 FASE 4: Add-ons
    opt Illustrasjoner / TTS
        FE->>+Edge: POST ai-image (kapittel)
        Edge->>Imagen: Generer illustrasjon
        Imagen-->>Edge: Base64 bilde
        Edge-->>-FE: chapter image
        FE->>+Edge: POST ai-script-convert / ai-tts
        Edge->>Gemini: Script/TTS behandling
        Gemini-->>Edge: Audio/script-data
        Edge-->>-FE: Audio chunks
    end

    Note over User,Imagen: 🔍 FASE 5: Final Review (QA Memo)
    opt Final Review aktivert
        FE->>+Edge: POST ai-final-review
        Note over Edge: Hele dokumentet sendes til pro-modell
        Edge->>+Gemini: Helhetlig dokumentvurdering
        Gemini-->>-Edge: QA Memo JSON
        Edge-->>-FE: verdict + issues + priority actions
        FE-->>User: Viser QA Memo i CompleteView
    end

    Note over User,DL: 📥 FASE 6: Eksport
    
    User->>FE: 📁 Velg eksportformat
    FE->>DL: Parse markdown + bygg filer
    
    DL-->>User: TXT / PDF / DOCX / MP3 / MP4 / ZIP / PPTX / EPUB
```
</details>

---

## 📂 Filstruktur & Modul-analyse

<details>
<summary><strong>Klikk for filstruktur</strong></summary>

Prosjektet har gjennomgått en omfattende refaktorering for å øke vedlikeholdbarhet og skalerbarhet. Vi bruker nå en tydelig domenestruktur under `services`, samt et delt prompt-lag i `shared/prompts` for å hindre prompt-drift mellom frontend og Edge Functions.

```text
.
├── App.tsx                                   # Global state, view-ruting og kostnadssporing
├── README.md                                 # Dokumentasjon
├── CHANGELOG.md                              # Endringslogg
├── ROADMAP.md                                # Veikart og fremtidsplaner
├── constants.ts                              # Globale konstanter (stemmer, stiler)
├── types.ts                                  # TypeScript definisjoner for hele applikasjonen
├── genres.ts                                 # Definisjoner av hovedsjangre og kategorier
├── genreOptions.ts                           # Kontekstuelle sub-options (faktasjekk, lengde, etc.)
├── genreUtils.ts                             # Delte sjanger-hjelpere (fiction/non-fiction checks)
├── languages.ts                              # Støttede språk for I/O
├── components/
│   ├── Icons.tsx                             # Ikoner (SVG)
│   ├── MermaidDebugPage.tsx                  # Debug side for Mermaid
│   ├── OnboardingModal.tsx                   # Førstegangs onboarding
│   ├── ParserTest.tsx                        # Test-komponent for parser
│   ├── landing/                              # Landingsside komponenter
│   │   └── LandingPage.tsx                   # Hovedinngang / Hero-seksjon
│   ├── ui/                                   # Gjenbrukbare UI-komponenter
│   │   ├── ContentRenderer.tsx               # Markdown/Mermaid renderer (ReactMarkdown)
│   │   ├── DownloadModal.tsx                 # Modal for valg av eksportformat
│   │   ├── ErrorBoundary.tsx                 # Feilhåndtering
│   │   ├── LoadingView.tsx                   # Animerte laste-steg (Analyzing -> Finalizing)
│   │   ├── LogViewer.tsx                     # Debug-konsoll i UI
│   │   ├── Mermaid.tsx                       # Wrapper for Mermaid-diagrammer
│   │   ├── PlanningStepper.tsx               # Visuell fremdriftsindikator
│   │   ├── ResearchSourcesBox.tsx            # Visning av Google Search-kilder
│   │   └── SettingsModal.tsx                 # Avanserte innstillinger (Logger, Terskelverdier)
│   └── views/                                # Hovedvisninger (States)
│       ├── AdminUsersView.tsx                # Egen admin-visning for brukerstyring
│       ├── BillingView.tsx                   # Abonnement, kreditter og Stripe-portal
│       ├── DashboardView.tsx                 # Brukerdashboard og prosjektoversikt
│       ├── ProjectsView.tsx                  # Prosjektliste, Remake og prosjektstyring
│       ├── QuotaHealthView.tsx               # Google Cloud kvote-monitoring dashboard
│       ├── quotaHealthPlanData.ts            # Plan-data for fase 2 quota readiness
│       ├── pageShell.ts                      # Delt shell-layout for admin-sider
│       ├── LoginView.tsx                     # Innlogging og autentisering
│       ├── QrAuthorizeView.tsx               # Mobil autorisering for QR-login
│       ├── WaitlistView.tsx                  # Venteliste og early access
│       ├── IntroView.tsx                     # Input, filanalyse, drag-n-drop
│       ├── CastingView.tsx                   # Karakteroversikt og stemmevalg
│       ├── GenerationView.tsx                # Live streaming av innhold
│       └── CompleteView.tsx                  # Ferdig resultat, Final Review Preview, regenerering
├── scripts/                                  # Verktøy og test-skript
│   ├── check-prompt-drift.mjs                # CI-guard mot inline core-prompts i Edge Functions
│   ├── smoke-prompt-builders.ts              # Smoke-test av shared prompt-builders
│   ├── smoke-routing-decision.ts             # Smoke-test av model routing-logikk
│   ├── smoke-suggest-settings-heuristics.ts  # Test av suggest-settings heuristikker
│   ├── smoke-human-nuance-modes.ts           # Test av human-nuance prompt-modi
│   ├── smoke-human-nuance-default-matrix.ts  # Default-matrise for human-nuance
│   ├── eval-human-nuance-ab.ts               # A/B-evaluering av prompt-kvalitet
│   └── archive/                              # Arkiverte/utdaterte skript
├── services/                                 # FORRETNINGSLOGIKK (MODULÆR)
│   ├── ContentParser.ts                      # AST-parser som konverterer MD til blokker
│   ├── ContentSanitizer.ts                   # "Vaskemaskinen" (Regex-rensing, header-fiks)
│   ├── documentStyles.ts                     # Fasade for styles/index.ts
│   ├── downloadService.ts                    # Fasade for export/index.ts
│   ├── api.ts                                # URL-analyse og ekstern API-kommunikasjon
│   ├── auth.ts                               # Autentiseringslogikk
│   ├── formatConstants.ts                    # Konstanter for overskriftsformater
│   ├── geminiService.ts                      # Fasade for ai/index.ts
│   ├── modelPricing.ts                       # Prismodeller for Gemini/Imagen
│   ├── prompts.ts                            # Stabil offentlig entrypoint (barrel re-export)
│   ├── supabaseApi.ts                        # Klient for Supabase Edge Functions
│   ├── supabaseClient.ts                     # Supabase autentisering og oppsett
│   ├── ai/                                   # AI-integrasjon (Google GenAI)
│   │   ├── audioHelpers.ts                   # PCM/Base64 hjelpere
│   │   ├── chapters.ts                       # Generering av kapitler (tekst + add-ons)
│   │   ├── config.ts                         # Konfigurasjon (tokens, sikkerhet)
│   │   ├── fileExtract.ts                    # Filanalyse (DOCX, PDF, Code, Images)
│   │   ├── imageGenerator.ts                 # Bildegenerering via Supabase/API-lag
│   │   ├── imagen.ts                         # Bildegenerering (Imagen & Gemini)
│   │   ├── index.ts                          # Eksportør
│   │   ├── retry.ts                          # Feilhåndtering og retry-logikk
│   │   ├── schemas.ts                        # Zod/JSON schemas for AI output
│   │   ├── summarize.ts                      # AI-oppsummering for PPTX bullet points
│   │   ├── tts.ts                            # Tekst-til-tale logikk (Gemini)
│   │   └── utils.ts                          # Delte AI-hjelpere
│   ├── aiHybrid.ts                           # Edge-first orkestrering (lokal fallback fjernet)
│   ├── export/                               # Eksport-moduler
│   │   ├── docx.ts                           # DOCX-generering
│   │   ├── epub.ts                           # EPUB 3 e-bok generering (XHTML + Cover)
│   │   ├── index.ts                          # Eksportør
│   │   ├── markdown.ts                       # Markdown-generering
│   │   ├── mp3.ts                            # Lyd-sammenstilling (MP3 64kbps / WAV)
│   │   ├── pdf.ts                            # PDF-generering med avansert formatering
│   │   ├── pptx.ts                           # PowerPoint-generering (Non-Fiction)
│   │   ├── utils.ts                          # Delte eksport-hjelpere (Mermaid render)
│   │   ├── video.ts                          # Videorendring (MP4 H.264/AAC, 16:9 / 9:16) med "Smart Split"
│   │   └── website.ts                        # Interaktiv nettside-pakking (ZIP)
│   ├── format/                               # Tekstformatering
│   │   └── sectionHeaders.ts                 # Håndtering av kapitteloverskrifter og språk
│   ├── i18n/                                 # Internasjonalisering
│   │   └── translations.ts                   # Oversettelser (14 språk) for UI og eksport
│   ├── prompts/                              # Lokale prompt-moduler (split refaktor)
│   │   ├── README.md                         # Modulgrense + safe refactor-regler
│   │   ├── core.ts                           # Delte lokale prompt-konstanter/hjelpere
│   │   ├── referencePrompts.ts               # Fil-/media-analyse prompts
│   │   ├── settingsPrompts.ts                # Settings + enhance-idea prompts
│   │   ├── chapterPrompts.ts                 # Chapter/section + export/QA/TTS prompts
│   │   └── fragments/                        # Re-export av shared fragments
│   │       ├── markdownRules.ts              # MD-regler (fra shared/prompts)
│   │       ├── mermaidRules.ts               # Mermaid-regler (fra shared/prompts)
│   │       ├── mermaidSyntaxV11.ts           # Mermaid v11 syntaks (shared)
│   │       └── professionalVisualization.ts  # Visualiseringsstrategi (shared)
│   ├── sanitize/                             # Rens og validering
│   │   └── mermaidFixer.ts                   # Self-healing Mermaid logikk
│   └── styles/                               # Stildefinisjoner
│       ├── config.ts                         # Globale stilvariabler
│       ├── docx.ts                           # DOCX-spesifikke stiler
│       ├── helpers.ts                        # Hjelpefunksjoner for farger/størrelser
│       ├── index.ts                          # Eksportør
│       ├── pdf.ts                            # PDF-spesifikke stiler
│       ├── types.ts                          # Type-definisjoner for stiler
│       └── units.ts                          # Enhetskonvertering (mm, px, pt)
├── shared/                                   # Delt kode mellom frontend og Edge Functions
│   ├── billing/                              # Abonnement- og tier-konfigurasjon
│   │   ├── productPolicy.ts                  # Produktpolicy (kreditt-utløp, top-up regler)
│   │   └── tierPresets.ts                    # Tier-definisjoner (Free/Starter/Pro/Enterprise)
│   ├── fiction/                              # Fiction-spesifikk logikk
│   ├── routing/                              # Intelligent model routing
│   │   ├── decision.ts                       # Routing-beslutningsmotor
│   │   ├── mapping.ts                        # Modell-til-oppgave mapping
│   │   ├── types.ts                          # Routing-types
│   │   └── index.ts                          # Eksportør
│   ├── suggestSettings/                      # Delt suggest-settings logikk
│   └── prompts/                              # Prompt source-of-truth (core generation flows)
│       ├── builders/                         # Prompt-builders for Edge flows
│       │   ├── sectionPrompt.ts              # ai-generate-section
│       │   ├── planPrompt.ts                 # ai-plan
│       │   ├── suggestPrompt.ts              # ai-suggest-prompt
│       │   ├── suggestSettingsPrompt.ts      # ai-suggest-settings
│       │   └── mermaidFixPrompt.ts           # ai-mermaid-fix
│       ├── fragments/                        # Delte prompt-fragmenter
│       │   ├── markdownRules.ts              # Markdown-regler
│       │   ├── mermaidRules.ts               # Mermaid-regler
│       │   ├── mermaidSyntaxV11.ts           # Mermaid v11 syntaks
│       │   └── professionalVisualization.ts  # Visualisering
│       └── index.ts                          # Stabil eksportflate
├── supabase/                                 # SUPABASE BACKEND (Edge Functions + DB)
│   ├── config.toml                           # Supabase lokal konfigurasjon
│   ├── deno.json                             # Deno konfigurasjon for Edge Functions
│   ├── functions/
│   │   ├── _shared/                          # Delt logikk for alle Edge Functions
│   │   │   ├── utils.ts                      # Auth, allowlist, kvote/credit-håndtering
│   │   │   ├── openai.ts                     # OpenAI Responses API helper (server-side)
│   │   │   ├── pricing.ts                    # Pris- og kredittkonvertering (server-side)
│   │   │   ├── rateLimit.ts                  # Upstash Redis rate limiting
│   │   │   ├── genres.ts                     # Delt sjangerdata
│   │   │   ├── genreOptions.ts               # Delt sub-option data
│   │   │   ├── types.ts                      # Delte Edge Function-typer
│   │   │   ├── vertexAuth.ts                 # Vertex AI autentisering (service account JWT)
│   │   │   └── vertexGemini.ts               # Vertex AI Gemini API-klient
│   │   ├── ai-admin-adjust-credits/          # Admin: kredittjustering (+/-)
│   │   ├── ai-admin-list-users/              # Admin: brukerliste/status/tier/limits
│   │   ├── ai-admin-manage-flags/            # Admin: legg til/løs opp brukerflagg
│   │   ├── ai-admin-update-user/             # Admin: allowlist + tier-endring
│   │   ├── ai-analyze-file/                  # Analyse av opplastede filer (multimodal)
│   │   ├── ai-codex-postcheck/               # Post-check revisjon (OpenAI Codex, non-fiction)
│   │   ├── ai-final-review/                  # Helhetlig QA Memo (whole-document review)
│   │   ├── ai-generate-section/              # Server-side generering (SSE Streaming)
│   │   ├── ai-image/                         # Bildegenerering (Imagen 4.x)
│   │   ├── ai-mermaid-fix/                   # Mermaid-fiksing med AI
│   │   ├── ai-plan/                          # Planleggings-agent (Google Search)
│   │   ├── ai-quota-sync/                    # Google Cloud kvote-synkronisering
│   │   ├── ai-script-convert/                # Konvertering til filmmanus
│   │   ├── ai-stripe-checkout/               # Oppretter Stripe Checkout for kredittkjøp
│   │   ├── ai-stripe-portal/                 # Stripe Customer Portal (abonnement)
│   │   ├── ai-stripe-subscription-checkout/  # Oppretter Stripe Checkout for abonnement
│   │   ├── ai-stripe-webhook/                # Verifiserer betaling og fyller kreditter
│   │   ├── ai-suggest-prompt/                # Prompt-forbedring
│   │   ├── ai-suggest-settings/              # Innstillings-anbefalinger
│   │   ├── ai-summarize/                     # Oppsummerings-agent
│   │   ├── ai-tts/                           # Tekst-til-tale (Gemini TTS)
│   │   ├── ai-user-profile/                  # Brukerprofil, entitlements og feature-flagg
│   │   ├── qr-login/                         # QR login (create/authorize/exchange)
│   │   ├── url-analyze/                      # Analyse av nettsider (Scraping)
│   │   └── deno.d.ts                         # Supplerende module declarations
│   └── migrations/                           # Database-migrasjoner
│       ├── 20260120000000_quota_system.sql                    # Kvote-system tabeller og RPC
│       ├── 20260129000000_add_credits_columns.sql             # Credits-kolonner og flyt
│       ├── 20260216160000_fix_credit_idempotency_by_type.sql  # Idempotens-fiks for kreditt-trekk
│       ├── 20260216173000_create_admin_users_table.sql        # Admin-brukere tabell
│       └── ...                               # Videre fixes/cleanup migrasjoner
└── utils/                                    # Generelle hjelpefunksjoner
    ├── audio.ts                              # PCM/WAV-hjelpere (lavnivå)
    ├── dom.ts                                # DOM-manipulasjon
    └── fileParser.ts                         # Parsing av opplastede filer (.txt gjenoppretting)
```
### Nøkkelkomponenter forklart

* `services/ai/chapters.ts`: Kjernen i innholdsgenereringen. Bruker nå "Smart Chunking" for å bevare linjeskift i TTS-tekst, noe som er kritisk for korrekt videorendring og synkronisering.
* `services/export/video.ts`: Videomotor som bruker Canvas API og WebCodecs. Har innebygd logikk for å splitte lange overskrifter fra brødtekst visuelt.
* `services/export/website.ts`: Genererer en komplett HTML/CSS/JS-pakke som lar brukeren navigere i historien interaktivt.
* `services/sanitize/mermaidFixer.ts`: Intelligent "selvhelbredende" modul som oppdager syntaksfeil i Mermaid-diagrammer og fikser dem automatisk.
* `components/views/AdminUsersView.tsx`: Separat admin-view for brukerliste, allowlist-status, tier-endringer, kredittjustering og brukerflagg.
* `components/views/QuotaHealthView.tsx`: Dedikert dashboard for overvåking av Google Cloud API-kvoter med automatisk synkronisering og helseberegning.
* `components/views/CompleteView.tsx`: Ferdig-visning med nedlasting, Final Review Preview (QA Memo), og prosjekthandlinger.
* `shared/prompts/*`: Felles prompt source-of-truth for kjerneflytene (`ai-generate-section`, `ai-plan`, `ai-suggest-*`, `ai-mermaid-fix`) slik at frontend og Edge Functions bruker samme instruksjonsgrunnlag.
* `shared/routing/*`: Intelligent model routing-motor som velger optimal AI-modell basert på oppgavetype, kategori, kreativitet og genre.
* `shared/billing/*`: Produktpolicy og tier-presets (`productPolicy.ts`, `tierPresets.ts`) som definerer kredittregler, utløpspolicyer og tier-grenser.
* `scripts/check-prompt-drift.mjs`: Drift-guard som stopper innføring av nye inline core-prompts i Edge Functions.
* `supabase/functions/_shared/utils.ts`: Delt logikk for Edge Functions inkludert auth, allowlist, admin checks, kvote-reservering og brukslogging.
* `supabase/functions/_shared/vertexAuth.ts`: Vertex AI autentisering via service account JWT for direkte Google Cloud API-tilgang.
* `supabase/functions/_shared/pricing.ts`: Server-side prismapping (`USD -> credits`) for konsistent kredittbelastning.
* `supabase/functions/ai-final-review/`: Helhetlig QA-agent som leser hele det genererte dokumentet og returnerer et strukturert QA-memo med verdict, prioriterte tiltak og seksjonsspesifikke issues.
* `supabase/functions/ai-quota-sync/`: Synkroniserer og returnerer normaliserte Google Cloud kvote-snapshots for Quota Health-dashboardet.
* `supabase/migrations/20260120000000_quota_system.sql`: Database-migrasjon med tabeller for `entitlements`, `usage_counters`, `usage_events` og atomiske RPC-funksjoner.

</details>

---

## 🚀 Tilgang & Installasjon

Kildekoden til Story Engine er for tiden i et privat repository (novel-planner) for å beskytte immaterielle rettigheter (IP). Dette repoet fungerer som teknisk dokumentasjon.

For investorer, partnere eller utviklere som har fått tildelt tilgangsrettigheter, gjelder følgende oppsett:

### 🛠️ Forutsetninger
*   **Node.js**: v20+
*   **Deno**: v2.6.8+ (for Edge Functions)
*   **Supabase CLI**: v2.76.3+

### 🚀 Installasjon

1.  **Klon kildekode-repoet**
   (Krever autorisasjon)
    ```bash
    git clone https://github.com/engan/novel-planner.git
    cd novel-planner
    ```

2.  **Installer avhengigheter**
    ```bash
    npm install
    ```

3.  **Sett opp miljøvariabler**
    Lag en `.env.local` fil i rotmappen og legg inn Supabase-oppsett:
    ```env
    VITE_SUPABASE_URL=https://<project-ref>.supabase.co
    VITE_SUPABASE_ANON_KEY=<anon-key>
    ```
    For enkelte lokale testskript kan du i tillegg trenge:
    ```env
    VITE_GEMINI_API_KEY=din_nøkkel_her
    ```

    For server-side AI (Supabase Edge Functions) må hemmelige nøkler settes som Supabase secrets
    (ikke kun i `.env.local`). Codex post-check (fase 1) bruker OpenAI Responses API og styres
    av server-side feature flags:
    ```bash
    supabase secrets set OPENAI_API_KEY=sk-...
    supabase secrets set CODEX_POSTCHECK_MODE=non-fiction-only
    # optional toggles / tuning:
    # supabase secrets set ENABLE_CODEX_POSTCHECK=true
    # supabase secrets set CODEX_POSTCHECK_MODEL=gpt-5.3-codex
    # current backend default is 2 credits unless overridden:
    # supabase secrets set CODEX_POSTCHECK_CREDITS=2
    # set to 0 only for temporary testing / non-billed validation
    # supabase secrets set CODEX_POSTCHECK_MAX_INPUT_CHARS=120000
    # supabase secrets set CODEX_POSTCHECK_TIMEOUT_MS=60000
    # supabase secrets set CODEX_POSTCHECK_MAX_RETRIES=1
    ```

    **Codex post-check (fase 1) flyt (non-fiction):**
    1. `ai-generate-section` genererer seksjonstekst med Gemini 3.1 Pro.
    2. Klienten sender ferdig seksjonstekst til `ai-codex-postcheck` (server-side) for revisjon.
    3. Codex returnerer full revidert tekst (eller blir hoppet over / fallback ved feil).
    4. Story Engine kjører fortsatt Mermaid-validering etterpå som ekstra sikkerhetsnett.

4.  **Start utviklingsserveren**
    ```bash
    npm run dev
    ```
---

## 📝 Endringslogg

Kortversjon av siste endringer. Full historikk finnes i `CHANGELOG.md` (og i GitHub Releases).

### Siste endringer (Mars 2026)
- 🔍 **Final Review**: Ny `ai-final-review` Edge Function for helhetlig dokumentkvalitetsvurdering (QA Memo). Returnerer verdict, priority actions, og seksjonsspesifikke issues. Synlig i CompleteView under "Final Review Preview".
- 🧭 **Model Routing**: Ny `shared/routing/`-modul med intelligent modellvalg basert på oppgavetype, kategori, kreativitet og genre. Erstatter hardkodede modellvalg.
- � **Quota Health**: Ny `QuotaHealthView` og `ai-quota-sync` for sanntids-overvåking av Google Cloud API-kvoter.
- 💳 **Billing/Tiers**: `shared/billing/` med `productPolicy.ts` og `tierPresets.ts` for komplett tier-konfigurasjon (Free/Starter/Pro/Enterprise).
- ☁️ **Vertex AI**: Ny `vertexAuth.ts` og `vertexGemini.ts` i `_shared/` for direkte Vertex AI-tilgang via service account JWT.
- 🧠 **Prompt Engineering**: Utvidet `shared/prompts/` med human-nuance prompt-modi og A/B-evalueringsskript.
- 🎬 **Video**: Mermaid-diagrammer viser nå "Diagram er utelatt i video"-melding. Smart Split for perfekt typografi.
- 📄 **PDF/DOCX**: Inline math støttes som kursiv tekst. Forbedret word-wrap i kodeblokker.
- �️ **Admin**: Utvidet `AdminUsersView` med brukerflagg, tier-endringer og detaljert brukerinfo.

> Tips: Bruk GitHub Releases for "release notes", og hold `CHANGELOG.md` som den tekniske kilden.

---

## 🗺️ Veikart

Vi bygger fremtidens publiseringsverktøy. Her er hva som er aktivt og planlagt:

### Aktive planer (Q1-Q2 2026)
*   🔁 **Multi-Round Final Review**: Bevaring av QA-memo historikk på tvers av "Remake"-handlinger, slik at AI-en husker sine tidligere revisjonsforslag. Se `docs/active-plans/final-review-multi-round-strategy.md`.
*   🔧 **Guided Patch Mode** (deferred): Fremtidig utvidelse der AI-en foreslår konkrete, seksjonsmålrettede tekstendringer basert på QA-memoet. Se `docs/active-plans/final-review-guided-patch-decision-packet.md`.
*   🌐 **Social Media Link Analysis**: Utvidelse av "Analyze Link" til YouTube-transkripter, X/Twitter-poster, Facebook/Instagram (oEmbed) og Gemini-basert videoanalyse. Se `docs/social-media-link-analysis-plan.md`.
*   ☁️ **Vertex AI Phase 2 Migration**: Full migrering fra Gemini Developer API til Vertex AI for bedre kvoter, SLA og enterprise-features.

### Fremtidige visjoner
*   📰 **Integrasjon mot Retriever/Mediearkivet**: For dypere faktasjekk mot norske kilder.
*   🗣️ **Multi-LLM Konsensus-debatt**: La flere AI-modeller diskutere en sak før konklusjon trekkes.
*   📻 **Advanced Audio (Radio Play)**: Lydeffekter og bakgrunnsmusikk mikset med fortellerstemmen.
*   🗞️ **Pilotprosjekt med lokalavis**: Test av "Breaking News"-agent (f.eks journalist, etter avtale).
*   📱 **PWA-støtte**: Full offline-støtte for journalister i felt (etter avtale).

---

## 🎵 Bonus: The Story Engine Anthem

Fordi en multimodal AI-plattform fortjener sitt eget lydspor. Tekst og melodi er generert for å fange essensen av overgangen fra idé til ferdig produkt.

> *"Story Engine / Turning one small flame to a wildfire..."*

[▶️ **Hør sangen her (Suno)**](https://suno.com/s/bYmMmpVi77OgbCm2)

---

<details>
  <summary>📊</summary>
  <img src="https://komarev.com/ghpvc/?username=engan&label=V&color=0e75b6&style=flat" alt="Besøksstatistikk" />
</details>

<div align="center">
  <p>Utviklet med ❤️ i Norge</p>
  <p>© 2025-2026 Story Engine</p>
</div>
