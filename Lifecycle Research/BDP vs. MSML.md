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