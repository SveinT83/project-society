# Project Society Documentation

## Purpose

This directory is the authoritative design and architecture source for Project Society.

Project Society is currently in the **design and documentation phase**. The documents in this directory define the intended world, its rules, its domain boundaries and the technical direction that future implementation must follow.

The documentation is deliberately written at two levels:

1. **Product and simulation rules** explain what the world must do and why.
2. **Technical rules** explain how those behaviours should be represented safely and maintainably.

Numbers used in examples are illustrative unless explicitly marked as approved balance values. Exact balance constants will live in versioned configuration once implementation begins.

## Authority

When documents conflict, use the authority order defined in the root `AGENTS.md`:

1. explicit current instruction from the project owner
2. approved architectural decision records under `/decisions`
3. `01-game-constitution.md`
4. approved domain documents under `/docs`
5. root `AGENTS.md`
6. existing implementation patterns

Conflicts must be documented rather than silently resolved.

## Documentation Map

| Document | Purpose |
|---|---|
| `00-project-overview.md` | Product definition, audience, experience and boundaries |
| `01-game-constitution.md` | Non-negotiable laws for the simulation and product |
| `02-world-generation-and-geography.md` | Planet, continents, regions, climate, terrain and world expansion |
| `03-plots-geology-and-resources.md` | Plot model, soils, deposits, resource discovery and extraction |
| `04-time-actions-travel-and-offline.md` | Authoritative time, timers, movement, pathfinding and offline behaviour |
| `05-characters-needs-health-and-skills.md` | Player character, health, needs, equipment, XP and death |
| `06-npcs-population-and-ai.md` | NPC population, rule-driven behaviour, AI boundaries and player replacement |
| `07-items-quality-provenance-and-inventory.md` | Item identity, quality propagation, durability, storage and traceability |
| `08-production-logistics-and-markets.md` | Recipes, factories, transport, trade, pricing and supply chains |
| `09-companies-employment-and-organizations.md` | Legal entities, employment, shares, groups and non-profit organisations |
| `10-property-construction-and-infrastructure.md` | Plot ownership, buildings, modules, rentals, roads, rail and public works |
| `11-banking-finance-insurance-and-currency.md` | Currency, accounts, loans, collateral, banks, defaults and insurance |
| `12-government-politics-law-and-public-services.md` | Villages, municipalities, countries, elections, laws, taxes and services |
| `13-crime-policing-justice-war-and-substances.md` | Crime, investigation, punishment, organised crime, war and substances |
| `14-education-research-and-technology.md` | Schools, teachers, research jobs, knowledge, patents and technology |
| `15-energy-utilities-and-environment.md` | Energy generation, grid abstraction, pollution and renewable state |
| `16-information-communication-interface-and-api.md` | Fog of information, UI, in-world devices, social features and public API |
| `17-technical-architecture.md` | Laravel architecture, modules, events, queues, consistency and scaling |
| `18-domain-model-and-data-strategy.md` | Entity map, identifiers, persistence, spatial data and audit strategy |
| `19-security-integrity-and-anti-abuse.md` | Authentication, authorisation, cheating, automation and economic integrity |
| `20-mvp-roadmap-and-release-strategy.md` | Vertical slice, staged releases and scope controls |
| `21-testing-observability-and-operations.md` | Test strategy, simulation validation, telemetry, backup and recovery |
| `22-glossary.md` | Canonical terminology |
| `rejected-ideas.md` | Rejected, simplified and deliberately deferred ideas |

## Decision Records

Major architectural and irreversible product choices are recorded under `/decisions`.

Decision records explain:

- the problem being decided
- the chosen direction
- alternatives considered
- consequences and trade-offs
- conditions that may justify revisiting the decision

Domain documents describe the current design. Decision records preserve why that design was chosen.

## Status Labels

Documents use these labels where needed:

- **Approved baseline** — accepted direction; future work should follow it.
- **Provisional** — current recommendation that may change without breaking the constitution.
- **Open decision** — not yet decided; implementation must not invent the answer.
- **Illustrative balance** — example values used to explain behaviour, not final constants.
- **Future expansion** — supported by the long-term model but outside the current release scope.
- **Rejected** — deliberately excluded unless explicitly reconsidered.

## Design Method

Each domain is expected to describe:

1. purpose
2. player-facing experience
3. authoritative rules and invariants
4. relationships to other domains
5. events and state transitions
6. information visibility
7. performance strategy
8. failure and abuse cases
9. future expansion boundaries
10. unresolved balance choices

## Implementation Gate

Documentation does not need every final recipe or numeric constant before implementation can begin. It must, however, define enough of a domain to prevent Codex or a developer from inventing foundational rules.

A domain is ready for implementation when:

- its core entities and ownership are clear
- commands and important state transitions are known
- invariants and permissions are documented
- time and retry behaviour are defined
- dependencies on other domains are explicit
- information exposure is defined
- important economic exploits have been considered
- unresolved choices are limited to configurable balance values or explicitly isolated extensions

## Current Baseline

The initial documentation package captures the design decisions established by the project owner, including:

- one persistent planet and no world reset
- no mandatory end goal
- a two-dimensional plot map
- coherent geography, geology and deposits
- deep but computationally bounded simulation
- player-created economy and society
- capped NPC competence and graceful replacement by players
- skill-specific XP, education and research
- quality propagation and provenance
- property speculation, banking, companies and public government
- travel time, physical presence and incomplete information
- automatic bookkeeping and taxes
- controlled API access, including permitted external automation
- a modular Laravel application as the expected starting architecture

This package is a complete **first authoritative baseline**, not the last word on every future feature. It is expected to evolve through explicit decisions and version control rather than undocumented implementation drift.
