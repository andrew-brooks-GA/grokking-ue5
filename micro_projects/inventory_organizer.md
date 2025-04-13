
# 🧃 Micro-Project: Inventory Organizer

## 🎯 Gameplay Goal:
Design a dynamic inventory system that allows players to collect, remove, and cycle through items in the order they were added. This system supports **undo/redo mechanics** using a **linked list**, and showcases how item history and reversible actions can feel natural in gameplay.

---

## 🔍 Step 1: Build the Inventory Using a Doubly Linked List

### 🎮 What You’re Building:
Each inventory item is a node in a list. Players can scroll through, add new items, remove old ones, or undo recent actions.

### 🧱 Data Structure:
- **Doubly Linked List** – Enables backward and forward traversal with minimal overhead.

### 🛠️ In Unreal Engine:
- Use a USTRUCT or UObject to define inventory nodes.
- Use pointers (or array indices) to connect previous/next items.
- Display current item visually via UI or HUD.

---

## 🌐 Step 2: Add Undo/Redo History and Limits

- **What You’re Building:**
  - A stack-based memory of actions (pickup, drop, consume).
  - Let the player undo/redo a limited number of steps.

- **Why Linked List?**
  It's ideal for maintaining item order and enables clean insert/delete at runtime.

### 🧠 What It Powers:
- Quick item swapping and reversal
- Strategic usage of consumables
- Satisfaction from responsive undo actions

---

## ✅ Gameplay System Flow

```
Item Pickup → Add Node → Display Active Item
     ↓              ↓           ↓
Undo Pressed → Step Back → Item Restored or Reversed
```

---

## 🧩 Design Patterns In Use

- **Command Pattern** – Store undoable actions
- **Iterator** – Scroll through inventory
- **Memento** (optional) – Snapshot inventory state

---

## 🎲 GAS Integration (Gameplay Ability System)

Abilities linked to inventory can activate on item usage or combination.

### 🧪 Ability: Quick Use
- **Description:** Immediately consumes the current item.
- **System Behavior:**
  - Applies an effect based on the item's properties.
  - Triggers cooldown on inventory slot.
- **Why GAS?**
  Allows attribute-driven item consumption with extensible gameplay effects.

---

### ♻️ Ability: Undo Use
- **Description:** Rewinds the last item interaction (e.g., restores a used potion).
- **System Behavior:**
  - Re-adds last node if valid.
  - May only be used a limited number of times.
- **Why GAS?**
  Encapsulates usage constraints and reuse logic in a controlled way.

---

## 🤔 Thought Starter

What if you could rewind multiple actions at once—what design would keep it intuitive without breaking player flow?
