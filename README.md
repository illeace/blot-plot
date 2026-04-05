# Bot-Plot: World-Agnostic Character & Story System

Welcome to **Bot-Plot**, a framework for creating and evolving character-driven stories and LLM personas. This system is designed to be world-agnostic, providing the data structures and rules for any genre (Fantasy, Sci-Fi, etc.).

## Getting Started

### 1. Bootstrapping a New World
To start a new project, follow these steps:
- **Choose a Setting**: Decide on a theme (e.g., Space Opera, Post-Apocalyptic, etc.).
- **Define the World**: Use `schema/world-template.md` to create your `world.md`.
- **Set the Scene**: Create a `setting.md` using the same template principles.
- **Create Characters**: For each character, create a folder in `/characters/` and populate `sheet.md`, `memories.md`, and `relationships.md` using the templates in `schema/`.

### 2. The Nightly Event Loop
The core of Bot-Plot is the **Event Loop**, which evolves the story over time.
- **Read Context**: Load all current data files (world, setting, characters, history).
- **Generate Event**: Use the rules in `rules/core-mechanics.md` to resolve a new story moment.
- **Update Files**: Record the event in `history/` and update character memories, relationships, and sheets as needed.

### 3. Roleplaying as a Character
The LLM agent can adopt any character's persona by loading their `sheet.md`, `memories.md`, and `relationships.md`. This context provides a rich background and evolving personality for interactions.

## Core Rules
The system uses a **Narrative d20** mechanic for resolving checks and events. See `rules/core-mechanics.md` for details on stats, difficulty classes, and outcomes.

## Example Project
A complete example of a **Low Fantasy Fishing Village** is provided in `examples/fishing-village/`. Use this as a reference for your own projects.

## Structure
- `/schema/`: Markdown templates for all data types.
- `/rules/`: Core mechanics and event loop protocols.
- `/examples/`: A sample world and character roster.
- `/history/`: Logs of generated events.
- `/characters/`: Current character data (each in its own folder).
