# Story Engine Roadmap

This document captures future feature ideas and their priorities.

---

## 🟢 High Priority (Low Effort)

### EPUB Export
**Status:** Not started  
**Complexity:** Low  
**Value:** High for fiction authors

EPUB is essentially HTML + manifest files in a ZIP.

**Implementation:**
- Reuse existing `generateFullMarkdown` logic
- Convert Markdown to XHTML
- Pre-render Mermaid diagrams to PNG (already done for PDF)
- Generate `content.opf` manifest and `toc.ncx` navigation
- Package with JSZip

**Features:**
- Clickable table of contents
- Cover image as ebook thumbnail
- Metadata (author, description, genre) from plan
- Chapter images embedded

---

## 🟡 Medium Priority (High Impact)

### PowerPoint Export (Non-Fiction)
**Status:** Not started  
**Complexity:** Medium-High  
**Value:** Very high for business users

Transform reports into "boardroom-ready" presentations.

**Data Flow:**
```
Sanitized Markdown (per chapter)
        │
        ▼
┌──────────────────────────────────────┐
│  🤖 AI SUMMARIZATION PASS            │  ◄── New step (not in other exports)
│  "Extract 3-5 bullet points"         │
└──────────────────────────────────────┘
        │
        ▼
┌──────────────────────────────────────┐
│  Structured Slide Data:              │
│  - title: "Section 3: Costs"         │
│  - bullets: ["Point 1", "Point 2"]   │
│  - imageBase64: "..."                │
│  - diagramPng?: "..." (from Mermaid) │
└──────────────────────────────────────┘
        │
        ▼
┌──────────────────────────────────────┐
│  PptxGenJS                           │
│  Place text/images on slides         │
└──────────────────────────────────────┘
        │
        ▼
     .PPTX file
```

**Key Difference from Other Exports:**

| Export | Uses AI during export? | Input |
|--------|------------------------|-------|
| TXT/HTML | No | Sanitized markdown directly |
| PDF/DOCX | No* | Sanitized markdown → Layout engine |
| Website | No | Sanitized markdown → HTML template |
| **PPTX** | **Yes** | Sanitized markdown → AI summarizer → Slide data → PptxGenJS |

*PDF uses Mermaid pre-rendering but no AI text processing.

**Implementation:**
- Use [PptxGenJS](https://gitbrent.github.io/PptxGenJS/) library
- AI summarization pass: Extract 3-5 bullet points per section
- Design 2-3 master slide templates

**Slide Structure:**
1. Title slide (cover image + title + summary)
2. Agenda slide (from chapter plan)
3. Per-chapter slides (heading, bullets left, illustration right)
4. Full-screen diagram slides (Gantt, Quadrant, etc.)

**Extra Ideas:**
- "Presentation Tone" slider: Technical → Executive Summary
- Speaker notes generated from full chapter content

---

### PowerPoint Export (Fiction)
**Status:** Not started  
**Complexity:** Medium  
**Value:** Niche but powerful for pitching

Visual storyboard / moodboard for authors pitching to publishers or film producers.

**Slide Structure:**
- Full-bleed chapter images as backgrounds
- Atmospheric quote or turning point as overlay text
- Character cards with image and key traits

---

## 🔵 Future Ideas

### EPUB Export
**Status:** Not started  
**Complexity:** Low (basic) / High (with Media Overlays)  
**Value:** Universal for all content types

**Basic EPUB:**
- XHTML from markdown + cover image + metadata
- Works on all e-readers
- No audio synchronization

**EPUB 3 with Media Overlays (Talking Book):**
- Requires SMIL files for text-audio synchronization
- Currently blocked: Gemini TTS doesn't return per-sentence timing data
- Would need speech-to-text re-transcription or sentence-by-sentence TTS generation
- Limited reader support (Apple Books, Kobo – not Kindle)

---

### Audio Compression Options
**Status:** Under consideration  
**Decision:** Keep 128kbps MP3 for now, evaluate later

**Current flow:** PCM/WAV → MP3 128kbps at export time

**Options for future:**
1. Offer 64kbps option for smaller files (half size, minimal quality loss for speech)
2. Let user choose bitrate in download modal
3. Store both high/low quality versions (more memory but flexible)

**Preference:** If memory isn't a concern, prefer storing both versions for maximum flexibility.

---

### Vertical Video Export (9:16)
Social media optimized video for TikTok/Reels/Shorts with automatic subtitle animation.

### Advanced Audio (Radio Play)
AI-selected background music and sound effects.

### Parallel Localization
Multi-language export pipeline for generating content in several languages simultaneously.

### Automatic Source Overview
"Research Report" PDF listing all sources, citations, and credibility assessments when Google Search is used.

---

## Implementation Notes

All export features should:
1. Work 100% in the browser (no server required)
2. Use the same visual design language as existing exports
3. Support both fiction and non-fiction content types
4. Include production report metadata where applicable
