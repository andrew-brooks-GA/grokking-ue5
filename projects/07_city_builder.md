
# 🌆 Project 7: City Builder: Urban Architect

## 🎯 Gameplay Goal:
Build and manage a growing city. Players place zones (residential, commercial, industrial), lay roads, and balance resources. Behind the scenes, BFS helps simulate citizen movement and traffic. A greedy algorithm helps prioritize upgrades, and trees/graphs model infrastructure connections.

---

## 🔍 Step 1: Build the City Grid and Zoning System

### 🎮 What You’re Building:
A grid where players place buildings and roads. Each tile has a zone type (residential, etc.), and roads connect nodes in a city graph.

### 🧱 Data Structures:
- **2D Array/Grid** – Represent tiles and zones.
- **Graph** – Connect infrastructure like power lines and traffic paths.
- **Tree** – Hierarchy of building upgrades or city systems.

### 🛠️ In Unreal Engine:
- Each tile is a blueprint or actor.
- Buildings are spawned on demand via click or UI event.

---

## 🌐 Step 2: Simulate Movement Using BFS and Greedy Upgrades

- **What You’re Building:**
  - Citizens moving from homes to jobs.
  - A greedy system that chooses the next most-needed upgrade based on demand.

- **Why BFS?**
  Efficient for calculating shortest commute paths.

- **Why Greedy?**
  Smart prioritization: if pollution is high, pick the best-value fix now.

### 🧠 What It Powers:
- Traffic logic, service coverage
- Population happiness and challenge progression

---

## 🚦 Step 3: Use Design Patterns for Modular System Management

- **Composite Pattern** – Manage systems as parent/child modules (e.g. Water > Pipes > Pump)
- **Facade Pattern** – A unified CityManager simplifies subsystem calls.
- **Builder Pattern** – Construct layered building upgrades.

---

## ✅ Gameplay System Flow

```
Tile Placement → Graph Connection → Population Simulation (BFS)
     ↓                ↓                     ↓
System Needs Check  → Greedy Upgrade → Composite Subsystem Activation
```

---

## 🧩 Design Patterns In Use

- **Composite** – City systems within systems
- **Builder** – Upgrade chains
- **Facade** – Simplified interface for simulation

---

## 🎲 GAS Integration (Gameplay Ability System)

GAS enables macro-level decisions the player can make to solve emergent crises.

### 🚒 Ability: Emergency Response Boost
- **Description:** Temporarily buffs fire/police/medical services.
- **System Behavior:**
  - Adds bonus coverage radius or response speed via attribute mods.
  - May only be used once per crisis event.
- **Why GAS?**
  Encourages strategic timing, uses cooldowns, and integrates with tag-based events.

---

### 🌪️ Ability: Reroute Traffic
- **Description:** Dynamically changes traffic pathfinding to ease congestion.
- **System Behavior:**
  - Temporarily alters graph weights or path logic.
  - Reverts after N seconds or until demand shifts.
- **Why GAS?**
  Time-limited effects, scalable modifiers, and stack logic.

---

## 🤔 Thought Starter

What if your citizens had individual behavior states (workaholic, lazy, nomad)? Could BFS and GAS react to those behaviors in a living simulation?
