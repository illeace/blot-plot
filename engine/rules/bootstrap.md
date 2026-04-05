# Bot-Plot: Bootstrap Protocol

Use this protocol when the user wants to initialize a new story world.

## Phase 1: Gathering Information
Ask the user the following questions (one at a time or together):
1.  **World Theme**: What is the general genre or setting? (e.g., High Fantasy, Cyberpunk, etc.)
2.  **Starting Setting**: Where does the story begin? (e.g., a derelict space station, a frontier tavern, etc.)
3.  **Initial Focus**: Any specific themes or character concepts you want to start with?

## Phase 2: Directory & File Creation
Once the user provides the theme, create the following structure:
1.  `story/[world-name]/world/`: Create `world.md`, `setting.md`, and `facts.md`.
2.  `story/[world-name]/characters/`: Create folders for at least two starting characters, each with `sheet.md`, `memories.md`, and `relationships.md`.
3.  `story/[world-name]/events/`: Create `log.md`.
4.  `story/[world-name]/user-notes/`: Create this directory for the user's private notes (you MUST NOT read this).
5.  `story/[world-name]/`: Create `status.md`.

## Phase 3: Content Generation
- **World & Setting**: Populate `world.md` and `setting.md` based on the user's theme.
- **Initial Characters**: Create two compelling, contrasting characters with d20 stats (use `engine/templates/sheet.md`).
- **Initial Memories**: Give each character one or two significant past memories.
- **Initial Relationships**: Define how the two characters know each other.

## Phase 4: Handoff
Confirm the world is initialized and summarize the current state. Ask the user if they want to:
- Run the first **Event Loop** (Day 1).
- **Roleplay** with one of the characters.
- Add more characters or details to the world.
