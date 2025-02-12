# README

## Top-level Schemas

*   [Block Schema](./block.md) – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/block.schema.json`

*   [Processor Schema](./processor.md) – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json`

*   [Project](./bdp.md "A project within the block diagram protocol") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/bdp.schema.json`

*   [Space Schema](./space.md) – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/space.schema.json`

*   [System Schema](./system.md) – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/system.schema.json`

*   [Toolbox Schema](./toolbox.md "This schema is used for describing a toolbox in bdp-lib") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json`

*   [Wire Schema](./wire.md) – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json`

*   [Workbench](./workbench.md "The actual instances in bdp-lib which is the actual instances of the toolbox which it would be paired with in the large bdp project") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/workbench.schema.json`

## Other Schemas

### Objects

*   [Source](./wire-properties-source.md "The source of the wire/space") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Source`

*   [Target](./wire-properties-target.md "The target of the wire/space") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Target`

### Arrays

*   [Blocks](./toolbox-properties-blocks.md "A list of blocks in the block diagram protocol that follow the block schema") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json#/properties/Blocks`

*   [Codomain](./block-properties-codomain.md "The codomain of the block which are IDs of spaces") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/block.schema.json#/properties/Codomain`

*   [Domain](./block-properties-domain.md "The domain of the block which are IDs of spaces") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/block.schema.json#/properties/Domain`

*   [Ports](./processor-properties-ports.md "The IDs of spaces which must match the domain of the parent block") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Ports`

*   [Processors](./workbench-properties-processors.md "A list of processors in the block diagram protocol that follow the processor schema") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/workbench.schema.json#/properties/Processors`

*   [Processors](./system-properties-processors.md "A list of processor IDs that are part of the system") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/system.schema.json#/properties/Processors`

*   [Spaces](./toolbox-properties-spaces.md "A list of spaces in the block diagram protocol that follow the space schema") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json#/properties/Spaces`

*   [Systems](./workbench-properties-systems.md "A list of systems in the block diagram protocol that follow the system schema") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/workbench.schema.json#/properties/Systems`

*   [Terminals](./processor-properties-terminals.md "The IDs of spaces which must match the codomain of the parent block") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Terminals`

*   [Wires](./workbench-properties-wires.md "A list of wires in the block diagram protocol that follow the wire schema") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/workbench.schema.json#/properties/Wires`

*   [Wires](./system-properties-wires.md "A list of wire IDs that are part of the system") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/system.schema.json#/properties/Wires`

## Version Note

The schemas linked above follow the JSON Schema Spec version: `http://json-schema.org/draft-07/schema#`
