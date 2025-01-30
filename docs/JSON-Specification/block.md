# Block Schema Schema

```txt
https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/block.schema.json
```



| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                              |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :-------------------------------------------------------------------------------------- |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Forbidden             | none                | [block.schema.json](../../out/bdp_lib/schemas/block.schema.json "open original schema") |

## Block Schema Type

`object` ([Block Schema](block.md))

# Block Schema Properties

| Property                    | Type     | Required | Nullable       | Defined by                                                                                                                                                        |
| :-------------------------- | :------- | :------- | :------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [ID](#id)                   | `string` | Required | cannot be null | [Block Schema](block-properties-id.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/block.schema.json#/properties/ID")                   |
| [Name](#name)               | `string` | Required | cannot be null | [Block Schema](block-properties-name.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/block.schema.json#/properties/Name")               |
| [Description](#description) | `string` | Optional | cannot be null | [Block Schema](block-properties-description.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/block.schema.json#/properties/Description") |
| [Domain](#domain)           | `array`  | Required | cannot be null | [Block Schema](block-properties-domain.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/block.schema.json#/properties/Domain")           |
| [Codomain](#codomain)       | `array`  | Required | cannot be null | [Block Schema](block-properties-codomain.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/block.schema.json#/properties/Codomain")       |

## ID



`ID`

*   is required

*   Type: `string`

*   cannot be null

*   defined in: [Block Schema](block-properties-id.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/block.schema.json#/properties/ID")

### ID Type

`string`

## Name



`Name`

*   is required

*   Type: `string`

*   cannot be null

*   defined in: [Block Schema](block-properties-name.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/block.schema.json#/properties/Name")

### Name Type

`string`

## Description



`Description`

*   is optional

*   Type: `string`

*   cannot be null

*   defined in: [Block Schema](block-properties-description.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/block.schema.json#/properties/Description")

### Description Type

`string`

## Domain



`Domain`

*   is required

*   Type: `string[]`

*   cannot be null

*   defined in: [Block Schema](block-properties-domain.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/block.schema.json#/properties/Domain")

### Domain Type

`string[]`

## Codomain



`Codomain`

*   is required

*   Type: `string[]`

*   cannot be null

*   defined in: [Block Schema](block-properties-codomain.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/block.schema.json#/properties/Codomain")

### Codomain Type

`string[]`
