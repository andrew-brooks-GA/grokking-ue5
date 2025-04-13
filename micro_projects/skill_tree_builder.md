
# 🎯 Micro-Project: Skill Tree Builder

## 🎯 Gameplay Goal:
Build a branching skill tree system where unlocking one ability unlocks its children. The structure should follow a **tree**, with unlock rules, dependencies, and dynamic updates to reflect the player’s progression.

---

## 🔍 Step 1: Define Skill Nodes and Tree Layout

### 🎮 What You’re Building:
Each skill is a node. Nodes connect hierarchically and require parent nodes to be unlocked first. Some trees may allow horizontal or multiple parent paths.

### 🧱 Data Structure:
- **Tree** – Parent/child relationships between skills.
- **Hash Map** – Store unlock flags and skill metadata.

### 🛠️ In Unreal Engine:
- Skill nodes can be USTRUCTs or UObjects.
- Tree displayed using UMG with unlock status tracked on click.

---

## 🌐 Step 2: Implement Unlock Logic and Dependencies

- **What You’re Building:**
  - A rule engine that validates whether a skill is unlockable.
  - Updates child availability when a parent is learned.

- **Why Trees?**
  Trees give you depth-first and breadth-first paths with minimal complexity.

### 🧠 What It Powers:
- Deep progression without clutter
- Skill gating and pacing
- Custom builds based on choices

---

## ✅ Gameplay System Flow

```
Player XP Gained → Skill Unlock Click → Dependency Check
     ↓                    ↓                ↓
Node Unlock        → Enable Child Skills → GAS Ability Unlock
```

---

## 🧩 Design Patterns In Use

- **Composite** – Treat skill trees as nested parts
- **Observer** – Notify UI when new skills unlock
- **Builder** – Generate complex trees dynamically

---

## 🎲 GAS Integration (Gameplay Ability System)

Skills correspond directly to GAS abilities or tags.

### 💡 Ability: Unlock Passive Bonus
- **Description:** Grants passive effects like +10% crit or health regen.
- **System Behavior:**
  - Applies a permanent Gameplay Effect once skill is unlocked.
- **Why GAS?**
  Cleanly connects skill UI and backend effects.

---

### ⚔️ Ability: Active Skill Learn
- **Description:** Enables a new combat ability (e.g., "Power Slash").
- **System Behavior:**
  - Grants ability via GAS AbilitySystemComponent.
- **Why GAS?**
  It’s the standard method for modular, tag-driven ability management.

---

## 🤔 Thought Starter

What if players could respec—undo tree branches and regain spent points? How would you track parent-child dependencies during reversal?
