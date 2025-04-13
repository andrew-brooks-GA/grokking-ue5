
# ♻️ Micro-Project: Grid Iterator Demo

## 🎯 Gameplay Goal:
Build a utility system that walks through a 2D grid and applies effects or logic tile by tile. Use custom iterators to traverse the grid in multiple patterns: row-wise, column-wise, diagonal, zig-zag, or spiral. Great for fog-of-war, traps, or AOE effects.

---

## 🔍 Step 1: Create Grid and Basic Iteration Logic

### 🎮 What You’re Building:
A 2D grid of tiles with metadata. Each tile can be visited in a specific order based on the iterator selected.

### 🧱 Data Structures:
- **2D Array** – Base grid
- **Iterator Pattern** – Encapsulate traversal order logic

### 🛠️ In Unreal Engine:
- Each tile is an actor with a coordinate system.
- Iterator logic controls which tiles are highlighted or affected.

---

## 🌐 Step 2: Build Different Iterator Modes

- **What You’re Building:**
  - Separate iterator classes or functions that yield tiles in different patterns.

- **Why Iterator?**
  Cleanly separates traversal from tile effect logic.

### 🧠 What It Powers:
- Turn-based area targeting
- Fog clearing or effect zones
- Runtime tile animations

---

## ✅ Gameplay System Flow

```
Trigger Event → Select Iterator → Loop Tiles
     ↓                  ↓               ↓
 Apply Effect     → Highlight Tile   → End Condition
```

---

## 🧩 Design Patterns In Use

- **Iterator** – Traverse grid in unique ways
- **Strategy** – Choose traversal method dynamically

---

## 🎲 GAS Integration (Gameplay Ability System)

Grid iterators can be used to activate GAS effects on multiple tiles.

### 🔄 Ability: Tile Wave
- **Description:** Applies a visual and gameplay effect in a wave pattern across the grid.
- **System Behavior:**
  - Iterator yields tiles → each gets tagged or damaged.
- **Why GAS?**
  Reusable logic and scalability across ability types.

---

### 🧲 Ability: Trap Disarm Sweep
- **Description:** Clears traps row by row across a grid.
- **System Behavior:**
  - Applies conditional status clear on visited tiles.
- **Why GAS?**
  Combines tag application + timing-based visual feedback.

---

## 🤔 Thought Starter

Could you use multiple iterators simultaneously to simulate converging or diverging magical effects?
