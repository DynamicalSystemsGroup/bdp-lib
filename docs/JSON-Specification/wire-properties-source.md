# Source Schema

```txt
https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Source
```

The source of the wire/space.

| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                              |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :-------------------------------------------------------------------------------------- |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Allowed               | none                | [wire.schema.json\*](../../out/bdp_lib/schemas/wire.schema.json "open original schema") |

## Source Type

`object` ([Source](wire-properties-source.md))

# Source Properties

| Property                | Type      | Required | Nullable       | Defined by                                                                                                                                                                              |
| :---------------------- | :-------- | :------- | :------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Processor](#processor) | `string`  | Optional | cannot be null | [Wire](wire-properties-source-properties-processor.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Source/properties/Processor") |
| [Index](#index)         | `integer` | Optional | cannot be null | [Wire](wire-properties-source-properties-index.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Source/properties/Index")         |

## Processor

The ID of the processor that the wire is coming from.

`Processor`

*   is optional

*   Type: `string` ([Processor](wire-properties-source-properties-processor.md))

*   cannot be null

*   defined in: [Wire](wire-properties-source-properties-processor.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Source/properties/Processor")

### Processor Type

`string` ([Processor](wire-properties-source-properties-processor.md))

## Index

The index of the terminal that the wire is coming from.

`Index`

*   is optional

*   Type: `integer` ([Index](wire-properties-source-properties-index.md))

*   cannot be null

*   defined in: [Wire](wire-properties-source-properties-index.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Source/properties/Index")

### Index Type

`integer` ([Index](wire-properties-source-properties-index.md))
