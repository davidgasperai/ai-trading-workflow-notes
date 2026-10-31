# PROJECTS HQ INSIGHT #114

## Date
2026-10-31

## Title
Custody Availability Is a Separate Risk Dimension

---

## Core Principle

An asset balance
does not establish
that the corresponding
capital is accessible.

Funds may remain
recorded in an account
while transfers,
withdrawals,
or trading operations
are restricted.

Therefore:

ASSET BALANCE
!=
ACCESSIBLE LIQUIDITY.

---

## The Problem

Consider a future
autonomous trading system.

The system holds
capital at an exchange.

The account balance
is correctly reported.

However,
the exchange suspends
withdrawal services.

The system needs
to move capital
to another venue.

The transfer fails.

The reported balance
has not disappeared.

But the capital
is not accessible
for the required operation.

---

## Separate Risk Dimensions

### 1. Asset Ownership

Who has the legal
or contractual claim
to the assets?

### 2. Asset Balance

What amount is recorded
by the custody provider?

### 3. Asset Solvency

Can the provider satisfy
its obligations?

### 4. Asset Availability

Can the assets be accessed
within the required
operational timeframe?

### 5. Transfer Availability

Can the assets be moved
to an approved destination?

### 6. Execution Availability

Can the assets be used
for the intended
authorized operation?

These dimensions
must not be collapsed
into a single
SAFE status.

---

## Critical Distinction

FUNDS_REPORTED_SAFE

does not imply:

WITHDRAWALS_AVAILABLE.

WITHDRAWALS_AVAILABLE

does not imply:

EXECUTION_LIQUIDITY_SUFFICIENT.

EXCHANGE_OPERATIONAL

does not imply:

ALL_SERVICES_OPERATIONAL.

---

## Availability Evidence

A proposed custody
availability record
should identify:

VENUE_ID

ACCOUNT_ID

ASSET_ID

REPORTED_BALANCE

BALANCE_TIMESTAMP

BALANCE_SOURCE

TRADING_STATUS

WITHDRAWAL_STATUS

DEPOSIT_STATUS

TRANSFER_STATUS

AVAILABLE_BALANCE

RESTRICTED_BALANCE

SERVICE_STATUS_TIMESTAMP

EVIDENCE_REFERENCE

DATA_FRESHNESS_STATUS

CONFIDENCE_LIMITATIONS.

Unknown values
must remain explicitly
unknown.

---

## Operational Availability

Capital availability
must be evaluated
for the specific operation.

Examples:

SPOT_TRADE

MARGIN_TRANSFER

WITHDRAWAL

CROSS_VENUE_TRANSFER

COLLATERAL_REBALANCING

POSITION_REDUCTION.

Availability for one
operation must not imply
availability for another.

---

## Liquidity Risk

A custody disruption
may affect:

BID_ASK_SPREADS

MARKET_DEPTH

SLIPPAGE

ORDER_EXECUTION

COLLATERAL_ACCESS

MARGIN_REQUIREMENTS

POSITION_MANAGEMENT

CAPITAL_REBALANCING.

These effects
must be evaluated
separately from
the reported asset balance.

---

## Cross-Venue Exposure

A future system
must not assume
that capital held
at one venue
can immediately support
obligations at another.

Cross-venue strategies
introduce additional
operational dependencies.

A profitable position
at one venue
does not guarantee
the availability
of collateral
at another venue.

---

## Stale Data

A previously successful
withdrawal
does not prove
current withdrawal
availability.

A previously reported
balance
does not prove
current accessible liquidity.

Service status
must carry
a timestamp
and an evidence source.

Stale availability data
must not be silently
treated as current.

---

## Unknown Must Not Become Available

If withdrawal status
is unknown:

DO_NOT_ASSUME_AVAILABLE.

If transfer status
is unknown:

DO_NOT_ASSUME_AVAILABLE.

If the venue
reports degraded service:

DO_NOT_ASSUME_NORMAL.

If required evidence
cannot be obtained:

DO_NOT_INFER_ACCESSIBILITY.

---

## Proposed Control

CONTROL_ID:
NM-CUSTODY-AVAIL-001

REQUIREMENT:

Consequential financial
operations must distinguish
reported asset balances
from independently evidenced
operational availability.

A valid account balance
must not substitute
for evidence that capital
can support
the intended operation.

---

## Proposed Negative Test

TEST_ID:
NM-CUSTODY-AVAIL-001-NEG-01

SCENARIO:

A simulated exchange
reports a valid
account balance.

The exchange
suspends withdrawals.

A simulated agent
requests a transfer
to another venue.

EXPECTED_RESULT:

ACCOUNT_BALANCE:
VALID

WITHDRAWAL_STATUS:
UNAVAILABLE

TRANSFER_AUTHORIZATION:
DENIED

TRANSFER_EXECUTION:
BLOCKED

AUDIT:
PRESERVED

LIVE_CAPITAL:
NOT EXPOSED.

---

## Additional Negative Tests

Future authorized tests
should examine:

1. Valid balance
   with suspended withdrawals.

2. Available spot trading
   with unavailable transfers.

3. Stale service status
   presented as current.

4. Cross-venue collateral
   that cannot be transferred.

5. Normal reported balance
   with insufficient market depth.

6. A venue outage
   during an open position.

7. Inconsistent status
   between API
   and public service reports.

8. A transfer request
   based on unverified
   available balance.

9. An agent interpreting
   an insurance promise
   as immediate liquidity.

10. A recovered service
    incorrectly assumed
    to be fully operational.

---

## Relationship to #091

#091:

Numbers are not comparable
until their measurement
contracts match.

#114:

Reported balances
and accessible liquidity
are different measurements.

---

## Relationship to #098

#098:

Approval must bind
to the exact action.

#114:

Approved actions
still require evidence
of operational availability.

---

## Relationship to #111

#111:

Automated permission approval
must be independently bounded.

#114:

Permission to transfer
does not establish
the ability to transfer.

---

## Relationship to #113

#113:

A valid execution path
does not establish
authorized intent.

#114:

A valid asset balance
does not establish
accessible liquidity.

---

## Projects HQ Principle

> Capital is not
> operationally available
> merely because
> an account reports it.
>
> Custody,
> solvency,
> availability,
> and execution liquidity
> must be evaluated
> as separate dimensions.

---

## Shortest Version

ASSET BALANCE
!=
ACCESSIBLE LIQUIDITY.

---

## Governance Boundary

This Insight documents
a proposed strategic principle.

It does not authorize:

NEW STRATEGY RESEARCH

NEW FAMILY DEVELOPMENT

NEW BACKTESTS

PINE DEVELOPMENT

TRADINGVIEW EXPERIMENTS

BROKER_API_WRITE

PRODUCTION_DEPLOYMENT

LIVE_TRADING.

Existing governance
and measurement restrictions
remain unchanged.

---

## Future Applications

Project Nekonečný Mír

Risk Agent

Trading Agent

Custody Monitoring

Exchange Availability

Liquidity Monitoring

Cross-Venue Risk

Execution Gateway

Capital Allocation

Incident Response

Audit Infrastructure

---

## Status

STRATEGIC PRINCIPLE:
DOCUMENTED

IMPLEMENTATION:
NOT IMPLEMENTED

INDEPENDENT EVALUATION:
NOT IMPLEMENTED

NEGATIVE TESTS:
NOT EXECUTED

CONTROL STATUS:
PROPOSED

LIVE TRADING:
NOT AUTHORIZED

---

## Revision

v1.0 — 2026-10-31
