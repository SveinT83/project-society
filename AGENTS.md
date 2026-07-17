# AGENTS.md

## Purpose

This document defines mandatory instructions for Codex and every other AI agent contributing to Project Society.

These rules apply to the entire repository unless a more specific `AGENTS.md` exists deeper in the directory tree. A nested instruction file may add domain-specific requirements, but it must not weaken or contradict this root document.

If implementation conflicts with the approved documentation, the implementation is wrong.

## Authority Order

When instructions conflict, use this order:

1. Explicit instructions from the project owner for the current task
2. Approved architectural decision records
3. The Game Constitution
4. Approved domain documentation under `/docs`
5. This file
6. Existing implementation patterns

Do not silently resolve meaningful conflicts. Report them before implementation.

## Current Project Phase

Project Society is currently in the design and documentation phase.

Until the project owner explicitly authorises implementation:

- do not scaffold Laravel
- do not add application code
- do not create database migrations
- do not install dependencies
- do not choose libraries on behalf of the project
- do not turn design examples into production code

Documentation, analysis, diagrams, decision records and planning files are allowed.

## Mandatory Design Principles

### 1. Documentation is the source of truth

Read all relevant documentation before proposing or implementing changes.

Never invent missing rules merely to complete a task. Identify the ambiguity and propose a documented decision.

### 2. Design before implementation

Do not implement a domain before its core behaviour, boundaries, invariants and dependencies are documented sufficiently for the requested scope.

### 3. Players define their own goals

Do not introduce a mandatory final objective, universal victory condition or linear campaign progression.

### 4. The world is persistent

The world continues while individual players are offline.

An offline player may finish an already-started personal action, but must not automatically begin unlimited new personal actions unless an explicitly documented automation system allows it.

### 5. Deep simulation, simple interaction

Preserve meaningful causes and consequences while hiding unnecessary administrative work.

Routine accounting, tax calculation, payroll deductions, interest and similar bookkeeping should normally be automatic.

### 6. Interesting decisions over unnecessary realism

A feature must create meaningful choices, consequences or social interaction. Do not add complexity solely because it exists in the real world.

### 7. Quality propagates

Quality must flow through relevant production chains. Raw resources, worker skills, equipment, processes and intermediate goods may affect the final product.

Do not create isolated quality values that ignore provenance and upstream inputs.

### 8. Everything important has provenance

Resources, products, buildings, research outputs and ownership changes should retain a traceable origin whenever practical.

### 9. Players are preferred over NPCs

NPCs keep the world operational when players do not fill necessary roles.

NPC behaviour should be rule-driven wherever possible. Constrained AI may select only from validated game actions where rules alone are insufficient.

NPC skills must have documented caps that committed players can exceed.

### 10. Information is a resource

Never expose information merely because it exists in the database.

A player may only receive information their character can reasonably know through presence, recent observation, ownership, employees, friends who share location, public records, sensors, communication or technology.

Authorisation and information visibility are domain rules, not only interface concerns.

### 11. Store aggregate state; calculate details when needed

Avoid continuous simulation of individual trees, fish, wildlife or other entities when aggregate plot or regional state produces the same meaningful consequences.

Prefer calculations triggered by:

- player actions
- world events
- scheduled regional updates
- material state transitions

### 12. The API follows the same rules as the official client

External API consumers, scripts and AI-controlled players must not bypass permissions, timers, physical-presence requirements, costs, rate limits or simulation rules.

All commands must pass through the same application and domain services used by the official interface.

## Architecture Rules

### Domain boundaries

Keep domains explicit and cohesive. Avoid large generic services, catch-all models and utility modules that mix unrelated responsibilities.

Likely domains include world, geography, resources, characters, NPCs, skills, actions, inventory, production, companies, property, finance, government, law, crime, education, research, energy, transport, communication and information.

These boundaries are provisional until approved in the technical architecture.

### Domain communication

Prefer explicit commands, domain events and stable contracts over direct cross-domain mutation.

Do not introduce distributed services prematurely. A modular monolith is the expected starting direction unless approved documentation decides otherwise.

### State changes

Important state changes must be:

- authorised
- validated
- transactional where required
- auditable
- idempotent when retried by queues or external clients

### Time and queued work

Timers and scheduled work must use server-authoritative timestamps.

Never trust a client to decide that an action has completed.

Queued and scheduled operations must tolerate retries without duplicating money, resources, products, XP or ownership changes.

### Performance

Do not prematurely optimise, but reject designs that require constant per-entity ticking across the entire planet.

Prefer regional batching, lazy evaluation, cached derived values and event-driven recalculation where appropriate.

## Documentation Workflow

Before changing or adding a system:

1. Read `README.md`, this file and all relevant documents.
2. Identify affected domains and existing decisions.
3. State assumptions and unresolved conflicts.
4. Update or create the design documentation.
5. Record important architectural decisions under `/decisions`.
6. Only implement after the design is approved for implementation.
7. Add or update tests when implementation is authorised.
8. Update documentation when an approved design changes.

## Writing Documentation

Documentation should distinguish clearly between:

- approved rules
- current recommendations
- open questions
- future expansion
- rejected ideas
- implementation notes

Do not present speculation as an approved decision.

Use concrete examples to explain systems, but label example numbers as illustrative unless they are approved balance values.

Avoid duplicating the same rule across many files. Link to the authoritative document instead.

## Rejected or Deferred Ideas

When the project deliberately rejects or postpones an idea, record it in the appropriate rejected-ideas or roadmap document with the reason.

Do not reintroduce a rejected idea without explicitly revisiting that decision.

Examples already rejected or deliberately simplified include:

- individual simulation of every tree
- individual simulation of fish populations
- manual bookkeeping and VAT reporting
- players writing arbitrary executable programs inside the game
- exposing complete live plot information without an in-world information source

## Coding Standards for the Future Implementation Phase

These rules become active once implementation is authorised:

- prefer readable and explicit code over clever abstractions
- keep controllers and transport layers thin
- place business invariants inside domain or application services
- use typed value objects for important concepts where useful
- use database constraints in addition to application validation
- avoid unbounded queries and hidden N+1 behaviour
- test economic transactions, timers, retries and concurrency thoroughly
- never use floating-point arithmetic for money
- document non-obvious formulas and their design rationale
- do not leave placeholder TODO implementations in completed work

Project-specific formatting, testing and static-analysis tools will be selected in the technical architecture before application development begins.

## Required Agent Response When Uncertain

When a requested change is unclear or conflicts with existing rules:

1. Do not silently choose an interpretation.
2. Identify the exact ambiguity or conflict.
3. Explain the affected domains and consequences.
4. Recommend the smallest number of viable alternatives.
5. Wait for an explicit decision when the choice is consequential.

Minor implementation details may be resolved using documented conventions once the project enters implementation.

## Definition of Done

Documentation work is complete when:

- scope and purpose are clear
- authoritative rules are separated from open questions
- affected domains and dependencies are identified
- rejected alternatives are recorded where relevant
- terminology is consistent

Future implementation work is complete when:

- it follows approved documentation
- tests cover normal behaviour and important failure cases
- migrations and queued operations are safe
- permissions and information visibility are enforced server-side
- documentation and decision records remain accurate

Project Society is intended to evolve for many years. Every contribution must preserve its internal consistency and long-term maintainability.
