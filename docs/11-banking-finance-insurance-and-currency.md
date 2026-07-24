# Banking, Finance, Insurance and Currency

**Status:** Approved baseline

## Currency

The world launches with one fictional system currency. Its name is an open decision. Money uses fixed-precision integer minor units; floating point is forbidden.

Players cannot purchase currency for real money.

## Accounts and settlement

Characters and legal entities hold accounts. Every transfer creates balanced ledger entries, an idempotency key, purpose and counterparty. User-facing accounting remains simple.

## Banks

System, municipal and player-owned private banks may coexist. Banks accept permitted deposits, assess credit, originate loans, manage liquidity and may fail.

Bank decisions must use visible game factors such as income, collateral, debt, history, business plan and regulation. AI may assist a bounded assessment but cannot secretly invent approval criteria.

## Loans

A loan records principal, rate, schedule, borrower, lender, collateral, arrears and governing law. Interest and payments are automatic. Default can lead to restructuring, repossession or bankruptcy through documented procedures.

Banks must not lend the same reserved capital repeatedly. Capital and liquidity constraints are part of the simulation, with initial values set by balance testing.

## System monetary authority

A bootstrap authority may issue the initial currency and provide minimum settlement. Advanced central-bank policy, national currencies and private currencies are future expansions; architecture should avoid assuming they can never exist.

## Insurance

Insurance is approved but staged. Policies define covered events, exclusions, premium, limits and beneficiary. Claims are triggered by authoritative events and may be investigated for fraud.

Initial insurance should focus on one or two material risks, not attempt to model every real-world product.

## Failure

Bankruptcy preserves history and follows an ordered claims process. A failed company or bank does not silently delete debt, collateral or depositor claims.

