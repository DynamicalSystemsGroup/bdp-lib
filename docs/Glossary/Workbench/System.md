---
title: System
nav_order: 3
layout: default
parent: Workbench
---

# System

## Schema

```
object {
    ID: string (required)
    Name: string (required)
    Description: string
    Processors: array[string] (required)
    Wires: array[string] (required)
  }
```