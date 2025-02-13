# Subsystem Schema

```txt
https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem
```

The subsystem of the processor which is a system that the processor represents and passes its ports to and receives spaces to its terminals from.

| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                                        |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :------------------------------------------------------------------------------------------------ |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Allowed               | none                | [processor.schema.json\*](../../out/bdp_lib/schemas/processor.schema.json "open original schema") |

## Subsystem Type

`object` ([Subsystem](processor-properties-subsystem.md))

# Subsystem Properties

| Property                | Type     | Required | Nullable       | Defined by                                                                                                                                                                                                   |
| :---------------------- | :------- | :------- | :------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [System ID](#system-id) | `string` | Required | cannot be null | [Processor](processor-properties-subsystem-properties-system-id.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/System ID") |
| [Wires](#wires)         | `array`  | Required | cannot be null | [Processor](processor-properties-subsystem-properties-wires.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/Wires")         |

## System ID

The ID of the system that the processor is a processor for.

`System ID`

*   is required

*   Type: `string` ([System ID](processor-properties-subsystem-properties-system-id.md))

*   cannot be null

*   defined in: [Processor](processor-properties-subsystem-properties-system-id.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/System ID")

### System ID Type

`string` ([System ID](processor-properties-subsystem-properties-system-id.md))

## Wires

The IDs of the wires that connect the processor ports and terminals to the system ports and terminals.

`Wires`

*   is required

*   Type: `string[]`

*   cannot be null

*   defined in: [Processor](processor-properties-subsystem-properties-wires.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/Wires")

### Wires Type

`string[]`
