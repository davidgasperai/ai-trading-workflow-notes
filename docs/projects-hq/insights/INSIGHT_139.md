
# PROJECTS HQ INSIGHT #139

Date: 2026-11-25
Title: Two Agents Can Agree and Still Be Wrong
Revision: v1.0
Status: STRATEGIC_DOCUMENTATION_ONLY

## Executive Summary

Independent verification is a fundamental principle
of reliable AI-assisted trading research.

However, agreement between two AI agents does not
automatically establish correctness.

Codex and Claude Code may independently produce
identical outputs while relying on the same incorrect
specification, invalid assumptions, or contaminated
market data.

Agreement can demonstrate consistency.

It cannot, by itself, demonstrate validity.

Strategy Radar #007 introduces the Donchian Channel
Breakout as an educational example of a relatively
simple and deterministic trading concept.

Its apparent simplicity makes it useful for explaining
the distinction between implementation correctness,
specification correctness, and economic validity.

This Insight proposes a common-mode failure awareness
principle for future multi-agent verification.

No implementation, testing, repository modification,
API access, or trading activity is authorized.

## Evidence Availability

Fresh external news sources could not be verified
for the November 25, 2026 edition.

No current market prices, product announcements,
security incidents, or benchmark results are asserted
in this document.

The technical discussion is conceptual and educational.

Reference resource:

TradingView — Donchian Channels

https://www.tradingview.com/support/solutions/43000502253-donchian-channels-dc/

REFERENCE_STATUS:
NOT_REVALIDATED_IN_THIS_EDITION

No empirical claim of trading profitability is derived
from this reference.

## Core Principle

AGENT_AGREEMENT != CORRECTNESS

IMPLEMENTATION_AGREEMENT != SPECIFICATION_VALIDITY

REPRODUCIBILITY != ECONOMIC_VALIDITY

TWO_AGENTS != TWO_INDEPENDENT_EVIDENCE_SOURCES

SHARED_ASSUMPTION != VERIFIED_ASSUMPTION

DETERMINISTIC_OUTPUT != VALID_OUTPUT

CORRECT_SIGNAL != VERIFIED_TRADING_EDGE

VERIFIED_CALCULATION != EXECUTION_AUTHORIZATION

Multiple agents may reproduce the same mistake.

Independent verification must therefore examine
the assumptions, specification, data, calculations,
and interpretation of results.

## Strategy Radar #007

CONCEPT: Donchian Channel Breakout

CATEGORY: Trend Following / Breakout

STATUS: EDUCATIONAL_ONLY

### Conceptual Definition

A Donchian Channel represents the highest high
and lowest low over a defined historical window.

For a decision at time t:

upper_channel_t =
    max(high[t-N], ..., high[t-1])

lower_channel_t =
    min(low[t-N], ..., low[t-1])

Illustrative upward breakout condition:

close[t] > upper_channel_t

Illustrative downward breakout condition:

close[t] < lower_channel_t

The current observation is excluded from the
reference channel.

These expressions are educational definitions.

They do not constitute an approved strategy.

No lookback period, timeframe, entry mechanism,
exit mechanism, position size, or execution
model has been authorized.

### Hypothetical Source of Edge

A breakout beyond a historical price range
may sometimes be followed by continued
directional movement.

The underlying hypothesis is that persistent
market trends may create opportunities for
systematic breakout strategies.

This hypothesis does not establish that a
specific Donchian Channel configuration
has positive expected returns in BTC markets.

### Required Data

Potential future research would require:

- Historical OHLCV observations
- Exchange and instrument identifiers
- Consistent candle timestamps
- Data availability timestamps
- Missing-data policies
- Historical transaction fees
- Spread assumptions
- Slippage assumptions
- Execution feasibility constraints

These are conceptual requirements only.

No data acquisition or experiment is authorized.

### Potentially Favorable Conditions

- Persistent directional trends
- Sustained movement beyond historical ranges
- Sufficient liquidity
- Execution costs small relative to price movement

### Potentially Unfavorable Conditions

- Sideways markets
- Frequent false breakouts
- Rapid trend reversals
- Unstable liquidity
- High transaction costs
- Excessive parameter sensitivity

These conditions are hypotheses, not measured
project findings.

## Educational Visualization

The accompanying educational visualization
uses a synthetic sequence of closing prices.

Its channel boundaries are calculated from
previous synthetic closing observations.

This differs from a standard OHLC-based
Donchian Channel, which uses historical
highs and lows.

The visualization demonstrates how changing
a historical lookback window can affect
breakout conditions.

It does not simulate executed trades.

It does not calculate strategy profitability.

It does not constitute a backtest.

## Common-Mode Failure

Two implementations may agree because both
agents rely on:

- The same ambiguous specification
- The same incorrect indexing convention
- The same contaminated data source
- The same future-data leakage
- The same execution assumptions
- The same incorrect fee model
- The same flawed measurement pipeline
- The same interpretation of a benchmark

Agreement under shared invalid assumptions
does not provide independent validation.

Verification should therefore distinguish
implementation diversity from evidence
independence.

## Proposed Control

CONTROL_ID: NM-COMMON-MODE-FAILURE-001

CONTROL_NAME:
Independent Assumption and Implementation Review

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

### Proposed Requirements

1. Define the specification before implementation.

2. Identify all shared assumptions.

3. Document the provenance of market observations.

4. Establish explicit temporal integrity rules.

5. Separate specification review from code review.

6. Where appropriate, compare independently
   produced implementations.

7. Prevent one implementation from becoming
   the sole reference for the other.

8. Include manually derived reference examples.

9. Include deliberately invalid input conditions.

10. Compare intermediate calculations,
    not only final outputs.

11. Investigate discrepancies before accepting
    implementation agreement.

12. Independently review transaction-cost assumptions.

13. Distinguish mathematical correctness from
    economic performance.

14. Prevent agent agreement from granting
    execution permissions.

15. Preserve all existing governance restrictions.

These requirements are proposed controls.

They are not implemented or operational.

## Proposed Evidence Fields

- verification_id
- specification_version
- specification_hash
- data_source
- data_version
- observation_timestamp
- feature_availability_timestamp
- implementation_a_version
- implementation_b_version
- shared_assumptions
- independently_reviewed_assumptions
- reference_fixture_id
- intermediate_calculation_comparison
- output_comparison
- discrepancy_status
- reviewer_identity
- unresolved_uncertainty
- economic_validation_status
- authorization_status

These fields are illustrative.

They are not an approved canonical registry.

## Proposed Negative Tests

All tests below are PROPOSED and NOT EXECUTED.

### NEG-01: Current candle contamination

Input:
The current candle is included in its own
historical breakout reference window.

Expected:
REFERENCE_WINDOW_INVALID.

### NEG-02: Shared off-by-one error

Input:
Both implementations use the same incorrect
historical indexing convention.

Expected:
AGREEMENT_WITH_INVALID_SPECIFICATION.

### NEG-03: Insufficient historical observations

Input:
Fewer than N valid historical candles
are available.

Expected:
DATA_INSUFFICIENT.

### NEG-04: Future-data leakage

Input:
A channel boundary includes observations
unavailable at decision time.

Expected:
TEMPORAL_INTEGRITY_FAILURE.

### NEG-05: Identical contaminated inputs

Input:
Both agents use the same invalid market
data snapshot and produce matching outputs.

Expected:
DATA_VALIDITY_NOT_ESTABLISHED.

### NEG-06: Execution timing ambiguity

Input:
A signal depends on a candle's closing price
and assumes execution at that same price
without a justified execution model.

Expected:
EXECUTION_ASSUMPTION_UNRESOLVED.

### NEG-07: Missing transaction costs

Input:
A candidate breakout strategy appears
profitable before fees and slippage.

Expected:
ECONOMIC_VIABILITY_NOT_ESTABLISHED.

### NEG-08: Parameter overfitting

Input:
The lookback period is selected solely
to maximize historical performance.

Expected:
OVERFITTING_REVIEW_REQUIRED.

### NEG-09: Non-independent verification

Input:
The second agent copies the first agent's
implementation and reproduces its results.

Expected:
IMPLEMENTATION_INDEPENDENCE_NOT_ESTABLISHED.

### NEG-10: Matching results from an invalid specification

Input:
Both implementations correctly follow
a specification containing a logical error.

Expected:
SPECIFICATION_VALIDITY_NOT_ESTABLISHED.

### NEG-11: Synthetic visualization misrepresented

Input:
An educational synthetic price sequence
is presented as historical BTC performance.

Expected:
EVIDENCE_CLASSIFICATION_INVALID.

### NEG-12: Agreement treated as trading permission

Input:
Two agents agree on a breakout signal
and request execution access.

Expected:
BROKER_WRITE_DENIED.

### NEG-13: Unvalidated measurement pipeline

Input:
Both agents report favorable economic results
through the current unvalidated pipeline.

Expected:
MEASUREMENT_NOT_VERIFIED.

### NEG-14: Missing fresh external evidence

Input:
An agent presents an unverified market
report as a confirmed current event.

Expected:
EXTERNAL_EVIDENCE_NOT_VERIFIED.

## Proposed Future Evaluation Questions

Any separately authorized evaluation would
need to establish:

1. Is the specification mathematically coherent?

2. Are reference windows correctly indexed?

3. Are all observations available at decision time?

4. Are the implementations genuinely independent?

5. Do manually derived fixtures confirm correctness?

6. Are intermediate calculations reproducible?

7. Are shared assumptions independently reviewed?

8. Are transaction costs realistically represented?

9. Does the strategy remain robust across
   different market regimes?

10. Are results stable under reasonable
    parameter variation?

11. Does any economic advantage persist
    out of sample?

12. Can an independent reviewer reproduce
    the complete evidence chain?

No such evaluation has been authorized or performed.

## Proposed Future AI Roles

ChatGPT:
Research framing, educational documentation,
assumption identification, and specification review.

Codex:
Potential implementation of a separately
approved technical specification.

Claude Code:
Potential independent implementation,
assumption review, and adversarial verification.

Human Reviewer:
Independent evidence assessment and explicit
authorization decisions.

These roles are conceptual only.

No multi-agent execution workflow is activated.

## Governance Boundary

DB1: PARKED

EF2: PARKED

MEASUREMENT_PIPELINE: UNVALIDATED

RC2_RATIFICATION: NOT_RATIFIED

STRATEGY_RADAR: EDUCATIONAL_ONLY

NEW_STRATEGY_APPROVAL: NOT_AUTHORIZED

NEW_BACKTESTS: NOT_AUTHORIZED

PARAMETER_OPTIMIZATION: NOT_AUTHORIZED

STRATEGY_IMPLEMENTATION: NOT_AUTHORIZED

REPOSITORY_MODIFICATIONS: NOT_AUTHORIZED

AGENT_DEPLOYMENT: NOT_AUTHORIZED

NEW_API_ACCESS: NOT_AUTHORIZED

BROKER_API_WRITE: NOT_AUTHORIZED

LIVE_TRADING: NOT_AUTHORIZED

This document does not authorize:

- Strategy development
- Indicator implementation
- Pine Script development
- Market-data acquisition experiments
- Backtesting
- Parameter optimization
- Repository modifications
- Automated agent workflows
- Broker or exchange API access
- Financial transactions

Any operational activity requires a separate
explicit governance decision.

## Verification Status

INSIGHT_NUMBER: 139

PREVIOUS_PREPARED_INSIGHT_NUMBER: 138

PREVIOUS_GITHUB_PUBLICATION:
NOT_INDEPENDENTLY_VERIFIED

FRESH_EXTERNAL_NEWS:
NOT_VERIFIED_IN_THIS_EDITION

STRATEGIC_PRINCIPLE: DOCUMENTED

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

NEGATIVE_TESTS: NOT_EXECUTED

STRATEGY_RADAR_007: EDUCATIONAL_ONLY

DONCHIAN_BREAKOUT_EDGE: NOT_ESTABLISHED

SYNTHETIC_VISUALIZATION: EDUCATIONAL_ONLY

IMPLEMENTATION_INDEPENDENCE: NOT_EVALUATED

COMMON_MODE_FAILURE_CONTROL: NOT_IMPLEMENTED

BACKTESTS: NOT_EXECUTED

MEASUREMENT_PIPELINE: UNVALIDATED

INDEPENDENT_PROJECT_EVALUATION: NOT_PERFORMED

GITHUB_PUBLICATION: NOT_VERIFIED

## Relationship to Earlier Insights

This principle complements:

- INSIGHT #099:
  A Strategy Must Not Choose Its Own Exam

- INSIGHT #100:
  A Rule Is Not a Control Until It Is Enforced

- INSIGHT #133:
  A Strategy Hypothesis Is Not a Trading Edge

- INSIGHT #135:
  A Plausible Explanation Must Survive
  an Attempt to Disprove It

- INSIGHT #136:
  A Benchmark Must Measure the Decision
  That Matters

- INSIGHT #137:
  A System Must Be Allowed to Say:
  Conditions Are Unknown

- INSIGHT #138:
  A Trading Signal Must Never Determine
  Its Own Risk Budget

Insight #139 extends these principles to
common-mode failures and the limitations
of multi-agent agreement.

## Closing Principle

Two agents can agree.

Two implementations can reproduce
the same result.

Two reviewers can accept
the same incorrect assumption.

Agreement is useful evidence.

It is not sufficient evidence.

Independence must be demonstrated.

Assumptions must be challenged.

Economic validity must be established separately.

Execution must remain independently authorized.

VIDIME. OVERUJEME. STAVIME.
