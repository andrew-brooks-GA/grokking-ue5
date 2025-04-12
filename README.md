# Unreal Engine 5: Data Structures, Algorithms & Design Patterns Roadmap

This roadmap outlines **five mini-projects** designed to help you master:
- **Data Structures** (_Grokking Data Structures_, Marcello La Rocca)  
- **Algorithms** (_Grokking Algorithms_, Aditya Y. Bhargava)  
- **Design Patterns** (_Head First Design Patterns_)  
- **Unreal Engine 5** development

Each project focuses on a different aspect, gradually introducing more complexity and covering a wide range of concepts in both **game dev** and **computer science**.

---

## Table of Contents
1. [Project 1: Data Structures Playground](#project-1-data-structures-playground)
2. [Project 2: AI Maze Explorer](#project-2-ai-maze-explorer)
3. [Project 3: RPG Inventory & Crafting System](#project-3-rpg-inventory--crafting-system)
4. [Project 4: Tower Defense / Wave Spawner](#project-4-tower-defense--wave-spawner)
5. [Project 5: Quest & Dialogue System (Compound)](#project-5-quest--dialogue-system-compound)
6. [Additional Notes](#additional-notes)
7. [License](#license)

---

# Project 1: Data Structures Playground

**Goal**  
Learn and implement fundamental data structures from _Grokking Data Structures_ within a UE5 C++ environment.  
Minimal gameplay logic; focus on building, testing, and debugging your own structures (linked lists, stacks, queues, trees, etc.).

**Key Data Structures & Algorithms**
- Linked Lists (insertion, removal, traversal)
- Stacks & Queues (LIFO/FIFO operations)
- Binary Trees (BFS/DFS traversals)
- Basic Hash Maps (collision handling)
- Optional: **Iterator** pattern

**Progress Checklist**
- [ ] **Linked List**: Create a `Node` class; implement insert, remove, traversal.  
- [ ] **Stack & Queue**: Implement push/pop (stack), enqueue/dequeue (queue).  
- [ ] **Binary Tree**: Insert, search, BFS/DFS traversal logic.  
- [ ] **Hash Map** (optional advanced): Key-value storage, collision handling.  
- [ ] **Iterator Pattern** (optional): Custom iterator to traverse a data structure.

---

# Project 2: AI Maze Explorer

**Goal**  
Build a small maze or puzzle environment where an AI character uses **BFS, DFS, or Dijkstra’s** to find a goal. Leverage a **Strategy Pattern** to swap pathfinding algorithms.

**Key Points**
- **Data Structures**: Graph representation (adjacency lists/arrays)  
- **Algorithms**: BFS, DFS, (Dijkstra’s or A*)  
- **Patterns**: **Strategy** (for pathfinding), **Observer** (optional UI notifications)

**Progress Checklist**
- [ ] **Maze/Graph Setup**: Visual maze or node/edge data.  
- [ ] **Pathfinding Algorithms**: BFS, DFS, and either Dijkstra’s or A*.  
- [ ] **Strategy Pattern**: Switch pathfinding strategies at runtime.  
- [ ] **Observer (optional)**: Notify HUD or logs when the AI reaches a checkpoint.

---

# Project 3: RPG Inventory & Crafting System

**Goal**  
Create a robust inventory system featuring sorting, searching, item creation (via a Factory), and item enhancement (via a Decorator).  

**Key Points**
- **Data Structures**: Arrays, maps, tree-like categories  
- **Algorithms**: Sorting (quicksort/mergesort), binary search  
- **Patterns**:
  - **Decorator** (buffs/effects on items)
  - **Factory** (create items)
  - **Iterator** (inventory traversal)
  - **Observer** (update UI or react to inventory changes)

**Progress Checklist**
- [ ] **Data Structure**: Store items in a `UInventoryComponent` (`TArray` or custom).  
- [ ] **Sorting & Searching**: Implement custom mergesort/quicksort for sorting, binary search for lookups.  
- [ ] **Decorator**: Buff or enchant items with added functionality.  
- [ ] **Factory**: Generate weapons, armor, potions, etc.  
- [ ] **UI Integration**: Basic UMG inventory display (optional **Observer** to refresh UI).  
- [ ] **Crafting**: Combine items or apply decorators to create new items.

---

# Project 4: Tower Defense / Wave Spawner

**Goal**  
Develop a tower defense (or wave-based) prototype to practice advanced AI, scheduling waves, and resource allocation with algorithms like **greedy** or **dynamic programming**.

**Key Points**
- **Data Structures**: Queues, priority queues for spawning waves  
- **Algorithms**: BFS/DFS pathfinding, greedy or DP for resource use  
- **Patterns**:
  - **Command** (build/undo tower placements)
  - **Singleton** (global game manager)
  - **State** (enemy states: idle, pathing, attacking)
  - **Strategy** (enemy attack or tower targeting behaviors)

**Progress Checklist**
- [ ] **Wave Spawner**: Use a queue/priority queue to schedule enemy waves.  
- [ ] **Command**: Place towers (execute) and remove them (undo).  
- [ ] **Singleton**: Manage global currency, wave count, difficulty, etc.  
- [ ] **AI Pathfinding**: BFS/DFS or A* for enemy movement.  
- [ ] **Resource Allocation**: Optionally implement a greedy or DP approach for tower upgrades.  
- [ ] **Enemy States**: Use a simple State machine for enemies (spawn → path → attack → die).

---

# Project 5: Quest & Dialogue System (Compound)

**Goal**  
Tie all concepts together in a more advanced **open-world** or **multi-level** style system. Manage multi-step quests, branching dialogue, saving/loading, etc.

**Key Points**
- **Data Structures**: Trees/graphs for quest lines, BFS/DFS for searching quest states  
- **Algorithms**: BFS/DFS for quest progression, optional DP for advanced branching logic  
- **Patterns**:
  - **Facade** (simplify save/load of multiple subsystems)
  - **Composite** (nested quest objectives or dialogue trees)
  - **Proxy** (lazy loading or remote data)
  - **Template Method** or **State** for quest update logic
  - (And any others you want to consolidate, e.g. Observer, Factory, etc.)

**Progress Checklist**
- [ ] **Quest Graph**: Represent quests as nodes with sub-objectives (Composite or hierarchical tree).  
- [ ] **Dialogue Trees**: Implement branching dialogues with BFS/DFS or state transitions.  
- [ ] **Facade**: Centralized `USaveLoadFacade` to handle game persistence.  
- [ ] **Proxy**: Optionally for large assets or remote data.  
- [ ] **Template Method / State**: For quest updates, transitions between states.  
- [ ] **Integration**: Reuse and refine modules from previous projects where possible (inventory, AI, etc.).

---

## Additional Notes

1. **Scope Management**  
   - It’s easy to get overwhelmed. Start each project small, confirm the core mechanics work, then expand.

2. **Testing & Debugging**  
   - Consider writing small unit tests for your data structures and algorithms. Use `UE_LOG` or custom printouts to confirm correctness.

3. **Integration & Reusability**  
   - These projects can be kept separate, or you can “carry forward” code from one project to the next. 
   - Over time, you’ll accumulate a **library** of systems that can be adapted to real game projects.

4. **Unreal-Specific Knowledge**  
   - Familiarize yourself with `AActor`, `UActorComponent`, `UObject`, `UGameInstance`, Blueprints, UMG, AIController, and NavMesh. 
   - Gradually incorporate more advanced UE features like networking or animation if desired.

5. **Algorithms & Data Structures**  
   - Focus on **why** you’re using BFS, DFS, sorting, etc., for a given scenario. Understanding performance trade-offs is key.

6. **Design Patterns**  
   - Practice decoupling logic and abiding by SOLID principles. Real projects often combine multiple patterns (e.g., a State-driven AI that also uses Strategy for pathfinding).

---

## License

Feel free to use, modify, and distribute this roadmap under any open-source or personal license of your choice. This is a learning resource; the goal is to help you gain expertise in UE5, data structures, algorithms, and design patterns.

---

**Happy Developing!**  
Check off each item as you go, and don’t be afraid to revisit or refine earlier projects once you learn new techniques. The best learning happens iteratively!
