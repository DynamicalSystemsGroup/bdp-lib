# Block Diagram Protocol Schema Schema

```txt
undefined
```



| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                        |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :-------------------------------------------------------------------------------- |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Allowed               | none                | [schema.schema.json](../../out/bdp_lib/schema.schema.json "open original schema") |

## Block Diagram Protocol Schema Type

`object` ([Block Diagram Protocol Schema](schema.md))

# Block Diagram Protocol Schema Properties

| Property                          | Type    | Required | Nullable       | Defined by                                                                                                  |
| :-------------------------------- | :------ | :------- | :------------- | :---------------------------------------------------------------------------------------------------------- |
| [Spaces](#spaces)                 | `array` | Required | cannot be null | [Block Diagram Protocol Schema](schema-properties-spaces.md "undefined#/properties/Spaces")                 |
| [Blocks](#blocks)                 | `array` | Required | cannot be null | [Block Diagram Protocol Schema](schema-properties-blocks.md "undefined#/properties/Blocks")                 |
| [ConcreteBlocks](#concreteblocks) | `array` | Required | cannot be null | [Block Diagram Protocol Schema](schema-properties-concreteblocks.md "undefined#/properties/ConcreteBlocks") |
| [Wires](#wires)                   | `array` | Required | cannot be null | [Block Diagram Protocol Schema](schema-properties-wires.md "undefined#/properties/Wires")                   |
| [Systems](#systems)               | `array` | Required | cannot be null | [Block Diagram Protocol Schema](schema-properties-systems.md "undefined#/properties/Systems")               |

## Spaces



`Spaces`

*   is required

*   Type: `object[]` ([Space Schema](space.md))

*   cannot be null

*   defined in: [Block Diagram Protocol Schema](schema-properties-spaces.md "undefined#/properties/Spaces")

### Spaces Type

`object[]` ([Space Schema](space.md))

## Blocks



`Blocks`

*   is required

*   Type: `object[]` ([Details](schema-properties-blocks-items.md))

*   cannot be null

*   defined in: [Block Diagram Protocol Schema](schema-properties-blocks.md "undefined#/properties/Blocks")

### Blocks Type

`object[]` ([Details](schema-properties-blocks-items.md))

## ConcreteBlocks



`ConcreteBlocks`

*   is required

*   Type: `object[]` ([Details](schema-properties-concreteblocks-items.md))

*   cannot be null

*   defined in: [Block Diagram Protocol Schema](schema-properties-concreteblocks.md "undefined#/properties/ConcreteBlocks")

### ConcreteBlocks Type

`object[]` ([Details](schema-properties-concreteblocks-items.md))

## Wires



`Wires`

*   is required

*   Type: `object[]` ([Details](schema-properties-wires-items.md))

*   cannot be null

*   defined in: [Block Diagram Protocol Schema](schema-properties-wires.md "undefined#/properties/Wires")

### Wires Type

`object[]` ([Details](schema-properties-wires-items.md))

## Systems



`Systems`

*   is required

*   Type: `object[]` ([Details](schema-properties-systems-items.md))

*   cannot be null

*   defined in: [Block Diagram Protocol Schema](schema-properties-systems.md "undefined#/properties/Systems")

### Systems Type

`object[]` ([Details](schema-properties-systems-items.md))
