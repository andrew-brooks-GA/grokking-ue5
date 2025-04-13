
# ⚔️ Project 8: Fantasy War Tactics

## 🎯 Gameplay Goal:
Create a turn-based tactics game where units battle across a grid. Each unit acts based on initiative, and movement uses **A* pathfinding**. Combat logic is modular and extensible using design patterns. GAS powers active and passive unit abilities.

---

## 🔍 Step 1: Tactical Grid and Unit System

### 🎮 What You’re Building:
A grid-based battlefield. Each tile is addressable and units are placed on valid tiles. Turn order is determined by a priority queue.

### 🧱 Data Structures:
- **Grid** – Positioning system for units and obstacles.
- **Graph** – Walkable map for A* pathfinding.
- **Priority Queue** – For initiative/turn order.

### 🛠️ In Unreal Engine:
- Units are pawns placed via selection.
- Turn logic handled by a TurnManager component.

---

## 🌐 Step 2: A* Movement and Initiative System

- **What You’re Building:**
  - A pathfinding system that finds optimal movement paths.
  - An initiative system that queues units based on speed or RNG.

- **Why A\*?**
  Finds shortest path with weighted costs (terrain, range, etc.).

- **Why Priority Queue?**
  Manages who goes next based on unit stats or effects.

### 🧠 What It Powers:
- Strategic depth and pacing
- Terrain control and positioning tactics

---

## 🚦 Step 3: Modular Combat via Design Patterns

- **Command Pattern** – Encapsulate unit actions (attack, move, wait).
- **Strategy Pattern** – AI can switch targeting or positioning strategy.
- **Iterator Pattern** – Traverse unit groups or tiles during buffs or AoEs.

---

## ✅ Gameplay System Flow

```
Turn Queue → Unit Selected → Move (A*) → Action (Command)
     ↓            ↓                 ↓              ↓
GAS Triggered → Status Effects → Response Action → Next Turn
```

---

## 🧩 Design Patterns In Use

- **Command** – Unit actions
- **Strategy** – AI and player decision logic
- **Iterator** – AoE effects, unit traversals

---

## 🎲 GAS Integration (Gameplay Ability System)

Abilities add layer upon layer of tactical variety and counters.

### 💥 Ability: Special Attack
- **Description:** Powerful move that uses bonus energy and applies status effects.
- **System Behavior:**
  - Applies knockback, DoT, or debuff tags.
  - May interrupt enemy turn queue.
- **Why GAS?**
  Tag-based responses and stat-scaled effects make it cleanly extensible.

---

### 🛡️ Ability: Defensive Stance
- **Description:** Player unit braces and reduces incoming damage until next turn.
- **System Behavior:**
  - Modifies attributes like defense and block chance.
  - Adds reactive tags to auto-parry or counterattack.
- **Why GAS?**
  Delivers passive + active effects with fine-grained conditions.

---

## 🤔 Thought Starter

Could you allow enemies to steal abilities or interrupt turns via GAS triggers and tag reactions? How would you design a system to cleanly allow that?
