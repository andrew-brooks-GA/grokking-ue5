
# 🏰 Project 4: Dungeon Navigator

## 🎯 Gameplay Goal:
Design a procedurally generated dungeon made of interconnected rooms and hallways. The player explores this dungeon, revealing new areas as they move. The dungeon is generated using **Depth-First Search (DFS)**, modeled as a **graph**, and pathfinding within the dungeon uses **Breadth-First Search (BFS)**. The player can unlock traversal-based abilities like seeing hidden doors or warping between rooms via GAS.

---

## 🔍 Step 1: Generate the Dungeon Layout Using DFS

### 🎮 What You’re Building:
Create a dungeon map of rooms arranged on a grid. The algorithm starts from a random room and carves a path deeply before backtracking—naturally forming a maze-like structure.

### 🧱 Algorithm + Data Structure:
- **Depth-First Search (DFS)** for maze generation
- **Graph** structure where each node = a room
- Edges = doors or hallways between rooms

### 🛠️ In Unreal Engine:
- Use procedural mesh components or modular level pieces (rooms, halls).
- Rooms are actors or data structs with a list of connected neighbors.
- DFS is used at runtime or on level load to carve the layout.

---

## 🌐 Step 2: Model and Explore the Dungeon as a Graph

- **What You’re Building:**
  - Every room is connected as a node in a graph.
  - Graph traversal logic is used for fog-of-war, quest routing, and AI path hints.

- **Why a Graph?**
  A graph makes it easy to:
  - Visualize connections
  - Perform pathfinding (BFS, A*)
  - Track player’s exploration state

### 🧠 What It Powers:
- Minimap systems
- Room visitation logic
- AI or NPC movement between rooms

---

## 🚦 Step 3: Use BFS for Navigation and Pathfinding

- **What You’re Building:**
  - A system to find shortest paths between two rooms (e.g. current position to objective).
  - Used for guiding the player or NPC companions.

- **Why BFS?**
  BFS guarantees the shortest number of steps in an unweighted graph (like a dungeon).

---

## ✅ Gameplay System Flow

```
Grid of Rooms → DFS Maze Generation → Graph Construction
     ↓                    ↓                   ↓
Player Enters Room   → Connect Nodes     → BFS Hint System
     ↓                    ↓                   ↓
Fog Reveal + GAS Trigger  → UI/Map Update → Next Objective Path
```

---

## 🧩 Design Patterns In Use

- **Singleton** – DungeonManager generates and stores dungeon layout
- **Observer** – Minimap and UI update when rooms are discovered
- **Factory** – Modular spawning of rooms and doors

---

## 🎲 GAS Integration (Gameplay Ability System)

These abilities help the player explore, escape, or manipulate the dungeon environment.

### 🔍 Ability: Hidden Door Reveal
- **Description:** Temporarily highlights hidden or secret passages on the minimap.
- **System Behavior:**
  - BFS used to locate “hidden” tagged edges in graph.
  - Triggers FX or map updates for player visibility.
- **Why GAS?**
  Enhances player agency with context-based exploration powers.

---

### 🌀 Ability: Warp Step
- **Description:** Instantly transports the player to a previously visited room.
- **System Behavior:**
  - Performs a BFS check to confirm the room is reachable and previously explored.
  - Applies teleport + cooldown gameplay effect.
- **Why GAS?**
  Enforces limits on mobility and integrates with exploration rules.

---

## 🤔 Thought Starter

What if room connections were dynamic (i.e., traps or magic doors rewiring parts of the graph)? How would that impact the logic for pathfinding and fog-of-war tracking?
