
# 🏰 Project 1: Dungeon Navigator Explained

Your primary goal is to understand how a maze (dungeon) can be effectively generated and modeled using both a **Graph** data structure and the **Depth-First Search (DFS)** algorithm.

## 🔍 Step 1: Use DFS to Generate the Maze
DFS works by visiting nodes (rooms) recursively, creating paths by connecting unvisited rooms until no unvisited neighbors remain.

**Why DFS?**
It naturally produces branching, maze-like structures—perfect for procedural dungeon generation, ensuring each room is reachable.

**Visually:** DFS explores deeply into paths first, creating winding corridors and dead-ends, ideal for dungeon crawlers.

## 🌐 Step 2: Represent Your Maze as a Graph
Each room becomes a node (vertex), and connections between rooms become edges.

**Why a Graph?**
Clearly represents room interconnectivity, ideal for pathfinding and dynamic game state updates.

**Visually:** Clearly illustrates room connections, aiding navigation logic.

## 🚦 Step 3: Use BFS to Navigate
Use Breadth-First Search (BFS) for efficient shortest-path navigation.

**Why BFS?**
Ensures optimal paths for player and NPC navigation, useful for game hints.

## ✅ Project Flow in Short:
- **DFS →** Procedurally generate dungeon structure.
- **Graph →** Model dungeon.
- **BFS →** Navigate dungeon.

## 🎲 Gameplay Ability System (GAS) Role:
Introduce abilities like **"Trap Avoidance"** (disable trap interactions temporarily) and **"Speed Boost"** (enhance player speed).

## Thought Starter:
How does altering DFS (room size or branching) affect exploration?
