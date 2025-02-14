---
title: Space
nav_order: 2
layout: default
parent: Toolbox
---

# Space

A space represents the conceptual spaces through which data, signals, or states flow. An example might be a cartesian space meant to represent an X, Y coordinate. In implementations that enhance the definition of a space, this could be represented by {"X": float, "Y": float}.

## Schema

```
object {
  ID: string (required)
  Name: string (required)
  Description: string
}
```