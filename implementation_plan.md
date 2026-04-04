# Building TimeVerse Explorer

This plan details the one-shot generation of the complete "TimeVerse Explorer" module based on our fully-polished Geography template, ensuring all mechanics smoothly carry over alongside seamless app-to-app cross-linking.

## Proposed Changes

### 1. Cross-Linking the Modules
#### [MODIFY] `index.html` (Geography)
- Inject a subtle, stylish navigation link in the universal footer: `🕰️ Jump to TimeVerse Explorer` pointing relatively to `../History/index.html`.

### 2. TimeVerse Scaffolding & Core UI
#### [NEW] `index.html` (History)
- **Rebranding:** Duplicate the `Geography/index.html` logic exactly, but rebrand all titles, headers, and metadata to **"🕰️ TimeVerse Explorer 🕰️"**.
- **Data Persistence:** Switch the `localStorage` high score key from `geoGridHighScores` to `timeVerseHighScores`.
- **Area 1 (Left Grid - Global API):** Update OpenTDB fetch API to uniquely target Category `23` (History), with UI rebranded to `"🕰️ Random History Trivia"`.
- **Area 2 (Middle Grid - Visuals):** Implement the requested `"History's Mysteries"` visual challenge. Instead of fetching flags, this will map to a curated offline array of 15 handpicked image URLs encompassing **Famous Monuments**, **Empires**, and **Ancient Portraits**. It will randomly shuffle these mechanics during gameplay.
- **Area 3 (Right Grid - Offline DB):** Update the UI grid buttons to reflect:
  - World / USA / India
  - Sub-categories: *Wars, Battles & Conflicts*, *Famous People & Structures*, *Key Movements & Events*, *Inventions & Discoveries*, *Culture, Society & Art*.
- **Cross-link Back:** Add `🌍 Jump to GeoVerse Explorer` to the TimeVerse footer, completing the loop.

#### [NEW] `data/questions.json` (History)
- Generate a fully formed JSON schema mirroring Area 3's setup. 
- Populate it with at least 5 baseline trivia questions for each category so that "Local Mode" functionality can be immediately tested and played without throwing "Category zeroed out" errors.

#### [NEW] `about.md` (History)
- Translate the offline instructional documentation to reflect TimeVerse.

## Executive Summary
Are you ready to execute this one-shot build? Once approved, I will sequentially duplicate, configure, and ignite the entirely functional History app based completely on our Geography findings!
