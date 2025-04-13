
# 🚀 Project 5: Space Fleet Commander

## 🎯 Gameplay Goal:
Design a space strategy system where the player commands a fleet navigating between planets and star systems. Each system is a node in a galaxy graph. The player plots hyperspace jumps using **Dijkstra’s Algorithm** to find the shortest route. Events may occur en route, and the player can use abilities to protect or reroute their ships.

---

## 🔍 Step 1: Create the Galaxy Map as a Weighted Graph

### 🎮 What You’re Building:
A map of star systems (nodes) connected by hyperspace lanes (edges). Each connection has a travel cost, such as fuel, time, or risk.

### 🧱 Algorithm + Data Structure:
- **Graph (Weighted)**: Systems = nodes; hyperspace lanes = weighted edges.
- Each node tracks system data and neighboring connections.

### 🛠️ In Unreal Engine:
- Create star systems as actors or widgets placed in 2D/3D space.
- Connections visualized via lines or curved splines.

---

## 🌐 Step 2: Use Dijkstra’s Algorithm for Route Planning

- **What You’re Building:**
  A navigation AI that calculates the most efficient route based on fuel/time.

- **Why Dijkstra’s?**
  It finds the cheapest path from point A to B when edge costs differ.

### 🧠 What It Powers:
- Player routing and re-routing
- Enemy path prediction
- Dynamic cost-based travel

---

## 🚦 Step 3: Add Travel Events and Player Fleet Management

- **Factory Pattern**: Spawn different ship types (scouts, carriers).
- **Observer Pattern**: UI updates when fleet reaches or exits systems.
- **Adapter Pattern**: Convert star system data to visual UI representations.

---

## ✅ Gameplay System Flow

```
Galaxy Nodes + Lanes → Player Route Input → Dijkstra Shortest Path
     ↓                        ↓                     ↓
Display Jump Route     → Travel System       → Random Events/GAS Abilities
```

---

## 🧩 Design Patterns In Use

- **Factory** – Ship construction
- **Adapter** – World data → UI rendering
- **Observer** – Notify fleet arrival events

---

## 🎲 GAS Integration (Gameplay Ability System)

GAS allows space abilities that can manipulate routes, reduce damage, or initiate fast travel.

### ✨ Ability: Warp Shield
- **Description:** Temporarily nullifies danger events during travel.
- **System Behavior:**
  - Applies invulnerability tag and event ignore filters.
  - Lasts one jump cycle.
- **Why GAS?**
  Works well with cooldown, tag-based effect system, and stacking logic.

---

### ⏩ Ability: Emergency Jump
- **Description:** Instantly jump to the next system (skipping one leg of the route).
- **System Behavior:**
  - Requires energy cost and applies a cooldown.
  - Triggers a cutscene or visual hyperspace jump.
- **Why GAS?**
  You can tie ability to stats, upgrade tiers, and consumables.

---

## 🤔 Thought Starter

What happens if enemy ships also use Dijkstra’s to plan around you—or try to intercept? Could you inject false weights or "decoys" into their planning logic?
