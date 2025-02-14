---
title: Wire
nav_order: 2
layout: default
parent: Workbench
---

# Wire

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