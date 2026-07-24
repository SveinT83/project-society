# Security, Integrity and Anti-Abuse

**Status:** Approved principles; controls evolve before launch

## Trust boundary

The client, browser, external API and AI automation are untrusted. The server validates identity, authority, visibility, location, time, cost and state.

## Required controls

- secure authentication and session revocation
- scoped entity roles and API tokens
- server-side rate and concurrency limits
- CSRF and standard web protections
- encryption in transit and protected secrets
- idempotency keys for economic mutations
- transaction isolation or explicit locks for scarce state
- audit trails for administration and high-value transfers

## Economic integrity

Threats include duplicate completion, race-based double spending, circular XP farming, wash trading, related-account manipulation, price-feed leakage, bot swarms and privileged information abuse.

Controls should target harmful advantage rather than prohibit the explicitly approved public API. Automation is visible, rate-limited and bound to one character.

## Information security

Every query applies a knowledge/visibility policy. Search, exports, notifications and WebSockets must not leak records hidden in the primary UI.

## Administrative power

Game administrators use separate, auditable capabilities. Corrections create compensating transactions. Direct database edits are emergency-only and documented.

## Social safety

Provide reporting, blocking, moderation and platform-wide conduct enforcement. In-world laws cannot legalise real-world harassment, threats, exploitation or prohibited content.

## Recovery

Maintain tested backups, point-in-time recovery, incident runbooks and the ability to pause high-risk economic commands without stopping read-only access.

