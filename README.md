# Block Diagram Protocol Library

The "Block Diagram Protocol Library" or bdp-lib for short is a library for instantiating and validating fundamental block diagrams. Additional functionalities and enhancements come out of libraries which use it as the base object.

## Functional Requirements

1. The library provides a schema for defining out the elements of a basic block diagram.
2. The library can be extended with two primitive functionalities:
    A. Modifying - Support for basic zooming, tearing and linking functions while not breaking validity rules
    B. Enriching - Attatching further enhancements such as types, units, semantic labels, etc.
3. The library performs validation for the following constraints:
    A. All inputs follow the schemas supplied
    B. All references (through IDs) are present
    C. All ports/domains have one and only one input
    D. [Optional] All blocks are connected to at least one other block

## Component Definitions

### Space

A space represents the values passed between blocks.

### Block

A block represents a unit of computation or action

### Concrete Block

A concrete block is a specific instance of a block

### Wiring

A relationship that goes from one blocks codomain to another blocks domain

### System

Defines out the spaces, blocks, concrete blocks and wirings used in a system

## JSON Spec

## Example bdp-lib Input

```{
    "Spaces": [
        {"ID": "S1", "Name": "Space A", "Description": "A space"},
        {"ID": "S2", "Name": "Space B", "Description": "Another space"},
        {"ID": "S3", "Name": "Space C", "Description": "A third space"},
    ],
    "Blocks": [
        {
            "ID": "B1",
            "Name": "Block A",
            "Description": "A block",
            "Domain": ["S1"],
            "Codomain": ["S2"],
        },
        {
            "ID": "B2",
            "Name": "Block B",
            "Description": "Another block",
            "Domain": ["S1"],
            "Codomain": ["S3"],
        },
        {
            "ID": "B3",
            "Name": "Block C",
            "Description": "A third block",
            "Domain": ["S2", "S3"],
            "Codomain": ["S1", "S1"],
        },
    ],
    "ConcreteBlocks": [
        {
            "ID": "CB1",
            "Name": "Concrete Block A",
            "Description": "A concrete block",
            "Parent": "B1",
        },
        {
            "ID": "CB2",
            "Name": "Concrete Block B",
            "Description": "Another concrete block",
            "Parent": "B2",
        },
        {
            "ID": "CB3",
            "Name": "Concrete Block C",
            "Description": "A third concrete block",
            "Parent": "B3",
        },
    ],
    "Wires": [
        {
            "ID": "W1",
            "Parent": "S2",
            "SourceBlock": "CB1",
            "TargetBlock": "CB3",
            "SourceIndex": 0,
            "TargetIndex": 0,
        },
        {
            "ID": "W2",
            "Parent": "S3",
            "SourceBlock": "CB2",
            "TargetBlock": "CB3",
            "SourceIndex": 0,
            "TargetIndex": 1,
        },
        {
            "ID": "W3",
            "Parent": "S1",
            "SourceBlock": "CB3",
            "TargetBlock": "CB1",
            "SourceIndex": 0,
            "TargetIndex": 0,
        },
        {
            "ID": "W4",
            "Parent": "S1",
            "SourceBlock": "CB3",
            "TargetBlock": "CB2",
            "SourceIndex": 1,
            "TargetIndex": 0,
        },
    ],
    "Systems": [
        {
            "ID": "Sys1",
            "Name": "System A",
            "Description": "A system",
            "ConcreteBlocks": ["CB1", "CB2", "CB3"],
            "Wires": ["W1", "W2", "W3", "W4"],
        }
    ],
}
```

