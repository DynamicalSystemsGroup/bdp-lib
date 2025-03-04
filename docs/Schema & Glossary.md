---
title: Schema & Glossary
nav_order: 2
layout: default
---

# Project, Schema & Glossary

The following is the definition of a project in the block diagram protocol, a glossary of all the terms, and the entire schema.

## Project

A project is defined by two components: a toolbox which has the abstract components and a workbench which has the concrete components. If the data presented follows the schema, then any client should be able to interact with it.

## Glossary

 - Project: A project within the block diagram protocol. The toolbox contains the abstract representations and the workbench contains the implementations.
   - Toolbox: The abstract classes of blocks and spaces which the workbench will instantiate.
     - Spaces: A list of spaces in the block diagram protocol that follow the space schema. One can think of a space as a typed dictionary of data.
       - ID: The unique identifier of the space.
       - Name: The name of the space.
       - Description: The description of the space.
     - Blocks: A list of blocks in the block diagram protocol that follow the block schema.
       - ID: A unique identifier for the block.
       - Name: The name of the block.
       - Description: A description of the block.
       - Domain: The domain of the block which are IDs of spaces. Spaces may be repeated or it may be an empty array.
       - Codomain: The codomain of the block which are IDs of spaces. Spaces may be repeated or it may be an empty array.
   - Workbench: The actual instances in bdp-lib which is the actual instances of the toolbox which it would be paired with in the large bdp project.
     - Processors: A list of processors in the block diagram protocol that follow the processor schema.
       - ID: A unique identifier for the processor.
       - Name: The name of the processor.
       - Description: A description of the processor.
       - Parent: The ID of the block that the processor is an instance of.
       - Ports: The IDs of spaces which must match the domain of the parent block.
       - Terminals: The IDs of spaces which must match the codomain of the parent block.
       - Subsystem: The subsystem of the processor which is a system that the processor represents and passes its ports to and receives spaces to its terminals from.
         - System ID: The ID of the system that the processor is a processor for.
         - Port Mappings: This array, which is equal in length to the number of ports on the processor, maps each port to an internal processor within the subsystem and its port index that the port should be passed on to.
           - Processor: The ID of the processor in the system.
           - Index: The index of the terminal.
         - Terminal Mappings: This array, which is equal in length to the number of terminals on the processor, maps terminal port to an internal processor within the subsystem and its terminal index that the outer terminal should receive output from.
           - Processor: The ID of the processor in the system.
           - Index: The index of the terminal.
     - Wires: A list of wires in the block diagram protocol that follow the wire schema.
       - ID: A unique identifier for the wire.
       - Parent: The ID of the space that the wire is passing.
       - Source: The source of the wire/space.
         - Processor: The ID of the processor that the wire is coming from.
         - Index: The index of the terminal that the wire is coming from.
       - Target: The target of the wire/space.
         - Processor: The ID of the processor that the wire is going to.
         - Index: The index of the port that the wire is going to.
     - Systems: A list of systems in the block diagram protocol that follow the system schema.
       - ID: A unique identifier for the system.
       - Name: The name of the system.
       - Description: A description of the system.
       - Processors: A list of processor IDs that are part of the system.
       - Wires: A list of wire IDs that are part of the system.


## Schema

The schema defined here is the entire thing, however, there are two other places which give more detailed descriptions:

1. The component documentation in this section goes through each component, its schema, and any important notes about it
2. The [JSON Documentation](./JSON-Specification/bdp.md) has highly detailed documentation on each part of the JSON schema

There is also a visual representation of the nested schema below as well.

```
object {
  Toolbox: object {
    Spaces: array[object {
      ID: string (required)
      Name: string (required)
      Description: string
    }] (required)
    Blocks: array[object {
      ID: string (required)
      Name: string (required)
      Description: string
      Domain: array[string] (required)
      Codomain: array[string] (required)
    }] (required)
  } (required)
  Workbench: object {
    Processors: array[object {
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
    }] (required)
    Wires: array[object {
      ID: string (required)
      Parent: string (required)
      Source: object {
        Processor: string
        Index: integer
      } (required)
      Target: object {
        Processor: string
        Index: integer
      } (required)
    }] (required)
    Systems: array[object {
      ID: string (required)
      Name: string (required)
      Description: string
      Processors: array[string] (required)
      Wires: array[string] (required)
    }] (required)
  } (required)
}
```

![Nested Schema](Nested-Schema.png)

