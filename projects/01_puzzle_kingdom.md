
# 🧩 Project 1: Puzzle Kingdom

## 🎯 Gameplay Goal:
Design a tile-based puzzle game where the player must navigate a magical grid to unlock ancient doors. The puzzle is procedurally generated using recursive backtracking, ensuring that every level is solvable. The player can request hints, which are selected using binary search from a precomputed list of valid paths.

The grid is navigated by selecting tiles to move across in a specific sequence. The game checks whether a path is valid, offers hint suggestions, and allows the player to backtrack.

---

## 🔍 Step 1: Build a Grid-Based Puzzle Represented as a Graph

### 🎮 What You’re Building:
You’re creating a **2D puzzle grid**—like a 5x5 or 7x7 map—where each cell (tile) is a **node** in a graph. The player starts at one tile and attempts to navigate to a goal tile by moving to adjacent, valid tiles.

### 🧱 Graph Structure:
- Each tile is a **node**.
- Legal adjacent movement = **edges** between nodes.
- Some paths will be valid; others blocked or locked.

### 🛠️ How It Works in Unreal Engine:
- You define a grid size in code (e.g., 7x7).
- You **spawn tile actors at runtime** in a nested loop.
- Each tile tracks its grid coordinates and knows its potential neighbors.
- The connections between tiles form a **graph**, which is later carved into a maze using a recursive algorithm.

```cpp
for (int X = 0; X < GridSize; ++X) {
    for (int Y = 0; Y < GridSize; ++Y) {
        FVector Position = FVector(X * TileSize, Y * TileSize, 0);
        APuzzleTile* Tile = GetWorld()->SpawnActor<APuzzleTile>(TileClass, Position, FRotator::ZeroRotator);
        Tile->InitCoordinates(X, Y);
        Grid[X][Y] = Tile;
    }
}
```

### 🧠 What It Powers:
- **Move validation** – Is the selected tile connected to the current one?
- **Pathfinding** – The generator and player can explore paths recursively.
- **Hint logic** – Valid path data can be used for future hint suggestions.

### 📈 Why Use a Graph?
- A 2D array only stores spatial layout, not logic.
- A graph allows traversal, rule enforcement, and dynamic edge management.

---

## 🌐 Step 2: Use Recursive Backtracking to Generate Solvable Puzzles

- **What You’re Building:**  
  A level generator that places locked doors, keys, and dead ends by traversing the grid recursively.

- **Why Backtracking?**  
  It ensures that puzzles are not just randomized, but also solvable. It will try paths until one meets design constraints, then backtrack to fix invalid layouts.

- **What It Powers:**  
  Puzzle solvability, gameplay fairness, and meaningful level variety.

---

## 🚦 Step 3: Implement Hint Suggestion with Binary Search

- **What You’re Building:**  
  A hint system that pulls from a sorted list of valid moves or paths and quickly finds the most relevant one.

- **Why Binary Search?**  
  You’re working with a precomputed sorted hint set, and players might request help mid-puzzle. Fast lookup is crucial.

- **What It Powers:**  
  Real-time hint delivery without performance lag.

---

## 🧩 Design Patterns In Use:

- **Template Method** — Shared puzzle logic with customizable rule overrides per level
- **Factory Method** — Generate different puzzle types (spatial, numerical, matching)
- **Observer** — Notify UI when puzzle state changes (moves, solves, hint requested)

---

## ✅ Gameplay System Flow

```
Grid + Graph Structure → Recursive Puzzle Generation → Puzzle Interact
     ↓                             ↓                      ↓
Player Move Input         Valid Path Check         Hint / Solve Check
     ↓                             ↓                      ↓
Observer Event → UI Update     → Backtrack if Fail      → Binary Search Hint
```

---

## 🎲 GAS Integration (Gameplay Ability System)

In this project, GAS is used to encapsulate magical puzzle powers that the player can activate to aid in solving the level.

### 🔮 Ability: Hint Reveal
- **Description:** When activated, the player receives a magical vision that highlights the next optimal move.
- **System Behavior:**
  - Applies a Gameplay Effect that triggers a binary search lookup in a sorted hint array.
  - Highlights the hint tile on the puzzle grid.
  - Sends an observer event to update UI visuals.
- **Why GAS?**
  Enables modular puzzle powers that can be enhanced, locked behind upgrades, or used sparingly via cooldowns or mana cost.

---

### 🕰️ Ability: Time Freeze
- **Description:** Temporarily stops the puzzle timer, giving the player space to think.
- **System Behavior:**
  - Applies a Gameplay Effect that halts all UI countdowns and disables puzzle penalties for N seconds.
  - Resumes normal puzzle flow once the effect ends.
- **Why GAS?**
  You gain time-based gameplay control and can scale difficulty by limiting this ability per level.

---

### 🧩 Optional: Puzzle Key Unlock
- **Description:** Automatically unlocks one locked tile or gate on the board.
- **System Behavior:**
  - Checks for a “key fragment” tag or collected item.
  - Triggers an animated cue that clears the block and updates puzzle state.
- **Why GAS?**
  Integrates puzzle progression with attribute or item systems using GAS tag-based logic.

---

## 🤔 Thought Starter

How could you expand this system to allow for multiplayer puzzle collaboration or competitive “race to solve” scenarios?
