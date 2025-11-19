# Help Desk & Dragons - Core Design Document v3.0

## High Concept

IT support for D&D adventuring parties. Tickets flood your desktop. Clear them before you drown in windows.

**Genre:** Time Management / Panic Simulator  
**Platform:** PC (Unity), Controller & Keyboard  
**Session Length:** Until you break  
**Core Loop:** Clear tickets faster than they spawn, unlock upgrades on breaks, survive the accelerating chaos

---

## The Entire Game

### What You Do
1. Tickets appear as windows on your desktop monitor
2. Click/select tickets to open them
3. Press the correct button sequence to start the fix (X, Square, Circle, or Triangle)
4. Fix timer runs based on coffee speed
5. Switch to other tickets while timers run
6. Return to completed tickets and mark them done
7. Tickets spawn faster and faster as time goes on
8. Drink coffee to work faster
9. Every ~2 minutes, you get a "cigarette break" - choose 1 of 3 random upgrades
10. Survive as long as you can

### How You Lose
- **Failure is inevitable**
- Tickets spawn faster than humanly possible to clear
- Eventually you can't keep up
- Game measures how long you survived

### The Progression Loop
- **No waves** - just continuous play with increasing spawn rates
- Every ~2 minutes of survival = **Break time**
- During break: Choose 1 of 3 random upgrades
- Upgrades modify your capabilities for all future rounds
- Common upgrades: More monitors, better coffee, extra remote access charges, faster base speed
- After break: Back to work, tickets spawn even faster
- Repeat until death

---

## Controls

### Controller (Primary Input Method)
- **Left Stick** - Move cursor
- **A Button** - Click/select window
- **X Button** - Start fix (if ticket requires X)
- **Square Button** - Start fix (if ticket requires Square)
- **Circle Button** - Start fix (if ticket requires Circle)
- **Triangle Button** - Start fix (if ticket requires Triangle)
- **A Button (on completed ticket)** - Mark as done, close window
- **LB** - Drink coffee
- **RB** - Remote access (instant complete selected ticket)

### Keyboard (Alternative)
- **Mouse** - Click to select windows
- **J Key** - X equivalent
- **K Key** - Square equivalent  
- **L Key** - Circle equivalent
- **I Key** - Triangle equivalent
- **Space or Enter** - Mark completed ticket as done
- **C** - Drink coffee
- **R** - Remote access

**Core Flow:**
1. New ticket window pops up on desktop
2. Click it to select/focus it
3. Read which button it needs (displays icon: X, Square, Circle, or Triangle)
4. Press that button to start the fix timer
5. Switch to another ticket while first timer runs
6. When timer completes, return to that window
7. Press A/Enter to mark as done and close it
8. Repeat with increasing panic

---

## Desktop Environment

### Monitor Setup
- **Start:** Single monitor
- **Upgrades:** Can unlock 2nd, 3rd, 4th monitors via break upgrades
- More monitors = more space for simultaneous tickets
- But spawn rate keeps accelerating regardless

**Single Monitor**
```
â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
â”‚  [Desktop - 1 Monitor]              â”‚
â”‚                                     â”‚
â”‚  â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”  â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”       â”‚
â”‚  â”‚ Ticket 1 â”‚  â”‚ Ticket 3 â”‚       â”‚
â”‚  â”‚ðŸ—¡ï¸Barbarianâ”‚  â”‚ðŸ”®Wizard   â”‚       â”‚
â”‚  â”‚  Press: Xâ”‚  â”‚ Press: â—‹ â”‚       â”‚
â”‚  â”‚ â–“â–“â–“â–‘â–‘â–‘   â”‚  â”‚[DONE]    â”‚       â”‚
â”‚  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜       â”‚
â”‚       â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”                 â”‚
â”‚       â”‚ Ticket 2 â”‚                 â”‚
â”‚       â”‚â›ªCleric   â”‚                 â”‚
â”‚       â”‚ Press: â–¡ â”‚                 â”‚
â”‚       â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜                 â”‚
â”‚                                     â”‚
â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
     [Coffee: â–ˆâ–ˆâ–ˆâ–ˆ] [Speed: 100%]
     [Remote Access: 3]
```

**Quad Monitor (Fully Upgraded)**
```
â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
â”‚Monitor 1 â”‚â”‚Monitor 2 â”‚
â”‚ [Chaos]  â”‚â”‚ [Chaos]  â”‚
â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
â”‚Monitor 3 â”‚â”‚Monitor 4 â”‚
â”‚ [Chaos]  â”‚â”‚ [Chaos]  â”‚
â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
```

### Window Behavior
- Tickets appear as desktop windows
- Windows can overlap (need to click through them)
- Each window shows: Customer icon, problem text, **required button sequence**, progress bar
- Windows stay on screen until you close them
- No window can be "minimized" - must complete and close

---

## Coffee Mechanic

- **Action speed** starts at 100%
- Drains to 50% over 90 seconds
- Press LB/C to drink coffee (instant restore to 100%)
- Limited coffee per wave (replenished at wave start)
- At 50% speed, fix timers take twice as long
- At 100% speed, timers run at normal pace (3 seconds)

Coffee is survival - without it, you physically cannot keep up.

---

## Tickets (Desktop Windows)

### Each Window Shows
```
â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
â”‚ âš”ï¸ Barbarian (#1847)        â”‚
â”œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”¤
â”‚ "Rage ability not working"  â”‚
â”‚                             â”‚
â”‚      Press: [X] [â—‹]         â”‚
â”‚                             â”‚
â”‚ Status: [FIXING...]         â”‚
â”‚ â–“â–“â–“â–“â–‘â–‘â–‘â–‘â–‘â–‘ 40%             â”‚
â”‚                             â”‚
â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
```

### Ticket Types (Uniform & Clear)

Each ticket has a **Type** that determines its button sequence:

**Type 1: Single Button**
- Press one button: X, Square, Circle, or Triangle
- Most common early on

**Type 2: Two Buttons**
- Press two in sequence: Xâ†’Circle, Squareâ†’Triangle, etc.
- More common as time goes on

**Type 3: Three Buttons**
- Press three in sequence: Xâ†’Circleâ†’Triangle, etc.
- Rare, appears in later play

The **Type is clear from the button prompt** - you see exactly what sequence you need to press.

### Randomized Flavor Text

Each ticket has randomized elements:
- **Customer name & icon** - Different adventurer each time
- **Problem description** - "Fireball crashing", "Rage not working", "Login failed", etc.
- **Ticket number** - Randomly generated

But the **button sequence is always clearly displayed** and determines the actual gameplay.

### Example Tickets

```
â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
â”‚ ðŸ—¡ï¸ Grog the Barbarian (#1847)â”‚
â”‚ "Rage ability not activating"â”‚
â”‚      Press: [X]             â”‚
â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
Type 1 ticket
```

```
â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
â”‚ ðŸ”® Taako the Wizard (#2156) â”‚
â”‚ "Fireball spell memory leak"â”‚
â”‚      Press: [â–¡] [â–³]         â”‚
â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
Type 2 ticket
```

```
â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
â”‚ â›ª Pike the Cleric (#3891)  â”‚
â”‚ "Divine network auth failed"â”‚
â”‚      Press: [â—‹][X][â–³]       â”‚
â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
Type 3 ticket
```

### States & Flow

**1. APPEARS**
- New window pops up on desktop
- Shows customer, problem, and required button sequence

**2. NEEDS INPUT**
- Window is focused/selected
- Button sequence displayed prominently
- Press buttons in order
- Wrong button = nothing happens (or visual shake/error)
- Correct sequence = starts fix timer

**3. FIXING**
- Player pressed correct sequence
- Timer starts (3 seconds base, modified by coffee speed)
- Progress bar shows completion
- Player can switch focus to other tickets
- Timer continues in background

**4. COMPLETE**
- Timer finished
- Window state changes to [DONE] with visual indicator
- Player must return focus to this window
- Press A/Enter to mark done and close

### Remote Access Tool
- Press RB/R on any selected window
- Instantly completes it (closes the window)
- Bypasses button requirement and timer
- Limited uses (recharge via upgrades or between breaks)
- Save for when you're drowning in windows

---

## Progression System (Breaks & Upgrades)

### How It Works

**Continuous Play:**
- No discrete waves - tickets just keep spawning
- Spawn rate continuously accelerates over time
- Survival timer tracks how long you've lasted

**Breaks (Every ~2 minutes):**
- Game pauses
- You get a "cigarette break"
- Choose 1 upgrade from 3 random options
- Upgrades persist for rest of the run
- After break, spawn rate increases significantly
- Back to work

**The Escalation:**
- Each break = new difficulty tier
- Spawn rate accelerates faster after each break
- Eventually becomes impossible
- Upgrades help you survive longer but can't prevent inevitable death

### Break Timing
- **Break 1:** ~2 minutes of survival
- **Break 2:** ~4 minutes total (2 min since last break)
- **Break 3:** ~6 minutes total
- **Break 4:** ~8 minutes total
- And so on...

Actual timing can be tuned based on playtesting.

### Upgrade Categories

**Monitor Upgrades:**
- **Second Monitor** - Adds a 2nd monitor to your setup
- **Third Monitor** - Adds a 3rd monitor (requires 2nd first)
- **Fourth Monitor** - Adds a 4th monitor (requires 3rd first)
- **Ultrawide Monitor** - Increases window space per monitor

**Coffee Upgrades:**
- **Espresso Shot** - Coffee restores to 125% speed for 30 seconds
- **Caffeine Pills** - +2 max coffee charges
- **Coffee IV** - Coffee drains 50% slower
- **Energy Drink** - Coffee restores instantly, no drinking animation
- **Double Shot** - Each coffee charge counts as 2

**Speed Upgrades:**
- **Mechanical Keyboard** - +10% base typing speed
- **Ergonomic Chair** - +15% base speed
- **Adderall** - +20% base speed (stacks with coffee)
- **Two Hands** - Can work on 2 tickets simultaneously

**Utility Upgrades:**
- **Remote Desktop** - +2 remote access charges
- **Macro Keys** - Single buttons auto-complete Type 1 tickets
- **Auto-Close** - Completed tickets auto-close after 2 seconds
- **Window Snapping** - Windows arrange themselves neatly
- **Ticket Preview** - See next 3 incoming tickets
- **Slow Time** - One-use ability to slow spawn rate for 30 seconds

**Weird Upgrades:**
- **Intern** - Auto-completes 1 random ticket every 20 seconds (badly, might fail)
- **Ticket Filter** - Block Type 3 tickets (but Type 2 tickets spawn more)
- **Chaos Mode** - All tickets worth 2x, but spawn 50% faster
- **Rage Quit Button** - Instantly clear screen, but disabled for 2 minutes after

### Example Break Screen

```
â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
â”‚         CIGARETTE BREAK             â”‚
â”‚                                     â”‚
â”‚  Choose 1 Upgrade:                  â”‚
â”‚                                     â”‚
â”‚  â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â” â”‚
â”‚  â”‚ [1] SECOND MONITOR            â”‚ â”‚
â”‚  â”‚ Add a 2nd monitor to your     â”‚ â”‚
â”‚  â”‚ desktop for more space        â”‚ â”‚
â”‚  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜ â”‚
â”‚                                     â”‚
â”‚  â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â” â”‚
â”‚  â”‚ [2] CAFFEINE PILLS            â”‚ â”‚
â”‚  â”‚ +2 max coffee charges         â”‚ â”‚
â”‚  â”‚                               â”‚ â”‚
â”‚  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜ â”‚
â”‚                                     â”‚
â”‚  â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â” â”‚
â”‚  â”‚ [3] AUTO-CLOSE                â”‚ â”‚
â”‚  â”‚ Completed tickets auto-close  â”‚ â”‚
â”‚  â”‚ after 2 seconds               â”‚ â”‚
â”‚  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜ â”‚
â”‚                                     â”‚
â”‚  Time Survived: 4:32                â”‚
â”‚  Tickets Cleared: 87                â”‚
â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
```

### Upgrade Balance

- **Early breaks** offer foundational upgrades (monitors, basic coffee)
- **Later breaks** offer more powerful/niche upgrades
- Some upgrades are prerequisites for others (monitor chain)
- RNG ensures replayability - different upgrade paths each run
- Strategic choices matter - build synergies

### The Death Spiral

**Early Game (0-2 min):**
- 1 monitor
- Single button tickets mostly
- Spawn rate: ~1 every 15 seconds
- Manageable, learning the ropes

**Mid Game (2-6 min):**
- 2-3 monitors (if chosen)
- Mix of Type 1 and Type 2 tickets
- Spawn rate: ~1 every 8-10 seconds
- Some upgrades online, feeling powerful

**Late Game (6-12 min):**
- 3-4 monitors (if chosen)
- Type 2 and Type 3 tickets frequent
- Spawn rate: ~1 every 5 seconds
- Coffee management critical
- Remote access becomes panic button

**Death Game (12+ min):**
- Spawn rate: ~1 every 2-3 seconds
- Screen flooded with windows
- Even with upgrades, can't keep up
- Eventually impossible
- You die

**Theoretical max:** ~15-20 minutes for perfect players with optimal upgrades

---

## Unity Implementation

### Core Systems Needed

**1. Desktop Environment System**
- Render 1-4 monitor displays (based on upgrades)
- Manage "desktop" space for window placement
- Dynamic monitor addition during breaks
- Visual style: retro OS aesthetic (Windows 95 vibes)

**2. Window Management System**
- Spawn ticket windows on available monitors
- Windows can overlap
- Click to focus/select window
- Z-order management (bring to front on click)
- Close completed windows
- Optional: Auto-close upgrade

**3. Ticket Spawner**
- Continuous spawn with accelerating rate
- Rate increases over time
- Rate jumps significantly after each break
- Places new windows randomly on available monitors
- Tracks total tickets cleared

**4. Ticket Window (Prefab)**
- UI window with:
  - Customer icon/name (randomized)
  - Problem description (randomized)
  - **ButtonRequirements[] array** - e.g., [X], [Square, Triangle], [Circle, X, Triangle]
  - Current state indicator
  - Progress bar (when fixing)
- State machine: Needs Input â†’ Fixing â†’ Complete â†’ Closed
- Timers affected by coffee speed multiplier

**5. Button Input System**
- Detect X, Square, Circle, Triangle presses
- Track button sequence for current focused window
- Match against window's ButtonRequirements array
- On complete match: Start fix timer
- On wrong input: Visual feedback (shake, error sound)
- Simple and clear - no complex combo system

**6. Input Handler**
- Controller: Left stick cursor, A to select, face buttons for fixes
- Keyboard: Mouse click, IJKL for buttons
- LB/C for coffee
- RB/R for remote access
- A/Enter to close completed tickets

**7. Coffee System**
- Speed drains from 100% to 50% over 90 seconds (modifiable by upgrades)
- LB/C restores to 100% (or higher with upgrades)
- Starting coffee charges: 4 (modifiable by upgrades)
- Refills between breaks
- Speed multiplier affects all ticket fix timers

**8. Remote Access System**
- RB/R instantly completes and closes selected window
- Starting charges: 2 (modifiable by upgrades)
- Refills between breaks
- Panic button for overflow

**9. Break & Upgrade System**
- Timer tracks time survived
- Triggers break every ~2 minutes
- Pause game, show upgrade selection screen
- Present 3 random upgrades from available pool
- Player chooses 1
- Apply upgrade permanently to game state
- Resume with increased spawn rate

**10. Upgrade Manager**
- Track which upgrades player has
- Remove selected upgrades from pool (unless stackable)
- Apply upgrade effects to relevant systems
- Handle upgrade prerequisites (e.g., need Monitor 2 before Monitor 3)
- Some upgrades modify base stats, some add new mechanics

**11. Spawn Rate Controller**
- Base spawn rate starts at ~1 per 15 seconds
- Gradually accelerates over time
- Jumps significantly after each break
- Formula: `baseRate * timeMultiplier * breakMultiplier`
- Eventually reaches impossible rates (1+ per second)

**12. UI & HUD**
- Coffee meter
- Speed percentage
- Remote access charges remaining
- Time survived
- Tickets cleared (total)
- Optional: Current tickets per minute
- Wizard character at desk (corner of screen)
- **Button prompt overlay on selected window**

**13. Game Over System**
- Player manually gives up (pause menu)
- Or track "drowning" state (>20 windows on screen for 15+ seconds)
- Display: Time survived, tickets cleared, upgrades chosen
- High score / leaderboard potential

---

## What To Build First

### The MVP (Proof of Concept)

**Phase 1: Core Mechanics**
1. **Single monitor desktop rendering**
2. **Ticket window prefab** (customer icon, text, button requirements array, progress bar)
3. **Spawn system** - tickets appear at accelerating intervals
4. **Click to select/focus window** (bring to front, highlight)
5. **Button input detection** - X, Square, Circle, Triangle
6. **ButtonRequirements array** - ticket shows sequence like [X], [Square, Triangle], or [Circle, X, Triangle]
7. **Sequence matching** - player presses buttons in order, correct sequence starts timer
8. **Fix timer** - runs for 3 seconds (affected by coffee speed)
9. **State visual feedback** - window shows "FIXING" with progress bar
10. **Completion state** - window shows "DONE" when timer finishes
11. **Close completed ticket** - press A/Enter to remove window

**Test with continuous spawning, no breaks yet. Just survive as long as you can.**

**Phase 2: Resources**
12. **Coffee system** - LB to drink, speed meter drains over time, affects timer duration
13. **Remote access** - RB to instant-close selected window
14. **Spawn rate acceleration** - tickets spawn faster over time

**Test until it becomes impossible. Should die around 3-5 minutes.**

**Phase 3: Break & Upgrade System**
15. **Break timer** - pause game every 2 minutes
16. **Upgrade selection screen** - show 3 random upgrades
17. **Apply chosen upgrade** - modify game state permanently
18. **Resume with increased spawn rate**
19. **Implement 5-6 core upgrades** (Second Monitor, Caffeine Pills, Remote Desktop, Espresso Shot, Auto-Close)

**Test full loop. Should be able to survive 8-12 minutes with good upgrades.**

**Phase 4: Polish**
20. **More upgrades** (15-20 total)
21. **Randomized ticket flavor text** (customer names, problem descriptions)
22. **Visual effects** (window animations, button feedback)
23. **Sound effects** (pop, ding, typing, error beeps, button presses)
24. **Game over screen** with stats and upgrade history

**Phase 5: Balance & Juice**
25. **Spawn rate curve tuning** - should feel increasingly impossible
26. **Upgrade balance** - ensure no obviously broken combos
27. **Visual polish** (retro OS chrome, animations, screen shake)
28. **Coffee sip animation**
29. **Wizard character animations** (typing, drinking, panicking)
30. **Leaderboards/high scores**

---

## Technical Specifications

### Unity Setup
- **Unity Version:** 2022.3 LTS or newer
- **Input System:** New Input System (for better controller support)
- **UI Framework:** Unity UI (Canvas-based)
- **Resolution:** 1920x1080 base (scalable)

### Key Components

**TicketWindow.cs**
```csharp
public class TicketWindow : MonoBehaviour
{
    public enum WindowState { NeedsInput, Fixing, Complete, Closed }
    
    public WindowState currentState;
    public ButtonType[] buttonRequirements; // e.g., [X, Circle, Triangle]
    private int currentButtonIndex = 0;
    
    public string customerName;
    public string customerIcon;
    public string problemDescription;
    public int ticketNumber;
    
    private float fixTimer;
    private float fixDuration = 3f; // Modified by coffee speed
    
    // Methods
    public void OnButtonPressed(ButtonType button);
    public void StartFixTimer();
    public void UpdateFixProgress();
    public void MarkComplete();
    public void CloseWindow();
}

public enum ButtonType { X, Square, Circle, Triangle }
```

**TicketSpawner.cs**
```csharp
public class TicketSpawner : MonoBehaviour
{
    private float baseSpawnRate = 15f; // Seconds between spawns
    private float currentSpawnRate;
    private float timeElapsed;
    private int breakCount = 0;
    
    // Accelerate spawn rate over time
    private void UpdateSpawnRate();
    
    // Jump spawn rate after breaks
    public void OnBreakCompleted();
    
    // Generate random ticket
    private TicketWindow GenerateTicket();
    
    // Assign random button requirements based on difficulty
    private ButtonType[] GenerateButtonRequirements();
}
```

**CoffeeSystem.cs**
```csharp
public class CoffeeSystem : MonoBehaviour
{
    public float speedMultiplier = 1f; // 1.0 = 100%, 0.5 = 50%
    public float maxSpeed = 1f;
    public float minSpeed = 0.5f;
    public float drainRate = (0.5f / 90f); // Drain to 50% over 90 seconds
    
    public int coffeesRemaining = 4;
    public int maxCoffees = 4;
    
    // Affected by upgrades
    public float speedBonus = 0f; // From upgrades like Espresso
    public float drainMultiplier = 1f; // Affected by Coffee IV
    
    public void DrinkCoffee();
    private void Update(); // Handle speed drain
}
```

**BreakManager.cs**
```csharp
public class BreakManager : MonoBehaviour
{
    public float breakInterval = 120f; // 2 minutes
    private float timeSinceLastBreak = 0f;
    
    public List<Upgrade> availableUpgrades;
    public List<Upgrade> chosenUpgrades;
    
    public void TriggerBreak();
    public void ShowUpgradeSelection();
    public void ApplyUpgrade(Upgrade upgrade);
    public void ResumeGame();
}
```

**Upgrade.cs**
```csharp
[CreateAssetMenu(fileName = "New Upgrade", menuName = "Upgrades/Upgrade")]
public class Upgrade : ScriptableObject
{
    public string upgradeName;
    public string description;
    public Sprite icon;
    
    public UpgradeType type;
    public bool isStackable;
    public Upgrade prerequisite; // For monitor chain
    
    public void Apply(GameState gameState);
}

public enum UpgradeType
{
    Monitor,
    Coffee,
    Speed,
    Utility,
    Weird
}
```

**ButtonInputManager.cs**
```csharp
public class ButtonInputManager : MonoBehaviour
{
    private TicketWindow focusedWindow;
    
    public void OnButtonPressed(ButtonType button)
    {
        if (focusedWindow == null) return;
        
        focusedWindow.OnButtonPressed(button);
        
        // Visual feedback
        if (IsCorrectButton(button))
            ShowCorrectFeedback();
        else
            ShowIncorrectFeedback();
    }
    
    private bool IsCorrectButton(ButtonType button);
    private void ShowCorrectFeedback();
    private void ShowIncorrectFeedback();
}
```

**GameState.cs**
```csharp
public class GameState : MonoBehaviour
{
    // Singleton
    public static GameState Instance;
    
    // Stats
    public float timeElapsed;
    public int ticketsCleared;
    public int breakCount;
    
    // Current state
    public int monitorCount = 1;
    public float baseSpeed = 1f;
    public int maxCoffees = 4;
    public int maxRemoteAccess = 2;
    
    // Upgrades
    public List<Upgrade> activeUpgrades;
    
    // Apply upgrade modifiers
    public void RecalculateStats();
}
```

---

## Art Direction

### Visual Style
- **Retro OS aesthetic** (Windows 95/98 vibes)
- **Pixel art or low-poly** for character sprites
- **Clean UI** with clear button prompts
- **Color coding** for button types (X=blue, Square=pink, Circle=red, Triangle=green)

### Window Design
```
â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
â”‚ ðŸ—¡ï¸ Barbarian (#1847)   [X] â”‚ â† Close button (disabled until done)
â”œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”¤
â”‚ "Rage ability not working"  â”‚ â† Problem text
â”‚                             â”‚
â”‚      Press: [X]             â”‚ â† Button prompt (large, color-coded)
â”‚                             â”‚
â”‚ Status: [FIXING...]         â”‚ â† Current state
â”‚ â–“â–“â–“â–“â–‘â–‘â–‘â–‘â–‘â–‘ 40%             â”‚ â† Progress bar
â”‚                             â”‚
â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
```

### Character Icons
- **Barbarian** - ðŸ—¡ï¸ or muscular warrior
- **Wizard** - ðŸ”® or pointy hat
- **Cleric** - â›ª or holy symbol
- **Rogue** - ðŸ—¡ï¸ or hooded figure
- **Paladin** - ðŸ›¡ï¸ or armored knight
- **Druid** - ðŸŒ¿ or nature symbol
- **Ranger** - ðŸ¹ or bow
- **Bard** - ðŸŽµ or lute

### Desktop Environment
- **Monitor bezels** clearly defined
- **Desktop background** (generic fantasy-themed wallpaper)
- **Taskbar** at bottom showing coffee, speed, resources
- **Wizard character** in corner (animated typing when active)

---

## Audio Design

### Sound Effects
- **Ticket spawn** - Pop/ding sound
- **Window select** - Click
- **Button press** - Satisfying mechanical click (different tone per button)
- **Wrong button** - Error beep
- **Fix timer complete** - Success chime
- **Close window** - Swoosh/close sound
- **Coffee sip** - Gulp/slurp
- **Remote access** - Zap/warp sound
- **Wave complete** - Fanfare
- **Game over** - Descending tone

### Music
- **Main theme** - Upbeat fantasy tavern music with electronic elements
- **Escalation** - Tempo increases slightly with each wave
- **Late waves** - Music becomes more frantic, distorted
- **Game over** - Music stops abruptly

---

## Summary

**The game in one sentence:**  
A desktop simulator where IT tickets spawn continuously and accelerate relentlessly, requiring specific button sequences to fix, with periodic breaks offering random upgrades to delay the inevitable death.

**Core challenge:**  
Tickets spawn continuously at an accelerating rate. You click between overlapping windows, press button sequences to start fix timers, then return to completed tickets to close them. Every 2 minutes you get a break to choose 1 of 3 random upgrades. Coffee keeps you fast. Remote access saves you from overflow. Upgrades help you survive longer. Failure is inevitable.

**What makes it fun:**  
The panic of watching windows pile up. The satisfaction of perfect button sequences. The juggling act of running multiple fix timers. The strategic choice of upgrades during breaks. The relief of a coffee boost. The desperation of a clutch remote access. The escalation from manageable to impossible. The comedy of a wizard doing password resets. The bragging rights of "I survived 15 minutes."

**The comedy:**  
You're a wizard. At a desk. With a controller. Pressing Xâ†’Circle to fix a barbarian's rage ability. Pressing Squareâ†’Triangleâ†’X to debug a druid's wildshape bug. You're drowning in fantasy IT tickets on a Windows 95 desktop while drinking increasingly powerful caffeinated beverages. It's absurd.

**Why it works:**
- Clear, simple mechanics (click, press buttons, wait, close)
- Constant escalation (faster spawns forever)
- Strategic depth (upgrade choices, resource management)
- Skill expression (optimal routing, button memory, coffee timing)
- Panic comedy (desktop chaos, button sequences)
- High replayability (different upgrade paths each run)
- The rhythm game element (press correct button sequences)

**This is Papers, Please meets Overcooked meets WarioWare meets desktop hell meets roguelike progression.**

---

## Development Roadmap

### Week 1: Core Loop
- Single monitor desktop environment
- Ticket window prefab with ButtonRequirements array
- Button input system (sequence tracking)
- Fix timer system
- Continuous spawn with acceleration
- Window focus/close mechanics

### Week 2: Resources & Escalation
- Coffee system (drain, refill, speed modifier)
- Remote access system
- Spawn rate acceleration curve
- Test: Can you survive 3-5 minutes?

### Week 3: Break & Upgrade System
- Break timer (every 2 minutes)
- Upgrade selection screen
- Implement 8-10 core upgrades
- Upgrade application to game state
- Test: Can you survive 8-12 minutes with upgrades?

### Week 4: Content & Variety
- 15-20 total upgrades
- Randomized ticket flavor text (names, problems)
- More button sequence variety
- Upgrade prerequisite chains

### Week 5: Polish & Juice
- Visual effects (window animations, button feedback)
- Sound effects (spawn, button press, complete, error)
- Coffee sip animation
- Wizard character animations
- Screen shake, particle effects

### Week 6: Balance & Release
- Spawn rate curve tuning
- Upgrade balance (no broken combos)
- Game over screen with stats
- Leaderboards
- Settings menu
- Final polish

---

**Start here. Get the button sequences feeling snappy. Perfect the timer juggling. Build the upgrade system. Nail the escalation curve. Ship it.**
