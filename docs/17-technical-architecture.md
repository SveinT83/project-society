# Technical Architecture

**Status:** Provisional architecture baseline; implementation remains gated

## Direction

Begin as a modular monolith:

- Laravel
- PostgreSQL with spatial capabilities when justified
- Redis for cache, locks and queues
- Laravel queue workers and scheduler
- Vue, Inertia and Tailwind CSS
- WebSockets only for useful live updates

This provides transactional consistency and simple deployment while retaining explicit domain boundaries. Do not create microservices until measured scaling or organisational needs justify them.

## Layers

Each domain module should contain:

- **Domain:** entities, value objects, invariants, domain events and policies
- **Application:** commands, queries, orchestration and authorisation
- **Infrastructure:** persistence, queues and external adapters
- **Interface:** HTTP/API controllers, console commands and event delivery

Controllers must not contain economic formulas or mutate unrelated models.

## Command lifecycle

1. authenticate actor
2. authorise role and information channel
3. validate command and current world state
4. acquire narrow locks or use optimistic concurrency
5. reserve/consume inputs in a transaction
6. persist state and outbox events
7. dispatch asynchronous side effects after commit
8. return a filtered representation

## Events and consistency

Use domain events to describe committed facts. Cross-domain side effects use an outbox and idempotent handlers. Events are not a substitute for transactions inside a single invariant boundary.

Money, item conservation, ownership and action completion require strong consistency. Analytics, notifications, map caches and projections may be eventually consistent.

## Timers

Do not enqueue one fragile long-delay process as the only source of truth. Persist due work in the database. Workers claim due rows safely, complete idempotently and may be retried.

## Spatial and simulation workload

- partition and query by region
- maintain bounded neighbour lookups
- batch low-detail NPC and renewable updates
- activate detailed state only around material interaction
- cache derived map tiles and routes
- benchmark pathfinding and plot scale before committing world dimensions

## Formula engine

Formulas use versioned configuration or typed strategy classes. Every result records formula version and material inputs when it affects money, quality, crime, discovery or competitive outcomes.

Controlled randomness derives from server entropy and is auditable without being predictable to clients.

## Deployment baseline

Separate web, queue and scheduled workloads operationally even if they share one codebase. Use zero-downtime-compatible migrations, backups and a staging environment before persistent-world launch.

## Architecture gates

Before scaffolding, approve ADRs for the modular monolith, time/action completion, money ledger, spatial storage, IDs and outbox approach.

