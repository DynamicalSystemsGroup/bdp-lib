---
title: Processor
nav_order: 1
layout: default
parent: Workbench
---

# Processor

A processor is an instance of a block that interacts within the system based on its structure. Beyond a basic processor there is also a special case of the composite processor which functions as a processor which represents an actual system, allowing for composability. This idea is explained in the composite processor section.

## Schema

```
object {
    ID: string (required)
    Name: string (required)
    Description: string
    Parent: string (required)
    Ports: array[string]
    Terminals: array[string] (required)
    Subsystem: object {
      System ID: string (required)
      Wires: array[string] (required)
    }
  }
```

## Composite Processor