# Arcade: A Primer 
A simple 2D game built with the Python Arcade library, adapted from the [RealPython tutorial](https://realpython.com/arcade-python-game-framework/).

## Table of Contents (optional for short projects)

## Overview / Introduction

This repository contains the example game code from the RealPython Arcade Primer, adapted for quick setup and testing. It’s intended as a fast-start reference and a compatibility guide for running the game on modern versions of the Python Arcade library.

This tutorial is for anyone who wants to:
- **Run the Arcade Game immediately** — follow the Quickstart for an out-of-the-box working version.
- **Modify or extend the game** — explore the code structure and use the [RealPython Arcade Primer tutorial](https://realpython.com/arcade-python-game-framework/) for detailed explanations of each part. 

## What this README Adds Beyond RealPython

- **Direct repo access** without needing to copy from the tutorial.
- **Pinned package versions** so the game runs as written.
- **Known Issues section** for modern Arcade releases.
- **Screenshots/GIFs** for quick visual reference.

## Arcade Game Functionality 

- sprite movement
- soundtrack + sound effects
- collision detection
- score tracking 

## Prerequisites

**Important!** The game has not yet (as of August 2025) been updated to Arcade 3.0 or higher. It will only run on Arcade <3.0.
The game runs on Python version 3.7 or higher. However, if you are running Python 3.6, you will need to install a backport using pip:

```

$ python -m pip install dataclasses

```

## Dependencies

Arcade is a Python game framework built on top of several other libraries.  
When you install Arcade via `pip`, it automatically pulls in these dependencies:

arcade (2.x)
├─ pyglet (2.x)
│ └─ OpenGL / windowing (via your system's graphics backend)
├─ numpy
├─ Pillow
├─ pytiled-parser
└─ shapely (optional; boosts collision performance)

### Dependency Details

- **`pyglet`** — Handles low-level windowing, graphics rendering, audio, and input.  
  - Relies on your operating system's graphics stack:  
    - **macOS:** Uses Cocoa APIs with OpenGL.  
    - **Windows/Linux:** Uses their respective OpenGL drivers.
- **`numpy`** — Optimized math operations, used in collision detection and sprite movement.
- **`Pillow`** — Image loading and manipulation (e.g., sprite textures).
- **`pytiled-parser`** — Reads map files created with the [Tiled Map Editor](https://www.mapeditor.org/).
- **`shapely`** *(optional)* — High-performance polygon math for complex collision detection.  
  - Note: Some versions may require workarounds on newer Python/macOS setups.

### System Requirements

Arcade needs:
- A working **OpenGL** environment.
- Compatible graphics drivers.
- On macOS: no headless mode; must run with an active display.
- On Linux: you may need additional system packages like `libgl1-mesa-dev`.

---

## QuickStart Instructions


```
git clone https://github.com/<your-username>/arcade-a-primer.git
cd arcade-a-primer
python3 -m venv .venv
source .venv/bin/activate
pip install --upgrade pip
pip install "arcade<3.0"  # Arcade 2.x for tutorial compatibility
python arcade_primer.py
```

## Version notes

The original RealPython code was written for Arcade 2.x. In Arcade 3.x, calling arcade.start_render() in a windowed game throws:

```

RuntimeError: start_render() can only be called once during the application's lifetime...

```

**Fixes:**

- **Easiest:** Install Arcade <3.0 (as in the QuickStart instructions).
- **Modernize:** Replace arcade.start_render() in on_draw() with self.clear() or window.clear().

## Running the Game

To launch the game, enter:

```python3 arcade_game.py'''

A new window should pop up. Sound effects and gameplay should start immediately. If they do not, head to the next section of this tutorial.

<img width="1712" height="1340" alt="Screenshot 2025-08-14 at 3 03 46 PM" src="https://github.com/user-attachments/assets/0a65cded-6732-4ca2-9037-6c75befcc0a3" />

## Known Issues / Common Pitfalls

Bugs or breaking changes between library versions (this is where your start_render() → clear() bug goes).

Workarounds or fixes.

Links to relevant issue tracker threads if public.

Contributing (optional)

Guidelines for PRs, issue reporting.

License

Type of license (MIT, Apache 2.0, etc.).

A short note if based on a tutorial — credit original authors.

Acknowledgments (optional)

Tutorial authors, libraries used, community resources.Source files supporting the [Arcade: A Primer on the Python Game Framework](https://realpython.com/arcade-python-game-framework/) article on [Real Python](https://realpython.com/).
