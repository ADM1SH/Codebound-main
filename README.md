# Codebound: Terminal Action RPG Engine

[![Language: C++](https://img.shields.io/badge/Language-C%2B%2B17-00599C.svg?logo=cplusplus)](https://isocpp.org/)
[![Build: Make](https://img.shields.io/badge/Build-Makefile-orange.svg)](Makefile)
[![Genre: RPG](https://img.shields.io/badge/Genre-Terminal_Action_RPG-purple.svg)](https://github.com/ADM1SH/codebound)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

A modular, turn-based terminal RPG and battle simulation engine written in modern C++ featuring audio integration, multi-tier enemy AI, and persistent leaderboard tracking.

## Description
Codebound is an interactive console role-playing game built from scratch in C++. It demonstrates advanced object-oriented architecture through polymorphic character hierarchies, state-driven battle encounters, multi-phase boss mechanics, audio event management, and score persistence.

### Key Game Systems
* **Polymorphic Entities**: Base `Character` class inherited by `Player`, regular `Enemy`, and multi-phase `Boss` subclasses with virtual action methods.
* **Combat Mechanics**: Dynamic damage calculation incorporating critical strikes, defense mitigation, elemental vulnerabilities, and special abilities.
* **Boss Encounter Architecture**: Multi-phase boss battle with adaptive decision-making depending on player health and tactical state.
* **Audio Management Subsystem**: Event-driven `AudioManager` triggering sound effects and ambient tracks for critical encounters and level transitions.
* **Persistent Leaderboard**: File-backed `Leaderboard` subsystem that serializes player statistics, high scores, and run duration to disk.

## System Architecture
```text
┌─────────────────┐       ┌─────────────────┐
│     Player      │       │      Enemy      │
└────────┬────────┘       └────────┬────────┘
         │                         │
         ▼                         ▼
   ┌─────────────────────────────────────┐
   │         Character (Base)            │
   └──────────────────┬──────────────────┘
                      │
                      ▼
   ┌─────────────────────────────────────┐
   │        Battle / Combat Engine       │
   └───────────┬───────────────┬─────────┘
               │               │
               ▼               ▼
     ┌─────────────────┐ ┌───────────────┐
     │  AudioManager   │ │  Leaderboard  │
     └─────────────────┘ └───────────────┘
```

## Repository Structure
```text
Codebound/
├── AudioManager.h/cpp  # Audio playback driver and sound effect triggers
├── Character.h/cpp     # Base entity class with attributes and virtual methods
├── Player.h/cpp        # Player class with inventory, skills, and stats
├── Enemy.h/cpp         # Regular enemy variations and encounter behaviors
├── Boss.h/cpp          # Multi-stage boss entity with specialized attack patterns
├── Leaderboard.h/cpp   # High score record management and disk serialization
├── main.cpp            # Game loop, input handling, and terminal rendering
└── Makefile            # Automated compilation script
```

## Requirements
* Compiler: GCC (`g++`) or Clang supporting C++17
* Operating System: macOS, Linux, or Windows (WSL)
* Audio Libraries: Native macOS audio utilities (`afplay`) or SDL2/OpenAL on Linux

## Installation & Compilation
Clone the repository:
```bash
git clone https://github.com/ADM1SH/codebound.git
cd codebound
```

Compile using the Makefile or manual command:
```bash
g++ -std=c++17 -Wall -Wextra -O2 -o codebound *.cpp
```

## Usage
Start the game:
```bash
./codebound
```

### Gameplay Controls
* Navigate menus using numeric keys `[1]`, `[2]`, `[3]`.
* During combat:
  * `[1]` Attack: Standard physical strike.
  * `[2]` Skill: Special energy attack dealing scaled damage.
  * `[3]` Defend: Reduce incoming damage by 50% for one turn.
  * `[4]` Inventory: Consume healing potions or stat buffs.

## Support
Report bugs or game balance suggestions to:
https://github.com/ADM1SH/codebound/issues

## Roadmap
* [x] Core character inheritance and combat math.
* [x] Multi-phase boss battle logic.
* [x] Persistent leaderboard file I/O.
* [x] Terminal audio manager integration.
* [ ] Add procedural dungeon room generation.
* [ ] Implement equipment inventory system with randomized loot drops.

## Contributing
1. Fork the repository.
2. Create a branch: `git checkout -b feature/procedural-dungeon`.
3. Write clean, modular C++ code adhering to existing conventions.
4. Test thoroughly and open a Pull Request.

## Authors and Acknowledgment
* **Adam Anwar** (ADM1SH) - Game designer and lead developer.

## License
MIT License. See `LICENSE` for details.

## Project Status
Active indie game project. Periodic updates for content balance and engine expansion.
