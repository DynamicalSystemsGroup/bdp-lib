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

| Property          | Type     | Required | Nullable       | Defined by                                                                                                                                           |
| :---------------- | :------- | :------- | :------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------- |
| [ID](#id)         | `string` | Required | cannot be null | [Wire Schema](wire-properties-id.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/ID")         |
| [Parent](#parent) | `string` | Required | cannot be null | [Wire Schema](wire-properties-parent.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Parent") |
| [Source](#source) | `object` | Optional | cannot be null | [Wire Schema](wire-properties-source.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Source") |
| [Target](#target) | `object` | Optional | cannot be null | [Wire Schema](wire-properties-target.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Target") |

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

## Source

The source of the wire/space.

`Source`

*   is optional

*   Type: `object` ([Source](wire-properties-source.md))

*   cannot be null

*   defined in: [Wire Schema](wire-properties-source.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Source")

### Source Type

`object` ([Source](wire-properties-source.md))

## Target

The target of the wire/space.

`Target`

*   is optional

*   Type: `object` ([Target](wire-properties-target.md))

*   cannot be null

*   defined in: [Wire Schema](wire-properties-target.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Target")

### Target Type

`object` ([Target](wire-properties-target.md))
