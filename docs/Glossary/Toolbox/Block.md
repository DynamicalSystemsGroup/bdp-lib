---
title: Block
nav_order: 1
layout: default
parent: Toolbox
---

# Block

Defines reusable templates describing how components behave in a system.

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

- Both the domain and codomain not only be of type string, but they should be specific IDs that are present in the array of spaces for the toolbox.