# TimeVerse Explorer - Requirements Document

## 1. Core Look & Feel (UI/UX)
*   **Aesthetic Match:** Must be an exact 1:1 match with the Geography module. Maintain the same dark-mode color scheme, Glassmorphism `.glass-panel` UI, and button CSS styling.
*   **Header Elements:** Use similar emojis, title framing, an italicized curiosity byline, matching fonts (Outfit), and identical navigation flows.
*   **Footer & About:** Same legal/parental guardian disclaimer at the bottom syncing to the exact same kid-safe sandboxing "About" screen methodology and Kiddle.co redirects.

## 2. Session Scoring & Architecture
*   **State Machine:** Utilize the exact same fast, local Single Page Application (SPA) DOM manipulation.
*   **Feedback Loop:** 5-question rounds, running score persistence (total points + accuracy %), and the 'Keep Playing' vs 'Save Score & End Game' mechanic. High scores must be identically saved to the local web storage.

## 3. Play Frame Structure (The Modes)
The main lobby UI will feature the 3-split grid layout for game mode selection:

*   **Area 1 (Left): "Random History Trivia"**
    *   Pulls historical data specifically from the OpenTDB API dynamically.
*   **Area 2 (Middle): Special Visual Challenge**
    *   *(Agreed Point)* **Ancient Civilizations & Dynasties:** Trivia solely focused on sprawling empires (Gupta, Chola, Ming, Roman, Ottoman, Mayan).
    *   *(Proposed Idea A)* **Famous Monuments Challenge:** A direct mirror of the Geography "Flag Challenge" where kids are shown visual pictures (the Colosseum, Taj Mahal, Pyramids, etc.) and must identify the builder, era, or location!
    *   *(Proposed Idea B)* **"Who Am I?":** A visual portrait mode to guess famous historical figures.
*   **Area 3 (Right): "Specific Categories"**
    *   Reveals the offline-generated 3-column static grid.

## 4. Static Data Categories (The DB Structure)
Using the exact 3-column structural layout as Geography, broken strictly into US, World, and India.

**The 5 Core Modules:**
1. Wars, Battles & Conflicts
2. Famous People & Structures
3. Key Movements & Events
4. Inventions & Discoveries
5. Culture, Society & Art

**Example Matrix:**

| Category | USA Example | World Example | India Example |
| :--- | :--- | :--- | :--- |
| **Wars, Battles & Conflicts** | Civil War | World War II | Battle of Panipat |
| **Famous People & Structures** | Lincoln / Statue of Liberty | Joan of Arc / Great Wall | Ashoka / Red Fort |
| **Key Movements & Events** | Civil Rights Movement | French Revolution | Dandi March |
| **Inventions & Discoveries** | Lightbulb (Edison) | Printing Press | Zero (Aryabhata) |
| **Culture, Society & Art** | Jazz Age | Greek Myths | Vedic Traditions |
