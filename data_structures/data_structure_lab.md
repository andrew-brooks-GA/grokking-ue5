
# 🧪 Project: Codekeeper – Systems of the Ancients

## 🎯 Gameplay Goal:
Rebuild broken core systems of an ancient virtual world. Each system puzzle is powered by a specific data structure from *Grokking Data Structures*. As you repair each one, you unlock deeper layers of the simulation and new gameplay abilities.

---

## 🧩 Level-Based Gameplay (One System per Data Structure)

---

### 🧱 Level 1: The Overflowing Vault (Arrays & Lists)
**System to Repair:** Inventory management is hardcoded to a fixed-size array.

**Challenge Mechanic:**
- Fill the 10-slot array through item pickups.
- Once full, trigger a “Vault Overflow” state.
- Dynamically switch to a **linked list-based inventory** that can expand freely.
- Migrate old data into the new structure without item loss.

**Why This DS:**  
Compare fixed-size (array) vs dynamic (linked list) memory trade-offs in real gameplay.

---

### 🔄 Level 2: Chamber of Cycles (Stacks & Queues)
**System to Repair:** Time rewind and command buffer.

**Challenge Mechanic:**
- Record player actions using a **stack** (LIFO).
- Rewind mistakes by popping the last N actions.
- Implement a **queue** to manage NPC actions (FIFO) in a battle loop.

**Why This DS:**  
Stack = undo system. Queue = turn scheduling or command order.

---

### 🌳 Level 3: The Tree of Power (Trees – Binary & AVL)
**System to Repair:** A skill tree with access constraints.

**Challenge Mechanic:**
- Build a skill tree using a **binary search tree**.
- The tree becomes unbalanced over time.
- Use a “Balance Tree” power to convert it to an **AVL tree** for fair access.

**Why This DS:**  
Shows how balance affects access time and unlock order in hierarchical data.

---

### 🔐 Level 4: The Forgotten Index (Hash Tables)
**System to Repair:** Crafting table can no longer map inputs to outputs.

**Challenge Mechanic:**
- Implement a **hash map** with chaining to resolve ingredient collisions.
- Use a custom hash function to demonstrate distribution quality.
- Trigger random “Collision Events” and fix them in real time.

**Why This DS:**  
Hash maps model fast lookup and collision handling—great for crafting and spell matching.

---

### ⚖️ Level 5: The Arena of Order (Heaps & Priority Queues)
**System to Repair:** Action order system for combat rounds.

**Challenge Mechanic:**
- Implement a **priority queue** to manage unit initiative.
- Dynamically insert, update, or remove units during battle.
- Maintain a visual **binary heap tree** to show structure.

**Why This DS:**  
Core to real-time and turn-based combat pacing.

---

### 🌐 Level 6: The Network Gate (Graphs)
**System to Repair:** The fast-travel system and mission map.

**Challenge Mechanic:**
- Rebuild the map as a graph with rooms as nodes and paths as edges.
- Implement **BFS** for valid traversal and **DFS** to uncover secrets.
- Detect and remove cycles that cause endless loops in travel.

**Why This DS:**  
Graphs represent connectivity. Shows off real world navigation logic.

---

### 🔡 Level 7: The Spell Archive (Tries)
**System to Repair:** Spellcasting autocomplete engine.

**Challenge Mechanic:**
- Insert all known spells into a **Trie**.
- As the player types letters, show predicted matches.
- Add secret spells that only appear when exact prefixes are entered.

**Why This DS:**  
Tries are ideal for prefix-based lookup, especially under time pressure.

---

### ☁️ Level 8: The Fog Chamber (Bloom Filters)
**System to Repair:** Spell detection for incoming threats.

**Challenge Mechanic:**
- Recreate a **Bloom Filter** to identify whether a spell has been seen before.
- Handle **false positives** and explain why they occur.
- Detect if enemies are spoofing spell inputs.

**Why This DS:**  
Bloom Filters balance space efficiency and risk tolerance in large sets.

---

### 🔄 Level 9: The Shrine of Echoes (Sets)
**System to Repair:** Quest engine that prevents duplicate flag setting.

**Challenge Mechanic:**
- Use a **set** to track completed objectives and unlocked paths.
- Fix a bug where a player can repeat quests and stack rewards.
- Apply intersection and difference logic to branch endings.

**Why This DS:**  
Sets ensure uniqueness and allow fast existence checking.

---

## ✅ Gameplay System Flow

```
Start Game → Choose System to Repair
     ↓               ↓
Load Puzzle Logic → Apply DS Solution → Evaluate Outcome
     ↓               ↓
Trigger GAS Power → Unlock Next Level
```

---

## 🧩 Design Patterns In Use

- **Strategy** – Choose data structure implementations at runtime
- **Factory** – Spawn UI components and DS challenges
- **Observer** – Live updates to UI and performance feedback

---

## 🎲 GAS Integration (Gameplay Ability System)

GAS powers that evolve with each system:

| DS | Ability | Effect |
|----|---------|--------|
| Tree | Rebalance | Instantly correct unbalanced skill trees |
| Array | Memory Purge | Resets oldest array elements to clear space |
| Hash Table | Hash Lock | Detect and prevent crafting corruption |
| Priority Queue | Overclock | Force player to front of turn queue |

---

## 🤔 Thought Starter

What if the final boss broke each system *one by one* mid-fight—and you had to rebuild or hot-swap structures dynamically in order to survive?

