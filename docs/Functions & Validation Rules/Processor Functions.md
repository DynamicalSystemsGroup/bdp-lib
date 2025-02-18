---
title: Processor Functions
nav_order: 8
layout: default
parent: Functions & Validation Rules
---

Here’s the revised version with consistent LaTeX formatting:  

# Processor Functions  

## Is Primitive  

- $$\text{isPrimitive}: \text{Processor} \rightarrow \text{Bool}$$  

## Get System  

- $$\text{getSystem}: \text{Processor} \rightarrow \text{System}$$  

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