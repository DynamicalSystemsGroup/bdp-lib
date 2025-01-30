# Concrete Block Schema Schema

```txt
https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/concreteBlock.schema.json
```



| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                                              |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :------------------------------------------------------------------------------------------------------ |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Forbidden             | none                | [concreteBlock.schema.json](../../out/bdp_lib/schemas/concreteBlock.schema.json "open original schema") |

## Concrete Block Schema Type

`object` ([Concrete Block Schema](concreteblock.md))

# Concrete Block Schema Properties

| Property                    | Type     | Required | Nullable       | Defined by                                                                                                                                                                                 |
| :-------------------------- | :------- | :------- | :------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [ID](#id)                   | `string` | Required | cannot be null | [Concrete Block Schema](concreteblock-properties-id.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/concreteBlock.schema.json#/properties/ID")                   |
| [Name](#name)               | `string` | Required | cannot be null | [Concrete Block Schema](concreteblock-properties-name.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/concreteBlock.schema.json#/properties/Name")               |
| [Description](#description) | `string` | Optional | cannot be null | [Concrete Block Schema](concreteblock-properties-description.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/concreteBlock.schema.json#/properties/Description") |
| [Parent](#parent)           | `string` | Required | cannot be null | [Concrete Block Schema](concreteblock-properties-parent.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/concreteBlock.schema.json#/properties/Parent")           |

## ID

A unique identifier for the concrete block.

`ID`

*   is required

*   Type: `string` ([ID](concreteblock-properties-id.md))

*   cannot be null

*   defined in: [Concrete Block Schema](concreteblock-properties-id.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/concreteBlock.schema.json#/properties/ID")

### ID Type

`string` ([ID](concreteblock-properties-id.md))

## Name

The name of the concrete block.

`Name`

*   is required

*   Type: `string` ([Name](concreteblock-properties-name.md))

*   cannot be null

*   defined in: [Concrete Block Schema](concreteblock-properties-name.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/concreteBlock.schema.json#/properties/Name")

### Name Type

`string` ([Name](concreteblock-properties-name.md))

## Description

A description of the concrete block.

`Description`

*   is optional

*   Type: `string` ([Description](concreteblock-properties-description.md))

*   cannot be null

*   defined in: [Concrete Block Schema](concreteblock-properties-description.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/concreteBlock.schema.json#/properties/Description")

### Description Type

`string` ([Description](concreteblock-properties-description.md))

## Parent

The ID of the block that the concrete block is an instance of.

`Parent`

*   is required

*   Type: `string` ([Parent](concreteblock-properties-parent.md))

*   cannot be null

*   defined in: [Concrete Block Schema](concreteblock-properties-parent.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/concreteBlock.schema.json#/properties/Parent")

### Parent Type

`string` ([Parent](concreteblock-properties-parent.md))
