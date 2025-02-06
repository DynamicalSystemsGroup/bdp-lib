# Processor Schema Schema

```txt
https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json
```



| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                                      |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :---------------------------------------------------------------------------------------------- |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Forbidden             | none                | [processor.schema.json](../../out/bdp_lib/schemas/processor.schema.json "open original schema") |

## Processor Schema Type

`object` ([Processor Schema](processor.md))

# Processor Schema Properties

| Property                    | Type     | Required | Nullable       | Defined by                                                                                                                                                                    |
| :-------------------------- | :------- | :------- | :------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [ID](#id)                   | `string` | Required | cannot be null | [Processor Schema](processor-properties-id.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/ID")                   |
| [Name](#name)               | `string` | Required | cannot be null | [Processor Schema](processor-properties-name.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Name")               |
| [Description](#description) | `string` | Optional | cannot be null | [Processor Schema](processor-properties-description.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Description") |
| [Parent](#parent)           | `string` | Required | cannot be null | [Processor Schema](processor-properties-parent.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Parent")           |
| [Ports](#ports)             | `array`  | Optional | cannot be null | [Processor Schema](processor-properties-ports.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Ports")             |
| [Terminals](#terminals)     | `array`  | Required | cannot be null | [Processor Schema](processor-properties-terminals.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Terminals")     |

## ID

A unique identifier for the processor.

`ID`

*   is required

*   Type: `string` ([ID](processor-properties-id.md))

*   cannot be null

*   defined in: [Processor Schema](processor-properties-id.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/ID")

### ID Type

`string` ([ID](processor-properties-id.md))

## Name

The name of the processor.

`Name`

*   is required

*   Type: `string` ([Name](processor-properties-name.md))

*   cannot be null

*   defined in: [Processor Schema](processor-properties-name.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Name")

### Name Type

`string` ([Name](processor-properties-name.md))

## Description

A description of the processor.

`Description`

*   is optional

*   Type: `string` ([Description](processor-properties-description.md))

*   cannot be null

*   defined in: [Processor Schema](processor-properties-description.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Description")

### Description Type

`string` ([Description](processor-properties-description.md))

## Parent

The ID of the block that the processor is an instance of.

`Parent`

*   is required

*   Type: `string` ([Parent](processor-properties-parent.md))

*   cannot be null

*   defined in: [Processor Schema](processor-properties-parent.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Parent")

### Parent Type

`string` ([Parent](processor-properties-parent.md))

## Ports

The IDs of spaces which must match the domain of the parent block.

`Ports`

*   is optional

*   Type: `string[]`

*   cannot be null

*   defined in: [Processor Schema](processor-properties-ports.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Ports")

### Ports Type

`string[]`

## Terminals

The IDs of spaces which must match the codomain of the parent block.

`Terminals`

*   is required

*   Type: `string[]`

*   cannot be null

*   defined in: [Processor Schema](processor-properties-terminals.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Terminals")

### Terminals Type

`string[]`
