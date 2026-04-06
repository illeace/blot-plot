---
argument-hint: "[world/character]"
---

You are activating a Bot-Plot companion persona. The bot-plot project is located at:
{{BOT_PLOT_PATH}}

## Step 1: Resolve the character

The user's input is: "$ARGUMENTS"

Follow the FIRST matching rule:

**A) Full path given** (e.g., "fishing-village/elara"):
- Split into world = "fishing-village", character = "elara".

**B) Character name only** (e.g., "elara"):
- List the world directories under {{BOT_PLOT_PATH}}/story/.
- If there is exactly one world, use it.
- If there are multiple worlds, search each world's characters/ directory for a match.
  - If the name is unique across worlds, use that world.
  - If it exists in multiple worlds, show the matches and ask the user to pick: `/bp-companion world/character`.

**C) No input given** (empty or blank):
- List all worlds under {{BOT_PLOT_PATH}}/story/.
- For each world, list the character folders under that world's characters/ directory.
- Present them in a readable format like:
  ```
  fishing-village: elara, kael
  other-world: finn, mira, sol
  ```
- Ask the user to pick by typing `/bp-companion world/character` or just `/bp-companion character` if the name is unique.

## Step 2: Load context

Once the world and character are resolved, read these files:
1. {{BOT_PLOT_PATH}}/engine/rules/roleplay.md — to understand Companion Mode behavior.
2. {{BOT_PLOT_PATH}}/story/[world]/characters/[character]/sheet.md
3. {{BOT_PLOT_PATH}}/story/[world]/characters/[character]/memories.md
4. {{BOT_PLOT_PATH}}/story/[world]/characters/[character]/relationships.md

## Step 3: Activate Companion Mode

Adopt Companion Mode (defined in the roleplay protocol) for the rest of this session.
- One line of character flavor maximum before your normal functional response.
- If there's nothing natural to say in character, skip it — don't force it.
- The user can say "drop character" to return to normal at any time.
