---
title: Block Validation Guide
nav_order: 1
layout: default
parent: Functions & Validation Rules
---

# WORK IN PROGRESS - NOT READY



Work originally written by Michael Zargham:


# Block Validation Guide

This guide explains how to determine whether a **block diagram model** can serve as a **valid substitute** for a block pattern.

---

## **1. Overview**
A **Block** defines an **abstract pattern** with:
- **Domain (inputs, from specific spaces)** → These must be fully supported.
- **Codomain (outputs, from specific spaces)** → The model must provide these outputs.

A **Processor** is a **specific implementation** of a block, but **a subsystem composed of multiple processors could also satisfy a block**.

### **Substitutability Test**
💡 **Can this model be used in place of a processor that directly implements the block?**

---

## **2. The Two Block Patterns**
| **Block Name**   | **Inputs (Domain)** | **Outputs (Codomain)** |
|----------------|----------------|-----------------|
| **`open_game`** | `["U", "U"]`  | `["Y", "Y"]` |
| **`closed_game`** | `[]`  | `["U", "U", "Y", "Y"]` |

### **Block Definitions**
#### **📝 `open_game.json`**
```json
{
  "ID": "open_game",
  "Name": "Open Game",
  "Description": "A game that accepts player actions and produces payoffs.",
  "Domain": ["U", "U"],
  "Codomain": ["Y", "Y"]
}
```
#### **📝 `closed_game.json`**
```json
{
  "ID": "closed_game",
  "Name": "Closed Game",
  "Description": "A game where players' policies are included, requiring no external inputs, but tracking both actions and payoffs.",
  "Domain": [],
  "Codomain": ["U", "U", "Y", "Y"]
}
```

---

## **3. Four Example Models**
Each of these models will be tested against either `open_game` or `closed_game`.

| **Type**         | **Matches `open_game`?** | **Matches `closed_game`?** |
|----------------|----------------------|---------------------------|
| **Simple Open Game**  | ✅ **Valid Substitute** | ❌ **Invalid** |
| **Detailed Open Game** | ✅ **Valid Substitute** | ❌ **Invalid** |
| **Simple Closed Game** | ❌ **Invalid** | ✅ **Valid Substitute** |
| **Detailed Closed Game** | ❌ **Invalid** | ✅ **Valid Substitute** |

---

## **4. Example JSON Models**
### **📝 Model 1: Simple Open Game (✅ Valid for `open_game`)**
A **single `Game` processor** implementing `open_game`.

```json
{
  "processors": [
    {
      "ID": "game_instance",
      "Parent": "Game",
      "Name": "Simple Game",
      "Ports": ["U", "U"],
      "Terminals": ["Y", "Y"]
    }
  ]
}
```
✅ **Matches `open_game`** because:
- It has **exactly** the required inputs and outputs.

---

### **📝 Model 2: Detailed Open Game (✅ Valid for `open_game`)**
A **stateful game (`dynamic_game_model`) implementing `open_game`**.

```json
{
  "processors": [
    {
      "ID": "dynamics",
      "Parent": "F",
      "Name": "Game Dynamics",
      "Ports": ["X", "U"],
      "Terminals": ["X"]
    },
    {
      "ID": "sensor",
      "Parent": "S",
      "Name": "Game Sensor",
      "Ports": ["X"],
      "Terminals": ["Y"]
    }
  ],
  "wires": [
    {
      "ID": "w1",
      "Parent": "U",
      "Source": ["dynamics", 1],
      "Destination": ["sensor", 0]
    }
  ]
}
```
✅ **Matches `open_game`** because:
- Despite using state (`X`), it **still has two `U` inputs and two `Y` outputs**.

---

### **📝 Model 3: Simple Closed Game (✅ Valid for `closed_game`)**
A **single `Game` processor**, but **with policies included**.

```json
{
  "processors": [
    {
      "ID": "game_instance",
      "Parent": "Game",
      "Name": "Simple Game",
      "Ports": [],
      "Terminals": ["U", "U", "Y", "Y"]
    },
    {
      "ID": "policy_1",
      "Parent": "G",
      "Name": "Player 1 Policy",
      "Ports": ["Y"],
      "Terminals": ["U"]
    },
    {
      "ID": "policy_2",
      "Parent": "G",
      "Name": "Player 2 Policy",
      "Ports": ["Y"],
      "Terminals": ["U"]
    }
  ],
  "wires": [
    {
      "ID": "w1",
      "Parent": "U",
      "Source": ["policy_1", 0],
      "Destination": ["game_instance", 0]
    },
    {
      "ID": "w2",
      "Parent": "U",
      "Source": ["policy_2", 0],
      "Destination": ["game_instance", 1]
    }
  ]
}
```
✅ **Matches `closed_game`** because:
- The policies **remove external inputs (`U`)**, making it self-contained.
- It **explicitly outputs both `U` (actions taken) and `Y` (payoffs).**

---

### **📝 Model 4: Detailed Closed Game (✅ Valid for `closed_game`)**
The **dynamic game, but with policies included**, making it self-contained.

```json
{
  "processors": [
    {
      "ID": "dynamics",
      "Parent": "F",
      "Name": "Game Dynamics",
      "Ports": ["X", "U"],
      "Terminals": ["X"]
    },
    {
      "ID": "sensor",
      "Parent": "S",
      "Name": "Game Sensor",
      "Ports": ["X"],
      "Terminals": ["Y"]
    },
    {
      "ID": "policy_1",
      "Parent": "G",
      "Name": "Player 1 Policy",
      "Ports": ["Y"],
      "Terminals": ["U"]
    },
    {
      "ID": "policy_2",
      "Parent": "G",
      "Name": "Player 2 Policy",
      "Ports": ["Y"],
      "Terminals": ["U"]
    }
  ],
  "wires": [
    {
      "ID": "w1",
      "Parent": "U",
      "Source": ["policy_1", 0],
      "Destination": ["dynamics", 1]
    },
    {
      "ID": "w2",
      "Parent": "U",
      "Source": ["policy_2", 0],
      "Destination": ["dynamics", 1]
    },
    {
      "ID": "w3",
      "Parent": "Y",
      "Source": ["sensor", 0],
      "Destination": ["policy_1", 0]
    },
    {
      "ID": "w4",
      "Parent": "Y",
      "Source": ["sensor", 1],
      "Destination": ["policy_2", 0]
    }
  ]
}
```
✅ **Matches `closed_game`** because:
- The policies **remove external inputs (`U`)**, making it self-contained.
- The game **explicitly outputs `U` (actions taken) and `Y` (payoffs).**

---

### **5. Summary**
✅ **A model satisfies a block if:**
- It **accepts the required inputs** (or none, for `closed_game`).
- It **produces the required outputs** (`Y` and, for `closed_game`, `U` as well).