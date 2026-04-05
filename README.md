# Bot-Plot: World-Agnostic Character & Story System

Welcome to **Bot-Plot**, a framework for creating and evolving character-driven stories and LLM personas. This system is designed to be world-agnostic, providing the data structures and rules for any genre (Fantasy, Sci-Fi, etc.).

## Project Structure

- `engine/`: The core system files (the "Engine").
  - `rules/`: Game mechanics and protocols.
  - `templates/`: Markdown templates for all data types.
- `story/`: Instance-specific world data (the "Save Games").
  - `[world-name]/`: A specific world "run".
    - `world.md`: High-level lore and context.
    - `setting.md`: Current location and environmental factors.
    - `characters/`: Character-specific data.
    - `history/`: Logs of generated events.

## Getting Started

### 1. Bootstrapping a New World
To start a new project, follow these steps:
- **Choose a Setting**: Decide on a theme (e.g., Space Opera, Post-Apocalyptic, etc.).
- **Define the World**: Use `engine/templates/world.md` to create your `world.md` in a new `story/[world-name]` folder.
- **Set the Scene**: Create a `setting.md` using the same template principles.
- **Create Characters**: For each character, create a folder in `story/[world-name]/characters/` and populate `sheet.md`, `memory.md`, and `relationship.md` using the templates in `engine/templates/`.

### 2. The Nightly Event Loop
The core of Bot-Plot is the **Event Loop**, which evolves the story over time.
- **Read Context**: Load all current data files (world, setting, characters, history).
- **Generate Event**: Use the rules in `engine/rules/core-mechanics.md` to resolve a new story moment.
- **Update Files**: Record the event in `history/` and update character memories, relationships, and sheets as needed.

### 3. Roleplaying as a Character
The LLM agent can adopt any character's persona by loading their `sheet.md`, `memory.md`, and `relationship.md`. This context provides a rich background and evolving personality for interactions.

## Core Rules
The system uses a **Narrative d20** mechanic for resolving checks and events. See `engine/rules/core-mechanics.md` for details on stats, difficulty classes, and outcomes.

## Example Project
A complete example of a **Low Fantasy Fishing Village** is provided in `story/fishing-village/`. Use this as a reference for your own projects.
