# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Help Desk & Dragons** is a Unity-based time management/panic simulator where the player is a wizard providing IT support to D&D adventuring parties. Tickets appear as windows on a desktop interface, requiring specific button sequences (X, Square, Circle, Triangle) to resolve. The game features continuous spawning with accelerating difficulty, periodic upgrade breaks, and inevitable failure as the core mechanic.

**Genre:** Time Management / Panic Simulator
**Platform:** PC (Unity), Controller & Keyboard
**Core Loop:** Clear tickets faster than they spawn, unlock upgrades on breaks, survive the accelerating chaos

## Unity Project Setup

**Target Unity Version:** 2022.3 LTS or newer
**Input System:** New Input System (for controller support)
**UI Framework:** Unity UI (Canvas-based)
**Target Resolution:** 1920x1080 base (scalable)

## Core Game Architecture

### Key Systems (From design-doc.md)

The game is built around several interconnected systems:

1. **Desktop Environment System** - Renders 1-4 monitor displays that can be upgraded, manages desktop space for window placement

2. **Window Management System** - Spawns ticket windows on monitors, handles overlapping, Z-order, focus/selection, and closing

3. **Ticket Spawner** - Continuous spawn with accelerating rate that increases over time and jumps after each break

4. **Ticket Window (Prefab)** - Core game object with:
   - `ButtonRequirements[]` array defining required button sequence (e.g., [X], [Square, Triangle], [Circle, X, Triangle])
   - State machine: Needs Input → Fixing → Complete → Closed
   - Progress bar showing fix completion
   - Randomized customer data (icon, name, problem text, ticket number)

5. **Button Input System** - Detects X/Square/Circle/Triangle presses, tracks sequences for focused window, matches against ButtonRequirements array

6. **Coffee System** - Speed drains from 100% to 50% over 90 seconds, affects all fix timer durations, limited charges per break

7. **Remote Access System** - Instant-complete selected window, limited charges

8. **Break & Upgrade System** - Triggers every ~2 minutes, pauses game, presents 3 random upgrades, player chooses 1

9. **Spawn Rate Controller** - Formula: `baseRate * timeMultiplier * breakMultiplier`, eventually reaches impossible rates

### Critical Component Structure

**TicketWindow.cs** - The core gameplay object:
- `ButtonType[] buttonRequirements` - Defines the exact sequence needed
- `int currentButtonIndex` - Tracks progress through sequence
- `WindowState currentState` - Needs Input/Fixing/Complete/Closed
- `fixTimer` and `fixDuration` - Modified by coffee speed multiplier
- Methods: `OnButtonPressed()`, `StartFixTimer()`, `MarkComplete()`, `CloseWindow()`

**GameState.cs** - Singleton managing global state:
- Monitor count, base speed, max resources
- Active upgrades list
- `RecalculateStats()` - Applies upgrade modifiers

**Upgrade.cs** - ScriptableObject defining upgrades:
- Categories: Monitor, Coffee, Speed, Utility, Weird
- `prerequisite` field for chained upgrades (e.g., Monitor 2 requires Monitor 1)
- `Apply(GameState)` method to modify game state

## Game Flow & Mechanics

### Core Gameplay Loop
1. Ticket window spawns on desktop
2. Player clicks to select/focus window
3. Window displays required ButtonRequirements (visual icons)
4. Player presses buttons in correct sequence
5. Correct sequence starts fix timer (3s base, modified by coffee speed)
6. Player switches to other tickets while timers run
7. When timer completes, return to window and close it
8. Repeat with increasing panic as spawn rate accelerates

### Progression System
- **No discrete waves** - continuous play with accelerating spawn rate
- Every ~2 minutes = break time (pause, choose 1 of 3 random upgrades)
- After break: spawn rate jumps significantly higher
- **Failure is inevitable** - spawn rate eventually exceeds human capability
- Goal: Survive as long as possible (theoretical max: ~15-20 minutes)

### Input Mapping
**Controller:**
- Left Stick = Move cursor
- A = Click/select window, mark done on completed tickets
- X/Square/Circle/Triangle = Start fix (when ticket requires that button)
- LB = Drink coffee
- RB = Remote access (instant complete)

**Keyboard:**
- Mouse = Click to select
- J/K/L/I = X/Square/Circle/Triangle equivalents
- Space/Enter = Mark completed ticket as done
- C = Drink coffee
- R = Remote access

## Development Phases (From design-doc.md)

### Phase 1: Core Mechanics (MVP)
- Single monitor, ticket window prefab, spawn system
- Click to select/focus, button input detection
- ButtonRequirements array with sequence matching
- Fix timer (3s, affected by coffee speed)
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

## Key Design Principles

### Button Sequence System
- Tickets show **clear visual button prompts** - player sees exactly what to press
- Sequences are uniform: Type 1 (1 button), Type 2 (2 buttons), Type 3 (3 buttons)
- Wrong button press = visual feedback (shake/error), no action
- Correct sequence completion = starts fix timer immediately
- **This is NOT a complex combo system** - it's simple sequence matching

### Escalation & Difficulty
- Spawn rate formula: `baseRate * timeMultiplier * breakMultiplier`
- Early game: ~1 ticket per 15 seconds
- Late game: ~1 ticket per 2-3 seconds
- Coffee management becomes critical to survival
- More monitors help but don't prevent inevitable death

### Upgrade Categories (Examples from design-doc.md)
- **Monitor**: Second/Third/Fourth Monitor, Ultrawide
- **Coffee**: Espresso Shot (+25% speed), Caffeine Pills (+2 charges), Coffee IV (slower drain)
- **Speed**: Mechanical Keyboard (+10%), Ergonomic Chair (+15%), Two Hands (work on 2 tickets simultaneously)
- **Utility**: Remote Desktop (+2 charges), Macro Keys (auto-complete Type 1), Auto-Close (completed tickets close after 2s)
- **Weird**: Intern (auto-completes random ticket, might fail), Chaos Mode (tickets worth 2x but spawn 50% faster)

### Visual Style
- Retro OS aesthetic (Windows 95/98 vibes)
- Color coding for buttons: X=blue, Square=pink, Circle=red, Triangle=green
- Desktop environment with monitor bezels, taskbar showing resources
- Wizard character in corner animating during gameplay

## Important Notes

- **Speed multiplier affects ALL fix timers** - coffee system is survival-critical
- **Upgrades are permanent for the run** - strategic choices matter
- **Some upgrades have prerequisites** - handle dependency chains (e.g., Monitor 3 requires Monitor 2)
- **Spawn rate continuously accelerates** - no safe plateau, only delayed death
- **Windows can overlap** - requires click-to-focus Z-order management
- **Fix timers run in background** - player juggles multiple simultaneous fixes

## Design Document Reference

The complete game design is in `design-doc.md` (v3.0), which includes:
- Detailed upgrade list (~20 upgrades)
- Complete technical specifications with component pseudo-code
- UI mockups and window design
- Audio/visual design direction
- Week-by-week development roadmap

Refer to design-doc.md for specific implementation details, upgrade descriptions, and balance tuning targets.

## MCP Server Usage Rules

### MANDATORY: Always use Context7 MCP for code generation
**When writing ANY C# code, Unity scripts, or implementing game features:**
1. **ALWAYS call `mcp__context7__resolve-library-id`** first to get documentation for relevant libraries (Unity, C#, Input System, etc.)
2. **ALWAYS call `mcp__context7__get-library-docs`** with the resolved library ID to retrieve up-to-date API documentation and best practices
3. Use the retrieved documentation to ensure code follows current Unity best practices and APIs
4. This applies to ALL code generation tasks, including:
   - Creating new C# scripts
   - Modifying existing Unity components
   - Implementing gameplay systems
   - Writing editor tools
   - Any other code-related tasks

**Example workflow for creating a Unity script:**
1. Call `resolve-library-id` for "Unity" or specific Unity packages (e.g., "Unity Input System")
2. Call `get-library-docs` with the resolved library ID and relevant topic (e.g., "MonoBehaviour lifecycle", "Input System actions")
3. Write code using the retrieved documentation as reference
4. Use Unity MCP tools to create/modify the script in the editor

### MANDATORY: Always use Unity MCP for editor operations
**When interacting with Unity Editor or build tooling:**
1. **Use Unity MCP resources** to read editor state before making changes:
   - Check `editor_state` resource for compilation status, play mode, etc.
   - Check `project_info` for project structure
   - Check `tests` resource for test status
2. **Use Unity MCP tools** for ALL Unity operations:
   - `manage_editor` - Play/pause/stop, editor state queries
   - `manage_scene` - Scene creation, loading, hierarchy inspection
   - `manage_gameobject` - GameObject and component operations
   - `manage_asset` - Asset import, creation, modification
   - `manage_script` / `script_apply_edits` - Script creation and editing
   - `manage_prefabs` - Prefab operations
   - `read_console` - Check for compilation errors after script changes
   - `run_tests` - Execute Unity test suites
3. **Always check `read_console`** after creating or modifying scripts to verify compilation success
4. **Never proceed** with operations that depend on new components/types until compilation completes

**Example workflow for creating a GameObject with custom component:**
1. Use Context7 to get Unity documentation for component implementation
2. Create the C# script using `manage_script` or `script_apply_edits`
3. Call `read_console` to verify compilation succeeded
4. Use `manage_gameobject` with action="create" to create GameObject
5. Use `manage_gameobject` with action="add_component" to attach the compiled component

### Integration Guidelines
- **Context7 is for KNOWLEDGE** - Use it to learn APIs, patterns, and best practices before writing code
- **Unity MCP is for EXECUTION** - Use it to actually create, modify, and inspect Unity project elements
- **Always use BOTH** when implementing Unity features:
  1. Context7 → Get documentation
  2. Write informed code
  3. Unity MCP → Apply to project
  4. Unity MCP → Verify results (console, editor state)

### Prohibited Actions
- **NEVER** write Unity code without consulting Context7 documentation first
- **NEVER** use generic file operations (Read/Write tools) for Unity scripts when Unity MCP tools are available
- **NEVER** assume compilation succeeded without checking `read_console`
- **NEVER** use bash commands for Unity operations when Unity MCP tools exist
