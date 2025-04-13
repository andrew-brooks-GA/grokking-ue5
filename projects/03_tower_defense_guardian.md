
# 🛡️ Project 3: Tower Defense Guardian

## 🎯 Gameplay Goal:
Build a classic tower defense game where enemies follow a predefined path toward a base, and the player places towers along the way to destroy them. You’ll use greedy algorithms for tower upgrades, priority queues for spawn timing, and queues to manage enemy wave deployment. The player uses special abilities like slowing or buffing towers via GAS.

---

## 🔍 Step 1: Create the Path Grid and Enemy Spawn System

### 🎮 What You’re Building:
A linear or winding path made of waypoints that enemies follow. Towers are placed on grid tiles along the path but cannot block it. Enemies spawn in waves with a time delay.

### 🧱 Data Structures:
- **Queue**: Manage enemies waiting to spawn during a wave.
- **Grid (Array)**: Represent tower placement slots and path alignment.
- **Priority Queue**: Schedule high-health enemies or bosses to appear at key moments.

### 🛠️ In Unreal Engine:
- Place towers via click/spawn on tower tiles.
- Enemies are actors with waypoint-following logic.
- Use a queue to dequeue enemy actors on a spawn timer.

---

## 🌐 Step 2: Apply Greedy Algorithms for Tower Upgrades

- **What You’re Building:**
  - A system to automatically suggest or trigger tower upgrades based on available resources.
  - Choose the most damage per cost ratio (DPC) at each decision point.

- **Why Greedy?**
  Because you’re making locally optimal choices (upgrade the best-value tower now), which is effective in fast-paced scenarios.

### 🧠 What It Powers:
- Smarter upgrade decisions
- Player helper system or auto-defense mode

---

## 🚦 Step 3: Apply Patterns for Combat, Pathing, and Ability Integration

- **Factory Pattern**: Used to spawn towers and enemies with varying stats.
- **Strategy Pattern**: Towers can switch targeting modes (first, last, strongest).
- **Observer Pattern**: Trigger UI updates when towers attack or enemy HP changes.

---

## ✅ Gameplay System Flow

```
Enemy Wave Queue → Spawn Timer → Enemy Path Movement
        ↓                    ↓            ↓
 Tower Placement → Greedy Upgrade Check → Target + Fire
        ↓                    ↓            ↓
  Strategy Switch      → UI Update     → Enemy Destroyed
```

---

## 🧩 Design Patterns In Use

- **Factory** – Modular spawning for enemies and towers
- **Strategy** – Change tower targeting behavior on the fly
- **Observer** – Notify UI of health updates and effects

---

## 🎲 GAS Integration (Gameplay Ability System)

This game uses GAS to allow players to tactically alter battlefield conditions.

### 🌀 Ability: Area Slow
- **Description:** Temporarily slows all enemies in a radius.
- **System Behavior:**
  - Applies a Gameplay Effect to all enemies in a target zone.
  - Reduces their movement speed for X seconds.
- **Why GAS?**
  Manage stacking, timing, cooldowns, and area-based effects cleanly.

---

### ⚡ Ability: Overcharge Tower
- **Description:** Grants a selected tower rapid fire and bonus damage for a short period.
- **System Behavior:**
  - Applies a Gameplay Effect to the tower actor, modifying stats.
  - May require targeting with a gameplay cue or tag filter.
- **Why GAS?**
  Stat modifications are scalable, and effect duration can be reused across abilities.

---

## 🤔 Thought Starter

What if towers had unique personalities or traits, unlocking different upgrade trees or ability synergies? How would you track and trigger those conditions cleanly?
