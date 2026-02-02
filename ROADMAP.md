# Story Engine Roadmap

This document captures future feature ideas and their priorities.

---

## 🟢 High Priority (Low Effort)

### Vertical Video Export (9:16)
**Target:** TikTok, Instagram Reels, YouTube Shorts  
**Status:** Ready to implement  
**Complexity:** Low  
**Value:** High for social media marketing

Reuse existing `mp4` logic but with crop and layout adjustments.

**Implementation Strategy:**
- **Zero Cost:** Reuse existing defined content (audio/text). No new generation needed.
- **Resolution:** 720x1280 (9:16 portrait) instead of 1280x720.
- **Background:** Center-crop the existing landscape image (zoom to fill heigth).
- **Layout:**
    - Hide Tables (too wide for phone screens).
    - Increase font size slightly for readability.
    - Adjust line-breaking for narrower width.
- **Format:** MP4 (H.264/AAC) only.

---

## 🟡 Medium Priority (High Impact)



### Advanced Audio (Radio Play)
**Status:** Concept  
**Value:** High immersion

AI-selected background music and sound effects mixed with the narration.

---

## 🔵 Future Ideas

### Parallel Localization
Multi-language export pipeline for generating content in several languages simultaneously.

### Automatic Source Overview
"Research Report" PDF listing all sources, citations, and credibility assessments.

---

## ✅ Completed Features (Phase 1)

### EPUB Export
**Status:** Implemented 🟢  
**Features:** Universal e-book format with cover, metadata, and chapter logic.

### Video Export (WebM & MP4)
**Status:** Implemented 🟢  
**Features:** Dual format support, "Smart Split" typography, synchronized audio.

### Auto-detect Language
**Status:** Implemented 🟢  
**Features:** Heuristic detection for Norwegian/English context.

---

## Implementation Notes

All export features should:
1. Work 100% in the browser (no server required)
2. Use the same visual design language as existing exports
3. Support both fiction and non-fiction content types
4. Include production report metadata where applicable
