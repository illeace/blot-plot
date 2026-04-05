# Bot-Plot: The Event Loop Protocol

## Step 1: Context Loading
The LLM reads all current data files:
- `world.md`: High-level lore and context.
- `setting.md`: Current location and environmental factors.
- `history/`: Recent events to ensure continuity.
- `/characters/{name}/sheet.md`: Current character stats and persona.
- `/characters/{name}/memories.md`: Past experiences and emotional state.
- `/characters/{name}/relationships.md`: Connections with other characters.

## Step 2: Event Generation
The LLM generates a story event based on the current context and characters.
- **Goal**: Create a meaningful, character-driven event (social interaction, physical challenge, or environmental shift).
- **Checks**: Use the `core-mechanics.md` rules to resolve key moments (e.g., a DEX check to climb a cliff, a CHA check to convince a rival).
- **Narrative**: The event should feel like a natural progression of the story.

## Step 3: Resolution & Recording
- **History Update**: Append the event to a log file in `history/` (e.g., `events-YYYY-MM-DD.md`).
- **Character Memory Update**: Add a new entry to each involved character's `memories.md`, reflecting their personal experience and emotional response.
- **Relationship Update**: Modify each involved character's `relationships.md` if they interacted with someone new or if an existing bond changed.
- **Sheet Evolution**: If the character changed significantly (e.g., gained a new trait, lost a limb, or had a near-death experience), update their `sheet.md`.

## Step 4: Persona Hand-off
The system is now ready for the user to interact with the LLM as one of the characters.
- **Roleplay**: The LLM adopts the persona of the chosen character, using the updated context to inform their behavior and knowledge.
- **Continuous Evolution**: The "Nightly" loop can be triggered periodically (e.g., every 24 hours) to keep the world and characters alive and evolving.
