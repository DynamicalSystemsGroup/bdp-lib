## Executive Summary

- MSML is currently a superset of all bdp-lib functionality and could replicate a bdp-lib style schema by parsing out the extra pieces
- This document outlines all the differences between the two
- Nothing is set in stone, many of the paradigms of MSML may change if it makes it cleaner
- It is important to consider to what extent we want to break things out, for example, we could split out certain aspects of the MSML into certain bdp-protocol enhancements, for example it might be:
	- The schema enhancement for adding in ontologies for blocks/processors so that we can have specialized versions (i.e. a boundary action vs. a policy)
	- The schema enhancement that allows one to represent state and parameters
	- etc.
- If we split it like this, we might be able to allow users to pick only the enhancements they need to add in, i.e. you might need no state representation if it is a pure dynamical system where you want to pass the state as part of the spaces
	- But for a representation of a system with a large state, it might be better to have state abstracted out with the JSON schema enhancement
- Some of these features might also depend on each other and would have dependencies know up front
	- For example if you want to add the schema enhancement that allows you to say what pieces of state are updated by blocks, you would need the schema enhancement that adds the idea of state outside of the blocks

## Block/Processor Data Differences

- MSML only has blocks which has sub-classes of boundary action, control action, policy and mechanism. But this can be changed moving forward.
- In addition some of the other MSML components might be better modified going forward as well, this is just for showing current state of things

|                               | BDP         | MSML                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ----------------------------- | ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Splits to block and processor | X           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Domain                        | X           | X                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Codomain                      | X           | X                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Description                   | X, optional | X, optional                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Constraints                   |             | X, optional - However it is only currently string descriptions, plan to  switch to programatic in the future                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Parameters Used               |             | X, optional                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Metadata                      |             | X, optional - mostly used for things like aliases for Obsidian but completely modular for any data someone wants to track (dictionary type)                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Block Type                    |             | X - but is assigned by factory method for if the block is boundary action, control action etc. **This may change going forward to a bring your own ontology kind of thing**                                                                                                                                                                                                                                                                                                                                                                                                                     |
| State Updates                 |             | X, optional, only used by mechanisms - assigns the relationship of what aspects of state either global or local are updated by this block                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Called by                     |             | X, optional, only used by boundary actions - denotes which entities are initiating a block                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Options                       |             | X, not used in mechanisms since they should have only one implementation, they are different specific implementations **without** code. I.e. if you wanted to specify for a game theoretic model different response functions different players might be taking. **NOTE**: This is not the same as blocks vs. processors, it would be more similar to saying we have a processor that might be "Player 2 Response" but then options which are something like "always play A" or "randomly choose between response A/B" or more complicated logic that takes into account player 1's latest move |
| Bound Code                    |             | X, the code gets bound to different options (or for mechanisms it is just one piece of code), it can be in any language but currently it is only python supported fully                                                                                                                                                                                                                                                                                                                                                                                                                         |


## Block Types & Bring your Own Ontology

### Block Types in MSML

- The current paradigm is defining blocks separately as either:
	- Boundary Action: Actions which entities initiate, this could be something like a trader entity makes a trade
	- Control Action: Actions abstracted to what the overall system will do, i.e. if a smart contract every hour initiates a checking for quality of service metrics which then aggregates
	- Policy: Blocks for defining out all the logic, i.e. if you have something like uniswap, you might have a swap boundary action which leads into a policy which determines what amount you get out and any downstream impacts to state (through passing spaces to mechanisms)
	- Mechanisms: Blocks which are meant to be the central place for certain kinds of state updates so that you can add things like 1. state variable update listeners 2. constraints 3. have a central location to update for scenarios where you might have the mechanism update on state variable but later on want to expand it to also update another linked state variable... for example if you were updating a stake amount variable each time but later wanted to add in a way to add to some log what the dates are that different stake can be unstaked at
- This is currently rigid but can be updated to be based on a tags system or bring your own ontology kind of paradigm

### Bring your Own Ontology

- There are three aspects to this potential change:
	- Tagging for visibility
	- Modifying constructors of the block class so that making a block is like a factory method and you can toggle certain feature on or off depending on the specific ontology
	- Allowing a flexible way to have different breakdowns of the types of blocks, i.e. allowing a user to come in and say I want to denote blocks as either on-chain or off-chain for crypto systems

#### Tagging

- The idea with tagging would be that either one or multiple tags could be attached to blocks
- This could allow for quick filtering of different blocks to look at something like "user actions"
#### Modifying Constructors

- Right now, for example, only boundary actions are allowed to have "called_by" because they are the only blocks that are initiated by an entity
- Mechanisms are the only blocks that are able to have state updates
- Turning this modular means a user can denote which features are or are not used within a block
- This could be something like a tag that says "Updates State" and this turns on state updating in the factory method or "Called by Entity" which makes it accept the data for what entities are triggering it

#### Flexible Schemas

- Define a way to have a set of subsets of block that have these tags so that you can define out specific versions of blocks, but you as the users write an ontology that defines out what those specific versions are
- Built-in, off-the-shelf options like the Boundary Action/Control Action/Policy/Mechanism ontology

## MSML Wiring vs. BDP Systems & Wirings

- The primary difference with how to connect blocks in MSML is:
	- An MSML "wiring" is similar to a system in bdp-lib
	- The wires in MSML are automatically inferred and error out on loading if they don't match up
	- Composability happens with MSML by referencing wirings as components of other wirings
- The wiring types here take in components and a name as attributes and then essentially represent a composed bunch of blocks - **this is similar to a composite processor**
	- The domain and codomain is inferred by the components and type of wiring
### MSML Wiring Types

- **Keep in mind that a component can be a wiring which is how you get composition / recursion**
- **There can also be an ending component which is either a mechanism or parallel block of mechanisms in which case the codomain out is going to be the empty space/no spaces but there will be state updates**
	- There can also be intermediate mechanisms, especially if you have a component that is a wiring which contains some mechanisms and some blocks returning spaces
- **Parallel Block**: A wiring that executes the blocks in parallel
	- Domain is the sum of component domains
		- Anything passed to the domain has to be in this exact ordering and then it passes it in that exact ordering to the components
		- If block 1 has domain [A, C] and block 2 has domain of [B, A], then the wiring domain is [A, C, B, A] and index 0 goes to block 1's port 0, index 1 to block 1's port 1, index 2 to block 2's port 0, index 3 to block 2's port 1
	- Codomain is the sum of component codomains
		- Similar idea with exact mapping of the component codomains to wiring codomain
	- Execution flow is take the full domain, allocate the spaces to their respective blocks, execute each block in parallel, then sequentially build up the output codomain by grabbing the component domain's
- **Stack Block**: A wiring for sequential execution of components
	- Domain is the domain of the first component
	- Codomain is the codomain of the last component
	- For each component $i$ and $i+1$ , the codomain of $i$ must match the domain of $i+1$ and there is validation for this
	- Execution takes the wiring domain, passes it to block 1, grabs the codomain of that and passes it as domain to block 2, repeated until it is the last block which passes it to the wiring's codomain
- **Split Block**: A wiring which takes components and then splits the execution so that it is similar to breadth first, i.e. component 1 executes, then it pops back up to component 2 and executes everything in it, etc.
	- Domain: Sum of component domains
	- Codomain: None, the execution of blocks are split out from here so there is no recombining like in the parallel block

### Future Direction

- We might be able to get rid of this altogether by defining out the logic of when processors execute and in what order, i.e. if we say there is a stack queue of processor to execute and whenever a processor has all of its domain fulfilled it executes
- More research is needed to figure out the best way to add computation to bdp-lib style block diagrams
- **NOTE**: The current format does allow reverse compatibility to bdp-lib because the wires are implied and could easily be automatically written out so that an MSML spec can write a bdp-lib spec, but forward compatibility will struggle with the following issues:
	- Non-supported structures of the graph made by bdp-lib wirings, i.e. if you want two ports on a processor but two separate wirings actually feed into them (but are not considered a parallel wiring)
	- The ability to have looping for bdp-lib diagrams (right now you would have one larger wiring which calls all your sub wirings or you feed a list of wirings that should be executed sequentially 0-N times each)
		- This could be solved by the forcing of making a "cut" in a bdp-lib diagram to denote start and finish

## Spaces Differences

- The only difference for spaces is that MSML requires you to give a space a schema which is a typed dictionary of name -> type. I.e. your cartesian space has {"X": "Coordinate Value Type", "Y": "Coordinate Value Type"}
	- Coordinate value type would map to a floating point number
	- But this specificity makes it so you understand that X and Y should only represent the value used in a coordinate and not something like a dollar amount
## Additional MSML Components

### Types

- Defines out by description what types are used in the system such as "USD Currency Type" or "Data Log Type"
- Has ability to add in mappings to programming language types so that one can automatically have strong typing on code representations of spaces or anywhere else that types are referenced (and that you can translate between different programming languages)
### States

- Defines out states in the system
- Only required one is global state which says what the global variables used in the system are
	- Has types attached to each
	- Can also be things like users = List[UserEntity] in which case it represents all the local states of user entities / references to the user entities
- Local states can also be defined here and linked to the global state / entities to make it clear which states are related directly to someone or something versus global
- Global state is the one that the execution engine uses so all local states need to be somehow linked to an entity/the global state
### Entities

- Defines out the actors within a system
- Similar to class definitions
- Gets local state attached which define out what state variables are tracked
- Can be singleton or multiple 

### Parameters

- Defined out as the values which can be toggled that impact blocks
- Blocks have an attribute where they denote which parameters are used
	- This could be a parameter like a random distribution for representing exogenous signals
	- Or something like a parameter which defines the rate of fees charged
- Currently three classes of parameters
	- Behavioral: Defines out behaviors in the system like randomness of actions or how entities might act
	- System: Any parameters related to how the logic of the system works, i.e. a fee based on system_fee parameter is charged when computing a policy
	- Functional: Special class of parameter that for all blocks which have more than one "option" defines out which specific version of the block to use when doing execution of a simulation / wiring
- **NOTE**: This can also be expanded out to a bring your own ontology approach
	- The handling of how to specify which option to execute, however, might need to stay the same so we have a way to denote the way you do A/B testing of different policy options of a policy for example or different assumptions of exogenous signals by varying the boundary action options of boundary actions

### Stateful Metrics

- Define out all information which could be computed from pieces of state and parameters
- This is for holding anything you do not want held in state as it would be redundant
- Code can be mapped for executing this and having it accessible globally from all blocks
- Useful for things like "Total Supply" coming from adding up all individual holdings between users and the treasury for example

### Metrics

- The same as stateful metrics except they also take in a domain as well as using stateful metrics or other metrics as input
- These are for the same idea - repeatable computations
- For example, if you often need to compute the size of a trade relative to the total volume, you could have a metric that takes as input the trade size in $ and then divides that by the stateful metric of "Total Supply" to return the percentage

### Displays

- A way to group together multiple wirings
- Given the defined components which are wirings, it is useful for producing reports that are a view on a system, i.e. user wirings only
- **Could be replaced by tags potentially**
- Also can be implemented in code and then accessed globally by blocks

## Extra MSML Outputs

### Obsidian Vault & Reports

- MSML produces an obsidian vault which has a markdown note for every single component and automatically writes out all the connections between them
- Also has specific PDF and markdown reports that can be auto-written from an MSML spec

### Block & Wiring Execution

- Individual wirings and blocks can be executed as long as they or their components have code attached
- Allows you to write block by block and then wiring by wiring the implementation instead of the entire simulation
### MSML Execution Engine

- Given a set of parameters and initial state (defined with the schema of global state), one can run one or multiple experiments as long as all code is wired up
- All blocks/wirings must have code attatched

### cadCAD Execution

- Can create a factory of cadCAD models which gives a data scientist the state and parameters required to run as well as an executable object which give just those two runs as code without requiring the user to even know what is happening at the MSML level
- Provides a strict interface to separate MSML writing from running an actual model

### Meta-Programming

- Work in progress work for writing out MSML specs to specific software packages in any language
- Given bound code, has methods which automatically translate all the code and metadata into nicely written and typed functions
- Can return something like all the blocks defined out as their functions
- And all the wirings defined out as the specific instructions that make them correctly run for execution

## Conclusions & Thoughts

- Given all this information we need to potentially break MSML into multiple components
- Things such as model execution could be split up into a library that just handles this aspect
- The JSON schema enhancements might be better of as something like JSON LD where you bring in different enhancements/features as context and this opens the door up more and more on what extra features you can use
- We may want to consider what is protocol level (i.e. if we define out the JSON schema for state) as well as what is client (the code to compose the local states together)
- Even if we leave it flexible what features you adopt, it could be useful to define out the extent to which we have a "normal" set of phases to build up from a core bdp-lib block diagram all the way to entire simulations and what the intermediate steps are.