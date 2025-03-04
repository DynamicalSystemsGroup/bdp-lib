---
title: Processor Functions
nav_order: 8
layout: default
parent: Functions & Validation Rules
---

# Processor Functions  

## Is Primitive  

$$\text{isPrimitive}: \text{Processor} \rightarrow \text{Bool}$$

### Description

- The function will return true if there is no linked subsystem which it may be representing, i.e. it is NOT a composite block

### Python Implementation

```python
class Processor:
    ...
    def is_primitive(self):
        return self.subsystem is None
```

## Get System  

$$\text{getSystem}: \text{Processor} \rightarrow \text{System}$$  

### Description

- Function for getting the linked system that this processor represents
- If there is no linked function it will return NULL

### Python Implementation

## Get Shape

$$\text{getShape}: \text{Processor} \rightarrow \text{Block}$$  

### Description

- A function which returns the block that a processor is meant to be implementing

### Python Implementation

- The following is implemented on the python client's Processor class:

```python
class Processor:
    ...
    def get_shape(self):
        return self.parent
```