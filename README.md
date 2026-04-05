# Bot-Plot: World-Agnostic Character & Story System

**Bot-Plot** is a framework for creating and evolving character-driven stories and LLM personas. This system is designed to be world-agnostic, providing a simple data structures and even loop for creating worlds, characters, and stories.

## Project Structure

- `engine/`: The core system files (the "Engine").
  - `rules/`: Game mechanics and protocols.
  - `templates/`: Markdown templates for all data types.
- `story/`: Instance-specific world data (the "Save Games").
  - `[world-name]/`: A specific world "run".
    - `world/`: World and setting descriptions.
      - `world.md`: High-level world/genre description.
      - `setting.md`: Specific setting for this story.
      - `facts.md`: List of established world facts for consistency.
    - `characters/`: Character-specific data.
      - `[name]/`:
        - `sheet.md`: d20 character sheet.
        - `memories.md`: Event memories.
        - `relationships.md`: List of other characters and relationship description.
    - `events/`: Logs of generated events.
      - `log.md`: A ledger describing the daily event(s) (one paragraph per event).
      - `day-nnnn.md`: Detailed daily event descriptions (e.g., day-0001.md).

## Getting Started

### 1. Bootstrapping a New World
To start a new project, follow these steps:
- **Choose a Setting**: Decide on a theme (e.g., Space Opera, Post-Apocalyptic, etc.).
- **Define the World**: Use `engine/templates/world.md` to create your `world/world.md` in a new `story/[world-name]` folder.
- **Set the Scene**: Create a `world/setting.md` and `world/facts.md`.
- **Create Characters**: For each character, create a folder in `story/[world-name]/characters/` and populate `sheet.md`, `memories.md`, and `relationships.md` using the templates in `engine/templates/`.

### 2. The Nightly Event Loop
The core of Bot-Plot is the **Event Loop**, which evolves the story over time.
- **Read Context**: Load all current data files (world, characters, events).
- **Generate Event**: Use the rules in `engine/rules/event-loop.md` to resolve a new story moment.
- **Update Files**: Record the event in `events/dayX.md`, summarize it in `events/log.md`, and update character files and world facts as needed.

### 3. Roleplaying as a Character
The LLM agent can adopt any character's persona by loading their `sheet.md`, `memories.md`, and `relationships.md`. This context provides a rich background and evolving personality for interactions.

## Core Rules
The system uses a **Narrative d20** mechanic for resolving checks and events. See `engine/rules/core-mechanics.md` for details on stats, difficulty classes, and outcomes.

## Example Project
A complete example of a **Low Fantasy Fishing Village** is provided in `story/fishing-village/`. Use this as a reference for your own projects.
