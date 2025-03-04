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

- A function which checks the following is true of the system:
    - All inputs follow the schemas supplied
    - All references (through IDs) are present
    - There is one and only one wire into every port [NOTE: This means that systems which are part of composite processors are NOT valid outide of that context]
    - All blocks are connected to at least one other block


### Python Implementation

- The python implementation assumes certain conditions, such as all inputs adhering to the schema, during loading. If these assumptions were incorrect, an error would already occur at that stage, making additional checks in this function redundant.

```python
class System:
    ...
    def is_valid(self):
        condition1 = len(self.get_open_ports()) == 0
        condition2 = self.is_connected()
        return condition1 and condition2
```

## Is Directed

$$\text{isDirected}: \text{system} \rightarrow \text{Bool}$$

### Description

- A function which checks that there are no loops in the system

### Python Implementation

## Is Connected

$$\text{isConnected}: \text{system} \rightarrow \text{Bool}$$

### Description
- A function which determines if there is a path between any two nodes, in the weakly connected sense

### Python Implementation

## Is Dynamical

$$\text{isDynamical}: \text{system} \rightarrow \text{Bool}$$

### Description

- [NOTE]: Is this just the opposite of is directed?

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

- Returns a list of open or available terminals based on a default parameter of "open_only = True"
    - If open_only is true this will only return the list of terminals which have no wiring coming out of them
    - If false, it will return every single terminal in the system given terminals can be used more than once
- The data type has a reference to the processor, the index of the terminal that is open and the space which that port is a type of

### Python Implementation

## Get Connected Components

$$\text{getConnectedComponents}: \text{system} \rightarrow \text{List[Processor]}$$

### Description

- Returns a list of all processors which have at least one connection
- [NOTE]: Is this supposed to be something else?

### Python Implementation

## Get Subsystems

$$\text{getSubsystems}: \text{system} \rightarrow \text{List[Processor]}$$  


### Description

- This function will return the processors of the system which are also subsystems (meaning the isPrimitive function is false)
- It will only return the top level, i.e. nested subsystems will not be returned, but the getHierachy function can achieve that

### Python Implementation


## Get Hierarchy

$$\text{getHierarchy}: \text{system} \rightarrow \text{NestedDict}$$


### Description

- This function will recursively look through a system defining out branches where there are subsystems and leaves where there are processors to show the hierachy of nested subsystems

### Python Implementation

## Get Spaces

$$\text{getSpaces}: \text{system} \rightarrow \text{List[Space]}$$

### Description

- A function which returns all the spaces used by processors in a system
- If the argument nested=True, then it will also return all spaces which are used in subsystems of the system as well

### Python Implementation

## Make Processor

$$\text{makeProcessor}: \text{system} \times \text{block} \times \text{List[wires]} \rightarrow \text{Processor}$$

### Description

- A function which takes a system, a block it should represent, and the wires necessary to link up the composite processor and then turns it into a composite processor

### Python Implementation

## Lazy Make Processor

$$\text{Imp}: \text{system} \rightarrow \text{Processor}$$

### Description

- A function which lazily makes the composite processor following these steps:

1. get the ports using getOpenPorts(system)
2. assign open ports to the new processors ports (inner wiring)
3. get the terminals using getAvailableTerminals(system)
4. assign the available terminals to the new processors terminals (inner wiring)
5. create a block_id for a block which has these domains and codomains
6. write the new block to the local toolbox
7. create a new processor record with the above
8. write the new processor record to the local workbench

### Python Implementation
