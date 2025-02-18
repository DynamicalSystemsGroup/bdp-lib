---
title: System Functions
nav_order: 10
layout: default
parent: Functions & Validation Rules
---

# System Functions

## Is Valid

$$\text{isValid}: \text{system} \rightarrow \text{Bool}$$

### Description

### Python Implementation

## Is Directed

$$\text{isDirected}: \text{system} \rightarrow \text{Bool}$$

### Description

### Python Implementation

## Is Connected

$$\text{isConnected}: \text{system} \rightarrow \text{Bool}$$

### Description

### Python Implementation

## Is Dynamical

$$\text{isDynamical}: \text{system} \rightarrow \text{Bool}$$

### Description

### Python Implementation

## Get Open Ports

$$\text{getOpenPorts}: \text{system} \rightarrow \text{List[Port]} = \text{List}[\{\text{Processor, Index, Space}\}]$$

### Description

- Returns a list of open ports which are defined as any ports in a system which have no wire going into them
- The data type has a reference to the processor, the index of the port that is open and the space which that port is a type of

### Python Implementation

## Get Available Terminals

$$\text{getAvailableTerminals}: \text{system} \rightarrow \text{List[Terminal]} = \text{List}[\{\text{Processor, Index, Space}\}]$$


### Description

### Python Implementation

## Get Connected Components

$$\text{getConnectedComponents}: \text{system} \rightarrow \text{List[System]}$$

### Description

### Python Implementation


## Get Subsystems

$$\text{getSubsystems}: \text{system} \rightarrow \text{List[Processor]}$$  


### Description

### Python Implementation
  (subset of the processor list which isSubsystem)

## Get Hierarchy

- $$\text{getHierarchy}: \text{system} \rightarrow \text{NestedDict}$$  
  (primitive processors are leaves in this tree)

### Description

### Python Implementation

## Get Spaces

- $$\text{getSpaces}: \text{system} \rightarrow \text{List[Space]}$$

### Description

### Python Implementation

## Make Processor

$$\text{makeProcessor}: \text{system} \times \text{block} \times \text{List[wires]} \rightarrow \text{Processor}$$

### Description

### Python Implementation

## Lazy Make Processor

- $$\text{Imp}: \text{system} \rightarrow \text{Processor}$$

### Description

### Python Implementation
