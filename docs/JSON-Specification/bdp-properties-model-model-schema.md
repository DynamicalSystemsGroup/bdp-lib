# Model Schema Schema

```txt
https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/model.schema.json#/properties/Model/items
```

This schema is used to describe a model in bdp-lib which is the actual instances of the toolbox which it would be paired with in the large bdp schema.

| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                            |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :------------------------------------------------------------------------------------ |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Forbidden             | none                | [bdp.schema.json\*](../../out/bdp_lib/schemas/bdp.schema.json "open original schema") |

## items Type

`object` ([Model Schema](bdp-properties-model-model-schema.md))

# items Properties

| Property                  | Type    | Required | Nullable       | Defined by                                                                                                                                                      |
| :------------------------ | :------ | :------- | :------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Processors](#processors) | `array` | Required | cannot be null | [Model Schema](model-properties-processors.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/model.schema.json#/properties/Processors") |
| [Wires](#wires)           | `array` | Required | cannot be null | [Model Schema](model-properties-wires.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/model.schema.json#/properties/Wires")           |
| [Systems](#systems)       | `array` | Required | cannot be null | [Model Schema](model-properties-systems.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/model.schema.json#/properties/Systems")       |

## Processors

A list of processors in the block diagram protocol that follow the processor schema.

`Processors`

*   is required

*   Type: `object[]` ([Processor Schema](processor.md))

*   cannot be null

*   defined in: [Model Schema](model-properties-processors.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/model.schema.json#/properties/Processors")

### Processors Type

`object[]` ([Processor Schema](processor.md))

## Wires

A list of wires in the block diagram protocol that follow the wire schema.

`Wires`

*   is required

*   Type: `object[]` ([Wire Schema](wire.md))

*   cannot be null

*   defined in: [Model Schema](model-properties-wires.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/model.schema.json#/properties/Wires")

### Wires Type

`object[]` ([Wire Schema](wire.md))

## Systems

A list of systems in the block diagram protocol that follow the system schema.

`Systems`

*   is required

*   Type: `object[]` ([System Schema](system.md))

*   cannot be null

*   defined in: [Model Schema](model-properties-systems.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/model.schema.json#/properties/Systems")

### Systems Type

`object[]` ([System Schema](system.md))
