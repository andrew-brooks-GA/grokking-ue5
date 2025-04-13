
# 🤖 Project 9: Robotic Arena: AI Combat Simulator

## 🎯 Gameplay Goal:
Develop an arena-based combat game where robotic units fight autonomously based on programmed logic. Each robot evaluates its environment using **decision trees** and **state machines**, choosing behaviors like attack, defend, or reposition. GAS is used to implement customizable active and passive modules, like shields or targeting systems.

---

## 🔍 Step 1: Define the Robot AI Framework

### 🎮 What You’re Building:
Each robot acts based on internal logic without direct player control. The game loop constantly evaluates conditions to switch behaviors.

### 🧱 Data Structures:
- **Hash Table** – Store sensors, cooldowns, threat levels.
- **State Machine** – Tracks whether robot is idle, attacking, fleeing, etc.
- **Decision Tree** – Makes higher-order choices using conditional branches.

### 🛠️ In Unreal Engine:
- Robots are controlled by AI Controllers and Behavior Components.
- Each robot blueprint includes sensors (raycasts, distance checks) and state logic.

---

## 🌐 Step 2: Implement AI Decision Logic

- **What You’re Building:**
  - A decision tree that picks an action (engage, reposition, defend).
  - A state machine that maintains behavior between ticks.

- **Why These Algorithms?**
  Decision trees are intuitive for strategy. State machines are stable and easy to debug.

### 🧠 What It Powers:
- Smooth behavior switching
- Dynamic, autonomous combat

---

## 🚦 Step 3: Modularize Actions with Design Patterns

- **Strategy Pattern** – Swap out combat approaches (melee, ranged, flank).
- **State Pattern** – AI shifts between idle, chase, flee, retreat, etc.
- **Command Pattern** – Queue and execute robot actions (fire, scan, reload).

---

## ✅ Gameplay System Flow

```
Evaluate Sensors → Decision Tree → Choose Action
     ↓                     ↓              ↓
Update State Machine   → Command Execution → Next Tick
```

---

## 🧩 Design Patterns In Use

- **Strategy** – Combat plans
- **State** – Mode switching
- **Command** – Execute robot behaviors

---

## 🎲 GAS Integration (Gameplay Ability System)

Robots are fitted with modular abilities that enhance or override their behavior.

### 🧲 Ability: Magnetic Pulse
- **Description:** Emits an AoE that disables nearby enemies' abilities for a few seconds.
- **System Behavior:**
  - Applies a suppression tag to other robots.
  - Interrupts current actions and disables abilities.
- **Why GAS?**
  Controlled via tags, duration, and resistances.

---

### 🛡️ Ability: Reactive Shield
- **Description:** Activates a damage-absorbing barrier when health is low.
- **System Behavior:**
  - Triggers via gameplay tag listener.
  - Applies shield attribute and blocks certain damage types.
- **Why GAS?**
  Enables conditional logic and reactive mechanics.

---

## 🤔 Thought Starter

What if robots could “hack” each other mid-match to temporarily change enemy logic trees or swap states? How would you protect or exploit that?
