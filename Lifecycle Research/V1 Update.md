## Executive Summary

- This note walks through the current work in progress on mapping the engineering lifecycle
- Canvases are used but they are pseuo-bdp diagrams
- The colors are as follow:
	- Green - Spaces which are not code/spec based
	- Yellow - State, things such as documents that are completed but might be pulled down in other flows
	- Orange - Code/spec based deliverables
- State is mostly being used here so that it is easier to track across many flows and also denote where there should be persistence

## Phase 1 - SOW Negotiation

- SOW negotiation covers getting an RFP and iteratively coming up with an SOW that is or is not signed off on
- Through iterations, a finalized SOW or failure to sign which can be logged is produced. The SOW is added to the state if it is signed.

![[Pasted image 20250401113110.png]]

## Phase 2 - BDP & Literature Review

- The next phase is taking the SOW produced prior and also client documentation/academic literature to produce a BDP-spec and the current economic mechanisms + candidate mechanisms
- As well a project plan can come out of the triage protocol
- Literature review is transforming the documentation and academic literature into internal documentation as well as the spaces needed for the economics flow
- Requirements engineering comes up with conceptual requirements which then leads into iterations on the BDP spec


![[Pasted image 20250401113147.png]]

## Phase 3 - Economics

- Given a BDP spec and the economic spaces, economic engineering comes up with the requirements and mechanisms agreed upon
- An empty MSML spec also gets initialized

![[Pasted image 20250401113219.png]]

## Phase 4 - MSML Concept Spec

- This is the first canvas that we break out into a separate file, we see all the state up until now on the left hand side
- Given all the economics and requirements work as well as the current BDP spec and MSML spec we iterate until we have a finalized MSML spec for concept

![[Pasted image 20250401113307.png]]