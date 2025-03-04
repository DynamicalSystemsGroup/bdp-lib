---
title: Workbench
nav_order: 2
layout: default
parent: Schema & Glossary
---

# Workbench

A workbench consists of the concrete components implemented from the abstract components of the toolbox.

A workbench contains the following:
- **Processors**: The implementations of blocks
- **Wires**: The implementations of spaces which are passed from one processor terminal to another processor port
- **Systems**: The definitions of wires and processors that form unique systems

## Schema

The top level schema of a workbench is:

```
object {
  Processors: array[Processor] (required)
  Wires: array[Wire] (required)
  Systems: array[System] (required)
}
```

And the children schemas are as follows below.

### Processor Schema


```
object {
  ID: string (required)
  Name: string (required)
  Description: string
  Parent: string (required)
  Ports: array[string] (required)
  Terminals: array[string] (required)
  Subsystem: object {
    System ID: string (required)
    Port Mappings: array[object {
      Processor: string (required)
      Index: integer (required)
    }] (required)
    Terminal Mappings: array[object {
      Processor: string (required)
      Index: integer (required)
    }] (required)
  }
}
```

### Wire Schema

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

### System Schema

```
object {
    ID: string (required)
    Name: string (required)
    Description: string
    Processors: array[string] (required)
    Wires: array[string] (required)
  }
```