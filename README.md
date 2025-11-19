# Help Desk & Dragons

> IT support for D&D adventuring parties. Tickets flood your desktop. Clear them before you drown in windows.

**Genre:** Time Management / Panic Simulator
**Platform:** PC (Unity), Controller & Keyboard
**Session Length:** Until you break

## Overview

Help Desk & Dragons is a Unity-based panic simulator where you play as a wizard providing IT support to D&D adventuring parties. Tickets appear as windows on a retro desktop interface, each requiring specific button sequences (X, Square, Circle, Triangle) to resolve. The game features continuous spawning with accelerating difficulty, periodic upgrade breaks, and inevitable failure as the core mechanic.

**This is Papers, Please meets Overcooked meets WarioWare meets desktop chaos meets roguelike progression.**

## Core Gameplay Loop

1. Tickets spawn as windows on your desktop monitor(s)
2. Click/select a ticket to focus it
3. Press the correct button sequence displayed on the ticket
4. Fix timer starts (runs in background while you work on other tickets)
5. Return to completed tickets and mark them done
6. Tickets spawn faster and faster as time progresses
7. Manage coffee to maintain work speed
8. Every ~2 minutes, take a "cigarette break" and choose 1 of 3 random upgrades
9. Survive as long as you can - **failure is inevitable**

## Key Features

### Panic-Driven Gameplay
- **Continuous spawning** with no discrete waves - just accelerating chaos
- **Background fix timers** require juggling multiple tickets simultaneously
- **Overlapping windows** create desktop management challenges
- **Coffee system** - speed drains from 100% to 50%, requiring strategic caffeine management
- **Remote access** - limited instant-complete charges for emergencies

### Upgrade System
- Breaks every ~2 minutes present 3 random upgrades
- Choose 1 permanent upgrade per break
- **5 Categories:** Monitor, Coffee, Speed, Utility, Weird
- **Strategic depth** - upgrades have prerequisites and synergies
- Examples: Second Monitor, Espresso Shot, Macro Keys, Auto-Close, Chaos Mode

### Button Sequence Mechanics
- Clear visual prompts - you always see what to press
- **Type 1:** Single button (early game)
- **Type 2:** Two button sequence (mid game)
- **Type 3:** Three button sequence (late game)
- Wrong button = visual feedback, no penalty
- Correct sequence = immediately starts fix timer

### Inevitable Escalation
- Spawn rate formula: `baseRate * timeMultiplier * breakMultiplier`
- Early game: ~1 ticket per 15 seconds
- Late game: ~1 ticket per 2-3 seconds
- Theoretical max survival: ~15-20 minutes for perfect players
- **You will die. The question is: how long can you last?**

## Controls

### Controller (Primary)
- **Left Stick** - Move cursor
- **A Button** - Select window / Mark completed ticket done
- **X / Square / Circle / Triangle** - Start fix (when ticket requires that button)
- **LB** - Drink coffee
- **RB** - Remote access (instant complete)

### Keyboard (Alternative)
- **Mouse** - Click to select windows
- **J / K / L / I** - X / Square / Circle / Triangle equivalents
- **Space / Enter** - Mark completed ticket done
- **C** - Drink coffee
- **R** - Remote access

## Unity Project Setup

### Requirements
- **Unity Version:** 2022.3 LTS or newer
- **Input System:** New Input System (for controller support)
- **UI Framework:** Unity UI (Canvas-based)
- **Target Resolution:** 1920x1080 base (scalable)

### Project Structure
```
HelpDesk&Dragons/
├── Assets/
│   ├── Scripts/          # C# game logic
│   ├── Prefabs/          # Ticket windows, UI elements
│   ├── Scenes/           # Main game scene
│   ├── UI/               # UI sprites and materials
│   ├── Audio/            # Sound effects and music
│   └── ScriptableObjects/ # Upgrade definitions
├── ProjectSettings/      # Unity project configuration
└── Packages/            # Package dependencies
```

### Core Systems

The game is built around several interconnected systems:

1. **Desktop Environment System** - Renders 1-4 monitor displays, manages desktop space
2. **Window Management System** - Spawns tickets, handles overlapping, Z-order, focus
3. **Ticket Spawner** - Continuous spawn with accelerating rate
4. **Ticket Window (Prefab)** - Core game object with ButtonRequirements array, state machine, progress bar
5. **Button Input System** - Detects button presses, tracks sequences, matches requirements
6. **Coffee System** - Speed drain/restore, affects all fix timers
7. **Remote Access System** - Instant-complete with limited charges
8. **Break & Upgrade System** - Periodic breaks with upgrade selection
9. **Spawn Rate Controller** - Formula-driven acceleration towards impossible rates

### Key Components

**TicketWindow.cs** - The core gameplay object
- `ButtonType[] buttonRequirements` - Defines the exact sequence needed
- `WindowState currentState` - Needs Input / Fixing / Complete / Closed
- Methods: `OnButtonPressed()`, `StartFixTimer()`, `MarkComplete()`, `CloseWindow()`

**GameState.cs** - Singleton managing global state
- Monitor count, base speed, max resources
- Active upgrades list
- `RecalculateStats()` - Applies upgrade modifiers

**Upgrade.cs** - ScriptableObject defining upgrades
- Categories: Monitor, Coffee, Speed, Utility, Weird
- `prerequisite` field for chained upgrades
- `Apply(GameState)` method to modify game state

## Development Phases

### Phase 1: Core Mechanics (MVP)
- Single monitor, ticket window prefab, spawn system
- Click to select, button input detection
- ButtonRequirements array with sequence matching
- Fix timer (3s base, affected by coffee speed)
- State visual feedback and completion

### Phase 2: Resources
- Coffee system (drain, refill, speed modifier)
- Remote access (instant close)
- Spawn rate acceleration

### Phase 3: Break & Upgrade System
- Break timer, upgrade selection screen
- 5-6 core upgrades initially
- Apply upgrades to game state

### Phase 4: Polish
- 15-20 total upgrades
- Randomized ticket flavor text
- Visual and sound effects

### Phase 5: Balance & Juice
- Spawn rate curve tuning
- Upgrade balance
- Visual polish, animations, screen shake

## Visual Style

- **Retro OS aesthetic** (Windows 95/98 vibes)
- **Color coding** for buttons: X=blue, Square=pink, Circle=red, Triangle=green
- **Desktop environment** with monitor bezels, taskbar showing resources
- **Wizard character** in corner animating during gameplay
- **Clear UI** with prominent button prompts on each ticket

## Design Philosophy

### Button Sequence System
- Tickets show **clear visual button prompts** - player sees exactly what to press
- Sequences are uniform by type (1/2/3 buttons)
- Wrong button press = visual feedback (shake/error), no action
- Correct sequence completion = starts fix timer immediately
- **This is NOT a complex combo system** - it's simple sequence matching

### Escalation & Difficulty
- Spawn rate continuously accelerates - no safe plateau
- Coffee management becomes critical to survival
- More monitors help but don't prevent inevitable death
- Upgrades delay death but can't prevent it
- Goal: Maximize survival time and tickets cleared

### Upgrade Balance
- Early upgrades: Foundational (monitors, basic coffee)
- Later upgrades: Powerful/niche mechanics
- Some upgrades have prerequisites (Monitor chain)
- RNG ensures replayability - different paths each run
- Strategic choices matter - build synergies

## Getting Started

1. Clone this repository
2. Open the project in Unity 2022.3 LTS or newer
3. Open the main scene in `Assets/Scenes/`
4. Connect a controller or use keyboard controls
5. Press Play and start clearing tickets

For AI assistants working on this project, see `CLAUDE.md` for detailed development guidelines and MCP server usage rules.

## Documentation

- **[design-doc.md](design-doc.md)** - Complete game design document (v3.0) with technical specifications, upgrade list, UI mockups, and development roadmap
- **[CLAUDE.md](CLAUDE.md)** - Project instructions for Claude Code, including architecture guidelines and MCP server usage rules

## License

### Code License (MIT)

The source code for Help Desk & Dragons is licensed under the MIT License:

```
MIT License

Copyright (c) 2025 [Your Name/Organization]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

### Assets License (Proprietary)

All game assets including but not limited to:
- Graphics, sprites, textures, and visual art
- Audio files, music, and sound effects
- 3D models and animations
- Game design documents and written content

are **NOT** covered by the MIT License and remain the proprietary property of the copyright holder. These assets may not be used, reproduced, or distributed without explicit permission.

### Third-Party Licenses

This project may include third-party assets and libraries. See `THIRD_PARTY_LICENSES.md` for details on their respective licenses.

## Credits

**Game Design & Development:** [Your name/team]
**Concept:** Help desk wizard providing IT support to fantasy adventurers
