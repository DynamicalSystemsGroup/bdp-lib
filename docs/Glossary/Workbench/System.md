---
title: System
nav_order: 3
layout: default
parent: Workbench
---

# System

Systems have an array of processors and wires (referenced by ID) which when put together describes the full graph.

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

- The attributes of processors and wires are arrays of strings that should match up with actual IDs of processors and wires in the workbench.