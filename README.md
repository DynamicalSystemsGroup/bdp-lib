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

## JSON Spec