# UE5 Game Projects Progress Tracker & Checklist

This repository contains a curated list of UE5 sample game project ideas that combine data structures, algorithms, and design patterns inspired by:

- **Grokking Data Structures** by Marcello La Rocca  
- **Grokking Algorithms** by Aditya Y Bhargava  
- **Head First Design Patterns** by Eric Freeman & Elisabeth Robson  

Each project includes specific checklists that guide you through setting up key systems and implementing the core concepts. All projects are designed to integrate the UE5 Gameplay Ability System (GAS) for a modular, network-ready framework.

---

## Quick Start Guide for Core Concepts

### Data Structures

- **Graph:**  
  - [ ] Create node classes representing rooms, star systems, or grid cells  
  - [ ] Set up connections using arrays (e.g., TArray)

- **Linked List:**  
  - [ ] Implement a class with a data field and a pointer/reference to the next element  
  - [ ] Use for inventory lists or move histories

- **Array/Grid:**  
  - [ ] Use UE5’s TArray for fixed or dynamic collections  
  - [ ] Structure grids for tower defense or tactical maps

- **Heap (Priority Queue):**  
  - [ ] Implement a binary heap (or use available containers)  
  - [ ] Use for scheduling or prioritizing events

- **Queue:**  
  - [ ] Create FIFO structures using TArrays or custom implementations  
  - [ ] Manage spawn orders or event processing

- **Hash Table:**  
  - [ ] Use TMap for quick key-based lookup  
  - [ ] Store player stats, quest keys, or inventory items

### Algorithms

- **DFS & BFS:**  
  - [ ] Write recursive DFS for maze or graph traversal  
  - [ ] Use a queue for BFS to find shortest paths

- **A* / Dijkstra’s:**  
  - [ ] Implement cost-based pathfinding in weighted graphs  
  - [ ] Integrate heuristic functions for A* (if applicable)

- **Recursive Backtracking:**  
  - [ ] Build a recursive function for puzzle solving  
  - [ ] Include logic to backtrack on dead ends

- **Sorting (Quick/Merge):**  
  - [ ] Write sorting routines for ranking and organizing data  
  - [ ] Test with arrays of game objects for performance

- **Dynamic Programming:**  
  - [ ] Break complex decisions into subproblems  
  - [ ] Implement memoization or tabulation techniques

- **Greedy Algorithms:**  
  - [ ] Create algorithms that select the locally optimal choice  
  - [ ] Use in scenarios like resource allocation

### Design Patterns

- **Singleton:**  
  - [ ] Create a static instance (e.g., Game Manager)  
  - [ ] Provide global access methods

- **Observer:**  
  - [ ] Set up event listeners for in-game updates  
  - [ ] Register UI elements or NPC responses

- **Factory Method:**  
  - [ ] Write creation methods for diverse objects (e.g., towers)  
  - [ ] Hide the instantiation logic in subclasses

- **Strategy:**  
  - [ ] Encapsulate interchangeable behaviors (e.g., targeting methods)  
  - [ ] Allow runtime swapping of algorithms

- **State Pattern:**  
  - [ ] Define state classes for objects that change behavior  
  - [ ] Integrate state transitions for quests or AI

- **Command:**  
  - [ ] Encapsulate player actions as objects  
  - [ ] Implement queues for undo/redo features

- **Decorator:**  
  - [ ] Create wrappers to add functionality dynamically  
  - [ ] Use for applying power-ups or additional effects

- **Adapter:**  
  - [ ] Write adapter classes to harmonize incompatible interfaces

- **Facade:**  
  - [ ] Provide a simplified interface to complex subsystems

- **Builder & Composite:**  
  - [ ] Use Builder to streamline complex object creation  
  - [ ] Design Composite structures for nested elements (e.g., city districts)

- **Iterator:**  
  - [ ] Implement a uniform interface to traverse collections

---

## Project Checklists

### 1. Dungeon Navigator  
**Difficulty:** Easiest  
*Players explore a procedurally generated dungeon with interconnected rooms, corridors, and traps.*

- **Graph & Maze Generation:**
  - [ ] Define a Room Node class (data, position, pointers to connected rooms)
  - [ ] Implement a DFS algorithm to recursively generate the dungeon layout
  - [ ] Test maze generation with visual debug outputs

- **Pathfinding:**
  - [ ] Write a BFS function to compute shortest paths between rooms
  - [ ] Use BFS to generate hints or NPC movement

- **Design Patterns:**
  - [ ] Implement a Singleton Game Manager for dungeon generation
  - [ ] Use Observer to notify when a player enters a new room

- **GAS Integration:**
  - [ ] Create a Base Character with an AbilitySystemComponent
  - [ ] Develop abilities such as **"Trap Avoidance"** and **"Speed Boost"**

- **Math Focus:**
  - [ ] Apply basic graph theory and coordinate geometry in layout design

---

### 2. Tower Defense Guardian  
**Difficulty:** Easy–Moderate  
*Defend your base by strategically placing towers along enemy paths to thwart waves of foes.*

- **Grid Setup:**
  - [ ] Create a 2D grid/array for the battlefield
  - [ ] Define placement rules for towers

- **Enemy Scheduling:**
  - [ ] Implement a Queue to manage enemy spawn ordering
  - [ ] Set up a Heap (priority queue) to schedule enemy wave priorities

- **Gameplay Algorithms:**
  - [ ] Use greedy logic to determine which tower upgrades are most beneficial
  - [ ] Implement sorting routines to rank towers/enemy performance

- **Design Patterns:**
  - [ ] Build a Factory Method for dynamic tower instantiation
  - [ ] Enable the Strategy pattern for changing tower targeting behaviors

- **GAS Integration:**
  - [ ] Add GAS-based abilities like **"Overcharge"** and **"Area Slow"**
  - [ ] Ensure each tower or hero unit has an AbilitySystemComponent

- **Math Focus:**
  - [ ] Utilize spatial reasoning and understand priority queues for wave management

---

### 3. Virtual Sports League Manager  
**Difficulty:** Easy–Moderate  
*Manage a sports league by overseeing team rosters, match scheduling, and live updates.*

- **Data Management:**
  - [ ] Set up TArrays/Linked Lists for team rosters and match schedules
  - [ ] Use TMaps (hash tables) to store player statistics

- **Algorithm Implementation:**
  - [ ] Develop sorting routines for leaderboards
  - [ ] Use dynamic programming techniques for scheduling optimization

- **Design Patterns:**
  - [ ] Implement Observer to update live statistics and UI elements
  - [ ] Create a Singleton League Manager for centralized control
  - [ ] Use Command to record events like substitutions and score changes

- **GAS Integration:**
  - [ ] Design abilities such as **"Momentum Shift"** to simulate performance boosts
  - [ ] Link attribute changes to GAS data tables for easy balancing

- **Math Focus:**
  - [ ] Apply basic arithmetic and probability for event simulation

---

### 4. Puzzle Kingdom: The Logic Challenge  
**Difficulty:** Moderate  
*Solve a series of logic puzzles to unlock segments of a forgotten kingdom.*

- **Puzzle Modeling:**
  - [ ] Represent each puzzle as a graph where nodes denote states
  - [ ] Use Stacks to record move history for backtracking

- **Algorithm Implementation:**
  - [ ] Write a recursive backtracking function to explore puzzle solutions
  - [ ] Implement binary search to retrieve sorted hints quickly

- **Design Patterns:**
  - [ ] Use the Template Method to define a common puzzle structure with customizable steps
  - [ ] Apply the Observer pattern to update UI elements when hints are revealed

- **GAS Integration:**
  - [ ] Integrate abilities such as **"Hint Reveal"** or **"Time Freeze"** via GAS
  - [ ] Connect these abilities to puzzle interactions

- **Math Focus:**
  - [ ] Leverage discrete math and logical reasoning for optimal puzzle solving

---

### 5. Space Fleet Commander  
**Difficulty:** Moderate  
*Command a fleet of spaceships to navigate between star systems, engage in battles, and manage resources.*

- **Graph & Array Setup:**
  - [ ] Create a graph representing star systems and connecting routes
  - [ ] Store spaceships in a dynamic array (TArray)

- **Pathfinding:**
  - [ ] Implement A* or Dijkstra’s Algorithm to compute optimal travel paths
  - [ ] Test pathfinding with various weight metrics (distance, fuel, etc.)

- **Design Patterns:**
  - [ ] Use Observer to update fleet and mission status in real time
  - [ ] Implement Adapter pattern if integrating external simulation modules

- **GAS Integration:**
  - [ ] Equip each spaceship with an AbilitySystemComponent
  - [ ] Develop abilities like **"Warp Jump"** or **"Shield Boost"**

- **Math Focus:**
  - [ ] Apply graph theory and vector math for accurate navigation

---

### 6. Quest for the Ancient Artifact  
**Difficulty:** Moderate–Advanced  
*Embark on an open-world RPG journey with branching quests to recover an ancient artifact.*

- **Data Structures Setup:**
  - [ ] Use TMaps for fast inventory and NPC dialogue lookups
  - [ ] Create a tree structure to model branching quest lines

- **Algorithm Implementation:**
  - [ ] Implement Dijkstra’s Algorithm for quest location navigation
  - [ ] Apply dynamic programming to optimize decision paths

- **Design Patterns:**
  - [ ] Use the State Pattern to manage quest progression and scene transitions
  - [ ] Employ Command to encapsulate player actions like using items or making quest decisions

- **GAS Integration:**
  - [ ] Create RPG abilities such as **"Lockpicking"** and **"Spell Casting"** through GAS
  - [ ] Utilize data tables to modify ability effects dynamically during quests

- **Math Focus:**
  - [ ] Utilize graph traversal techniques and probability to inform quest decisions

---

### 7. City Builder: Urban Architect  
**Difficulty:** Advanced  
*Design and manage a bustling city by planning road networks, zoning districts, and balancing resource distribution.*

- **Data Structures Setup:**
  - [ ] Model road networks with graphs
  - [ ] Use trees to represent the hierarchy of zoning (city > district > neighborhood)
  - [ ] Maintain arrays for tracking resources and building inventories

- **Algorithm Implementation:**
  - [ ] Apply BFS to optimize traffic or emergency response routes
  - [ ] Implement a greedy algorithm to allocate resources efficiently

- **Design Patterns:**
  - [ ] Develop a Facade to simplify interactions with complex subsystems (utilities, zoning)
  - [ ] Use Builder and Composite patterns to standardize and modularize construction processes

- **GAS Integration:**
  - [ ] Use GAS on city manager agents to create abilities like **"Emergency Response Boost"**
  - [ ] Set up ability effects that adjust city dynamics (e.g., economic stimulus)

- **Math Focus:**
  - [ ] Leverage optimization techniques and computational geometry for realistic urban planning

---

### 8. Fantasy War Tactics  
**Difficulty:** Advanced  
*Engage in turn-based tactical combat on a grid-based battlefield in a mythical realm.*

- **Data Structures Setup:**
  - [ ] Create a 2D array for the battlefield grid
  - [ ] Use graphs to model legal movement paths within the grid
  - [ ] Maintain a priority queue for unit turn order

- **Algorithm Implementation:**
  - [ ] Implement A* algorithm to plan unit movement
  - [ ] Apply sorting algorithms to determine unit sequencing for attacks
  - [ ] Use binary search for inventory or ability lookup

- **Design Patterns:**
  - [ ] Use Command pattern to encapsulate unit actions (move, attack, defend)
  - [ ] Implement an Iterator to traverse grid cells for nearby enemies or effects
  - [ ] Combine Adapter and Template Method patterns to standardize battle phases

- **GAS Integration:**
  - [ ] Equip each unit with an AbilitySystemComponent
  - [ ] Develop tactical abilities like **"Special Attack"** or **"Defensive Stance"** via GAS

- **Math Focus:**
  - [ ] Incorporate grid-based spatial calculations and vector operations for unit movement

---

### 9. Robotic Arena: AI Combat Simulator  
**Difficulty:** Advanced–Very Challenging  
*Program autonomous robots to battle in a dynamic arena, focusing on AI behavior and rapid decision-making.*

- **Data Structures Setup:**
  - [ ] Use TArrays to store active robot entities
  - [ ] Implement TMaps for quick status and resource lookups
  - [ ] Model the arena using graphs for obstacle navigation

- **Algorithm Implementation:**
  - [ ] Integrate A* pathfinding for efficient navigation
  - [ ] Utilize dynamic programming to optimize sequences of combat decisions

- **Design Patterns:**
  - [ ] Apply the Strategy pattern to allow switching between various AI tactics
  - [ ] Use the State pattern for managing robot behavioral changes (idle, attacking, retreating)
  - [ ] Encapsulate robot actions with the Command pattern for modularity

- **GAS Integration:**
  - [ ] Develop AI abilities such as **"Charge"**, **"Evasive Maneuver"**, or **"Power Surge"**
  - [ ] Ensure that each robot’s AbilitySystemComponent is set up to allow for future networking and replication

- **Math Focus:**
  - [ ] Deepen understanding of advanced graph theory, dynamic programming, and probability for AI decision-making

---

### 10. Battle Royale Blitz  
**Difficulty:** Very Challenging  
*Compete in a multiplayer battle royale where players face off in a dynamically shrinking arena.*

- **Data Structures Setup:**
  - [ ] Implement dynamic arrays or linked lists to track active players
  - [ ] Use TMaps to maintain live player stats and leaderboards
  - [ ] Create queues for matchmaking and respawn logic

- **Algorithm Implementation:**
  - [ ] Use merge sort to update leaderboards efficiently
  - [ ] Apply greedy methods to allocate resources (loot, spawn points) in real time

- **Design Patterns:**
  - [ ] Apply the Decorator pattern to dynamically add power-ups and abilities to players
  - [ ] Use a Singleton pattern for centralized game state management, such as arena boundaries
  - [ ] Implement a Proxy to handle network communication for smooth client-server interactions

- **GAS Integration:**
  - [ ] Set up high-impact abilities like **"Ultimate Moves"** or **"Area Denial"** using GAS
  - [ ] Configure replication and client-side prediction in GAS to prepare for multiplayer gameplay

- **Math Focus:**
  - [ ] Tackle real-time data processing and computational geometry for spatial awareness in a fast-paced environment

---

## Additional Learning and Considerations

- **Mathematics:**  
  Each project introduces various mathematical principles—from graph theory and spatial geometry to advanced optimization and probability. Strengthen these skills to efficiently implement and debug your systems.

- **UE5 Gameplay Ability System (GAS):**  
  Integrating GAS early in your projects provides a modular, data-driven foundation for abilities. This framework facilitates both single-player prototyping and future multiplayer expansion with built-in replication features.

- **Incremental Development:**  
  Start small with minimum viable products (MVPs) and iterate. Use free assets, online tutorials, and community resources as you build out your projects.

---

## Conclusion

This repository serves as a step-by-step roadmap to build a series of UE5 projects that combine key data structures, algorithms, and design patterns—all integrated with the UE5 Gameplay Ability System. Each project is laid out as a checklist with actionable steps, guiding you not only on *what* to build, but specifically *how* to construct, implement, and test each component.

Happy coding and game developing!
