# System Schema Schema

```txt
https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/system.schema.json
```



| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                                |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :---------------------------------------------------------------------------------------- |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Forbidden             | none                | [system.schema.json](../../out/bdp_lib/schemas/system.schema.json "open original schema") |

## System Schema Type

`object` ([System Schema](system.md))

# System Schema Properties

| Property                    | Type     | Required | Nullable       | Defined by                                                                                                                                                           |
| :-------------------------- | :------- | :------- | :------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [ID](#id)                   | `string` | Required | cannot be null | [System Schema](system-properties-id.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/system.schema.json#/properties/ID")                   |
| [Name](#name)               | `string` | Required | cannot be null | [System Schema](system-properties-name.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/system.schema.json#/properties/Name")               |
| [Description](#description) | `string` | Optional | cannot be null | [System Schema](system-properties-description.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/system.schema.json#/properties/Description") |
| [Processors](#processors)   | `array`  | Required | cannot be null | [System Schema](system-properties-processors.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/system.schema.json#/properties/Processors")   |
| [Wires](#wires)             | `array`  | Required | cannot be null | [System Schema](system-properties-wires.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/system.schema.json#/properties/Wires")             |

## ID

A unique identifier for the system.

`ID`

*   is required

*   Type: `string` ([ID](system-properties-id.md))

*   cannot be null

*   defined in: [System Schema](system-properties-id.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/system.schema.json#/properties/ID")

### ID Type

`string` ([ID](system-properties-id.md))

## Name

The name of the system.

`Name`

*   is required

*   Type: `string` ([Name](system-properties-name.md))

*   cannot be null

*   defined in: [System Schema](system-properties-name.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/system.schema.json#/properties/Name")

### Name Type

`string` ([Name](system-properties-name.md))

## Description

A description of the system.

`Description`

*   is optional

*   Type: `string` ([Description](system-properties-description.md))

*   cannot be null

*   defined in: [System Schema](system-properties-description.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/system.schema.json#/properties/Description")

### Description Type

`string` ([Description](system-properties-description.md))

## Processors

A list of processor IDs that are part of the system.

`Processors`

*   is required

*   Type: `string[]`

*   cannot be null

*   defined in: [System Schema](system-properties-processors.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/system.schema.json#/properties/Processors")

### Processors Type

`string[]`

## Wires

A list of wire IDs that are part of the system.

`Wires`

*   is required

*   Type: `string[]`

*   cannot be null

*   defined in: [System Schema](system-properties-wires.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/system.schema.json#/properties/Wires")

### Wires Type

`string[]`
