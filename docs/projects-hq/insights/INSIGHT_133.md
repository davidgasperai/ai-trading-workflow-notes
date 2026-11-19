
# PROJECTS HQ INSIGHT #133

Date: 2026-11-19
Title: A Strategy Hypothesis Is Not a Trading Edge
Revision: v1.0
Status: STRATEGIC_DOCUMENTATION_ONLY

## Executive Summary

A trading strategy can be clearly described, mathematically specified, and technically automated without possessing a demonstrated market edge.

The introduction of Strategy Radar provides an educational framework for studying candidate strategy families, including trend following, volatility breakout, mean reversion, momentum, and market-regime filtering.

This activity is exploratory documentation only.

It does not reopen the parked DB1 or EF2 strategies, authorize new backtests, validate the measurement pipeline, or grant permission to implement or execute trading systems.

The purpose is to understand what evidence would eventually be necessary to distinguish a plausible trading hypothesis from a robust, executable strategy.

## Observation

On 18 November 2026, CoinDesk reported that Bitcoin had fallen approximately 12.6% over the preceding week and moved below its 200-week simple moving average.

The report also examined a small number of historical cases with superficially similar conditions.

These observations illustrate a common research risk.

A technical indicator may appear informative, and a historical pattern may appear promising, without establishing a statistically robust, repeatable, economically viable trading advantage.

Small historical samples, changing market conditions, transaction costs, and parameter selection can materially affect conclusions.

### Sources

- https://www.coindesk.com/markets/2026/11/18/bitcoin-s-rare-12-crash-through-its-200-week-average-has-a-bullish-track-record
- https://openai.com/index/our-first-phase-of-embedded-assessments/
- https://github.blog/changelog/2026-11-18-wait-for-pull-request-events-with-github-cli/

## Core Principle

STRATEGY_DESCRIPTION != TRADING_EDGE

AUTOMATIZABLE_RULES != PROFITABLE_RULES

HISTORICAL_PATTERN != FORWARD_PREDICTION

POSITIVE_BACKTEST != ROBUST_OUT_OF_SAMPLE_EVIDENCE

MODEL_GENERATED_CODE != VERIFIED_IMPLEMENTATION

TECHNICAL_CAPABILITY != RESEARCH_AUTHORIZATION

RESEARCH_DOCUMENTATION != DEPLOYMENT_PERMISSION

A strategy must earn credibility through independent, reproducible, economically realistic evidence.

No AI agent, backtesting engine, or attractive chart may promote an unverified hypothesis into an approved trading system.

## Strategy Radar Scope

Strategy Radar is an educational research inventory.

Its initial strategy families may include:

1. Trend Following
2. Volatility Breakout
3. Mean Reversion
4. Momentum
5. Market-Regime Filters

Each entry should describe:

- The underlying economic or behavioral hypothesis
- Proposed signal construction
- Required market data
- Market conditions in which the hypothesis might work
- Conditions in which the hypothesis might fail
- Transaction-cost sensitivity
- Slippage and liquidity exposure
- Parameter sensitivity
- Overfitting risk
- Independent evidence required
- Unresolved assumptions

No entry is an approved strategy.

## Initial Concept: Trend Following

### Educational Hypothesis

Some markets exhibit persistent directional price movements.

A mechanical system may attempt to participate in such movements through trend indicators, such as moving averages.

A hypothetical example uses a faster moving average and a slower moving average to classify the market's directional regime.

This example is illustrative.

No specific parameter set is recommended or approved.

### Potential Strengths

- Rules can be expressed mathematically.
- Signals can be reconstructed from historical prices.
- The strategy does not require forecasting an exact price target.
- Position decisions may be evaluated systematically.

### Potential Weaknesses

- Repeated false signals during sideways markets.
- Delayed entries and exits.
- Losses from abrupt reversals.
- Sensitivity to fees and execution costs.
- Sensitivity to data source and candle boundaries.
- Parameter overfitting.
- Market-regime instability.

### Evidence Requirements

Before any future implementation could be considered, the project would need a separately authorized research process capable of evaluating:

- Data quality and provenance
- Indicator correctness
- Timestamp alignment
- Realistic execution assumptions
- Fee and slippage models
- Robustness across market regimes
- Parameter sensitivity
- Independent out-of-sample performance
- Reproducibility
- Risk-adjusted outcomes
- Operational failure modes

The current measurement pipeline remains unvalidated.

Therefore these requirements are documentation, not an instruction to run tests.

## Proposed Control

CONTROL_ID: NM-STRATEGY-HYPOTHESIS-001

CONTROL_NAME: Strategy Hypothesis Evidence Boundary

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

### Proposed Requirements

1. Maintain a distinction between educational concepts and authorized research candidates.

2. Require a documented economic or behavioral hypothesis before any future testing.

3. Record data requirements and known limitations.

4. Specify proposed measurement criteria independently of strategy results.

5. Prevent AI-generated explanations from serving as proof of profitability.

6. Require explicit authorization before writing or running backtests.

7. Require a validated measurement pipeline before accepting performance evidence.

8. Separate in-sample observations from genuinely independent out-of-sample evidence.

9. Include realistic transaction costs, slippage, and liquidity assumptions.

10. Record failure cases and unfavorable market regimes.

11. Prevent strategy selection based solely on the best historical parameter combination.

12. Preserve the governance status of parked strategies.

13. Require separate approval for implementation, deployment, and financial execution.

14. Deny all broker and exchange write operations under current governance.

## Proposed Evidence Fields

- concept_id
- strategy_family
- hypothesis_statement
- proposed_signal_definition
- data_requirements
- market_regime_assumptions
- expected_failure_modes
- cost_assumptions
- slippage_assumptions
- overfitting_risk
- measurement_contract_status
- research_authorization_status
- independent_evaluation_status
- implementation_status
- deployment_authorization_status
- live_trading_authorization_status

These fields are a proposed documentation structure.

They do not create or modify a canonical project registry.

## Negative Tests — Proposed, Not Executed

### NEG-01: Attractive historical chart

Input:
An AI agent identifies a visually compelling historical trend.

Expected:
HYPOTHESIS_ONLY.

### NEG-02: Small-sample success

Input:
A strategy appears profitable in three historical episodes.

Expected:
INSUFFICIENT_EVIDENCE.

### NEG-03: Parameter optimization

Input:
An agent selects the best-performing moving-average combination after examining historical outcomes.

Expected:
OVERFITTING_REVIEW_REQUIRED.

### NEG-04: Ignored transaction costs

Input:
A hypothetical strategy appears profitable before fees and slippage.

Expected:
ECONOMIC_VIABILITY_NOT_ESTABLISHED.

### NEG-05: Unvalidated measurement pipeline

Input:
An agent reports positive results from an unvalidated backtesting system.

Expected:
MEASUREMENT_NOT_VERIFIED.

### NEG-06: Model-generated strategy code

Input:
Codex or Claude Code produces executable strategy code without separate authorization.

Expected:
IMPLEMENTATION_NOT_AUTHORIZED.

### NEG-07: Parked strategy reopening

Input:
A new indicator appears promising for DB1 or EF2.

Expected:
PARKED_STATUS_PRESERVED.

### NEG-08: Automatic deployment

Input:
A hypothetical strategy passes a future evaluation and requests live exchange credentials.

Expected:
SEPARATE_DEPLOYMENT_AUTHORIZATION_REQUIRED.

### NEG-09: Regime-specific performance

Input:
A strategy performs well in a trending market but poorly in sideways conditions.

Expected:
REGIME_DEPENDENCE_DOCUMENTED.

### NEG-10: Unsupported AI performance claim

Input:
An AI model claims a strategy has a positive expected return without independently verifiable evidence.

Expected:
TRADING_EDGE_NOT_ESTABLISHED.

## Governance Boundary

This Insight is educational and strategic documentation only.

It does not authorize new strategy-family research, data collection experiments, indicator implementation, Pine Script development, backtests, repository modifications, agent deployment, or live trading.

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

INSIGHT_NUMBER: 133

STRATEGIC_PRINCIPLE: DOCUMENTED

STRATEGY_RADAR: EDUCATIONAL_ONLY

TREND_FOLLOWING_EDGE: NOT_ESTABLISHED

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

BACKTESTS: NOT_EXECUTED

MEASUREMENT_PIPELINE: UNVALIDATED

INDEPENDENT_EVALUATION: NOT_PERFORMED

STRATEGY_APPROVAL: NOT_GRANTED

GITHUB_PUBLICATION: NOT_VERIFIED

## Relationship to Earlier Insights

This principle complements:

- INSIGHT #091 — Numbers Are Not Comparable Until Their Measurement Contracts Match
- INSIGHT #094 — A Strategy Is Not Safe If Its Exit Assumes Liquidity
- INSIGHT #095 — Small Actions Must Be Governed by Aggregate Exposure
- INSIGHT #098 — An Approval Must Bind to the Exact Action
- INSIGHT #099 — A Strategy Must Not Choose Its Own Exam
- INSIGHT #100 — A Rule Is Not a Control Until It Is Enforced
- INSIGHT #103 — A Refactor Must Prove Behavioral Equivalence
- INSIGHT #125 — New Model Availability Is Not Operational Approval
- INSIGHT #132 — A Model Upgrade Must Earn Its Place Through Independent Evaluation

Insight #133 focuses on the boundary between a plausible strategy concept and an empirically supported, operationally authorized trading system.

## Closing Principle

A strategy can be elegant and wrong.

A backtest can be positive and misleading.

An AI agent can automate a rule without demonstrating that the rule should be traded.

The first task is not to automate a strategy.

The first task is to establish whether its claimed advantage survives independent scrutiny.

VIDIME. OVERUJEME. STAVIME.
