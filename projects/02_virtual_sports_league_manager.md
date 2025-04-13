
# 🏅 Project 2: Virtual Sports League Manager

## 🎯 Gameplay Goal:
Build a sports league simulation where teams compete in weekly matches across a full season. The player manages one of the teams—tracking wins, losses, player stats, and rankings. The game uses sorting algorithms to generate leaderboards and dynamic programming to simulate season outcomes. The player can activate motivational abilities to impact team performance using GAS.

---

## 🔍 Step 1: Set Up Teams, Players, and Season Data Structures

### 🎮 What You’re Building:
Define a league with N teams. Each team has a roster of players, and each player tracks stats like score, assists, energy, etc. You’ll also define a full match schedule for the season.

### 🧱 Data Structures:
- **Array**: Store team list and match schedule.
- **Linked List**: Track in-game events during a match (for replays or summaries).
- **Hash Table**: Store player stats and lookup by name or ID.

### 🛠️ In Unreal Engine:
- Teams and players can be represented by Data Assets or structs.
- Schedule and season logic can live in a manager component or GameInstance.

---

## 🌐 Step 2: Simulate Matches and Update Rankings Using Algorithms

- **What You’re Building:**
  - A match simulator that resolves games and updates stats.
  - A ranking engine that calculates leaderboard standings.

- **Why Sorting?**
  Sort teams by win ratio, goal difference, or total points to display the leaderboard.

- **Why Dynamic Programming?**
  For predictive outcomes: “If we win the next two games, what are our chances to reach the finals?”

### 🧠 What It Powers:
- Player stats, team stats, and league-wide leaderboard.
- Dynamic projections and strategy tools for the player.

---

## 🚦 Step 3: Design Pattern Integration for Simulation & Management

- **Command Pattern**: Queue and apply match events (goal, foul, substitution).
- **Observer Pattern**: Broadcast score updates to UI or announcer.
- **Singleton Pattern**: Centralized GameManager handles the entire season state.

---

## ✅ Gameplay System Flow

```
Team Setup → Match Schedule → Simulate Matches → Update Stats
     ↓            ↓                 ↓               ↓
Player Interaction       → Command Queue     → Observer Event
     ↓            ↓                 ↓               ↓
Leaderboard Update ← Sorting & Dynamic Projections ← GAS Boosts
```

---

## 🧩 Design Patterns In Use

- **Command** – Represent actions in a match (goal, card, etc.)
- **Observer** – Trigger UI animations and announcers
- **Singleton** – Central match and stat manager

---

## 🎲 GAS Integration (Gameplay Ability System)

In this project, GAS allows the player to influence match outcomes with motivational “coach” abilities.

### 💬 Ability: Momentum Shift
- **Description:** Give your team a temporary performance boost mid-game.
- **System Behavior:**
  - Increases team energy and aggression stats for 2–3 plays.
  - Triggers cheering animation and commentary.
- **Why GAS?**
  Allows effects with cooldowns, tags, and context-aware application.

---

### 🧘 Ability: Reset Morale
- **Description:** Calm down a flustered team after a major loss.
- **System Behavior:**
  - Resets performance penalties caused by low morale.
  - May only be used once per season.
- **Why GAS?**
  Adds meta-strategy through cooldown, resource gating, and one-time-use logic.

---

## 🤔 Thought Starter

What if each player had their own individual GAS-driven traits (like "Clutch Finisher" or "Defensive Wall") that activated contextually? How would you scale that system while maintaining match balance?
