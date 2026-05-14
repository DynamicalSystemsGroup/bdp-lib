# Subsystem Schema

```txt
https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem
```

The subsystem of the processor which is a system that the processor represents and passes its ports to and receives spaces to its terminals from.

| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                                        |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :------------------------------------------------------------------------------------------------ |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Allowed               | none                | [processor.schema.json\*](../../out/bdp_lib/schemas/processor.schema.json "open original schema") |

## Subsystem Type

`object` ([Subsystem](processor-properties-subsystem.md))

# Subsystem Properties

| Property                                | Type     | Required | Nullable       | Defined by                                                                                                                                                                                                                   |
| :-------------------------------------- | :------- | :------- | :------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [System ID](#system-id)                 | `string` | Required | cannot be null | [Processor](processor-properties-subsystem-properties-system-id.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/System ID")                 |
| [Port Mappings](#port-mappings)         | `array`  | Required | cannot be null | [Processor](processor-properties-subsystem-properties-port-mappings.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/Port Mappings")         |
| [Terminal Mappings](#terminal-mappings) | `array`  | Required | cannot be null | [Processor](processor-properties-subsystem-properties-terminal-mappings.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/Terminal Mappings") |

## System ID

The ID of the system that the processor is a processor for.

`System ID`

*   is required

*   Type: `string` ([System ID](processor-properties-subsystem-properties-system-id.md))

*   cannot be null

*   defined in: [Processor](processor-properties-subsystem-properties-system-id.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/System ID")

### System ID Type

`string` ([System ID](processor-properties-subsystem-properties-system-id.md))

## Port Mappings

This array, which is equal in length to the number of ports on the processor, maps each port to an internal processor within the subsystem and its port index that the port should be passed on to.

`Port Mappings`

*   is required

*   Type: `object[]` ([Details](processor-properties-subsystem-properties-port-mappings-items.md))

*   cannot be null

*   defined in: [Processor](processor-properties-subsystem-properties-port-mappings.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/Port Mappings")

### Port Mappings Type

`object[]` ([Details](processor-properties-subsystem-properties-port-mappings-items.md))

## Terminal Mappings

This array, which is equal in length to the number of terminals on the processor, maps terminal port to an internal processor within the subsystem and its terminal index that the outer terminal should receive output from.

`Terminal Mappings`

*   is required

*   Type: `object[]` ([Details](processor-properties-subsystem-properties-terminal-mappings-items.md))

*   cannot be null

*   defined in: [Processor](processor-properties-subsystem-properties-terminal-mappings.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/Terminal Mappings")

### Terminal Mappings Type

`object[]` ([Details](processor-properties-subsystem-properties-terminal-mappings-items.md))
