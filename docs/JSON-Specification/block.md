# Block Schema Schema

```txt
undefined
```



| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                              |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :-------------------------------------------------------------------------------------- |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Allowed               | none                | [block.schema.json](../../out/bdp_lib/schemas/block.schema.json "open original schema") |

## Block Schema Type

`object` ([Block Schema](block.md))

# Block Schema Properties

| Property                    | Type     | Required | Nullable       | Defined by                                                                          |
| :-------------------------- | :------- | :------- | :------------- | :---------------------------------------------------------------------------------- |
| [ID](#id)                   | `string` | Required | cannot be null | [Block Schema](block-properties-id.md "undefined#/properties/ID")                   |
| [Name](#name)               | `string` | Required | cannot be null | [Block Schema](block-properties-name.md "undefined#/properties/Name")               |
| [Description](#description) | `string` | Optional | cannot be null | [Block Schema](block-properties-description.md "undefined#/properties/Description") |
| [Domain](#domain)           | `array`  | Required | cannot be null | [Block Schema](block-properties-domain.md "undefined#/properties/Domain")           |
| [Codomain](#codomain)       | `array`  | Required | cannot be null | [Block Schema](block-properties-codomain.md "undefined#/properties/Codomain")       |

## ID



`ID`

*   is required

*   Type: `string`

*   cannot be null

*   defined in: [Block Schema](block-properties-id.md "undefined#/properties/ID")

### ID Type

`string`

## Name



`Name`

*   is required

*   Type: `string`

*   cannot be null

*   defined in: [Block Schema](block-properties-name.md "undefined#/properties/Name")

### Name Type

`string`

## Description



`Description`

*   is optional

*   Type: `string`

*   cannot be null

*   defined in: [Block Schema](block-properties-description.md "undefined#/properties/Description")

### Description Type

`string`

## Domain



`Domain`

*   is required

*   Type: `string[]`

*   cannot be null

*   defined in: [Block Schema](block-properties-domain.md "undefined#/properties/Domain")

### Domain Type

`string[]`

## Codomain



`Codomain`

*   is required

*   Type: `string[]`

*   cannot be null

*   defined in: [Block Schema](block-properties-codomain.md "undefined#/properties/Codomain")

### Codomain Type

`string[]`
