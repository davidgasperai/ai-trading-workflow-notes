
# PROJECTS HQ INSIGHT #136

Date: 2026-11-22
Title: A Benchmark Must Measure the Decision That Matters
Revision: v1.0
Status: STRATEGIC_DOCUMENTATION_ONLY

## Executive Summary

A benchmark is useful only when its measurements correspond to the decisions for which a system will be trusted.

On November 20, 2026, OpenAI introduced MedChemBench, a benchmark designed to evaluate AI reasoning in medicinal chemistry.

The benchmark focuses on interpreting molecular structures, experimental evidence, compound comparisons, and decisions about what to investigate next.

Its relevance to Nekonečný Mír is methodological rather than pharmaceutical.

General model capability does not establish competence in a particular operational domain.

A model may perform well on programming tasks while failing to identify invalid market data, flawed statistical assumptions, or unauthorized financial actions.

Future evaluations of AI-assisted trading systems should therefore measure the specific decisions and failure modes that matter.

This Insight documents a proposed domain-specific evaluation principle.

It does not authorize new tests, strategy implementation, repository modifications, agent deployment, or trading.

## External Evidence

### Primary Source

OpenAI Research
November 20, 2026

Can AI help scientists identify promising drug candidates?

https://openai.com/index/introducing-medchembench/

OpenAI introduced MedChemBench to evaluate reasoning tasks derived from medicinal chemistry research.

The benchmark examines the ability to:

- Interpret molecular structures
- Connect experimental results to explanations
- Compare candidate compounds
- Reason about competing properties
- Select potential next research directions

The benchmark illustrates why domain-specific evaluations can reveal limitations that general-purpose benchmarks may not capture.

OpenAI's published evaluation results are provider-reported.

They do not establish that AI systems can autonomously discover medicines or reliably make real-world laboratory decisions.

### Additional Engineering Context

OpenAI Engineering
November 19, 2026

How OpenAI's Performance Factory keeps ChatGPT fast

https://openai.com/index/how-openai-performance-factory-keeps-chatgpt-fast/

The report describes AI-assisted production investigations, adversarial review, and verification after changes.

The combination of domain-specific evaluation and independent review suggests a broader principle:

A model should be evaluated on the exact class of decisions for which it may eventually receive operational responsibility.

## Core Principle

GENERAL_BENCHMARK_SCORE != DOMAIN_COMPETENCE

DOMAIN_COMPETENCE != OPERATIONAL_RELIABILITY

CORRECT_CODE != CORRECT_STRATEGY

VALID_CALCULATION != PROFITABLE_DECISION

HIGH_MODEL_CONFIDENCE != VERIFIED_EVIDENCE

BENCHMARK_SUCCESS != DEPLOYMENT_AUTHORIZATION

A benchmark must measure the behavior that matters for the intended task.

Its measurement contract, evaluation data, scoring criteria, failure modes, and limitations must be documented before results are interpreted.

## Proposed Control

CONTROL_ID: NM-DOMAIN-EVALUATION-001

CONTROL_NAME: Decision-Relevant Benchmark Contract

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

### Proposed Requirements

1. Define the intended decision before selecting an evaluation.

2. Identify the specific capability being measured.

3. Document the evaluation's relationship to real operational tasks.

4. Establish scoring criteria independently of candidate model outputs.

5. Preserve evaluation data provenance.

6. Prevent future information from entering historical decision contexts.

7. Separate general coding capability from financial reasoning capability.

8. Distinguish correct calculations from correct interpretation.

9. Include negative cases and known failure modes.

10. Evaluate uncertainty handling and appropriate abstention.

11. Record tool access, model configuration, and execution conditions.

12. Prevent model-generated explanations from serving as sole verification.

13. Require independent review of consequential claims.

14. Record limitations of sample size and representativeness.

15. Prevent benchmark performance from granting execution privileges.

16. Preserve existing project governance restrictions.

## Proposed Evaluation Dimensions

Future authorized evaluations might distinguish:

### Calculation Correctness

Can an agent compute a specified indicator correctly?

### Data Integrity

Can an agent detect missing, duplicated, delayed, or inconsistent market observations?

### Temporal Integrity

Can an agent avoid look-ahead bias and future-data leakage?

### Statistical Reasoning

Can an agent distinguish correlation, overfitting, and unsupported causal claims?

### Economic Realism

Can an agent account for transaction costs, slippage, liquidity, and execution uncertainty?

### Risk Interpretation

Can an agent recognize exposure limits, concentration risk, and adverse market conditions?

### Authorization Awareness

Can an agent correctly refuse actions outside its approved permissions?

### Evidence Quality

Can an agent distinguish observations, provider claims, hypotheses, and independently verified conclusions?

These dimensions are proposed research concepts only.

No evaluation suite is approved or implemented.

## Proposed Evidence Fields

- evaluation_id
- intended_decision
- domain
- capability_under_test
- measurement_contract_version
- dataset_provenance
- dataset_time_boundary
- scoring_method
- model_identifier
- model_configuration
- tool_permissions
- expected_behavior
- observed_behavior
- independent_review_status
- failure_classification
- uncertainty_notes
- reproducibility_status
- authorization_status

These fields are not an implemented registry.

## Negative Tests — Proposed, Not Executed

### NEG-01: General benchmark substitution

Input:
A model scores highly on a general coding benchmark and is declared suitable for trading decisions.

Expected:
DOMAIN_COMPETENCE_NOT_ESTABLISHED.

### NEG-02: Correct indicator, incorrect decision

Input:
An agent calculates momentum correctly but claims the indicator guarantees future returns.

Expected:
TRADING_EDGE_NOT_ESTABLISHED.

### NEG-03: Data contamination

Input:
An evaluation includes future prices unavailable at the historical decision point.

Expected:
EVALUATION_CONTAMINATED.

### NEG-04: Self-defined scoring

Input:
A candidate model chooses evaluation criteria that favor its own outputs.

Expected:
INDEPENDENT_SCORING_REQUIRED.

### NEG-05: Unrepresentative dataset

Input:
A model is evaluated only during favorable market regimes.

Expected:
REPRESENTATIVENESS_INSUFFICIENT.

### NEG-06: Missing execution costs

Input:
A trading strategy is judged profitable before fees and slippage.

Expected:
ECONOMIC_VIABILITY_NOT_ESTABLISHED.

### NEG-07: Incorrect confidence

Input:
An agent presents a weakly supported prediction as certain.

Expected:
UNCERTAINTY_HANDLING_FAILURE.

### NEG-08: Benchmark-to-permission escalation

Input:
A model passes an evaluation and requests broker write access.

Expected:
SEPARATE_AUTHORIZATION_REQUIRED.

### NEG-09: Inconsistent model comparison

Input:
Two models are compared using different data, tools, or scoring rules.

Expected:
MEASUREMENT_CONTRACT_MISMATCH.

### NEG-10: Unsupported financial conclusion

Input:
An agent claims a momentum strategy has positive expected returns without independently verifiable evidence.

Expected:
EDGE_NOT_ESTABLISHED.

### NEG-11: Ignored adverse regime

Input:
A strategy succeeds in persistent trends but fails during reversals.

Expected:
REGIME_DEPENDENCE_UNRESOLVED.

### NEG-12: Unvalidated pipeline

Input:
A model produces attractive results through the existing unvalidated measurement pipeline.

Expected:
MEASUREMENT_NOT_VERIFIED.

## Strategy Radar Connection

Strategy Radar #004 introduces Momentum.

The educational hypothesis is that past directional price movement may contain information about subsequent movement under some market conditions.

A possible future research specification could use historical returns or a rate-of-change indicator.

However:

- Positive momentum does not guarantee further gains.
- Negative momentum does not guarantee further losses.
- Parameter selection can overfit historical outcomes.
- Transaction costs can eliminate apparent advantages.
- Sudden reversals can cause significant losses.
- Market regimes can change the relationship between past and future returns.

A future domain-specific evaluation would need to distinguish:

1. Correct signal computation
2. Valid data handling
3. Realistic execution assumptions
4. Statistical robustness
5. Independent out-of-sample evidence
6. Risk and failure-mode awareness
7. Authorization compliance

No momentum strategy has been implemented or backtested under this Insight.

MOMENTUM_EDGE: NOT_ESTABLISHED.

## Proposed Future AI Roles

ChatGPT:
Educational research framing and evaluation specification.

Codex:
Potential implementation of precisely defined calculations after separate authorization.

Claude Code:
Potential independent review of calculations, data handling, and assumptions after separate authorization.

Human Reviewer:
Assessment of evidence and explicit governance decisions.

These are conceptual roles only.

No new execution workflow is activated.

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

This Insight does not authorize:

- Market-data experiments
- Strategy implementation
- Indicator coding
- Pine Script development
- Backtesting
- Parameter optimization
- Repository changes
- Agent execution workflows
- Broker or exchange API writes
- Live financial transactions

Any future authorization requires a separate explicit decision.

## Verification Status

INSIGHT_NUMBER: 136

EXTERNAL_SOURCE: REVIEWED

STRATEGIC_PRINCIPLE: DOCUMENTED

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

NEGATIVE_TESTS: NOT_EXECUTED

DOMAIN_EVALUATION_SUITE: NOT_IMPLEMENTED

STRATEGY_RADAR_004: EDUCATIONAL_ONLY

MOMENTUM_EDGE: NOT_ESTABLISHED

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
- INSIGHT #125 — New Model Availability Is Not Operational Approval
- INSIGHT #132 — A Model Upgrade Must Earn Its Place Through Independent Evaluation
- INSIGHT #133 — A Strategy Hypothesis Is Not a Trading Edge
- INSIGHT #134 — An Automated Workflow Must Preserve the Evidence Behind Every Handoff
- INSIGHT #135 — A Plausible Explanation Must Survive an Attempt to Disprove It

Insight #136 focuses on evaluating models against the actual decisions and failure modes relevant to their intended domain.

## Closing Principle

A model should not be trusted because it performs well on an unrelated test.

A strategy should not be trusted because its chart looks convincing.

An automated decision should not be trusted because its explanation sounds intelligent.

Measure the decision that matters.

Verify the evidence independently.

Authorize consequential actions separately.

VIDIME. OVERUJEME. STAVIME.
