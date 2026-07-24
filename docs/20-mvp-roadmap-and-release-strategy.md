# MVP Roadmap and Release Strategy

**Status:** Approved scope direction

## MVP hypothesis

The first playable release must prove:

> A small persistent region can support player and NPC residence, movement, work, production, trade and property while time continues offline.

It does not need to prove every long-term profession.

## Stage 0 — executable design

- approve constitutional and architectural ADRs
- choose plot scale through benchmarks
- define one currency and minimal ledger
- define action, skill, item batch, quality and provenance contracts
- build simulation test harness before live economy

## Stage 1 — vertical slice

- one region and settlement
- player character and capped NPC workers
- plot map, location and walking
- hunger, energy and one food
- two raw resources, including one renewable
- three connected production steps
- item batches, quality, inventory and durability
- public job listings and timed work
- simple market and automatic tax
- one property/building type
- one NPC-run public authority
- offline action completion

Suggested illustrative chain: soil/seed → grain → flour → bread, plus wood/tool support. Final selection requires an owner decision after prototype cost review.

## Stage 2 — economy and settlement

- companies and shares
- rental property and modular construction
- road transport and logistics contracts
- loans and collateral
- school and vocational education
- energy service abstraction
- elections and municipal budgets

## Stage 3 — industrial society

- deposits and prospecting
- multi-facility manufacturing
- research and licensing
- private banks and insurance
- additional transport networks
- deeper health and public services

## Stage 4 — conflict and advanced society

- crime, investigation and justice
- controlled substances and black markets
- regions/countries and complex political systems
- war and territorial conflict
- additional continents

## Release gates

Each stage requires:

- conservation and retry tests
- load tests at projected scale
- economy simulations against runaway inflation/deflation
- exploit review
- recovery rehearsal
- player comprehension testing

## Scope rule

Do not add a later-stage domain merely because its table is easy to create. A feature enters a release only as a complete causal loop with understandable player consequences.

