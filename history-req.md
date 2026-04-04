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
*   **Area 2 (Middle): "History's Mysteries" (Mixed Visual Mode)**
    *   This center pillar will seamlessly randomly shuffle and mix three distinct visual challenge types together during a round:
        1. **Ancient Civilizations & Dynasties:** Image-based trivia focused on sprawling empires and maps (e.g. Gupta, Ming, Roman, Mayan).
        2. **Famous Monuments Challenge:** A mirror to the "Flag Challenge" where kids are shown visual architectural pictures (e.g. Colosseum, Taj Mahal, Pyramids) and must identify the builder, location, or era.
        3. **"Who Am I?":** A visual portrait mode to guess famous historical figures from their paintings/photos.
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

## 5. Game Mechanics & Polish (Learnings from GeoVerse)
To preserve the identical user experience and technical reliability refined in the Geography quiz, the following mechanics **must** be implemented exactly in HistoryVerse:

*   **Dynamic Wikipedia Context:** 
    *   **Hint Engine:** Utilize the `Wikipedia Extracts API` to auto-generate up to 2 hints per question dynamically. Use robust Regex to explicitly strip parenthetical text `(...)` from the fetch to prevent accidental translation/answer leaks. Include a visual fallback state when Wikipedia fails or when an answer is purely numerical.
    *   **Background Fetch:** Use the `Wikimedia Pageimages API` to fetch related thumbnails mapped to the answer, injected into a background at `25% opacity` to build contextual immersion dynamically.
    *   **Race-Condition Safety:** Network fetches must utilize an aggressive `fetchIdCounter` gating system upon resolution to prevent late-arriving Wikipedia packages from overwriting state when the user rapid-fires to the next question.
*   **The Fractional Scoring Engine (Pizzas):** 
    *   Score each question out of 1.0. Deduct exactly 0.2 points per hint taken.
    *   Implement the animated CSS geometric pie-chart "Pizza Tracker" that masks out a perfectly mathematical 72-degree slice visually per hint taken.
    *   Inject the cumulative `live-pizza-bank` across the top HUD so the player can intuitively grasp decimal accumulation across the 5 questions.
*   **Post-Round Polish:** 
    *   Calculate Accuracy safely post-round, avoiding unhandled reference variables that break execution strings.
    *   Draw the End-Screen Loot accurately (Full Pizzas vs Extra Slices) alongside scaled `canvas-confetti` fireworks directly multiplied by the player's final fractional score (no score = no confetti).
*   **Kid-Safe Web Flow:** 
    *   Enforce `kiddle.co/s.php?q=...` safe-search redirects for all "Know More" deep dives in the post-answer panel. 
