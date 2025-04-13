
# 📦 Micro-Project: Crafting System Map

## 🎯 Gameplay Goal:
Design a crafting system where players combine unique ingredients to produce items. Use **sets** to avoid duplicates and **multimaps** to associate ingredients with multiple recipes. The system must validate combinations and handle recipe resolution cleanly.

---

## 🔍 Step 1: Store Unique Ingredients with a Set

### 🎮 What You’re Building:
An inventory that tracks only unique crafting items collected by the player.

### 🧱 Data Structures:
- **Set** – To store ingredients without duplication.
- **Multimap** – To map recipes to multiple valid ingredient combinations.

### 🛠️ In Unreal Engine:
- Use a TSet for inventory storage.
- Use a Multimap or nested map/array for recipe lookup.

---

## 🌐 Step 2: Implement Recipe Validation

- **What You’re Building:**
  - A matching system that checks if the player’s current inventory contains ingredients required for a known recipe.

- **Why Set/Multimap?**
  Sets guarantee uniqueness, while multimaps allow multiple recipes to share ingredients.

### 🧠 What It Powers:
- Fair and flexible crafting
- Hidden/advanced recipes
- Scalable recipe sets

---

## ✅ Gameplay System Flow

```
Item Collected → Added to Set → Recipe Match Search
     ↓                ↓                  ↓
 Multimap Lookup → Valid Recipe → Craft Action Triggered
```

---

## 🧩 Design Patterns In Use

- **Factory** – Create crafted items
- **Strategy** – Allow for alternate crafting paths (e.g., 2 wood or 1 rare gem)

---

## 🎲 GAS Integration (Gameplay Ability System)

Crafting recipes can trigger abilities or unlock effects.

### 🛠️ Ability: Instant Craft
- **Description:** Immediately completes a recipe without needing a station.
- **System Behavior:**
  - Bypasses location requirement and grants item directly.
- **Why GAS?**
  Easily scoped, gated, or limited with tags/cooldowns.

---

### 📖 Ability: Discover Recipe
- **Description:** Automatically reveals a new valid recipe from collected ingredients.
- **System Behavior:**
  - Checks all unseen recipes and shows one match.
- **Why GAS?**
  Randomization and learning logic fits into gameplay effect conditions.

---

## 🤔 Thought Starter

What if recipes could change dynamically based on region, time, or character class? How would your Multimap evolve to support that?
