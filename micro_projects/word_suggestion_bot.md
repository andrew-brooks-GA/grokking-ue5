
# 🔠 Micro-Project: Word Suggestion Bot

## 🎯 Gameplay Goal:
Create an in-game autocomplete system for naming characters, casting spells, or using commands in a console. This system uses a **Trie** data structure to provide fast, efficient word predictions based on user input.

---

## 🔍 Step 1: Build a Trie and Insert Word Set

### 🎮 What You’re Building:
A data structure that stores strings in a prefix tree format. Each letter is a node that connects to children representing valid next characters.

### 🧱 Data Structure:
- **Trie (Prefix Tree)** – Enables fast prefix-based searches and insertions.

### 🛠️ In Unreal Engine:
- The Trie can be implemented in C++ or Blueprints using nested structs.
- Connect the Trie logic to a UI text input box to suggest completions.

---

## 🌐 Step 2: Implement Search and Autocomplete Behavior

- **What You’re Building:**
  - A lookup system that returns valid suggestions as the player types.
  - Filtering based on context or category (e.g., "spells", "commands").

- **Why Trie?**
  Provides O(k) lookup time where k = prefix length, regardless of dataset size.

### 🧠 What It Powers:
- Immersive command systems
- Spell-casting UIs
- Chat or NPC dialog

---

## ✅ Gameplay System Flow

```
Player Types Text → Trie Prefix Match → Suggestion List Displayed
     ↓                     ↓                    ↓
UI Updates → Accept Suggestion → Trigger Effect or Use Item
```

---

## 🧩 Design Patterns In Use

- **Iterator** – Traverse suggestion list
- **Factory** – Generate suggestion entries in UI

---

## 🎲 GAS Integration (Gameplay Ability System)

Abilities can be triggered by full word matches, creating a predictive input system.

### 🔤 Ability: Cast Autocomplete Spell
- **Description:** Autocompletes spell name and activates it immediately.
- **System Behavior:**
  - Matches full string → maps to GAS tag → activates ability.
- **Why GAS?**
  Hooks into a scalable ability system with tag-based matching.

---

### 💡 Ability: Dynamic Suggestion Unlock
- **Description:** As the player levels up, new words or commands are added to the Trie.
- **System Behavior:**
  - Updates word list from character level or tag triggers.
- **Why GAS?**
  Allows ability progression to influence input systems.

---

## 🤔 Thought Starter

What if certain rare suggestions only appeared when the player has specific buffs or gear equipped?
