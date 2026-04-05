# Bot-Plot: The Event Loop Protocol

## Phase 1: Context Loading
The LLM reads all relevant files to understand the current state:
- `story/[world-name]/world/world.md`: High-level world/genre description.
- `story/[world-name]/world/setting.md`: Specific setting for this story.
- `story/[world-name]/world/facts.md`: Established facts and details.
- `story/[world-name]/characters/[name]/sheet.md`: Character stats and persona.
- `story/[world-name]/characters/[name]/memories.md`: Character experiences.
- `story/[world-name]/characters/[name]/relationships.md`: Character connections.
- `story/[world-name]/events/log.md`: Short summary of all past events.
- `story/[world-name]/events/dayX.md`: Detailed event descriptions for recent days (skip older ones if context becomes too large).

## Phase 2: Event Generation
The LLM generates a new event for the day:
1.  **Continuity**: Consider if the previous day's event should be continued or if a new story arc should begin.
2.  **Scale**: Events can be minor or trivial (e.g., a lost pet, a party, a harvest). The goal is an evolving world, like a long-running TTRPG or soap opera.
3.  **Characters**: 
    - Determine which characters are involved based on previous events and relationships.
    - Create and introduce new characters as needed (maintain a limit of 50 active living characters).
    - If a new character is significant, create a new folder with a `sheet.md`.
4.  **Resolution**: Use the `engine/rules/core-mechanics.md` to resolve any uncertain outcomes.

## Phase 3: Recording & State Update
1.  **Detailed Event**: Write the event in `story/[world-name]/events/dayX.md` (where X is the day number). Keep it under 600 words.
2.  **Summary Log**: Append a few sentences summarizing the event to `story/[world-name]/events/log.md`, grouped by day number.
3.  **Character Updates**:
    - If the event affects a character's body, possessions, relationships, or motivations, update their `.md` files in `story/[world-name]/characters/[name]/`.
4.  **World Facts**: If new meaningful facts are established that distinguish the world from its typical genre, record them in `story/[world-name]/world/facts.md`.

## Phase 4: Persona Interaction
The system is now updated, and the LLM agent can use the new context to play a character, answer questions about their life, or evolve the story further.
