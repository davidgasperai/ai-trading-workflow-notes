
# PROJECTS HQ INSIGHT #137

Date: 2026-11-23
Title: A System Must Be Allowed to Say: Conditions Are Unknown
Revision: v1.0
Status: STRATEGIC_DOCUMENTATION_ONLY

## Executive Summary

Automated systems are frequently designed to produce a classification, prediction, or action.

However, forcing a decision when the available evidence is insufficient can create unnecessary risk.

This is particularly relevant to AI-assisted trading research.

A market-regime classifier may attempt to distinguish trending, ranging, and stressed market conditions.

But real markets can transition rapidly between regimes.

Indicators may disagree.

Data may be incomplete or delayed.

Historical patterns may fail to generalize.

A robust decision architecture should therefore recognize uncertainty as a legitimate outcome.

UNKNOWN is not necessarily a system failure.

It may be the correct response to insufficient evidence.

This Insight proposes an explicit uncertainty and abstention principle for future research.

It does not authorize implementation, testing, repository changes, agent deployment, or trading.

## External Research Context

### OpenAI Research

MedChemBench: Benchmarking AI for medicinal chemistry

Published: 2026-11-20

Source:
https://openai.com/research/index/

The benchmark evaluates domain-specific scientific reasoning.

Its relevance to Nekonečný Mír is methodological.

A model's ability to produce an answer must be distinguished from the reliability of that answer in a particular domain.

### OpenAI Engineering

How OpenAI's Performance Factory keeps ChatGPT fast

Published: 2026-11-19

Source:
https://openai.com/index/how-openai-performance-factory-keeps-chatgpt-fast/

The report describes automated investigations, independent review, and post-change verification.

Its relevance is the separation between a proposed explanation and an independently accepted conclusion.

### Market Context

Reuters reported substantial Bitcoin volatility on November 21, 2026.

Bitcoin fell to approximately USD 55,251.60 before rebounding toward USD 60,000.

Source:
https://www.reuters.com/business/bitcoin-falls-357-56814-2026-11-21/

This is historical market context.

It is not evidence that any particular regime classifier or trading strategy has predictive value.

## Core Principle

CLASSIFICATION_REQUIRED != CLASSIFICATION_JUSTIFIED

UNCERTAIN != FAILED

UNKNOWN != SAFE

LOW_CONFIDENCE != PERMISSION_TO_GUESS

REGIME_DETECTED != TRADING_EDGE_ESTABLISHED

NO_SIGNAL != MISSED_OPPORTUNITY

ABSTENTION != ECONOMIC_FAILURE

MODEL_OUTPUT != AUTHORIZED_ACTION

A system should be able to decline classification when evidence is insufficient.

Abstention must not silently become an alternative trading signal.

An UNKNOWN state must not grant permission to another strategy, model, or agent.

## Proposed Control

CONTROL_ID: NM-UNCERTAINTY-ABSTENTION-001

CONTROL_NAME: Explicit Unknown-State and Abstention Boundary

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

### Proposed Requirements

1. Permit an explicit UNKNOWN classification.

2. Distinguish missing data from contradictory evidence.

3. Distinguish low confidence from technical execution failure.

4. Define confidence criteria before evaluating candidate outputs.

5. Prevent forced classification when minimum evidence requirements are unmet.

6. Preserve the observations supporting each classification.

7. Record uncertainty and alternative interpretations.

8. Prevent agents from treating abstention as permission to bypass controls.

9. Separate regime classification from strategy authorization.

10. Preserve data timestamps and information availability boundaries.

11. Require independent validation of proposed classification logic.

12. Record transitions between known and unknown states.

13. Prevent unverified classifications from triggering consequential actions.

14. Require explicit human authorization for any future operational use.

15. Preserve existing project restrictions.

## Proposed Classification States

The following states are illustrative only.

- TREND_UP
- TREND_DOWN
- RANGE
- HIGH_VOLATILITY
- MARKET_STRESS
- TRANSITION
- UNKNOWN
- DATA_INSUFFICIENT
- DATA_INVALID

These labels are not a canonical taxonomy.

No thresholds, indicator periods, or classification rules are approved.

## Proposed Evidence Fields

- classification_id
- observation_timestamp
- data_source
- data_version
- data_quality_status
- feature_definition
- feature_availability_timestamp
- proposed_regime
- alternative_regimes
- confidence_method
- uncertainty_reason
- originating_agent
- independent_reviewer
- review_status
- authorization_status

These are proposed documentation fields.

They are not implemented.

## Strategy Radar Connection

Strategy Radar #005 introduces Market-Regime Filters.

A hypothetical regime filter may attempt to identify market conditions in which another strategy is more or less suitable.

Possible research inputs include:

- Historical price direction
- Moving-average slope
- Realized volatility
- Trend-strength measures
- Price-range characteristics
- Liquidity and spread observations

The underlying hypothesis is that strategy performance may vary across market conditions.

However, this does not establish that a particular regime classifier can improve future returns.

A regime filter may:

- Misclassify transitions
- React too slowly
- Overfit historical thresholds
- Increase turnover
- Introduce additional execution costs
- Exclude profitable opportunities
- Fail during previously unseen conditions

The classifier itself must be evaluated independently.

## Proposed Negative Tests

All tests below are PROPOSED and NOT EXECUTED.

### NEG-01: Missing observations

Input:
Required market observations are missing.

Expected:
DATA_INSUFFICIENT.

### NEG-02: Contradictory indicators

Input:
Independent indicators produce incompatible regime classifications.

Expected:
UNKNOWN or TRANSITION, subject to a future approved specification.

### NEG-03: Future-data leakage

Input:
A regime classification uses observations unavailable at decision time.

Expected:
TEMPORAL_INTEGRITY_FAILURE.

### NEG-04: Forced classification

Input:
An agent is required to choose TREND or RANGE despite insufficient evidence.

Expected:
ABSTENTION_REQUIRED.

### NEG-05: Confidence without calibration

Input:
A model reports 95% confidence without a validated confidence methodology.

Expected:
CONFIDENCE_NOT_VALIDATED.

### NEG-06: Regime label treated as trade authorization

Input:
A classifier labels the market TREND_UP and an agent requests a buy order.

Expected:
BROKER_WRITE_DENIED.

### NEG-07: Overfitted regime thresholds

Input:
Thresholds are selected solely to maximize historical profit.

Expected:
OVERFITTING_REVIEW_REQUIRED.

### NEG-08: Classification instability

Input:
Small parameter changes cause frequent regime reversals.

Expected:
ROBUSTNESS_NOT_ESTABLISHED.

### NEG-09: Ignored transaction costs

Input:
A regime-switching strategy appears profitable before turnover costs.

Expected:
ECONOMIC_VIABILITY_NOT_ESTABLISHED.

### NEG-10: Unvalidated measurement pipeline

Input:
A regime filter is evaluated through the current unvalidated pipeline.

Expected:
MEASUREMENT_NOT_VERIFIED.

### NEG-11: Unknown state bypass

Input:
An agent interprets UNKNOWN as permission to activate a fallback strategy.

Expected:
AUTHORIZATION_REQUIRED.

### NEG-12: Historical regime hindsight

Input:
A classifier identifies market regimes using the complete historical price path.

Expected:
LOOK_AHEAD_BIAS_DETECTED.

## Proposed Evaluation Questions

Future authorized research would need to determine:

1. Can regimes be classified using only information available at the time?

2. Are classifications reproducible across independent implementations?

3. Do results remain stable under reasonable parameter variation?

4. Does the classifier provide useful information out of sample?

5. Does adding the filter improve a strategy after fees and slippage?

6. Is the improvement economically meaningful?

7. Does the filter reduce risk without introducing unacceptable opportunity costs?

8. How frequently does the classifier abstain?

9. Are abstention rates and classification errors stable across regimes?

10. Does the system behave safely when observations are missing or invalid?

No such evaluation has been authorized or performed.

## Proposed Future AI Roles

ChatGPT:
Educational research framing and documentation.

Codex:
Potential future implementation of a precisely approved specification.

Claude Code:
Potential independent verification of calculations, temporal integrity, and failure cases.

Human Reviewer:
Independent assessment and explicit authorization decisions.

These roles are conceptual only.

No agent workflow is activated.

## Governance Boundary

DB1: PARKED

EF2: PARKED

MEASUREMENT_PIPELINE: UNVALIDATED

RC2_RATIFICATION: NOT_RATIFIED

REGISTRY_EXPOSURE_LEDGER_V0.3: DRAFT_NOT_CANONICAL

NEW_STRATEGY_RESEARCH: NOT_AUTHORIZED

NEW_BACKTESTS: NOT_AUTHORIZED

REPOSITORY_MODIFICATIONS: NOT_AUTHORIZED_BY_THIS_INSIGHT

GITHUB_WORKFLOW_ACTIVATION: NOT_AUTHORIZED

AGENT_DEPLOYMENT: NOT_AUTHORIZED

BROKER_API_WRITE: NOT_AUTHORIZED

LIVE_TRADING: NOT_AUTHORIZED

This document does not authorize:

- Market-data experiments
- Indicator implementation
- Regime-classifier implementation
- Strategy coding
- Pine Script development
- Backtesting
- Parameter optimization
- Repository changes
- New agent execution workflows
- Broker or exchange API access
- Live financial transactions

Any future authorization requires a separate explicit governance decision.

## Verification Status

INSIGHT_NUMBER: 137

EXTERNAL_SOURCES: REVIEWED_FOR_CONTEXT

STRATEGIC_PRINCIPLE: DOCUMENTED

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

NEGATIVE_TESTS: NOT_EXECUTED

UNKNOWN_STATE_CONTROL: NOT_IMPLEMENTED

STRATEGY_RADAR_005: EDUCATIONAL_ONLY

MARKET_REGIME_FILTER_EDGE: NOT_ESTABLISHED

BACKTESTS: NOT_EXECUTED

MEASUREMENT_PIPELINE: UNVALIDATED

INDEPENDENT_PROJECT_EVALUATION: NOT_PERFORMED

GITHUB_PUBLICATION: NOT_VERIFIED

## Relationship to Earlier Insights

This principle complements:

- INSIGHT #091 — Numbers Are Not Comparable Until Their Measurement Contracts Match
- INSIGHT #098 — An Approval Must Bind to the Exact Action
- INSIGHT #099 — A Strategy Must Not Choose Its Own Exam
- INSIGHT #100 — A Rule Is Not a Control Until It Is Enforced
- INSIGHT #109 — An Agent's Explanation Is Not Proof of Compliance
- INSIGHT #132 — A Model Upgrade Must Earn Its Place Through Independent Evaluation
- INSIGHT #133 — A Strategy Hypothesis Is Not a Trading Edge
- INSIGHT #134 — An Automated Workflow Must Preserve the Evidence Behind Every Handoff
- INSIGHT #135 — A Plausible Explanation Must Survive an Attempt to Disprove It
- INSIGHT #136 — A Benchmark Must Measure the Decision That Matters

Insight #137 focuses on uncertainty, abstention, and the distinction between classification and authorization.

## Closing Principle

A system that always produces an answer is not necessarily reliable.

A model that admits uncertainty may be safer than one that confidently guesses.

A market regime that cannot be classified should not be forced into a convenient category.

When evidence is insufficient, UNKNOWN may be the most accurate result.

And UNKNOWN must never become permission to act.

VIDIME. OVERUJEME. STAVIME.
