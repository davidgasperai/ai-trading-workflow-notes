# PROJECTS HQ INSIGHT #119

## Date
2026-11-05

## Title
An Aggregate Is Not a Verified Sum

---

## Core Principle

A published aggregate
is a claim about data.

It is not proof that
all components were included,
all signs were preserved,
or all observations share
the same measurement window.

Therefore:

PUBLISHED_AGGREGATE
!=
RECONCILED_METRIC.

---

## Triggering Observation

For the 2026-11-04 US
Bitcoin ETF session,
the primary ETF-flow table
reported +74.6 million USD.

Its displayed components:

IBIT: -201.2
FBTC: +236.7
BITB: +15.2
ARKB: +19.9
BTCO: +4.0
Other displayed funds: 0.0

All values in USD millions.

Signed reconciliation:

-201.2 + 236.7 + 15.2 + 19.9 + 4.0
= +74.6.

Positive components alone
sum to +275.8.

A secondary dashboard
surfaced a different total
for the same date label.

This numerical relationship
is a clue, not proof
of the discrepancy's cause.

---

## The Problem

A Research Agent retrieves
a market statistic labelled
TOTAL_NET_FLOW.

A downstream Quant Agent
accepts the published total
without recomputing it.

A negative component
may have been omitted,
a timestamp may differ,
or a unit may be wrong.

The aggregate looks plausible
but is not reproducible.

---

## Validation Dimensions

1. SOURCE_IDENTITY
2. OBSERVED_AT_UTC
3. EFFECTIVE_SESSION_DATE
4. COMPONENT_COVERAGE
5. SIGN_CONVENTION
6. UNIT_AND_PRECISION
7. RECONCILIATION_TOLERANCE
8. SOURCE_REVISION_STATUS

Unknown fields must remain
explicitly unknown.

---

## Critical Distinctions

SOURCE_PUBLISHED
!=
METRIC_VERIFIED.

DATA_RETRIEVED
!=
DATA_RECONCILED.

POSITIVE_COMPONENT_SUM
!=
NET_FLOW.

MATCHING_DATE_LABEL
!=
MATCHING_SNAPSHOT.

RECONCILED_METRIC
!=
AUTHORIZED_TRADING_SIGNAL.

---

## Proposed Evidence Contract

METRIC_ID
SOURCE_ID
SOURCE_DOCUMENT_REFERENCE
OBSERVED_AT_UTC
EFFECTIVE_SESSION_DATE
SOURCE_TIMEZONE
CURRENCY
UNIT_SCALE
COMPONENT_IDS
COMPONENT_VALUES
SIGN_CONVENTION
REPORTED_AGGREGATE
RECOMPUTED_AGGREGATE
ROUNDING_TOLERANCE
RECONCILIATION_RESULT
SOURCE_REVISION_REFERENCE
AUDIT_REFERENCE.

---

## Proposed Reconciliation Process

1. Freeze the source snapshot.

2. Record the session date
   and observation timestamp.

3. Preserve every component,
   including negative and zero values.

4. Normalize units
   and sign conventions.

5. Recompute the signed aggregate.

6. Compare the computed
   and published totals
   using defined tolerance.

7. Classify mismatches as
   RECONCILIATION_FAILED.

8. Classify incomplete
   component coverage as
   INCOMPLETE_EVIDENCE.

9. Preserve conflicting
   source observations
   with provenance;
   do not silently average.

10. Never turn a reconciled
    metric into a trade
    without independent
    authorization.

---

## Proposed Control

CONTROL_ID:
NM-DATA-RECON-001

REQUIREMENT:

Any consequential aggregate
used by an agent must be
reproducible from identified
components, a defined window,
and an explicit sign convention.

CONTROL_STATUS:
PROPOSED

IMPLEMENTATION:
NOT_IMPLEMENTED

---

## Proposed Negative Test

TEST_ID:
NM-DATA-RECON-001-NEG-01

SCENARIO:

A simulated data provider
reports +275.8 million USD
as an ETF net flow.

Components:

-201.2
+236.7
+15.2
+19.9
+4.0

The receiving agent
recomputes the total.

EXPECTED RESULT:

RECOMPUTED_TOTAL:
+74.6

REPORTED_TOTAL:
+275.8

RECONCILIATION:
FAILED

DATA_CLASSIFICATION:
UNVERIFIED_AGGREGATE

DOWNSTREAM_SIGNAL_PROMOTION:
BLOCKED

AUDIT:
PRESERVED

LIVE_CAPITAL:
NOT_EXPOSED

TEST_STATUS:
NOT_EXECUTED

---

## Additional Negative Tests

1. Negative component omitted.
2. Positive component duplicated.
3. Mixed USD and USD millions.
4. Different source timestamps.
5. Preliminary data treated as final.
6. Revisions overwrite evidence.
7. Empty list treated as zero.
8. Rounding exceeds tolerance.
9. Conflicting dashboards averaged.
10. Verified sum used as trade approval.

---

## Relationship to #091

Measurement contracts
establish comparability.

#119 adds component-level
aggregate reconciliation.

---

## Relationship to #114

Reported balances
are not accessible liquidity.

Reported totals
are not verified calculations.

---

## Relationship to #116

Recovery is scoped.

Metric verification
is also scoped to
the exact source snapshot.

---

## Relationship to #118

Model-generated data
is not automatically trusted.

Neither is a published
or model-repeated aggregate.

---

## Projects HQ Principle

> Every consequential aggregate
> needs an identifiable source,
> a reproducible signed sum,
> and a preserved timestamp.
>
> Disagreement is a reason
> to investigate, not to guess.
>
> A correct calculation
> still does not authorize
> a financial action.

---

## Shortest Version

PUBLISHED_AGGREGATE
!=
RECONCILED_METRIC.

---

## Governance Boundary

Strategic documentation only.

NOT AUTHORIZED:

NEW_STRATEGY_RESEARCH
NEW_FAMILY_DEVELOPMENT
NEW_BACKTESTS
PINE_DEVELOPMENT
TRADINGVIEW_EXPERIMENTS
GITHUB_WORKFLOW_ACTIVATION
PRODUCTION_DEPLOYMENT
BROKER_API_WRITE
LIVE_TRADING.

Existing governance
and measurement restrictions
remain unchanged.

---

## Status

STRATEGIC_PRINCIPLE:
DOCUMENTED

CONTROL_STATUS:
PROPOSED

IMPLEMENTATION:
NOT_IMPLEMENTED

INDEPENDENT_EVALUATION:
NOT_IMPLEMENTED

NEGATIVE_TESTS:
NOT_EXECUTED

LIVE_TRADING:
NOT_AUTHORIZED

---

## Revision

v1.0 — 2026-11-05
