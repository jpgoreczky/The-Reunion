# The Reunion 

A 2D top-down cozy murder mystery game built in Unity (C#) for CAP4053 – AI for Game Programming at the University of Central Florida (Spring 2025).

You've snuck away from a family reunion to investigate a murder. Explore the house, solve puzzles, and gather clues — but don't get caught.

---

## Gameplay Overview

The player moves through a multi-room map collecting evidence across three acts of increasing difficulty. Each act introduces harder puzzles and a faster-growing suspicion meter. Once all clues are gathered, the player must make a final accusation — choosing both the suspect and the murder weapon. A wrong accusation has consequences.

**Core mechanics:**
- **Evidence gathering** – Explore rooms, interact with clues, and solve puzzles to unlock new areas
- **Suspicion system** – Suspicion grows dynamically as you explore. Collect more clues and it escalates faster, putting pressure on puzzle-solving
- **NPC AI patrol** – Guards navigate the map using NavMesh waypoints. When suspicion reaches max, nearby NPCs actively search for the player. Getting caught sends you back to the main reunion area
- **Inventory & accusation** – Collected clues are stored with descriptions. At the end, review your evidence and submit a final accusation with three possible endings

---

## Puzzles

Five puzzle types of varying difficulty, all fully implemented:

| Puzzle | Description |
|--------|-------------|
| Sliding Jigsaw | Randomized tile shuffle — difficulty varies by generation |
| Pipe Connect | Connect tubes from start to end; resettable |
| Pill Sort | Drag-and-drop sorting into correct containers |
| Code Unlock | Numeric code entry |
| Color Flow | Connect color pairs without overlapping paths |

Completed puzzles highlight green. Puzzles are distributed across acts, with suspicion acting as the primary difficulty multiplier.

---

## AI & Technical Features

- **NavMesh pathfinding** – NPCs navigate a multi-room environment with door-aware pathing; locked rooms block NPC access
- **Suspicion-driven behavior** – NPCs transition from passive patrol to active search based on a global suspicion value that scales with player progress
- **Stationary NPCs** – Secondary characters with dialogue interaction
- **Detection radius** – Configurable per-NPC texture radius and speed settings via Unity Inspector
- **Multi-act progression** – Three acts with increasing suspicion growth rate and puzzle complexity
- **Three endings** – Outcome determined by accusation accuracy

---

## UI & Systems

- Main menu with settings (volume control)
- In-game HUD: suspicion meter, clue counter
- Interactive tutorial and on-screen controls
- Pause menu (resume, settings, quit)
- In-game map (M key)
- Inventory viewer (B key) with expandable clue descriptions
- Accusation scene with clue review panel
- Consistent resolution across all scenes

---

## Built With

- **Unity** (2D)
- **C#**
- **Unity NavMesh** for NPC pathfinding
- **Unity Asset Store** (character sprites, tilesets, UI, audio)
- **Jira** for sprint tracking and task management
- **Git / GitHub** for version control

---

## Team

Developed by a team of students for CAP4053 – AI for Game Programming, UCF Spring 2025.

---

## Running the Game

Run the included `.exe` — no additional setup required.

An answer key with screenshots is available [here](https://docs.google.com/document/d/1a1MK4QIwGZOvckUrP1hgLzlRmDAeJZEozfStLeu8d58/edit?usp=sharing) if you get stuck.

### Known Bugs
- Jigsaw puzzle: placing a correct piece over an incorrect piece locks both — reset the puzzle to recover
- Color Flow: allows overlapping lines in some cases, which may let you complete it incorrectly