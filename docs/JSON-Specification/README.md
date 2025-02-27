# README

## Top-level Schemas

*   [Block](./block.md "A block in the block diagram protocol which represents a function/computation that maps from a domain to a codomain") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/block.schema.json`

*   [Processor](./processor.md "A processor is an instance of a block where computation or actions would happen") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json`

*   [Project](./bdp.md "A project within the block diagram protocol") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/bdp.schema.json`

*   [Space](./space.md "A typed dictionary of data") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/space.schema.json`

*   [System](./system.md "A system is a collection of processors and wires which when loaded represent an actual block diagram") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/system.schema.json`

*   [Toolbox](./toolbox.md "The abstract classes of blocks and spaces which the workbench will instantiate") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json`

*   [Wire](./wire.md "A wire connects a terminal to a port and is the implementation of an underlying space which is passed between these two") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json`

*   [Workbench](./workbench.md "The actual instances in bdp-lib which is the actual instances of the toolbox which it would be paired with in the large bdp project") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/workbench.schema.json`

## Other Schemas

### Objects

*   [Source](./wire-properties-source.md "The source of the wire/space") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Source`

*   [Subsystem](./processor-properties-subsystem.md "The subsystem of the processor which is a system that the processor represents and passes its ports to and receives spaces to its terminals from") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem`

*   [Target](./wire-properties-target.md "The target of the wire/space") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/wire.schema.json#/properties/Target`

*   [Untitled object in Processor](./processor-properties-subsystem-properties-port-mappings-items.md) – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/Port Mappings/items`

*   [Untitled object in Processor](./processor-properties-subsystem-properties-terminal-mappings-items.md) – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/Terminal Mappings/items`

### Arrays

*   [Blocks](./toolbox-properties-blocks.md "A list of blocks in the block diagram protocol that follow the block schema") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json#/properties/Blocks`

*   [Codomain](./block-properties-codomain.md "The codomain of the block which are IDs of spaces") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/block.schema.json#/properties/Codomain`

*   [Domain](./block-properties-domain.md "The domain of the block which are IDs of spaces") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/block.schema.json#/properties/Domain`

*   [Port Mappings](./processor-properties-subsystem-properties-port-mappings.md "This array, which is equal in length to the number of ports on the processor, maps each port to an internal processor within the subsystem and its port index that the port should be passed on to") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/Port Mappings`

*   [Ports](./processor-properties-ports.md "The IDs of spaces which must match the domain of the parent block") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Ports`

*   [Processors](./workbench-properties-processors.md "A list of processors in the block diagram protocol that follow the processor schema") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/workbench.schema.json#/properties/Processors`

*   [Processors](./system-properties-processors.md "A list of processor IDs that are part of the system") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/system.schema.json#/properties/Processors`

*   [Spaces](./toolbox-properties-spaces.md "A list of spaces in the block diagram protocol that follow the space schema") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/toolbox.schema.json#/properties/Spaces`

*   [Systems](./workbench-properties-systems.md "A list of systems in the block diagram protocol that follow the system schema") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/workbench.schema.json#/properties/Systems`

*   [Terminal Mappings](./processor-properties-subsystem-properties-terminal-mappings.md "This array, which is equal in length to the number of terminals on the processor, maps terminal port to an internal processor within the subsystem and its terminal index that the outer terminal should receive output from") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Subsystem/properties/Terminal Mappings`

*   [Terminals](./processor-properties-terminals.md "The IDs of spaces which must match the codomain of the parent block") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/processor.schema.json#/properties/Terminals`

*   [Wires](./workbench-properties-wires.md "A list of wires in the block diagram protocol that follow the wire schema") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/workbench.schema.json#/properties/Wires`

*   [Wires](./system-properties-wires.md "A list of wire IDs that are part of the system") – `https://github.com/BlockScience/bdp-lib/tree/main/src/bdp_lib/schemas/system.schema.json#/properties/Wires`

## Version Note

The schemas linked above follow the JSON Schema Spec version: `http://json-schema.org/draft-07/schema#`
