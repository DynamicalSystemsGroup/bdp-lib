# Toolbox Schema

```txt
https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json
```

The abstract classes of blocks and spaces which the workbench will instantiate.

| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                                  |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :------------------------------------------------------------------------------------------ |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Forbidden             | none                | [toolbox.schema.json](../../out/bdp_lib/schemas/toolbox.schema.json "open original schema") |

## Toolbox Type

`object` ([Toolbox](toolbox.md))

# Toolbox Properties

| Property          | Type    | Required | Nullable       | Defined by                                                                                                                                             |
| :---------------- | :------ | :------- | :------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Spaces](#spaces) | `array` | Required | cannot be null | [Toolbox](toolbox-properties-spaces.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json#/properties/Spaces") |
| [Blocks](#blocks) | `array` | Required | cannot be null | [Toolbox](toolbox-properties-blocks.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json#/properties/Blocks") |

## Spaces

A list of spaces in the block diagram protocol that follow the space schema. One can think of a space as a typed dictionary of data.

`Spaces`

*   is required

*   Type: `object[]` ([Space](space.md))

*   cannot be null

*   defined in: [Toolbox](toolbox-properties-spaces.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json#/properties/Spaces")

### Spaces Type

`object[]` ([Space](space.md))

## Blocks

A list of blocks in the block diagram protocol that follow the block schema.

`Blocks`

*   is required

*   Type: `object[]` ([Block](block.md))

*   cannot be null

*   defined in: [Toolbox](toolbox-properties-blocks.md "https://github.com/DynamicalSystemsGroup/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json#/properties/Blocks")

### Blocks Type

`object[]` ([Block](block.md))
