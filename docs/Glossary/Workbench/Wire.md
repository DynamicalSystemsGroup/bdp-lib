---
title: Wire
nav_order: 2
layout: default
parent: Workbench
---

# Wire

A wire represents the transfer of a space between a terminal and a port.

## Schema

```
object {
    ID: string (required)
    Parent: string (required)
    Source: object {
      Processor: string
      Index: integer
    }
    Target: object {
      Processor: string
      Index: integer
    }
  }
```

- In both cases for Source/Target, the processor should be an ID of a valid processor
- The index is a 0-indexed index which references which index of the array of terminals (for a source) or array of ports (for a target) is being connected to the wire