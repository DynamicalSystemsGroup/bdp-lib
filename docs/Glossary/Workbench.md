---
title: Workbench
nav_order: 2
layout: default
parent: Schema & Glossary
---

# Workbench

A workbench consists of the concrete components implemented from the abstract components of the toolbox.


## Schema

The top level schema of a workbench is:

```json
{
  "ID": "string (required)",
  "Parent": "block_id (required)",
  "Name": "string (required)",
  "Description": "string (optional)",
  "Ports": "array[Space] (must match parent block Domain)",
  "Terminals": "array[Space] (must match parent block Codomain)"
}
```

And the children schemas are as follows below.

### Processor Schema


```json
{
  "ID": "string (required)",
  "Parent": "block_id (required)",
  "Name": "string (required)",
  "Description": "string (optional)",
  "Ports": "array[Space] (must match parent block Domain)",
  "Terminals": "array[Space] (must match parent block Codomain)"
}
```

### Wire Schema

```json
{
  "ID": "string (required)",
  "Parent": "space_id (required)",
  "Name": "string (optional)",
  "Description": "string (optional)",
  "Source": "tuple(processor_id, int) (must be valid terminal)",
  "Destination": "tuple(processor_id, int) (must be valid port)"
}
```

### System Schema

```json
{
  "ID": "string (required)",
  "Parent": "space_id (required)",
  "Name": "string (optional)",
  "Description": "string (optional)",
  "Source": "tuple(processor_id, int) (must be valid terminal)",
  "Destination": "tuple(processor_id, int) (must be valid port)"
}
```