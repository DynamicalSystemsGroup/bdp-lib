# Block Diagram Protocol Schema Schema

```txt
https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/bdp.schema.json
```

This schema is used to validate the JSON file that is used to store the block diagram protocol. There are two components, a toolbox which describes the abstract blocks and spaces and the model which has the actual instances of the toolbox - processors, wires and systems.

| Abstract            | Extensible | Status         | Identifiable | Custom Properties | Additional Properties | Access Restrictions | Defined In                                                                          |
| :------------------ | :--------- | :------------- | :----------- | :---------------- | :-------------------- | :------------------ | :---------------------------------------------------------------------------------- |
| Can be instantiated | No         | Unknown status | No           | Forbidden         | Forbidden             | none                | [bdp.schema.json](../../out/bdp_lib/schemas/bdp.schema.json "open original schema") |

## Block Diagram Protocol Schema Type

`object` ([Block Diagram Protocol Schema](bdp.md))

# Block Diagram Protocol Schema Properties

| Property            | Type     | Required | Nullable       | Defined by                                                                                                                                                  |
| :------------------ | :------- | :------- | :------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Toolbox](#toolbox) | `object` | Required | cannot be null | [Block Diagram Protocol Schema](toolbox.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json#/properties/Toolbox") |
| [Model](#model)     | `object` | Required | cannot be null | [Block Diagram Protocol Schema](model.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/model.schema.json#/properties/Model")       |

## Toolbox

This schema is used for describing a toolbox in bdp-lib.

`Toolbox`

*   is required

*   Type: `object` ([Toolbox Schema](toolbox.md))

*   cannot be null

*   defined in: [Block Diagram Protocol Schema](toolbox.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json#/properties/Toolbox")

### Toolbox Type

`object` ([Toolbox Schema](toolbox.md))

## Model

This schema is used to describe a model in bdp-lib which is the actual instances of the toolbox which it would be paired with in the large bdp schema.

`Model`

*   is required

*   Type: `object` ([Model Schema](model.md))

*   cannot be null

*   defined in: [Block Diagram Protocol Schema](model.md "https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/model.schema.json#/properties/Model")

### Model Type

`object` ([Model Schema](model.md))
