# Information, Communication, Interface and API

**Status:** Approved baseline

## Information model

Authoritative truth, recorded observation and player-visible knowledge are separate.

Knowledge may come from:

- current physical presence
- recent personal observation
- surveys and sensors
- ownership and employees
- a friend who opts to share location
- public or private registers
- contracts and organization roles
- purchased reports

Observations have source, subject, captured time, precision, expiry/staleness and access rights.

## Interface

The main interface combines a two-dimensional plot map with contextual panels. The map shows only permitted and suitably fresh data.

A plot panel may reveal public ownership and infrastructure remotely while withholding current occupants, stock, exact deposits and live activity.

## In-world technology

Without a computer or suitable mobile device, many services require physical attendance. Devices and connectivity enable job search, banking, registers, markets, company administration, messages and research access.

The game provides these services; players do not write arbitrary executable software inside the world.

## Communication

Support private messages, friends, entity chat and organization spaces in stages. Location sharing is opt-in. Moderation and blocking are platform capabilities and cannot be overridden by local government.

## Public API

The API may support statistics, dashboards, alerts, lawful information tools and controlled automation, including AI-assisted play.

Requirements:

- scoped tokens and explicit actor identity
- identical command validation to the official client
- rate limits and action concurrency limits
- no hidden information leakage
- idempotency for mutations
- auditable automation activity
- revocation and emergency disablement

Automation may choose actions but cannot bypass time, travel, costs or permissions. An API response must be filtered through the same knowledge policy as the UI.

