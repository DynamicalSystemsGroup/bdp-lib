# System Schema Schema

```txt
undefined
```



| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                                |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :---------------------------------------------------------------------------------------- |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Allowed               | none                | [system.schema.json](../../out/bdp_lib/schemas/system.schema.json "open original schema") |

## System Schema Type

`object` ([System Schema](system.md))

# System Schema Properties

| Property                          | Type     | Required | Nullable       | Defined by                                                                                  |
| :-------------------------------- | :------- | :------- | :------------- | :------------------------------------------------------------------------------------------ |
| [ID](#id)                         | `string` | Required | cannot be null | [System Schema](system-properties-id.md "undefined#/properties/ID")                         |
| [Name](#name)                     | `string` | Required | cannot be null | [System Schema](system-properties-name.md "undefined#/properties/Name")                     |
| [Description](#description)       | `string` | Optional | cannot be null | [System Schema](system-properties-description.md "undefined#/properties/Description")       |
| [ConcreteBlocks](#concreteblocks) | `array`  | Required | cannot be null | [System Schema](system-properties-concreteblocks.md "undefined#/properties/ConcreteBlocks") |
| [Wires](#wires)                   | `array`  | Required | cannot be null | [System Schema](system-properties-wires.md "undefined#/properties/Wires")                   |

## ID



`ID`

*   is required

*   Type: `string`

*   cannot be null

*   defined in: [System Schema](system-properties-id.md "undefined#/properties/ID")

### ID Type

`string`

## Name



`Name`

*   is required

*   Type: `string`

*   cannot be null

*   defined in: [System Schema](system-properties-name.md "undefined#/properties/Name")

### Name Type

`string`

## Description



`Description`

*   is optional

*   Type: `string`

*   cannot be null

*   defined in: [System Schema](system-properties-description.md "undefined#/properties/Description")

### Description Type

`string`

## ConcreteBlocks



`ConcreteBlocks`

*   is required

*   Type: `string[]`

*   cannot be null

*   defined in: [System Schema](system-properties-concreteblocks.md "undefined#/properties/ConcreteBlocks")

### ConcreteBlocks Type

`string[]`

## Wires



`Wires`

*   is required

*   Type: `string[]`

*   cannot be null

*   defined in: [System Schema](system-properties-wires.md "undefined#/properties/Wires")

### Wires Type

`string[]`
