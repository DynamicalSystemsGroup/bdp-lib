# Target Schema

```txt
https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Target
```

The target of the wire/space.

| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                              |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :-------------------------------------------------------------------------------------- |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Allowed               | none                | [wire.schema.json\*](../../out/bdp_lib/schemas/wire.schema.json "open original schema") |

## Target Type

`object` ([Target](wire-properties-target.md))

# Target Properties

| Property                | Type      | Required | Nullable       | Defined by                                                                                                                                                                              |
| :---------------------- | :-------- | :------- | :------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Processor](#processor) | `string`  | Optional | cannot be null | [Wire](wire-properties-target-properties-processor.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Target/properties/Processor") |
| [Index](#index)         | `integer` | Optional | cannot be null | [Wire](wire-properties-target-properties-index.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Target/properties/Index")         |

## Processor

The ID of the processor that the wire is going to.

`Processor`

*   is optional

*   Type: `string` ([Processor](wire-properties-target-properties-processor.md))

*   cannot be null

*   defined in: [Wire](wire-properties-target-properties-processor.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Target/properties/Processor")

### Processor Type

`string` ([Processor](wire-properties-target-properties-processor.md))

## Index

The index of the port that the wire is going to.

`Index`

*   is optional

*   Type: `integer` ([Index](wire-properties-target-properties-index.md))

*   cannot be null

*   defined in: [Wire](wire-properties-target-properties-index.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Target/properties/Index")

### Index Type

`integer` ([Index](wire-properties-target-properties-index.md))
