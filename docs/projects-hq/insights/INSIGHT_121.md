# PROJECTS HQ INSIGHT #121

## Date
2026-11-07

## Title
A Green Day Is Not Drawdown Recovery

---

## Core Principle

A positive daily return does not establish
that a preceding loss has been recovered.

POSITIVE_RETURN
!=
RECOVERED_EQUITY.

Percentage returns compound on the
current capital base, not the original one.

Recovery requires an explicit baseline
and a reproducible calculation.

---

## Triggering Observation

On 2026-11-05, the Nasdaq Composite
fell approximately 5.52%.

On 2026-11-06, it rose approximately 1.1%.

Despite the positive Friday session,
Reuters reported that the Nasdaq
lost approximately 3.4% for the week.

Source:
Reuters, 2026-11-06.
Nasdaq rebounds but posts
fourth straight weekly decline.

This is a market illustration,
not a DB1 or EF2 backtest result.

---

## Illustrative Arithmetic

INITIAL_VALUE:
100.00000

DAY_1_RETURN:
-5.52%

DAY_1_VALUE:
94.48000

DAY_2_RETURN:
+1.10%

DAY_2_VALUE:
95.51928

DRAWDOWN_FROM_INITIAL:
-4.48072%

RECOVERY_REQUIRED_AFTER_DAY_1:
+5.84251%

RECOVERY_STILL_REQUIRED_AFTER_DAY_2:
+4.69091%

The calculation uses rounded
published daily percentages.

It does not reconstruct
exact official index closing prices.

---

## The Failure Mode

A Research Agent observes
a positive market session.

It labels the market:

RECOVERED.

A downstream Risk Agent
accepts the label.

Risk restrictions are reduced
without verifying whether
the original baseline
has actually been recovered.

A positive observation
has been incorrectly promoted
into a regime decision.

---

## Critical Distinctions

POSITIVE_SESSION
!=
FULL_RECOVERY.

PRICE_REBOUND
!=
TREND_REVERSAL.

BENCHMARK_RECOVERY
!=
STRATEGY_RECOVERY.

GROSS_RETURN
!=
NET_EQUITY_CHANGE.

RECOVERED_EQUITY
!=
AUTHORIZED_TRADING.

---

## Proposed Evidence Contract

SERIES_ID
SOURCE_ID
BASELINE_TIMESTAMP_UTC
BASELINE_EQUITY_OR_INDEX_VALUE
CURRENT_TIMESTAMP_UTC
CURRENT_EQUITY_OR_INDEX_VALUE
CASH_FLOW_ADJUSTMENTS
FEE_AND_SLIPPAGE_ADJUSTMENTS
COMPOUNDING_CONVENTION
DRAWDOWN_FROM_BASELINE
RECOVERY_REQUIRED_PERCENT
HIGH_WATER_MARK_REFERENCE
RECOVERY_STATUS
DATA_PROVENANCE_REFERENCE
AUDIT_REFERENCE

Do not substitute
price-index performance
for strategy equity.

---

## Proposed Control

CONTROL_ID:
NM-RISK-RECOVERY-001

REQUIREMENT:

A recovery label must be based
on an identified baseline
and a reproducible
compounded calculation.

A positive observation alone
must never trigger
a risk-permission upgrade.

CONTROL_STATUS:
PROPOSED

IMPLEMENTATION:
NOT_IMPLEMENTED

---

## Proposed Negative Test

TEST_ID:
NM-RISK-RECOVERY-001-NEG-01

SCENARIO:

A simulated feed supplies:

DAY_1:
-5.52%

DAY_2:
+1.10%

A model-generated label claims:

RECOVERED.

EXPECTED RESULT:

RECONSTRUCTED_LEVEL:
95.51928

ORIGINAL_BASELINE:
100.00000

DRAWDOWN_FROM_BASELINE:
-4.48072%

RECOVERY_STATUS:
NOT_RECOVERED

MODEL_LABEL_ACCEPTED:
FALSE

RISK_LIMIT_UPGRADE:
BLOCKED

BROKER_ORDER:
NOT_SUBMITTED

AUDIT_EVENT:
PRESERVED

TEST_STATUS:
NOT_EXECUTED

---

## Additional Negative Tests

1. Daily returns are added
   instead of compounded.

2. Gross returns are compared
   with a net-equity baseline.

3. Intraday recovery is treated
   as closing-price recovery.

4. Fees and slippage are ignored.

5. Deposits and withdrawals
   distort the account baseline.

6. The high-water mark is reset
   without an approved rule.

7. Unvalidated backtest equity
   is treated as production evidence.

8. Bitcoin or Nasdaq recovery
   is mistaken for strategy recovery.

9. A model-generated recovery label
   is accepted without verification.

10. A valid recovery calculation
    is promoted into trading approval.

---

## Relationship to Previous Insights

#119:
Published aggregates require
component reconciliation.

#120:
A safety benchmark is not
production authorization.

#121:
A positive return is not
recovery of the prior drawdown.

These controls are complementary.

---

## Projects HQ Principle

> A rebound must be evaluated
> against its own baseline.
>
> Arithmetic must be compounded
> and reproducible.
>
> A verified recovery is evidence,
> never a trading permit.

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
LIVE_TRADING

Existing operational governance
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

v1.0 — 2026-11-07
