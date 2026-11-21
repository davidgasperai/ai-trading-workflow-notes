
# PROJECTS HQ INSIGHT #135

Date: 2026-11-21
Title: A Plausible Explanation Must Survive an Attempt to Disprove It
Revision: v1.0
Status: STRATEGIC_DOCUMENTATION_ONLY

## Executive Summary

A plausible explanation is not necessarily a correct explanation.

OpenAI's Performance Factory engineering report describes how Codex agents investigate production regressions and how separate adversarial review sessions challenge their diagnoses.

In a manual assessment of 100 root-cause suggestions, OpenAI reported that approximately 70% were accurate while 30% required refinement or did not fully establish causality.

This observation illustrates a critical problem for AI-assisted research and software engineering.

An agent can produce a coherent narrative that appears supported by evidence while overlooking contradictory information or alternative explanations.

The same risk applies to trading research.

A strategy may appear profitable because of a favorable historical period, selective parameter choices, omitted execution costs, or information that would not have been available at decision time.

Nekonečný Mír should distinguish between generating a hypothesis and attempting to falsify it.

This Insight documents a proposed adversarial-evaluation principle.

It does not authorize new tests, implementations, repository changes, agent deployments, or trading.

## External Evidence

### Primary Source

OpenAI Engineering
November 19, 2026

How OpenAI's Performance Factory keeps ChatGPT fast

https://openai.com/index/how-openai-performance-factory-keeps-chatgpt-fast/

The report describes:

- Automated investigation of performance regressions
- Persistent task records
- Separate Codex sessions reviewing proposed diagnoses
- Counterfactual reasoning
- Independent review of proposed fixes
- Human approval of consequential changes
- Verification after deployment
- Historical evaluation cases with controlled evidence access

OpenAI reports that an adversarial reviewer can reopen an investigation when the proposed diagnosis fails to explain observed behavior.

The 70% figure comes from an internal manual assessment of 100 root-cause suggestions.

It is not a general-purpose accuracy benchmark for Codex.

### Market Context

Reuters
November 20-21, 2026

Bitcoin fell below USD 60,000 during Friday's market sell-off.

A subsequent Reuters price report recorded approximately USD 55,830 at 04:13 UTC on November 21.

Sources:

https://www.reuters.com/technology/bitcoin-falls-below-60000-level-2026-11-20/

https://www.streetinsider.com/Reuters/Bitcoin%2Bfalls%2B3.57%25%2Bto%2B%2456%2C814/27382851.html

These are historical observations, not current prices or trading signals.

## Core Principle

PLAUSIBLE_EXPLANATION != VERIFIED_CAUSALITY

CORRELATION != CAUSATION

AGENT_CONFIDENCE != EVIDENCE_STRENGTH

HISTORICAL_SUCCESS != REPEATABLE_EDGE

FAILED_FALSIFICATION_ATTEMPT != UNIVERSAL_PROOF

REVIEW_COMPLETED != ACTION_AUTHORIZED

A consequential claim should be supported by evidence that has survived appropriate attempts to disprove it.

An adversarial reviewer must not merely agree with the original agent.

The reviewer should actively search for missing evidence, contradictory observations, alternative explanations, and invalid assumptions.

## Proposed Control

CONTROL_ID: NM-ADVERSARIAL-EVIDENCE-001

CONTROL_NAME: Independent Hypothesis Falsification Gate

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

### Proposed Requirements

1. State the original hypothesis explicitly.

2. Record the evidence supporting the hypothesis.

3. Record known uncertainty and competing explanations.

4. Define what observations would contradict the hypothesis.

5. Assign independent review to a separate evaluation context.

6. Preserve the reviewer's access boundaries and tool configuration.

7. Prevent the reviewer from inheriting unsupported conclusions as facts.

8. Require the reviewer to examine counterexamples and alternative causes.

9. Record the evidence supporting or weakening each competing explanation.

10. Distinguish a failed attempt to falsify a claim from proof that the claim is universally true.

11. Prevent the original agent from approving its own conclusions.

12. Preserve disagreements and unresolved questions.

13. Require independent evaluation before consequential promotion of findings.

14. Separate evidence acceptance from execution authorization.

15. Preserve the project's existing restrictions on research, implementation, and trading.

## Proposed Evidence Fields

- hypothesis_id
- hypothesis_statement
- originating_agent
- originating_model
- evidence_sources
- supporting_observations
- alternative_explanations
- falsification_conditions
- reviewer_identity
- reviewer_model
- reviewer_tool_scope
- contradictory_evidence
- review_findings
- unresolved_uncertainty
- measurement_contract_status
- independent_verification_status
- authorization_status
- decision_reference

These fields describe a proposed evidence structure.

They are not an implemented canonical registry.

## Negative Tests — Proposed, Not Executed

### NEG-01: Persuasive but unsupported explanation

Input:
An agent presents a convincing explanation without sufficient source evidence.

Expected:
EVIDENCE_INSUFFICIENT.

### NEG-02: Reviewer simply agrees

Input:
A reviewer repeats the original agent's conclusion without independent examination.

Expected:
ADVERSARIAL_REVIEW_INCOMPLETE.

### NEG-03: Contradictory observation ignored

Input:
The proposed explanation cannot account for an important observation.

Expected:
HYPOTHESIS_REOPENED.

### NEG-04: Alternative cause omitted

Input:
Multiple explanations fit the evidence, but only one is evaluated.

Expected:
ALTERNATIVE_EXPLANATIONS_REQUIRED.

### NEG-05: Correlation promoted to causality

Input:
Two variables move together and an agent claims one caused the other.

Expected:
CAUSALITY_NOT_ESTABLISHED.

### NEG-06: Reviewer contaminated by future evidence

Input:
A historical evaluation uses information that was unavailable at the original decision time.

Expected:
EVALUATION_CONTAMINATED.

### NEG-07: Trading edge inferred from a chart

Input:
An agent identifies a visually attractive historical price pattern.

Expected:
EDGE_NOT_ESTABLISHED.

### NEG-08: Transaction costs omitted

Input:
A strategy appears profitable before fees and slippage.

Expected:
ECONOMIC_VIABILITY_NOT_ESTABLISHED.

### NEG-09: Parameter overfitting

Input:
An agent selects parameters solely because they maximize historical profit.

Expected:
OVERFITTING_REVIEW_REQUIRED.

### NEG-10: Market regime dependence ignored

Input:
A strategy works in sideways markets but loses heavily during strong trends.

Expected:
REGIME_RISK_UNRESOLVED.

### NEG-11: Independent review treated as permission

Input:
An agent interprets a favorable review as authorization to modify a repository or execute trades.

Expected:
ACTION_AUTHORIZATION_REQUIRED.

### NEG-12: Self-generated success criteria

Input:
A candidate strategy defines and grades its own evaluation criteria.

Expected:
INDEPENDENT_EVALUATION_REQUIRED.

## Strategy Radar Connection

Strategy Radar #003 introduces Mean Reversion.

The educational hypothesis is that some temporary price deviations may partially reverse.

Possible implementations might use moving averages, volatility bands, or normalized deviations from a reference price.

However, a large price deviation does not guarantee reversal.

A sustained trend may cause repeated losses.

A sharp market decline may reflect a persistent change in information, liquidity, leverage, or risk appetite.

The relevant falsification questions include:

- Does the proposed effect survive realistic trading costs?
- Does it persist across different market regimes?
- Does it survive independent out-of-sample evaluation?
- Is it robust to reasonable parameter changes?
- Is the signal constructed without future information?
- Can it withstand extended adverse price movement?
- Does the result depend on a small number of favorable episodes?
- Are execution assumptions realistic during market stress?

No Mean Reversion strategy has been implemented or backtested under this Insight.

The hypothesis remains unverified.

## Proposed Roles for Future AI Tools

The following roles are conceptual only.

ChatGPT:
Research framing and hypothesis documentation.

Codex:
Potential future implementation of precisely specified calculations after authorization.

Claude Code:
Potential independent review of calculations, assumptions, and failure cases after authorization.

Human Reviewer:
Assessment of evidence, unresolved uncertainty, and any separate authorization decisions.

No role is activated by this document.

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

- New market-data experiments
- Strategy implementation
- Indicator coding
- Pine Script development
- Backtesting
- Parameter optimization
- Repository changes
- Agent execution workflows
- Broker or exchange API writes
- Live financial transactions

Any future change requires a separate explicit governance decision.

## Verification Status

INSIGHT_NUMBER: 135

EXTERNAL_EVIDENCE: REVIEWED

STRATEGIC_PRINCIPLE: DOCUMENTED

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

NEGATIVE_TESTS: NOT_EXECUTED

ADVERSARIAL_EVALUATION_GATE: NOT_IMPLEMENTED

STRATEGY_RADAR_003: EDUCATIONAL_ONLY

MEAN_REVERSION_EDGE: NOT_ESTABLISHED

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
- INSIGHT #103 — A Refactor Must Prove Behavioral Equivalence
- INSIGHT #109 — An Agent's Explanation Is Not Proof of Compliance
- INSIGHT #132 — A Model Upgrade Must Earn Its Place Through Independent Evaluation
- INSIGHT #133 — A Strategy Hypothesis Is Not a Trading Edge
- INSIGHT #134 — An Automated Workflow Must Preserve the Evidence Behind Every Handoff

Insight #135 focuses on independent attempts to falsify plausible claims before they are accepted as verified evidence.

## Closing Principle

A convincing explanation can still be wrong.

An attractive strategy can still lose money.

A successful historical test can still be misleading.

The objective is not to defend the first plausible hypothesis.

The objective is to discover whether it survives serious, independent attempts to disprove it.

VIDIME. OVERUJEME. STAVIME.
