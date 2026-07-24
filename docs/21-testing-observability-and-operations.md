# Testing, Observability and Operations

**Status:** Provisional baseline

## Test layers

- **Unit/property tests:** formulas, value objects, quality bounds and conservation.
- **Domain tests:** commands, permissions, state transitions and failure cases.
- **Integration tests:** database constraints, queues, outbox, Redis locks and spatial queries.
- **End-to-end tests:** critical player journeys in UI and API.
- **Simulation tests:** accelerated economies with many deterministic agents.
- **Load tests:** due actions, markets, map reads, pathfinding and regional updates.

## Critical invariants

Test repeatedly that:

- money ledger balances
- goods and deposit quantities are conserved
- action completion is exactly once under retries
- XP cannot be awarded twice
- unavailable information is not exposed
- ownership cannot have impossible overlapping claims
- NPC caps and replacement rules hold
- formulas remain within documented bounds

Use property-based and concurrency tests for these, not only happy-path examples.

## Determinism

Simulation scenarios use fixed seeds, formula versions and clock control. Production randomness remains secure and auditable.

## Observability

Track:

- command and queue failure rates
- overdue actions
- idempotency conflicts
- money supply and sinks/sources
- price, wage and inventory distributions
- NPC/player labour share
- regional simulation duration
- pathfinding latency and cache hit rate
- suspicious trading and automation patterns

Metrics must not become a player information leak.

## Operations

Run web, workers and schedulers with health checks. Use dead-letter handling, replay-safe jobs, backup verification, point-in-time recovery and staged migrations.

Persistent-world launch requires a rehearsed response for duplicated economic events, corrupted projections, compromised accounts and region-worker backlog.

