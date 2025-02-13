---
title: System Functions
nav_order: 10
layout: default
parent: Functions & Validation Rules
---

# System Functions

## Is Valid

- isValid: system $\rightarrow$ Bool

## Is Directed

- isDirected: system $\rightarrow$ Bool

## Is Connected

- isConnected: system $\rightarrow$ Bool

## Is Dynamical

- isDynamical: system $\rightarrow$ Bool

## Get Open Ports

- getOpenPorts: system $\rightarrow$ List[Terminal] = List[\{Processor, Index, Type\}]

## Get Available Terminals

- getAvailableTerminals: system $\rightarrow$ List[Terminal] = List[\{Processor, Index, Type\}]

## Get Connected Components

- getConnectedComponents: system $\rightarrow$ List[System]

## Get Subsystems

- getSubsystems: system $\rightarrow$ List[Processor] (subset of the processor list which isSubsystem)

## Get Hierarchy

- getHierarchy: system $\rightarrow$ NestedDict (primitive processors are leaves in this tree)

## Get Spaces

- getSpaces: system $\rightarrow$ List[Space]

## Make Processor

- makeProcessor:system x block x List[wires] $\rightarrow$ Processor

## Lazy Make Processor

- Imp: system $\rightarrow$ Processor (aka "lazy make processor)