## System Methods

- isValid: system $\rightarrow$ Bool
- isDirected: system $\rightarrow$ Bool
- isConnected: system $\rightarrow$ Bool
- isDynamical: system $\rightarrow$ Bool
- getOpenPorts: system $\rightarrow$ List[Terminal] = List[\{Processor, Index, Type\}]
- getAvailableTerminals: system $\rightarrow$ List[Terminal] = List[\{Processor, Index, Type\}]
- getConnectedComponents: system $\rightarrow$ List[System]
- getSubsystems: system $\rightarrow$ List[Processor] (subset of the processor list which isSubsystem)
- getHierarchy: system $\rightarrow$ NestedDict (primitive processors are leaves in this tree)
- getSpaces: system $\rightarrow$ List[Space]
- makeProcessor:system x block x List[wires] $\rightarrow$ Processor
- Imp: system $\rightarrow$ Processor (aka "lazy make processor)

## Processor Methods

- isSubsystem: processor $\rightarrow$ Bool
- isPrimitive: Process $\rightarrow$ Bool
- getSystem: processor $\rightarrow$ System
- getShape: processor $\rightarrow$ Block

## Project Methods

- lazyLoadCompositeProcessor