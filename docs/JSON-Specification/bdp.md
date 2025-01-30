# Block Diagram Protocol Schema Schema

```txt
https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/bdp.schema.json
```

This schema is used to validate the JSON file that is used to store the block diagram protocol.

| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                          |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :---------------------------------------------------------------------------------- |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Forbidden             | none                | [bdp.schema.json](../../out/bdp_lib/schemas/bdp.schema.json "open original schema") |

## Block Diagram Protocol Schema Type

`object` ([Block Diagram Protocol Schema](bdp.md))

# Block Diagram Protocol Schema Properties

| Property                          | Type    | Required | Nullable       | Defined by                                                                                                                                                                           |
| :-------------------------------- | :------ | :------- | :------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Spaces](#spaces)                 | `array` | Required | cannot be null | [Block Diagram Protocol Schema](bdp-properties-spaces.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/bdp.schema.json#/properties/Spaces")                 |
| [Blocks](#blocks)                 | `array` | Required | cannot be null | [Block Diagram Protocol Schema](bdp-properties-blocks.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/bdp.schema.json#/properties/Blocks")                 |
| [ConcreteBlocks](#concreteblocks) | `array` | Required | cannot be null | [Block Diagram Protocol Schema](bdp-properties-concreteblocks.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/bdp.schema.json#/properties/ConcreteBlocks") |
| [Wires](#wires)                   | `array` | Required | cannot be null | [Block Diagram Protocol Schema](bdp-properties-wires.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/bdp.schema.json#/properties/Wires")                   |
| [Systems](#systems)               | `array` | Required | cannot be null | [Block Diagram Protocol Schema](bdp-properties-systems.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/bdp.schema.json#/properties/Systems")               |

## Spaces

A list of spaces in the block diagram protocol that follow the space schema.

`Spaces`

*   is required

*   Type: `object[]` ([Space Schema](space.md))

*   cannot be null

*   defined in: [Block Diagram Protocol Schema](bdp-properties-spaces.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/bdp.schema.json#/properties/Spaces")

### Spaces Type

`object[]` ([Space Schema](space.md))

## Blocks

A list of blocks in the block diagram protocol that follow the block schema.

`Blocks`

*   is required

*   Type: `object[]` ([Block Schema](block.md))

*   cannot be null

*   defined in: [Block Diagram Protocol Schema](bdp-properties-blocks.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/bdp.schema.json#/properties/Blocks")

### Blocks Type

`object[]` ([Block Schema](block.md))

## ConcreteBlocks

A list of concrete blocks in the block diagram protocol that follow the concrete block schema.

`ConcreteBlocks`

*   is required

*   Type: `object[]` ([Concrete Block Schema](concreteblock.md))

*   cannot be null

*   defined in: [Block Diagram Protocol Schema](bdp-properties-concreteblocks.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/bdp.schema.json#/properties/ConcreteBlocks")

### ConcreteBlocks Type

`object[]` ([Concrete Block Schema](concreteblock.md))

## Wires

A list of wires in the block diagram protocol that follow the wire schema.

`Wires`

*   is required

*   Type: `object[]` ([Wire Schema](wire.md))

*   cannot be null

*   defined in: [Block Diagram Protocol Schema](bdp-properties-wires.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/bdp.schema.json#/properties/Wires")

### Wires Type

`object[]` ([Wire Schema](wire.md))

## Systems

A list of systems in the block diagram protocol that follow the system schema.

`Systems`

*   is required

*   Type: `object[]` ([System Schema](system.md))

*   cannot be null

*   defined in: [Block Diagram Protocol Schema](bdp-properties-systems.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/bdp.schema.json#/properties/Systems")

### Systems Type

`object[]` ([System Schema](system.md))
