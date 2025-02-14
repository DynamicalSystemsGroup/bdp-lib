---
title: Block
nav_order: 1
layout: default
parent: Toolbox
---

# Block

## Schema

```
object {
  ID: string (required)
  Name: string (required)
  Description: string
  Domain: array[string] (required)
  Codomain: array[string] (required)
}
```