
# 🏹 Project 10: Battle Royale Blitz

## 🎯 Gameplay Goal:
Create a fast-paced multiplayer battle royale mode. Players spawn on a shrinking map and compete to survive. Sorting algorithms manage leaderboard updates. Queues handle spawn logistics and elimination. GAS enables dynamic gameplay powers like stealth, healing, and area denial.

---

## 🔍 Step 1: Manage Player Pool and Spawn System

### 🎮 What You’re Building:
A scalable player manager that tracks spawns, deaths, and eliminations. Players spawn in rounds with a queue system.

### 🧱 Data Structures:
- **Dynamic Array** – Track live players and their scores.
- **Queue** – Manage spawn order for late-joining players.
- **Hash Map** – Store equipment, stats, GAS attributes per player.

### 🛠️ In Unreal Engine:
- Use replicated components and GameMode logic to manage state.
- GAS and elimination rules live in Actor Components or GameplayState.

---

## 🌐 Step 2: Implement Leaderboard Using Real-Time Sorting

- **What You’re Building:**
  - A scoreboard that updates every few seconds based on kills, damage dealt, or survival time.

- **Why Sorting?**
  Efficiently rank players as data changes frequently.

### 🧠 What It Powers:
- UI feedback and score announcements
- End-game rankings and victory logic

---

## 🚦 Step 3: Modular Match Logic via Design Patterns

- **Observer Pattern** – UI updates when a player is eliminated.
- **Proxy Pattern** – Player avatars act on behalf of server state.
- **Decorator Pattern** – Buffs and gear apply temporary effect wrappers.

---

## ✅ Gameplay System Flow

```
Player Join → Spawn Queue → Match Start
     ↓               ↓           ↓
 Live Player List  → Events   → Leaderboard Sort
     ↓               ↓           ↓
GAS Triggers → Effects → Elimination or Victory
```

---

## 🧩 Design Patterns In Use

- **Observer** – UI tracking
- **Proxy** – Remote state sync
- **Decorator** – Buffs and perks

---

## 🎲 GAS Integration (Gameplay Ability System)

Abilities drastically influence strategy and moment-to-moment gameplay.

### 🕶️ Ability: Cloak Field
- **Description:** Player becomes invisible to others for a limited time.
- **System Behavior:**
  - Hides from UI + removes targetability tags.
  - On damage or timer, effect breaks.
- **Why GAS?**
  Combines gameplay tags, visual cues, and status tracking.

---

### 🧨 Ability: Zone Lock
- **Description:** Blocks an area of the map for a limited time.
- **System Behavior:**
  - Places hazard volume.
  - Applies damage + movement penalty to enemies.
- **Why GAS?**
  Controlled, strategic area denial using scalable tags + damage models.

---

## 🤔 Thought Starter

What if the last surviving player could “consume” eliminated players’ remaining abilities? How would you represent that progression cleanly using GAS?
