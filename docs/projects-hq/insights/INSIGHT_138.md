
# PROJECTS HQ INSIGHT #138

Date: 2026-11-24
Title: A Trading Signal Must Never Determine Its Own Risk Budget
Revision: v1.0
Status: STRATEGIC_DOCUMENTATION_ONLY

## Executive Summary

Signal generation and risk allocation are separate responsibilities.

A trading signal may describe a potential opportunity.

It does not establish how much capital should be exposed to that opportunity.

Even a correctly calculated signal may be economically unreliable, statistically overfitted, or unsuitable for prevailing market conditions.

A strong signal must not automatically receive a larger risk budget.

Recent market volatility provides a useful educational context for this distinction.

Sharp declines followed by rapid recoveries can expose both long and short positions to substantial losses.

Strategy Radar #006 introduces Volatility Targeting as a conceptual exposure-management method.

Its purpose is to explore how estimated market volatility might inform position sizing under independently established constraints.

No trading edge, risk reduction, or economic improvement has been demonstrated for Nekonecny Mir.

This Insight documents a proposed separation between signal generation, risk allocation, and execution authorization.

It does not authorize implementation, testing, repository changes, API access, or trading.

## External Evidence

### Market Volatility

Reuters
November 23, 2026

Wall Street soars on Huang's return to Nvidia,
Treasury yields rise.

https://www.reuters.com/world/china/global-markets-global-markets-2026-11-22/

Reuters reported a substantial recovery in US equities.

The S&P 500 gained approximately 4.7%.

Nvidia shares gained more than 31%.

These observations describe a historical market session.

They do not establish a predictive trading relationship.

### Institutional Risk Reduction

Reuters
November 23, 2026

Hedge funds post worst week since April 2025,
sparks defensive shift.

https://www.reuters.com/world/china/hedge-funds-post-worst-week-since-april-2025-sparks-defensive-shift-2026-11-23/

Reuters reported that global hedge funds lost more than 3% during the week ended November 20, according to a JPMorgan client note.

The underlying figures are attributed to JPMorgan.

They have not been independently reconstructed by this project.

The report illustrates that professional portfolio management does not eliminate adverse market exposure.

### Reserve and Liquidity Distinction

Reuters
November 24, 2026

CFTC staff advisory says crypto can count
toward reserves, not liquidity rule.

https://www.reuters.com/legal/government/cftc-staff-advisory-says-crypto-can-count-toward-reserves-not-liquidity-rule-2026-11-24/

Reuters reported a distinction between eligible cryptocurrency assets used for reserve requirements and a separate liquidity requirement.

The relevance to this project is conceptual.

Asset value must not be treated as equivalent to immediately available liquidity.

The advisory does not establish the regulatory treatment of any future project activity.

## Core Principle

SIGNAL_STRENGTH != EXPECTED_RETURN

EXPECTED_RETURN != VERIFIED_EDGE

VERIFIED_EDGE != UNLIMITED_EXPOSURE

MODEL_CONFIDENCE != RISK_BUDGET

ESTIMATED_VOLATILITY != MAXIMUM_POSSIBLE_LOSS

TARGET_VOLATILITY != GUARANTEED_REALIZED_VOLATILITY

ASSET_VALUE != AVAILABLE_LIQUIDITY

RISK_APPROVAL != EXECUTION_AUTHORIZATION

A trading signal must not define or expand its own risk budget.

Risk constraints must be independently specified, evaluated, and authorized.

## Proposed Control

CONTROL_ID: NM-RISK-BUDGET-SEPARATION-001

CONTROL_NAME: Independent Signal and Risk Budget Boundary

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

### Proposed Requirements

1. Separate signal generation from exposure allocation.

2. Establish risk constraints independently of candidate signals.

3. Prevent a strategy from increasing its own exposure limits.

4. Distinguish estimated volatility from maximum possible loss.

5. Define the volatility measurement contract before evaluation.

6. Preserve the source and timestamp of every market observation.

7. Reject calculations based on missing, invalid, or future data.

8. Define behavior for zero or near-zero estimated volatility.

9. Establish independently approved exposure ceilings.

10. Prevent implicit leverage through position-sizing calculations.

11. Include transaction costs and liquidity constraints.

12. Evaluate exposure changes during adverse market conditions.

13. Preserve the distinction between available capital and total asset value.

14. Require independent review of risk-allocation logic.

15. Prevent favorable evaluation results from granting execution permissions.

16. Preserve all existing project governance restrictions.

These requirements are proposals.

They are not implemented controls.

## Strategy Radar #006

CONCEPT: Volatility Targeting

CLASSIFICATION: EXPOSURE_MANAGEMENT

STATUS: EDUCATIONAL_ONLY

### Conceptual Hypothesis

Market volatility may persist over time.

Reducing exposure when estimated volatility increases may help stabilize portfolio risk under some conditions.

However, this does not establish positive expected returns.

It does not guarantee lower drawdowns.

It does not guarantee that realized volatility will match a selected target.

### Illustrative Mathematical Model

exposure_weight = min(
    1,
    target_volatility / estimated_volatility
)

This expression is illustrative only.

It assumes:

- A positive and valid volatility estimate
- Consistent measurement units
- A single risky asset
- No financial leverage
- An upper exposure limit of 100%
- No transaction costs in the illustration

These assumptions are not an approved strategy specification.

### Educational Example

Hypothetical capital: EUR 4,000

Hypothetical target volatility: 15%

Hypothetical estimated BTC volatility: 60%

Illustrative exposure weight: 25%

Illustrative BTC exposure: EUR 1,000

Illustrative unallocated capital: EUR 3,000

These values are synthetic educational inputs.

They are not live market observations.

They are not recommended allocations.

They are not backtest results.

### Potential Failure Modes

- Delayed volatility estimation
- Sudden market discontinuities
- Excessive exposure during calm periods
- Procyclical selling after market declines
- Reduced participation in rapid recoveries
- Frequent rebalancing
- Transaction costs
- Slippage
- Parameter overfitting
- Incorrect annualization
- Invalid or incomplete market data
- Counterparty and liquidity risk

## Proposed Evidence Fields

- risk_evaluation_id
- signal_id
- strategy_version
- measurement_contract_version
- market_data_source
- observation_timestamp
- feature_availability_timestamp
- volatility_estimation_method
- volatility_estimation_window
- annualization_method
- estimated_volatility
- hypothetical_target_volatility
- exposure_ceiling
- proposed_exposure
- leverage_status
- liquidity_assumptions
- transaction_cost_assumptions
- independent_review_status
- unresolved_uncertainty
- authorization_status

These fields describe a proposed evidence structure.

They are not a canonical registry.

## Negative Tests

All tests are PROPOSED and NOT EXECUTED.

### NEG-01: Signal-defined risk budget

Input:
A strategy increases its exposure ceiling because
its signal confidence is unusually high.

Expected:
RISK_BUDGET_ESCALATION_DENIED.

### NEG-02: Zero volatility estimate

Input:
Estimated volatility equals zero.

Expected:
INVALID_VOLATILITY_ESTIMATE.

No division or exposure escalation is permitted
under the proposed conceptual boundary.

### NEG-03: Missing observations

Input:
Required historical observations are unavailable.

Expected:
DATA_INSUFFICIENT.

### NEG-04: Future-data leakage

Input:
A volatility estimate includes returns that were
not available at the historical decision time.

Expected:
TEMPORAL_INTEGRITY_FAILURE.

### NEG-05: Inconsistent annualization

Input:
BTC volatility is calculated using an inconsistent
calendar convention or mismatched return frequency.

Expected:
MEASUREMENT_CONTRACT_MISMATCH.

### NEG-06: Implicit leverage

Input:
The position-sizing formula produces exposure
above the independently established ceiling.

Expected:
EXPOSURE_LIMIT_VIOLATION.

### NEG-07: Target volatility interpreted as loss limit

Input:
An agent claims that a 15% volatility target
guarantees a maximum loss of 15%.

Expected:
INVALID_RISK_INTERPRETATION.

### NEG-08: Transaction costs omitted

Input:
Frequent exposure changes appear beneficial
before fees and slippage.

Expected:
ECONOMIC_VIABILITY_NOT_ESTABLISHED.

### NEG-09: Delayed reaction to a market shock

Input:
A historical volatility estimate remains low
during a sudden adverse price movement.

Expected:
SHOCK_RISK_UNRESOLVED.

### NEG-10: Overfitted volatility parameters

Input:
Estimation windows and volatility targets are
selected solely to maximize historical returns.

Expected:
OVERFITTING_REVIEW_REQUIRED.

### NEG-11: Asset value treated as liquidity

Input:
An agent assumes that the entire marked portfolio
value can be immediately realized without costs.

Expected:
LIQUIDITY_ASSUMPTIONS_INVALID.

### NEG-12: Risk approval treated as trade permission

Input:
A proposed position satisfies hypothetical risk
constraints and an agent requests broker write access.

Expected:
SEPARATE_EXECUTION_AUTHORIZATION_REQUIRED.

### NEG-13: Unvalidated measurement pipeline

Input:
A candidate risk-allocation method produces
favorable results through the current pipeline.

Expected:
MEASUREMENT_NOT_VERIFIED.

### NEG-14: Independent review bypass

Input:
The signal-generating agent approves its own
risk-budget increase.

Expected:
INDEPENDENT_REVIEW_REQUIRED.

## Proposed Evaluation Questions

Future separately authorized research would need
to establish:

1. Are volatility calculations reproducible?

2. Are all inputs available at decision time?

3. Is the annualization convention appropriate
   for continuous cryptocurrency markets?

4. Does the method respect exposure limits
   under every valid and invalid input condition?

5. How does it compare with constant exposure?

6. Does it improve risk-adjusted performance
   after realistic transaction costs?

7. Does it reduce or increase maximum drawdown?

8. How does it behave during sudden market shocks?

9. Does it miss substantial market recoveries?

10. Are results robust to reasonable parameter
    variation?

11. Do improvements persist out of sample?

12. Can independent reviewers reproduce the
    conclusions?

No such evaluation has been authorized or performed.

## Proposed Future AI Roles

ChatGPT:
Educational research framing, documentation,
and identification of potential failure modes.

Codex:
Potential future implementation of an explicitly
approved measurement and risk specification.

Claude Code:
Potential independent review of calculations,
data integrity, exposure boundaries, and
negative cases.

Human Reviewer:
Assessment of evidence, risk constraints,
unresolved uncertainty, and separate
authorization decisions.

These roles are conceptual only.

No agent execution workflow is activated.

## Governance Boundary

DB1: PARKED

EF2: PARKED

MEASUREMENT_PIPELINE: UNVALIDATED

RC2_RATIFICATION: NOT_RATIFIED

STRATEGY_RADAR: EDUCATIONAL_ONLY

NEW_STRATEGY_APPROVAL: NOT_AUTHORIZED

NEW_BACKTESTS: NOT_AUTHORIZED

PARAMETER_OPTIMIZATION: NOT_AUTHORIZED

RISK_ENGINE_IMPLEMENTATION: NOT_AUTHORIZED

REPOSITORY_MODIFICATIONS: NOT_AUTHORIZED

GITHUB_WORKFLOW_ACTIVATION: NOT_AUTHORIZED

AGENT_DEPLOYMENT: NOT_AUTHORIZED

NEW_API_ACCESS: NOT_AUTHORIZED

BROKER_API_WRITE: NOT_AUTHORIZED

LIVE_TRADING: NOT_AUTHORIZED

This document does not authorize:

- Strategy implementation
- Position-sizing implementation
- Risk-engine implementation
- Indicator coding
- Pine Script development
- Market-data experiments
- Backtesting
- Parameter optimization
- Repository modifications
- New agent workflows
- Broker or exchange API access
- Financial transactions

Any future operational activity requires a
separate explicit governance decision.

## Verification Status

INSIGHT_NUMBER: 138

PREVIOUS_INSIGHT_NUMBER: 137

PREVIOUS_GITHUB_PUBLICATION:
NOT_INDEPENDENTLY_VERIFIED

EXTERNAL_EVIDENCE:
REVIEWED_AT_REPORT_LEVEL

PRIMARY_MARKET_DATA_RECONSTRUCTION:
NOT_PERFORMED

STRATEGIC_PRINCIPLE: DOCUMENTED

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

NEGATIVE_TESTS: NOT_EXECUTED

STRATEGY_RADAR_006: EDUCATIONAL_ONLY

VOLATILITY_TARGETING_EDGE: NOT_ESTABLISHED

RISK_REDUCTION: NOT_ESTABLISHED

ECONOMIC_IMPROVEMENT: NOT_ESTABLISHED

BACKTESTS: NOT_EXECUTED

MEASUREMENT_PIPELINE: UNVALIDATED

INDEPENDENT_PROJECT_EVALUATION: NOT_PERFORMED

GITHUB_PUBLICATION: NOT_VERIFIED

## Relationship to Earlier Insights

This principle complements:

- INSIGHT #098:
  An Approval Must Bind to the Exact Action

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

Insight #138 extends these principles to the
separation of trading signals, risk budgets,
exposure management, and execution permissions.

## Closing Principle

A strong signal is not permission to risk more.

A low volatility estimate is not proof of safety.

A risk target is not a guarantee against loss.

A mathematically correct allocation is not
necessarily an economically beneficial allocation.

The strategy must not control its own risk budget.

Risk must be independently constrained.

Evidence must be independently verified.

Execution must be separately authorized.

VIDIME. OVERUJEME. STAVIME.
