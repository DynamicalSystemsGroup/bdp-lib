---
title: Toolbox
nav_order: 1
layout: default
parent: Schema & Glossary
---

# Toolbox

A toolbox is full of abstract objects that can be thought of as reusable patterns or templates that the concrete components in a workbench satisfy.

A toolbox consists of:
- **Blocks**: Reusable templates for system components.
- **Spaces**: Defines the types of inputs and outputs.

## Schema

The top level schema of a toolbox is:

```json
{
  "ID": "string (required)",
  "Name": "string (required)",
  "Description": "string (optional)"
}
```

And the children schemas are as follows below.

### Block Schema

```json
{
  "ID": "string (required)",
  "Name": "string (required)",
  "Description": "string (optional)"
}
```

### Space Schema

```json
{
  "ID": "string (required)",
  "Name": "string (required)",
  "Description": "string (optional)",
  "Domain": "array[Space] (required, can be empty)",
  "Codomain": "array[Space] (required, can be empty)"
}
```
