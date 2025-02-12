# Space Schema

```txt
https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/space.schema.json
```

A typed dictionary of data.

| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                              |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :-------------------------------------------------------------------------------------- |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Forbidden             | none                | [space.schema.json](../../out/bdp_lib/schemas/space.schema.json "open original schema") |

## Space Type

`object` ([Space](space.md))

# Space Properties

| Property                    | Type     | Required | Nullable       | Defined by                                                                                                                                                 |
| :-------------------------- | :------- | :------- | :------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [ID](#id)                   | `string` | Required | cannot be null | [Space](space-properties-id.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/space.schema.json#/properties/ID")                   |
| [Name](#name)               | `string` | Required | cannot be null | [Space](space-properties-name.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/space.schema.json#/properties/Name")               |
| [Description](#description) | `string` | Optional | cannot be null | [Space](space-properties-description.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/space.schema.json#/properties/Description") |

## ID

The unique identifier of the space.

`ID`

*   is required

*   Type: `string` ([ID](space-properties-id.md))

*   cannot be null

*   defined in: [Space](space-properties-id.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/space.schema.json#/properties/ID")

### ID Type

`string` ([ID](space-properties-id.md))

## Name

The name of the space.

`Name`

*   is required

*   Type: `string` ([Name](space-properties-name.md))

*   cannot be null

*   defined in: [Space](space-properties-name.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/space.schema.json#/properties/Name")

### Name Type

`string` ([Name](space-properties-name.md))

## Description

The description of the space.

`Description`

*   is optional

*   Type: `string` ([Description](space-properties-description.md))

*   cannot be null

*   defined in: [Space](space-properties-description.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/space.schema.json#/properties/Description")

### Description Type

`string` ([Description](space-properties-description.md))
