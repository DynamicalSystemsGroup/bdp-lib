# Project Schema

```txt
https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/bdp.schema.json
```

A project within the block diagram protocol. The toolbox contains the abstract representations and the workbench contains the implementations.

| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                          |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :---------------------------------------------------------------------------------- |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Forbidden             | none                | [bdp.schema.json](../../out/bdp_lib/schemas/bdp.schema.json "open original schema") |

## Project Type

`object` ([Project](bdp.md))

# Project Properties

| Property                | Type     | Required | Nullable       | Defined by                                                                                                                                  |
| :---------------------- | :------- | :------- | :------------- | :------------------------------------------------------------------------------------------------------------------------------------------ |
| [Toolbox](#toolbox)     | `object` | Required | cannot be null | [Project](toolbox.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json#/properties/Toolbox")       |
| [Workbench](#workbench) | `object` | Required | cannot be null | [Project](workbench.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/workbench.schema.json#/properties/Workbench") |

## Toolbox

The abstract classes of blocks and spaces which the workbench will instantiate.

`Toolbox`

*   is required

*   Type: `object` ([Toolbox](toolbox.md))

*   cannot be null

*   defined in: [Project](toolbox.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json#/properties/Toolbox")

### Toolbox Type

`object` ([Toolbox](toolbox.md))

## Workbench

The actual instances in bdp-lib which is the actual instances of the toolbox which it would be paired with in the large bdp project.

`Workbench`

*   is required

*   Type: `object` ([Workbench](workbench.md))

*   cannot be null

*   defined in: [Project](workbench.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/workbench.schema.json#/properties/Workbench")

### Workbench Type

`object` ([Workbench](workbench.md))
