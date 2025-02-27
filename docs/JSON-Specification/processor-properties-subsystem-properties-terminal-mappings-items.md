# Untitled object in Processor Schema

```txt
https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/Terminal Mappings/items
```



| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                                        |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :------------------------------------------------------------------------------------------------ |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Allowed               | none                | [processor.schema.json\*](../../out/bdp_lib/schemas/processor.schema.json "open original schema") |

## items Type

`object` ([Details](processor-properties-subsystem-properties-terminal-mappings-items.md))

# items Properties

| Property                | Type      | Required | Nullable       | Defined by                                                                                                                                                                                                                                                                         |
| :---------------------- | :-------- | :------- | :------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Processor](#processor) | `string`  | Required | cannot be null | [Processor](processor-properties-subsystem-properties-terminal-mappings-items-properties-processor.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/Terminal Mappings/items/properties/Processor") |
| [Index](#index)         | `integer` | Required | cannot be null | [Processor](processor-properties-subsystem-properties-terminal-mappings-items-properties-index.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/Terminal Mappings/items/properties/Index")         |

## Processor

The ID of the processor in the system.

`Processor`

*   is required

*   Type: `string` ([Processor](processor-properties-subsystem-properties-terminal-mappings-items-properties-processor.md))

*   cannot be null

*   defined in: [Processor](processor-properties-subsystem-properties-terminal-mappings-items-properties-processor.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/Terminal Mappings/items/properties/Processor")

### Processor Type

`string` ([Processor](processor-properties-subsystem-properties-terminal-mappings-items-properties-processor.md))

## Index

The index of the terminal.

`Index`

*   is required

*   Type: `integer` ([Index](processor-properties-subsystem-properties-terminal-mappings-items-properties-index.md))

*   cannot be null

*   defined in: [Processor](processor-properties-subsystem-properties-terminal-mappings-items-properties-index.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/Terminal Mappings/items/properties/Index")

### Index Type

`integer` ([Index](processor-properties-subsystem-properties-terminal-mappings-items-properties-index.md))
