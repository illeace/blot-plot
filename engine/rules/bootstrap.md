# Bot-Plot: Bootstrap Protocol

> **Operating Mode Reminder**: This file is part of the **Bot-Plot Engine**. Modifications to this file require **Meta Mode**. If you are simply using this protocol to create a new world, you are in **World Mode**.

Use this protocol when the user wants to initialize a new story world.

## Phase 1: Guided Gathering (One Item at a Time)
Engage with the user to define the world's core. For each step, offer to help with brainstorming by providing choices or by taking over if the user is unsure.

1.  **Genre**: What is the general tone or overarching genre? (e.g., High Fantasy, 1940s Steampunk, Cyberpunk).
2.  **World**: What is the name of the world and its high-level premise? (e.g., Imegico, a magic-realist version of Mexico).
3.  **Starting Setting**: Where specifically does the story begin? (e.g., a tiered metropolis, a frontier tavern).
4.  **Characters**: 
    - Ask the user how many starting characters they'd like to create (Recommend a range of 2-10).
    - Discuss character concepts (roles, backgrounds, motivations).
5.  **Narrative Style**: What are the world-specific notes about story structure, tone, or pacing? (e.g., Episodic "Story-of-the-Week" structure, 7-30 day arcs).

## Phase 2: Directory & File Creation
Once the information is gathered, create the following structure:
1.  `story/[world-name]/world/`: Create `world.md`, `setting.md`, and `facts.md`.
2.  `story/[world-name]/characters/`: Create folders for each character.
3.  `story/[world-name]/events/`: Create `_log.md`.
4.  `story/[world-name]/user-notes/`: Create this directory for the user's private notes (you MUST NOT read this).
5.  `story/[world-name]/`: Create `status.md`.

## Phase 3: Content Generation
- **World & Setting**: Populate `world.md` (including the **Narrative Style** section) and `setting.md` based on the gathered info.
- **Initial Characters**: Create the requested number of compelling characters with d20 stats (use `engine/templates/sheet.md`).
- **Initial Memories**: Give each character at least one or two significant past memories.
- **Initial Relationships**: Define how the characters are connected to each other.

## Phase 4: Handoff
Confirm the world is initialized and summarize the current state. Ask the user if they want to:
- Run the first **Event Loop** (Day 1).
- **Roleplay** with one of the characters.
- Add more characters or details to the world.
