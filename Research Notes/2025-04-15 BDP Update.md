# Current Open Work on the Block Diagram Protocol

## Executive Summary

The following summarizes the current state of different workstreams within the larger bdp umbrella.

## Core Protocol

### Extensions (Blocked)

- Currently extensions are in the planning stage
- The [hackmd](https://hackmd.io/bjtBLe3QRQCLxCRN7mxVgA?view) here details BDP vs. MSML and what changes might support a simple workflow to go from bdp to MSML

### Documentation (Rough Draft)

- Documentation work is in progress with iterative updates happening, the site [here](https://dynamicalsystemsgroup.github.io/bdp-lib/) is the working copy
- Looking for feedback from others on what can be improved


## pybdp

### User Interface (Work in Progress)

- Working primarily on a CRUD style interface to make it easier to build bdp projects on the fly
- In addition, considering nice to have features like automatic saving or checkpointing

### Supporting Pieces (To-Do)

- Still need to create stronger documentation on how to use pybdp
- Template repository to be created which can be forked and used as a starting point

### Tests (Rough Draft)

- A primary test suite is complete and all passing
- Working on adding more coverage


## bdp-typescript (Rough Draft)

- All core functionality is complete
- Only open issue is launching to npm
- Also should begin dogfooding


## Canonical Examples

### Homicidal Chauffeur (Blocked / Rough Draft)

- Current rough draft repository [here](https://github.com/DynamicalSystemsGroup/homicidal-chauffeur-canonical-example)
- Awaiting feedback on if this properly fits the model

### Toy Examples & Recipes (Rough Draft / Work in Progress)

- Repository [here](https://github.com/DynamicalSystemsGroup/bdp-toy-examples) with some examples completed
- Some past Zargham work still slated to be added in
- One recipe added so far, more to come


### BDP-ML (Work in Progress)

- Repository [here](https://github.com/DynamicalSystemsGroup/BDP-ML) which has a few examples of representing machine learning systems within bdp
- More examples and work being done for dogfooding with good real life examples
- Has shown already quite a few places where more attention is useful, i.e. the recipe for "switches" that came out of a specific issue with representing certain looping behaviors


## Capabilities Workstream

### Engineering Lifecycle (Blocked / Work in Progress)

- There is a first attempt at re-creating the engineering lifecycle with bdp [here](https://github.com/DynamicalSystemsGroup/bdp-eng-lifecycle)
- Blocked on getting feedback about the direction (https://dynamicalsystemsgroupteam.slack.com/archives/C08A70040KD/p1743779612293929)

### LLM -> BDP Worflow (New)

- New possible work on using LLMs to write bdp projects
- New channel created for discussing

## Front Ends (Work in Progress)

- Currently one front end [here](https://github.com/DynamicalSystemsGroup/bdp-frontend), which Rohan is working on