# Processor Schema

```txt
https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json
```

A processor is an instance of a block where computation or actions would happen. When the optional parameter of subsystem is present, the processor is a composite processor and it represents a system as a processor with the systsem ID it is a processor for as well as the wires that connect the processor ports and terminals to the system ports and terminals.

| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                                      |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :---------------------------------------------------------------------------------------------- |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Forbidden             | none                | [processor.schema.json](../../out/bdp_lib/schemas/processor.schema.json "open original schema") |

## Processor Type

`object` ([Processor](processor.md))

# Processor Properties

| Property                    | Type     | Required | Nullable       | Defined by                                                                                                                                                             |
| :-------------------------- | :------- | :------- | :------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [ID](#id)                   | `string` | Required | cannot be null | [Processor](processor-properties-id.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/ID")                   |
| [Name](#name)               | `string` | Required | cannot be null | [Processor](processor-properties-name.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Name")               |
| [Description](#description) | `string` | Optional | cannot be null | [Processor](processor-properties-description.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Description") |
| [Parent](#parent)           | `string` | Required | cannot be null | [Processor](processor-properties-parent.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Parent")           |
| [Ports](#ports)             | `array`  | Required | cannot be null | [Processor](processor-properties-ports.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Ports")             |
| [Terminals](#terminals)     | `array`  | Required | cannot be null | [Processor](processor-properties-terminals.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Terminals")     |
| [Subsystem](#subsystem)     | `object` | Optional | cannot be null | [Processor](processor-properties-subsystem.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem")     |

## ID

A unique identifier for the processor.

`ID`

*   is required

*   Type: `string` ([ID](processor-properties-id.md))

*   cannot be null

*   defined in: [Processor](processor-properties-id.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/ID")

### ID Type

`string` ([ID](processor-properties-id.md))

## Name

The name of the processor.

`Name`

*   is required

*   Type: `string` ([Name](processor-properties-name.md))

*   cannot be null

*   defined in: [Processor](processor-properties-name.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Name")

### Name Type

`string` ([Name](processor-properties-name.md))

## Description

A description of the processor.

`Description`

*   is optional

*   Type: `string` ([Description](processor-properties-description.md))

*   cannot be null

*   defined in: [Processor](processor-properties-description.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Description")

### Description Type

`string` ([Description](processor-properties-description.md))

## Parent

The ID of the block that the processor is an instance of.

`Parent`

*   is required

*   Type: `string` ([Parent](processor-properties-parent.md))

*   cannot be null

*   defined in: [Processor](processor-properties-parent.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Parent")

### Parent Type

`string` ([Parent](processor-properties-parent.md))

## Ports

The IDs of spaces which must match the domain of the parent block.

`Ports`

*   is required

*   Type: `string[]`

*   cannot be null

*   defined in: [Processor](processor-properties-ports.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Ports")

### Ports Type

`string[]`

## Terminals

The IDs of spaces which must match the codomain of the parent block.

`Terminals`

*   is required

*   Type: `string[]`

*   cannot be null

*   defined in: [Processor](processor-properties-terminals.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Terminals")

### Terminals Type

`string[]`

## Subsystem

The subsystem of the processor which is a system that the processor represents and passes its ports to and receives spaces to its terminals from.

`Subsystem`

*   is optional

*   Type: `object` ([Subsystem](processor-properties-subsystem.md))

*   cannot be null

*   defined in: [Processor](processor-properties-subsystem.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem")

### Subsystem Type

`object` ([Subsystem](processor-properties-subsystem.md))
