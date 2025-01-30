# Wire Schema Schema

```txt
https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json
```



| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                            |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :------------------------------------------------------------------------------------ |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Forbidden             | none                | [wire.schema.json](../../out/bdp_lib/schemas/wire.schema.json "open original schema") |

## Wire Schema Type

`object` ([Wire Schema](wire.md))

# Wire Schema Properties

| Property                    | Type     | Required | Nullable       | Defined by                                                                                                                                                     |
| :-------------------------- | :------- | :------- | :------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [ID](#id)                   | `string` | Required | cannot be null | [Wire Schema](wire-properties-id.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/ID")                   |
| [Parent](#parent)           | `string` | Required | cannot be null | [Wire Schema](wire-properties-parent.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Parent")           |
| [SourceBlock](#sourceblock) | `string` | Required | cannot be null | [Wire Schema](wire-properties-sourceblock.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/SourceBlock") |
| [TargetBlock](#targetblock) | `string` | Required | cannot be null | [Wire Schema](wire-properties-targetblock.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/TargetBlock") |
| [SourceIndex](#sourceindex) | `number` | Required | cannot be null | [Wire Schema](wire-properties-sourceindex.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/SourceIndex") |
| [TargetIndex](#targetindex) | `number` | Required | cannot be null | [Wire Schema](wire-properties-targetindex.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/TargetIndex") |

## ID

A unique identifier for the wire.

`ID`

*   is required

*   Type: `string` ([ID](wire-properties-id.md))

*   cannot be null

*   defined in: [Wire Schema](wire-properties-id.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/ID")

### ID Type

`string` ([ID](wire-properties-id.md))

## Parent

The ID of the space that the wire is passing.

`Parent`

*   is required

*   Type: `string` ([Parent](wire-properties-parent.md))

*   cannot be null

*   defined in: [Wire Schema](wire-properties-parent.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Parent")

### Parent Type

`string` ([Parent](wire-properties-parent.md))

## SourceBlock

The ID of the block that the wire is coming from.

`SourceBlock`

*   is required

*   Type: `string` ([SourceBlock](wire-properties-sourceblock.md))

*   cannot be null

*   defined in: [Wire Schema](wire-properties-sourceblock.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/SourceBlock")

### SourceBlock Type

`string` ([SourceBlock](wire-properties-sourceblock.md))

## TargetBlock

The ID of the block that the wire is going to.

`TargetBlock`

*   is required

*   Type: `string` ([TargetBlock](wire-properties-targetblock.md))

*   cannot be null

*   defined in: [Wire Schema](wire-properties-targetblock.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/TargetBlock")

### TargetBlock Type

`string` ([TargetBlock](wire-properties-targetblock.md))

## SourceIndex

The index of the codomain of the source block that the wire is coming from.

`SourceIndex`

*   is required

*   Type: `number` ([SourceIndex](wire-properties-sourceindex.md))

*   cannot be null

*   defined in: [Wire Schema](wire-properties-sourceindex.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/SourceIndex")

### SourceIndex Type

`number` ([SourceIndex](wire-properties-sourceindex.md))

## TargetIndex

The index of the domain of the target block that the wire is going to.

`TargetIndex`

*   is required

*   Type: `number` ([TargetIndex](wire-properties-targetindex.md))

*   cannot be null

*   defined in: [Wire Schema](wire-properties-targetindex.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/TargetIndex")

### TargetIndex Type

`number` ([TargetIndex](wire-properties-targetindex.md))
