
# PROJECTS HQ INSIGHT #128

Date: 2026-11-14
Title: A Market Observation Must Carry Its Time Boundary
Revision: v1.0
Status: STRATEGIC_DOCUMENTATION_ONLY

## Observation

On 13 November 2026, financial reporting described Bitcoin trading below USD 70,000, elevated crypto ETF outflows, leveraged-position liquidations, and persistent US inflation pressure.

These observations were reported at different times, with different data cutoffs and different measurement methods.

A Friday market price presented in a Saturday report is historical evidence, not a live Saturday quote.

Likewise, a five-day ETF flow total cannot be treated as a single-day flow, and a liquidation estimate cannot be assumed to be independently verified across every exchange.

The operational risk is not merely stale data. It is the silent promotion of a time-bounded observation into a current decision input.

### Sources

- https://www.wsj.com/finance/currencies/bitcoin-holds-below-70-000-as-risk-off-mood-pressures-crypto-d61d684d
- https://www.barrons.com/articles/bitcoin-price-coinbase-stock-robinhood-strategy-55be11f9
- https://apnews.com/article/5f427443fd31a4aa2bd2a1b6cebfe549

## Core Principle

OBSERVED_VALUE != CURRENT_VALUE

PUBLICATION_TIME != OBSERVATION_TIME

RETRIEVAL_TIME != MARKET_DATA_TIME

RECENT_SOURCE != FRESH_MEASUREMENT

TIME_BOUNDARY_MISSING != SAFE_TO_ASSUME_CURRENT

A factual observation is only operationally meaningful when its measurement period, source, and freshness requirements are known.

## Proposed Control

CONTROL_ID: NM-TEMPORAL-EVIDENCE-001

CONTROL_NAME: Temporal Evidence and Freshness Gate

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

### Requirements

1. Record the original source and source identifier for each consequential observation.

2. Preserve the observation timestamp or explicitly bounded observation period.

3. Record the publication timestamp separately from the observation timestamp.

4. Record the retrieval timestamp without treating retrieval as proof of data freshness.

5. Preserve the relevant timezone and normalize timestamps only through an explicit conversion rule.

6. Require a declared freshness threshold appropriate to the intended use.

7. Mark missing, conflicting, or ambiguous timestamps as TEMPORAL_UNCERTAINTY.

8. Prevent historical market values from being silently promoted into live execution inputs.

9. Prevent an AI-generated summary from extending a source's temporal validity.

10. Require renewed observation and independent authorization before any consequential action.

## Proposed Evidence Fields

- source_id
- source_url
- source_type
- observation_timestamp
- observation_period_start
- observation_period_end
- publication_timestamp
- retrieval_timestamp
- timezone
- measurement_definition
- freshness_requirement
- temporal_validation_status
- independent_verification_status
- authorization_status

These fields are a proposed evidence schema, not an implemented canonical ledger.

## Negative Tests — Proposed, Not Executed

### NEG-01: Historical price presented as live

Input: Friday BTC closing observation reused on Saturday.

Expected: HISTORICAL_ONLY.

### NEG-02: Retrieval timestamp replaces observation timestamp

Input: An old report is retrieved today and labeled as today's market data.

Expected: TEMPORAL_VALIDATION_FAILED.

### NEG-03: Publication date mistaken for measurement date

Input: A Saturday article describes Friday's trading session.

Expected: OBSERVATION_DATE_REQUIRED.

### NEG-04: Missing timezone

Input: A price record has a timestamp without a timezone or declared convention.

Expected: TEMPORAL_UNCERTAINTY.

### NEG-05: Aggregated ETF period mislabeled

Input: Five-day ETF outflows are reported as a one-day outflow.

Expected: MEASUREMENT_PERIOD_MISMATCH.

### NEG-06: Conflicting provider timestamps

Input: Two data providers report the same event with incompatible timestamps.

Expected: INDEPENDENT_REVIEW_REQUIRED.

### NEG-07: Stale source summarized by an agent

Input: An AI-generated summary presents a historical quote in present tense.

Expected: CURRENTNESS_CLAIM_BLOCKED.

### NEG-08: Cached response after service recovery

Input: An API returns cached market data after an outage.

Expected: FRESHNESS_REVALIDATION_REQUIRED.

### NEG-09: Fresh observation without authorization

Input: A current market value is verified, but no execution approval exists.

Expected: EXECUTION_DENIED.

### NEG-10: Timestamp check bypassed by fallback

Input: A fallback model supplies a plausible value without its measurement time.

Expected: TEMPORAL_GATE_FAILED.

## Governance Boundary

This Insight documents a proposed principle only.

It does not authorize new trading research, strategy development, implementation, deployment, or execution.

DB1: PARKED

EF2: PARKED

MEASUREMENT_PIPELINE: UNVALIDATED

RC2_RATIFICATION: NOT_RATIFIED

REGISTRY_EXPOSURE_LEDGER_V0.3: DRAFT_NOT_CANONICAL

NEW_STRATEGY_RESEARCH: NOT_AUTHORIZED

NEW_BACKTESTS: NOT_AUTHORIZED

GITHUB_WORKFLOW_ACTIVATION: NOT_AUTHORIZED

AGENT_DEPLOYMENT: NOT_AUTHORIZED

BROKER_API_WRITE: NOT_AUTHORIZED

LIVE_TRADING: NOT_AUTHORIZED

## Verification Status

INSIGHT_NUMBER: 128

STRATEGIC_PRINCIPLE: DOCUMENTED

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

NEGATIVE_TESTS: NOT_EXECUTED

INDEPENDENT_EVALUATION: NOT_IMPLEMENTED

GITHUB_PUBLICATION: NOT_VERIFIED

## Relationship to Earlier Insights

This principle complements:

- INSIGHT #091 — Numbers Are Not Comparable Until Their Measurement Contracts Match
- INSIGHT #102 — A Correct Decision on Stale Data Is Still Unsafe
- INSIGHT #124 — Research Scope Is Not Access Authorization
- INSIGHT #127 — Provider Availability Is Not Execution Resilience

The present Insight focuses specifically on preserving the temporal boundary of observations and preventing an agent from silently presenting historical evidence as current operational truth.

## Closing Principle

A value without its observation time is incomplete evidence.

A fresh value without authorization is still not permission to act.

VIDIME. OVERUJEME. STAVIME.
