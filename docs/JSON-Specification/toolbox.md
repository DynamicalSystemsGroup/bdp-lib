# Toolbox Schema Schema

```txt
https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json
```

This schema is used for describing a toolbox in bdp-lib.

| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                                  |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :------------------------------------------------------------------------------------------ |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Forbidden             | none                | [toolbox.schema.json](../../out/bdp_lib/schemas/toolbox.schema.json "open original schema") |

## Toolbox Schema Type

`object` ([Toolbox Schema](toolbox.md))

# Toolbox Schema Properties

| Property          | Type    | Required | Nullable       | Defined by                                                                                                                                                    |
| :---------------- | :------ | :------- | :------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [Spaces](#spaces) | `array` | Required | cannot be null | [Toolbox Schema](toolbox-properties-spaces.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json#/properties/Spaces") |
| [Blocks](#blocks) | `array` | Required | cannot be null | [Toolbox Schema](toolbox-properties-blocks.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json#/properties/Blocks") |

## Spaces

A list of spaces in the block diagram protocol that follow the space schema. It defines the abstract classes of blocks and spaces which models will instantiate.

`Spaces`

*   is required

*   Type: `object[]` ([Space Schema](space.md))

*   cannot be null

*   defined in: [Toolbox Schema](toolbox-properties-spaces.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json#/properties/Spaces")

### Spaces Type

`object[]` ([Space Schema](space.md))

## Blocks

A list of blocks in the block diagram protocol that follow the block schema.

`Blocks`

*   is required

*   Type: `object[]` ([Block Schema](block.md))

*   cannot be null

*   defined in: [Toolbox Schema](toolbox-properties-blocks.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json#/properties/Blocks")

### Blocks Type

`object[]` ([Block Schema](block.md))
