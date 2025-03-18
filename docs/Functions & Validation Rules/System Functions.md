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

### TypeScript Implementation

```typescript
class System {
    ...
    isValid(): boolean {
        const condition1 = this.getOpenPorts().length === 0;
        const condition2 = this.isConnected();
        return condition1 && condition2;
    }
}
```

## Is Directed

$$\text{isDirected}: \text{system} \rightarrow \text{Bool}$$

### Description

- A function which checks that there are no loops in the system

### Python Implementation

```python
class System:
    ...
    def is_directed(self):
        processors = set([x.id for x in self.processors])
        while len(processors) > 0:
            q = [processors.pop()]
            visited = []
            while len(q) > 0:
                cur = q.pop()
                visited.append(cur)
                cur = self.processors_map[cur]
                wires = [x for x in self.wires if x.source["Processor"].id == cur.id]
                for x in wires:
                    x = x.target["Processor"].id
                    if x in processors:
                        q.append(x)
                        processors.remove(x)
                    if x in visited:
                        return False
        return True
```

### TypeScript Implementation

```typescript
class System {
    ...
    isDirected(): boolean {
        const processors = new Set(this.processors.map(x => x.id));
        while (processors.size > 0) {
            const q = [processors.values().next().value];
            const visited: string[] = [];
            while (q.length > 0) {
                let cur_name = q.pop()!;
                visited.push(cur_name);
                const cur = this.processorsMap[cur_name];
                const wires = this.wires.filter(x => x.source.Processor.id === cur.id);
                for (const x of wires) {
                    const targetId = x.target.Processor.id;
                    if (processors.has(targetId)) {
                        q.push(targetId);
                        processors.delete(targetId);
                    }
                    if (visited.includes(targetId)) {
                        return false;
                    }
                }
            }
        }
        return true;
    }
}
```

## Is Connected

$$\text{isConnected}: \text{system} \rightarrow \text{Bool}$$

### Description

- A function which determines if there is a path between any two nodes, in the weakly connected sense, i.e. either A->B or B->A would suffice for A and be being connected.

### Python Implementation

```python
class System:
    ...
    def is_connected(self):
        processors = set([x.id for x in self.processors])

        q = [processors.pop()]
        while len(q) > 0:
            cur = q.pop()
            cur = self.processors_map[cur]
            wires = [
                x
                for x in self.wires
                if x.source["Processor"].id == cur.id
                or x.target["Processor"].id == cur.id
            ]
            for y in wires:
                x = y.target["Processor"].id
                if x in processors:
                    q.append(x)
                    processors.remove(x)
                x = y.source["Processor"].id
                if x in processors:
                    q.append(x)
                    processors.remove(x)
        return len(processors) == 0
```

### TypeScript Implementation

```typescript
class System {
    ...
    isConnected(): boolean {
        const processors = new Set(this.processors.map(x => x.id));

        const q = [processors.values().next().value];
        while (q.length > 0) {
            let cur_name = q.pop()!;
            const cur = this.processorsMap[cur_name];
            const wires = this.wires.filter(x => x.source.Processor.id === cur.id || x.target.Processor.id === cur.id);
            for (const y of wires) {
                let x = y.target.Processor.id;
                if (processors.has(x)) {
                    q.push(x);
                    processors.delete(x);
                }
                x = y.source.Processor.id;
                if (processors.has(x)) {
                    q.push(x);
                    processors.delete(x);
                }
            }
        }
        return processors.size === 0;
    }
}
```

## Is Dynamical

$$\text{isDynamical}: \text{system} \rightarrow \text{Bool}$$

### Description

- The opposite of `IsDirected` in the sense that there is looping behavior in the system

### Python Implementation

```python
class System:
    ...
    def is_dynamical(self):
        return not self.is_directed()
```

### TypeScript Implementation

```typescript
class System {
    ...
    isDynamical(): boolean {
        return !this.isDirected();
    }
}
```

## Get Open Ports

$$\text{getOpenPorts}: \text{system} \rightarrow \text{List[Port]} = \text{List}[\{\text{Processor, Index, Space}\}]$$

### Description

- Returns a list of open ports which are defined as any ports in a system which have no wire going into them
- The data type has a reference to the processor, the index of the port that is open and the space which that port is a type of

### Python Implementation

```python
class System:
    ...
    def get_open_ports(self):
        out = []
        for processor in self.processor_ports_map:
            for i, port_list in enumerate(self.processor_ports_map[processor]):
                if len(port_list) == 0:
                    out.append([processor, i, processor.ports[i]])
        return out
```

### TypeScript Implementation

```typescript
class System {
    ...
    getOpenPorts(): [Processor, number, Space][] {
        const out: [Processor, number, Space][] = [];
        for (const processor of this.processors) {
            for (let i = 0; i < this.processorPortsMap[processor.id].length; i++) {
                if (this.processorPortsMap[processor.id][i].length === 0) {
                    out.push([processor, i, processor.ports[i]]);
                }
            }
        }
        return out;
    }
}
```

## Get Available Terminals

$$\text{getAvailableTerminals}: \text{system} \rightarrow \text{List[Terminal]} = \text{List}[\{\text{Processor, Index, Space}\}]$$


### Description

- Returns a list of open or available terminals based on a default parameter of "open_only = True"
    - If open_only is true this will only return the list of terminals which have no wiring coming out of them
    - If false, it will return every single terminal in the system given terminals can be used more than once
- The data type has a reference to the processor, the index of the terminal that is open and the space which that port is a type of

### Python Implementation

```python
class System:
    ...
    def get_available_terminals(self, open_only=False):
        out = []
        for processor in self.processor_terminals_map:
            for i, terminal_list in enumerate(self.processor_terminals_map[processor]):
                if open_only:
                    if len(terminal_list) == 0:
                        out.append([processor, i, processor.terminals[i]])
                else:
                    out.append([processor, i, processor.terminals[i]])
        return out
```

### TypeScript Implementation

```typescript
class System {
    ...
    getAvailableTerminals(open_only = false): [Processor, number, Space][] {
        const out: [Processor, number, Space][] = [];
        for (const processor of this.processors) {
            for (let i = 0; i < this.processorTerminalsMap[processor.id].length; i++) {
                if (open_only) {
                    if (this.processorTerminalsMap[processor.id][i].length === 0) {
                        out.push([processor, i, processor.terminals[i]]);
                    }
                } else {
                    out.push([processor, i, processor.terminals[i]]);
                }
            }
        }
        return out;
    }
}
```

## Get Connected Components

$$\text{getConnectedComponents}: \text{system} \rightarrow \text{List[Processor]}$$

### Description

- This will return a nested list of processors which corresponds to different clusters of processors that are connected
- If all components are connected, the list will be of length 1 with the that one element being a list of all processors

### Python Implementation

```python
class System:
    ...
    def get_connected_components(self):
        processors = set([x.id for x in self.processors])
        clusters = []
        while len(processors) > 0:
            cluster = []
            q = [processors.pop()]
            while len(q) > 0:
                cur = q.pop()
                cur = self.processors_map[cur]
                cluster.append(cur)
                wires = [
                    x
                    for x in self.wires
                    if x.source["Processor"].id == cur.id
                    or x.target["Processor"].id == cur.id
                ]
                for y in wires:
                    x = y.target["Processor"].id
                    if x in processors:
                        q.append(x)
                        processors.remove(x)
                    x = y.source["Processor"].id
                    if x in processors:
                        q.append(x)
                        processors.remove(x)
            clusters.append(cluster)
        return clusters
```


### TypeScript Implementation

```typescript
class System {
    ...
    getConnectedComponents(): Processor[][] {
        const processors = new Set(this.processors.map(x => x.id));
        const clusters: Processor[][] = [];
        while (processors.size > 0) {
            const cluster: Processor[] = [];
            const q = [processors.values().next().value];
            processors.delete(q[0]!);
            while (q.length > 0) {
                let cur_name = q.pop()!;
                const cur = this.processorsMap[cur_name];
                cluster.push(cur);
                const wires = this.wires.filter(x => x.source.Processor.id === cur.id || x.target.Processor.id === cur.id);
                for (const y of wires) {
                    let x = y.target.Processor.id;
                    if (processors.has(x)) {
                        q.push(x);
                        processors.delete(x);
                    }
                    x = y.source.Processor.id;
                    if (processors.has(x)) {
                        q.push(x);
                        processors.delete(x);
                    }
                }
            }
            clusters.push(cluster);
        }
        return clusters;
    }
}
```

## Get Subsystems

$$\text{getSubsystems}: \text{system} \rightarrow \text{List[Processor]}$$  


### Description

- This function will return the subsystems that are part of this system by extracting systems from any composite processors present
- It will only return the top level, i.e. nested subsystems will not be returned, but the getHierachy function can achieve that

### Python Implementation

```python
class System:
    ...
    def get_subsystems(self):
        return [x.subsystem for x in self.processors if not x.is_primitive()]
```

### TypeScript Implementation

```typescript
class System {
    ...
    getSubsystems(): any[] {
        return this.processors.filter(x => !x.isPrimitive()).map(x => x.subsystem);
    }
}
```

## Get Hierarchy

$$\text{getHierarchy}: \text{system} \rightarrow \text{NestedDict}$$


### Description

- This function will recursively look through a system defining out branches where there are subsystems and leaves where there are processors to show the hierachy of nested subsystems

### Python Implementation

```python
class System:
    ...
    def get_hierarchy(self):
        out = {}
        for processor in self.processors:
            if processor.is_primitive():
                out[processor.id] = processor
            else:
                out[processor.id] = processor.subsystem.get_hierachy()
        return out
```

### TypeScript Implementation

```typescript
class System {
    ...
    getHierarchy(): { [key: string]: any } {
        const out: { [key: string]: any } = {};
        for (const processor of this.processors) {
            if (processor.isPrimitive()) {
                out[processor.id] = processor;
            } else {
                out[processor.id] = processor.subsystem.get_hierarchy();
            }
        }
        return out;
    }
}
```

## Get Spaces

$$\text{getSpaces}: \text{system} \rightarrow \text{List[Space]}$$

### Description

- A function which returns all the spaces used by processors in a system
- If the argument nested=True, then it will also return all spaces which are used in subsystems of the system as well

### Python Implementation

```python
class System:
    ...
    def get_spaces(self, nested=False):
        if not nested:
            spaces = set().union(
                *(
                    [x.ports for x in self.processors]
                    + [x.terminals for x in self.processors]
                )
            )
            spaces = list(spaces)
        else:
            spaces = set()
            for processor in self.processors:
                if processor.is_primitive():
                    spaces.update(processor.ports)
                    spaces.update(processor.terminals)
                else:
                    spaces.update(processor.subsystem.get_spaces(nested=True))
            spaces = list(spaces)
        return spaces
```

### TypeScript Implementation

```typescript
class System {
    ...
    getSpaces(nested = false): Space[] {
        let spaces: Set<Space>;
        if (!nested) {
            spaces = new Set(this.processors.flatMap(x => [...x.ports, ...x.terminals]));
        } else {
            spaces = new Set();
            for (const processor of this.processors) {
                if (processor.isPrimitive()) {
                    spaces = new Set([...spaces, ...processor.ports, ...processor.terminals]);
                } else {
                    spaces = new Set([...spaces, ...processor.subsystem.get_spaces(true)]);
                }
            }
        }
        return Array.from(spaces);
    }
}
```

## Lazy Make Processor

$$\text{Imp}: \text{system} \rightarrow \text{Processor}$$

### Description

- A function which lazily makes the composite processor that could represent a system following these steps:

1. get the ports using getOpenPorts(system)
2. assign open ports to the new processors ports (inner wiring)
3. get the terminals using getAvailableTerminals(system)
4. assign the available terminals to the new processors terminals (inner wiring)
5. create a block_id for a block which has these domains and codomains
6. write the new block to the local toolbox
7. create a new processor record with the above
8. write the new processor record to the local workbench

### Python Implementation

```python
class System:
    ...
    def make_processor_lazy(self):
        # Get open ports and terminals
        ports = self.get_open_ports()
        terminals = self.get_available_terminals(open_only=True)

        # Get spaces
        domain = list(map(lambda x: x[2].id, ports))
        codomain = list(map(lambda x: x[2].id, terminals))

        block_id = self.id + "-CP Block"
        processor_id = self.id + "-CP"

        block_scaffold = {
            "ID": block_id,
            "Name": self.name + "-CP Block",
            "Description": "A lazy loaded composite processor block for {}".format(
                self.name
            ),
            "Domain": domain,
            "Codomain": codomain,
        }

        port_mappings = []
        for d in ports:
            port_mappings.append({"Processor": d[0].id, "Index": d[1]})
        terminal_mappings = []
        for d in terminals:
            terminal_mappings.append({"Processor": d[0].id, "Index": d[1]})

        processor_scaffold = {
            "ID": processor_id,
            "Name": self.name + "-CP",
            "Description": "A lazy loaded composite processor block for {}".format(
                self.name
            ),
            "Parent": block_id,
            "Ports": domain,
            "Terminals": codomain,
            "Subsystem": {
                "System ID": self.id,
                "Port Mappings": port_mappings,
                "Terminal Mappings": terminal_mappings,
            },
        }

        print("-----Add the following to your JSON-----")
        print()
        print("Add to blocks:")
        pprint(block_scaffold)
        print()
        print("Add to processors:")
        pprint(processor_scaffold)
```

### TypeScript Implementation

```typescript
class System {
    ...
    makeProcessorLazy() {
        // Get open ports and terminals
        const ports = this.getOpenPorts();
        const terminals = this.getAvailableTerminals(true);

        // Get spaces
        const domain = ports.map(x => x[2].id);
        const codomain = terminals.map(x => x[2].id);

        const block_id = `${this.id}-CP Block`;
        const processor_id = `${this.id}-CP`;

        const block_scaffold = {
            ID: block_id,
            Name: `${this.name}-CP Block`,
            Description: `A lazy loaded composite processor block for ${this.name}`,
            Domain: domain,
            Codomain: codomain,
        };

        const port_mappings = ports.map(d => ({ Processor: d[0].id, Index: d[1] }));
        const terminal_mappings = terminals.map(d => ({ Processor: d[0].id, Index: d[1] }));

        const processor_scaffold = {
            ID: processor_id,
            Name: `${this.name}-CP`,
            Description: `A lazy loaded composite processor block for ${this.name}`,
            Parent: block_id,
            Ports: domain,
            Terminals: codomain,
            Subsystem: {
                "System ID": this.id,
                "Port Mappings": port_mappings,
                "Terminal Mappings": terminal_mappings,
            },
        };

        console.log("-----Add the following to your JSON-----");
        console.log();
        console.log("Add to blocks:");
        console.log(block_scaffold);
        console.log();
        console.log("Add to processors:");
        console.log(processor_scaffold);
    }
}
```