# Workbench Schema

```txt
https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/workbench.schema.json
```

The actual instances in bdp-lib which is the actual instances of the toolbox which it would be paired with in the large bdp project.

| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                                      |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :---------------------------------------------------------------------------------------------- |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Forbidden             | none                | [workbench.schema.json](../../out/bdp_lib/schemas/workbench.schema.json "open original schema") |

## Workbench Type

`object` ([Workbench](workbench.md))

# Workbench Properties

| Property                  | Type    | Required | Nullable       | Defined by                                                                                                                                                           |
| :------------------------ | :------ | :------- | :------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Processors](#processors) | `array` | Required | cannot be null | [Workbench](workbench-properties-processors.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/workbench.schema.json#/properties/Processors") |
| [Wires](#wires)           | `array` | Required | cannot be null | [Workbench](workbench-properties-wires.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/workbench.schema.json#/properties/Wires")           |
| [Systems](#systems)       | `array` | Required | cannot be null | [Workbench](workbench-properties-systems.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/workbench.schema.json#/properties/Systems")       |

## Processors

A list of processors in the block diagram protocol that follow the processor schema.

`Processors`

*   is required

*   Type: `object[]` ([Processor Schema](processor.md))

*   cannot be null

*   defined in: [Workbench](workbench-properties-processors.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/workbench.schema.json#/properties/Processors")

### Processors Type

`object[]` ([Processor Schema](processor.md))

## Wires

A list of wires in the block diagram protocol that follow the wire schema.

`Wires`

*   is required

*   Type: `object[]` ([Wire Schema](wire.md))

*   cannot be null

*   defined in: [Workbench](workbench-properties-wires.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/workbench.schema.json#/properties/Wires")

### Wires Type

`object[]` ([Wire Schema](wire.md))

## Systems

A list of systems in the block diagram protocol that follow the system schema.

`Systems`

*   is required

*   Type: `object[]` ([System Schema](system.md))

*   cannot be null

*   defined in: [Workbench](workbench-properties-systems.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/workbench.schema.json#/properties/Systems")

### Systems Type

`object[]` ([System Schema](system.md))
