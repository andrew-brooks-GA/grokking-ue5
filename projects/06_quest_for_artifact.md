
# 🗺️ Project 6: Quest for the Ancient Artifact

## 🎯 Gameplay Goal:
Create a quest-based RPG system where players make branching decisions that affect the outcome of their journey. The map is a tree of locations and events, and the optimal path to success is found using **Dynamic Programming** to evaluate potential routes. The player can unlock tools or abilities to bypass obstacles or gain better outcomes.

---

## 🔍 Step 1: Model the World as a Quest Tree

### 🎮 What You’re Building:
A branching map of quest locations. Each node is a challenge, event, or opportunity with different rewards or consequences.

### 🧱 Data Structures:
- **Tree**: Each location/event has children based on player choices.
- **Hash Table**: Store player inventory and quest flags.

### 🛠️ In Unreal Engine:
- Use datatables or structs for quests.
- Track quest state via an RPGManager component or QuestSystem.

---

## 🌐 Step 2: Use Dynamic Programming to Choose Optimal Path

- **What You’re Building:**
  A system that computes the best path based on inventory, risk, and rewards.

- **Why Dynamic Programming?**
  Many paths may share sub-problems. DP prevents redundant evaluation and ensures optimality.

### 🧠 What It Powers:
- Adaptive storytelling
- Optimal rewards for limited actions
- Branch-based replays and failure mitigation

---

## 🚦 Step 3: Implement Dialogue, Item Checks, and Quest Events

- **State Pattern**: Quest stages and branching dialogue options.
- **Command Pattern**: Player actions (talk, trade, fight) are encapsulated for modularity.
- **Builder Pattern**: Construct complex quest structures step-by-step.

---

## ✅ Gameplay System Flow

```
Start Location → Tree Expansion → Event Decision
     ↓                   ↓               ↓
Inventory Check → Dynamic Score Eval → Path Confirmed
```

---

## 🧩 Design Patterns In Use

- **State** – Track quest progression
- **Command** – Encapsulate actions
- **Builder** – Assemble branching logic

---

## 🎲 GAS Integration (Gameplay Ability System)

GAS lets you build quest-related powers like bypassing skill checks or revealing hidden paths.

### 🧠 Ability: Memory Vision
- **Description:** Reveals one possible consequence of a future choice.
- **System Behavior:**
  - Looks ahead in the quest tree and displays alternate options.
  - Tag-limited and costs mental energy stat.
- **Why GAS?**
  Tag conditions and attribute scaling make this dynamic.

---

### 🔓 Ability: Master Key
- **Description:** Automatically bypasses one locked option (dialogue, door).
- **System Behavior:**
  - Overrides a check once per quest line.
  - Cooldown limited or gated per quest arc.
- **Why GAS?**
  Works well with gameplay tags and one-time-use triggers.

---

## 🤔 Thought Starter

What if your decisions left “echoes” in the world that changed future quests? Could a dynamic programming structure allow those echoes to ripple backward?
