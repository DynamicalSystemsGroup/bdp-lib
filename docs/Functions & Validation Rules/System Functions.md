---
title: System Functions
nav_order: 10
layout: default
parent: Functions & Validation Rules
---

# System Functions

## Is Valid

- $$\text{isValid}: \text{system} \rightarrow \text{Bool}$$

## Is Directed

- $$\text{isDirected}: \text{system} \rightarrow \text{Bool}$$

## Is Connected

- $$\text{isConnected}: \text{system} \rightarrow \text{Bool}$$

## Is Dynamical

- $$\text{isDynamical}: \text{system} \rightarrow \text{Bool}$$

## Get Open Ports

- $$\text{getOpenPorts}: \text{system} \rightarrow \text{List[Terminal]} = \text{List}[\{\text{Processor, Index, Type}\}]$$

## Get Available Terminals

- $$\text{getAvailableTerminals}: \text{system} \rightarrow \text{List[Terminal]} = \text{List}[\{\text{Processor, Index, Type}\}]$$

## Get Connected Components

- $$\text{getConnectedComponents}: \text{system} \rightarrow \text{List[System]}$$

## Get Subsystems

- $$\text{getSubsystems}: \text{system} \rightarrow \text{List[Processor]}$$  
  (subset of the processor list which isSubsystem)

## Get Hierarchy

- $$\text{getHierarchy}: \text{system} \rightarrow \text{NestedDict}$$  
  (primitive processors are leaves in this tree)

## Get Spaces

- $$\text{getSpaces}: \text{system} \rightarrow \text{List[Space]}$$

## Make Processor

- $$\text{makeProcessor}: \text{system} \times \text{block} \times \text{List[wires]} \rightarrow \text{Processor}$$

## Lazy Make Processor

- $$\text{Imp}: \text{system} \rightarrow \text{Processor}$$  
  (aka "lazy make processor")  