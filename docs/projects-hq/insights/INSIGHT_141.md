
# PROJECTS HQ INSIGHT #141

Date: 2026-11-27
Title: Compare Trading Concepts by Function Before Comparing Performance
Revision: v1.0
Status: STRATEGIC_DOCUMENTATION_ONLY

## Executive Summary

Trading concepts must be classified according
to the function they are intended to perform
before their performance can be meaningfully
compared.

A signal-generation method, a market-regime
filter, and an exposure-management method
solve different problems.

Comparing them as interchangeable strategies
may produce misleading conclusions.

The Nekonecny Mir Strategy Radar now contains
nine educational research concepts.

Strategy Radar #009 introduces ATR Volatility
Breakout as a conceptual example of a
volatility-adjusted directional signal.

This Insight proposes a functional research
taxonomy and a structured preparation process
for a future Strategy Radar Research Checkpoint.

No strategy selection, implementation, testing,
repository modification, API access, or trading
activity is authorized.

## Evidence Availability

Fresh external news was not independently
verified for the November 27, 2026 edition.

No current BTC prices, ETF flows, product
announcements, security incidents, or benchmark
results are asserted.

The technical discussion is educational.

Reference resource:

TradingView — Average True Range

https://www.tradingview.com/support/solutions/43000501823-average-true-range-atr/

REFERENCE_STATUS:
NOT_REVALIDATED_IN_THIS_EDITION

No empirical profitability claim is derived
from this reference.

## Core Principle

SIGNAL_GENERATION != REGIME_CLASSIFICATION

REGIME_CLASSIFICATION != EXPOSURE_MANAGEMENT

EXPOSURE_MANAGEMENT != EXECUTION_AUTHORIZATION

INDICATOR_COMPLEXITY != TRADING_EDGE

ADAPTIVE_THRESHOLD != VERIFIED_IMPROVEMENT

CONCEPT_SIMILARITY != FUNCTIONAL_EQUIVALENCE

RESEARCH_PRIORITY != STRATEGY_APPROVAL

FUNCTIONAL_CLASSIFICATION != VALIDATED_ARCHITECTURE

Concepts must first be compared according to
their intended function.

Economic comparisons require comparable
objectives, assumptions, data, constraints,
and evaluation procedures.

## Strategy Radar Inventory

### RADAR-001: Trend Following

FUNCTION:
Directional signal generation.

HYPOTHESIS:
Persistent trends may provide opportunities
for systematic directional exposure.

STATUS: EDUCATIONAL_ONLY

EDGE: NOT_ESTABLISHED

### RADAR-002: Volatility Breakout

FUNCTION:
Directional signal generation.

HYPOTHESIS:
Movement beyond a predefined price range
may be followed by directional continuation.

STATUS: EDUCATIONAL_ONLY

EDGE: NOT_ESTABLISHED

### RADAR-003: Mean Reversion

FUNCTION:
Reversal signal generation.

HYPOTHESIS:
Some temporary deviations from a reference
value may subsequently reverse.

STATUS: EDUCATIONAL_ONLY

EDGE: NOT_ESTABLISHED

### RADAR-004: Momentum

FUNCTION:
Directional signal generation.

HYPOTHESIS:
Recent directional price movement may
contain information about subsequent returns.

STATUS: EDUCATIONAL_ONLY

EDGE: NOT_ESTABLISHED

### RADAR-005: Market-Regime Filters

FUNCTION:
Market-condition classification.

HYPOTHESIS:
Identifying relevant market conditions may
help determine when a particular research
concept is unsuitable.

STATUS: EDUCATIONAL_ONLY

BENEFIT: NOT_ESTABLISHED

### RADAR-006: Volatility Targeting

FUNCTION:
Exposure management.

HYPOTHESIS:
Adjusting exposure according to estimated
volatility may help stabilize portfolio risk
under some conditions.

STATUS: EDUCATIONAL_ONLY

BENEFIT: NOT_ESTABLISHED

### RADAR-007: Donchian Channel Breakout

FUNCTION:
Directional signal generation.

HYPOTHESIS:
A breakout beyond historical highs or lows
may sometimes precede continued movement.

STATUS: EDUCATIONAL_ONLY

EDGE: NOT_ESTABLISHED

### RADAR-008: VWAP Mean Reversion

FUNCTION:
Volume-weighted reversal signal generation.

HYPOTHESIS:
Some deviations from an explicitly anchored
volume-weighted reference may reverse.

STATUS: EDUCATIONAL_ONLY

EDGE: NOT_ESTABLISHED

### RADAR-009: ATR Volatility Breakout

FUNCTION:
Volatility-adjusted directional signal generation.

HYPOTHESIS:
A volatility-adjusted breakout threshold may
provide useful information about subsequent
directional movement.

STATUS: EDUCATIONAL_ONLY

EDGE: NOT_ESTABLISHED

## Strategy Radar #009

CONCEPT: ATR Volatility Breakout

CATEGORY: Volatility-Adjusted Breakout

STATUS: EDUCATIONAL_ONLY

### Conceptual Definition

True Range is defined as:

TR_t = max(
    high_t - low_t,
    abs(high_t - close_previous),
    abs(low_t - close_previous)
)

Average True Range applies a defined
smoothing method to True Range observations.

The smoothing convention, initialization,
observation frequency, and data availability
must be explicitly specified.

An illustrative breakout boundary is:

upper_t = reference_previous
          + multiplier * ATR_previous

lower_t = reference_previous
          - multiplier * ATR_previous

An illustrative upward breakout occurs when:

close_t > upper_t

An illustrative downward breakout occurs when:

close_t < lower_t

These expressions are educational definitions.

No reference-price convention, ATR period,
multiplier, timeframe, entry rule, exit rule,
position size, or execution model is approved.

### Hypothetical Source of Edge

A volatility-adjusted threshold may distinguish
some unusually large price movements from
ordinary market fluctuations.

However, a larger-than-usual price movement
does not establish directional continuation.

Adaptive thresholds may also react too slowly
to changing market conditions.

No economic advantage has been demonstrated.

### Required Data

Potential future research would require:

- Historical OHLCV observations
- Previous closing prices
- Exchange and instrument identifiers
- Observation timestamps
- Data availability timestamps
- ATR initialization conventions
- Smoothing conventions
- Transaction fees
- Spread observations
- Slippage assumptions
- Execution feasibility constraints

No new data acquisition is authorized.

### Potentially Favorable Conditions

- Persistent directional movement
- Sustained volatility expansion
- Sufficient market liquidity
- Execution costs small relative to
  potential price movements

### Potentially Unfavorable Conditions

- Rapid directional reversals
- Repeated false breakouts
- Sudden volatility discontinuities
- Delayed volatility estimates
- Deteriorating liquidity
- Excessive transaction costs

These conditions are hypotheses,
not measured project findings.

## Educational Example

Hypothetical reference price: USD 70,000

Hypothetical ATR: USD 800

Hypothetical multiplier: 2.0

Illustrative upper boundary: USD 71,600

Illustrative lower boundary: USD 68,400

Illustrative distance from reference: USD 1,600

These values are synthetic educational inputs.

They are not current market observations.

They are not recommended trading levels.

They are not executed trades.

They are not backtest results.

## Proposed Functional Research Taxonomy

TAXONOMY_STATUS: PROPOSED

### Group A: Directional Signal Concepts

- RADAR-001
- RADAR-002
- RADAR-004
- RADAR-007
- RADAR-009

### Group B: Reversal Signal Concepts

- RADAR-003
- RADAR-008

### Group C: Market-Condition Classification

- RADAR-005

### Group D: Exposure Management

- RADAR-006

This classification is a proposed research aid.

It is not an approved trading architecture.

It does not imply that all concepts should
be implemented or combined.

Concepts may overlap substantially.

Overlapping concepts must not be treated as
independent sources of diversification without
supporting empirical evidence.

## Proposed Control

CONTROL_ID: NM-FUNCTIONAL-COMPARISON-001

CONTROL_NAME:
Function-Aware Research Comparison Boundary

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

### Proposed Requirements

1. Identify the intended function of every
   research concept.

2. Distinguish directional signals from
   reversal signals.

3. Distinguish signal generation from
   market-regime classification.

4. Distinguish exposure management from
   execution authorization.

5. Document shared assumptions and overlapping
   mathematical components.

6. Define an appropriate comparison objective
   before evaluating any concept.

7. Require comparable data, costs, and
   constraints for economic comparisons.

8. Preserve the distinction between
   implementation correctness and economic edge.

9. Prevent research prioritization from
   becoming implicit strategy approval.

10. Prevent apparent conceptual diversity
    from being treated as verified diversification.

11. Require independent review of measurement
    definitions and evaluation procedures.

12. Preserve all existing governance restrictions.

These requirements are proposals.

They are not implemented controls.

## Proposed Research Checkpoint Preparation

CHECKPOINT_WORKING_TITLE:
STRATEGY_RADAR_RESEARCH_CHECKPOINT_v1.0

CHECKPOINT_STATUS: PROPOSED

### Phase 1: Research Inventory

Document all nine concepts with:

- Intended function
- Mathematical definition
- Required observations
- Hypothetical source of benefit
- Potential failure modes
- Data integrity requirements
- Economic evaluation requirements
- Evidence limitations
- Governance restrictions

### Phase 2: Specification Review

Identify:

- Ambiguous definitions
- Overlapping concepts
- Temporal integrity risks
- Data requirements
- Measurement boundaries
- Cost assumptions
- Parameter sensitivity
- Potential common-mode failures

### Phase 3: Independent Agent Review

Potential future reviewers:

- Codex
- Claude Code

Proposed review mode:

READ_ONLY_RESEARCH

Agents would be asked to evaluate existing
documentation and identify unresolved
technical questions.

No implementation, experiments, repository
changes, or new API access would be permitted.

The review has not been initiated.

### Phase 4: Human Decision Checkpoint

Review the documented evidence and unresolved
questions before deciding whether any further
research activity should be authorized.

No candidate is selected by this Insight.

### Phase 5: Separately Authorized Research

Any future experiment, implementation,
backtest, or operational activity requires
a separate explicit governance decision.

This phase remains unauthorized.

## Proposed Evidence Fields

- concept_id
- concept_version
- intended_function
- mathematical_definition
- required_data
- measurement_contract
- shared_assumptions
- overlapping_concepts
- hypothetical_source_of_edge
- potential_failure_modes
- comparison_objective
- baseline_definition
- cost_assumptions
- evaluation_constraints
- independent_review_status
- unresolved_uncertainty
- empirical_evidence_status
- authorization_status

These fields are illustrative.

They are not an approved canonical registry.

## Proposed Negative Tests

All tests are PROPOSED and NOT EXECUTED.

### NEG-01: Function mismatch

Input:
A regime filter is ranked against a
directional entry signal using raw
standalone trading returns.

Expected:
COMPARISON_OBJECTIVE_INVALID.

### NEG-02: Exposure management misclassified

Input:
Volatility Targeting is treated as an
independent directional entry strategy.

Expected:
FUNCTIONAL_CLASSIFICATION_INVALID.

### NEG-03: ATR initialization ambiguity

Input:
Two implementations use different ATR
initialization conventions without disclosure.

Expected:
MEASUREMENT_CONTRACT_MISMATCH.

### NEG-04: Future-data leakage

Input:
The breakout threshold includes volatility
observations unavailable at decision time.

Expected:
TEMPORAL_INTEGRITY_FAILURE.

### NEG-05: Inconsistent comparison costs

Input:
One candidate includes realistic fees
and slippage while another omits them.

Expected:
ECONOMIC_COMPARISON_INVALID.

### NEG-06: Overlapping concepts

Input:
Several breakout methods are assumed to
provide independent diversification solely
because their names differ.

Expected:
DIVERSIFICATION_NOT_ESTABLISHED.

### NEG-07: Parameter overfitting

Input:
The ATR period and multiplier are selected
solely to maximize historical returns.

Expected:
OVERFITTING_REVIEW_REQUIRED.

### NEG-08: Adaptive threshold overclaim

Input:
A volatility-adjusted threshold is declared
superior without comparative evidence.

Expected:
ECONOMIC_IMPROVEMENT_NOT_ESTABLISHED.

### NEG-09: Research priority treated as approval

Input:
A concept receives a high research priority
and an agent begins implementing it.

Expected:
IMPLEMENTATION_NOT_AUTHORIZED.

### NEG-10: Read-only boundary violation

Input:
A research-review agent attempts to modify
repository files.

Expected:
REPOSITORY_WRITE_DENIED.

### NEG-11: Unvalidated measurement pipeline

Input:
A candidate produces favorable results
through the current unvalidated pipeline.

Expected:
MEASUREMENT_NOT_VERIFIED.

### NEG-12: Synthetic data misrepresented

Input:
The educational ATR example is presented
as historical BTC performance.

Expected:
EVIDENCE_CLASSIFICATION_INVALID.

### NEG-13: Agent agreement treated as approval

Input:
Codex and Claude Code agree on a concept
and initiate an unauthorized backtest.

Expected:
BACKTEST_NOT_AUTHORIZED.

### NEG-14: Execution authorization bypass

Input:
A favorable research assessment is used
to request broker write permissions.

Expected:
SEPARATE_EXECUTION_AUTHORIZATION_REQUIRED.

## Proposed Future Evaluation Questions

Any separately authorized evaluation would
need to establish:

1. What function does each concept perform?

2. Which concepts share underlying assumptions?

3. Which comparisons are methodologically valid?

4. Are indicator definitions reproducible?

5. Are all inputs available at decision time?

6. Are comparison baselines appropriate?

7. Are transaction costs consistently modeled?

8. Are parameters selected without excessive
   historical optimization?

9. Are results robust across market regimes?

10. Does any improvement survive independent
    out-of-sample evaluation?

11. Are apparent diversification benefits
    supported by evidence?

12. Can independent reviewers reproduce
    the complete evidence chain?

No such evaluation has been authorized
or performed.

## Proposed Future AI Roles

ChatGPT:
Research organization, educational framing,
functional taxonomy, and checkpoint preparation.

Codex:
Potential read-only technical assessment of
separately approved research documentation.

Claude Code:
Potential independent assumption review,
mathematical review, and identification of
common-mode failure risks.

Human Reviewer:
Evidence assessment, research prioritization,
and explicit governance decisions.

These roles are conceptual only.

No agent workflow has been activated.

## Governance Boundary

DB1: PARKED

EF2: PARKED

MEASUREMENT_PIPELINE: UNVALIDATED

RC2_RATIFICATION: NOT_RATIFIED

STRATEGY_RADAR: EDUCATIONAL_ONLY

RESEARCH_CHECKPOINT: PROPOSED

AGENT_RESEARCH_EXECUTION: NOT_INITIATED

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

- Strategy implementation
- Indicator development
- Pine Script development
- Market-data acquisition experiments
- Backtesting
- Parameter optimization
- Repository modifications
- Automated agent execution workflows
- Broker or exchange API access
- Financial transactions

Any operational activity requires a separate
explicit governance decision.

## Verification Status

INSIGHT_NUMBER: 141

PREVIOUS_PREPARED_INSIGHT_NUMBER: 140

NUMBERING_BASIS:
PREPARED_DOCUMENTATION_SEQUENCE

PREVIOUS_GITHUB_PUBLICATION:
NOT_INDEPENDENTLY_VERIFIED

FRESH_EXTERNAL_NEWS:
NOT_VERIFIED_IN_THIS_EDITION

STRATEGY_RADAR_CONCEPT_COUNT: 9

STRATEGY_RADAR_009: EDUCATIONAL_ONLY

ATR_BREAKOUT_EDGE: NOT_ESTABLISHED

FUNCTIONAL_TAXONOMY: PROPOSED

RESEARCH_CHECKPOINT: PROPOSED

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

NEGATIVE_TESTS: NOT_EXECUTED

AGENT_REVIEW: NOT_PERFORMED

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

- INSIGHT #136:
  A Benchmark Must Measure the Decision
  That Matters

- INSIGHT #137:
  A System Must Be Allowed to Say:
  Conditions Are Unknown

- INSIGHT #138:
  A Trading Signal Must Never Determine
  Its Own Risk Budget

- INSIGHT #139:
  Two Agents Can Agree and Still Be Wrong

- INSIGHT #140:
  A Measurement Without a Defined Boundary
  Is Not Reproducible

Insight #141 extends these principles to
function-aware research classification,
methodologically valid comparisons, and
preparation for independent agent review.

## Closing Principle

Different concepts solve different problems.

A signal is not a risk budget.

A filter is not an execution system.

An adaptive indicator is not a verified edge.

Research priority is not operational permission.

Classify before comparing.

Define before measuring.

Challenge before accepting.

Verify before authorizing.

VIDIME. OVERUJEME. STAVIME.
