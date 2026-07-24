# Domain Model and Data Strategy

**Status:** Provisional baseline

## Domain map

| Domain | Owns |
|---|---|
| World | planet, region, plot, terrain, accessibility |
| Resources | deposits, soil state, renewable state, surveys |
| Characters | identity, location, needs, health, skills |
| Actions | timed personal actions and completion |
| Items | item/batch, inventory, condition, provenance |
| Production | recipes, facilities, jobs, production runs |
| Commerce | orders, contracts, market transactions |
| Entities | companies, organizations, roles, governance |
| Property | title, lease, building, construction |
| Finance | currency, accounts, ledger, loans, insurance |
| Government | jurisdictions, office, election, law, tax, budget |
| Justice | crime, evidence, case, sentence |
| Knowledge | education, research, technology rights |
| Infrastructure | transport, energy and service networks |
| Information | observations, registers, visibility and communication |

Boundaries are starting hypotheses, not permission for circular dependencies.

## Identity

Use globally unique, opaque identifiers for external references. Human-readable names are mutable and never primary keys.

## Data categories

- **Authoritative current state:** balances, ownership, location, condition.
- **Immutable business history:** ledger entries, transfers, production and law changes.
- **Observations:** what an actor knew and when.
- **Derived projections:** map views, statistics, search indexes.
- **Configuration:** versioned recipes, formulas, skill definitions and balance constants.

Derived data may be rebuilt. Authoritative state and history require backup and migration discipline.

## Spatial storage

Represent grid coordinates explicitly and enforce uniqueness per planet. Deposits need geometry capable of crossing plots and depths. PostgreSQL/PostGIS is the leading option, subject to a benchmark against simpler grid-native representations.

## Ledgers and conservation

Money uses double-entry ledger principles. Item and resource movements use immutable transfer/production records plus current balances. Never correct an economic mistake by deleting history; post a compensating event.

## Audit

Important mutations record actor, represented entity, command, source channel, timestamp, correlation ID and relevant before/after or event data.

## Retention

Long-lived provenance may be compacted into immutable lineage summaries only when detailed records remain recoverable or are no longer required by gameplay. Chat and operational logs have separate retention and privacy rules.

## Migrations

Persistent-world migrations must be forward-compatible, resumable and tested against production-scale copies. Generator, formula and configuration versions remain associated with existing outcomes.

