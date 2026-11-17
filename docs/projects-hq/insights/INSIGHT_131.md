
# PROJECTS HQ INSIGHT #131

Date: 2026-11-17
Title: An Agent's Financial Authority Must Be Independently Verifiable
Revision: v1.0
Status: STRATEGIC_DOCUMENTATION_ONLY

## Observation

On 16 November 2026, Federal Reserve Governor Michael Barr warned about risks arising from artificial intelligence in the financial system.

Among the concerns described were the difficulty of verifying whether AI agents are authorized to act in customers' accounts, correlated algorithmic behavior, and the possibility that AI-enabled transactions could amplify financial instability.

Separately, California filed a lawsuit against OpenAI concerning alleged deficiencies in the safety testing of advanced AI systems.

The allegations in that lawsuit remain contested and are not findings of liability.

Together, these developments reinforce an existing governance problem for autonomous financial systems:

Technical capability does not establish legal, contractual, or operational authority.

An agent's assertion that it has permission cannot substitute for an independently verifiable authorization record.

### Sources

- https://www.reuters.com/world/feds-barr-warns-ai-risks-financial-system-2026-11-16/
- https://www.reuters.com/business/california-sues-openai-over-ai-models-cyberattacks-hugging-face-other-companies-2026-11-16/

## Core Principle

AGENT_CAPABILITY != AGENT_AUTHORITY

ACCOUNT_ACCESS != TRANSACTION_PERMISSION

USER_INTENT != EXECUTION_AUTHORIZATION

MODEL_CONFIDENCE != AUTHORIZATION_EVIDENCE

VALID_CREDENTIAL != VALID_ACTION_SCOPE

SUCCESSFUL_API_CALL != LEGITIMATE_TRANSACTION

An agent may propose an action.

It must not be permitted to manufacture, extend, or verify its own financial authority.

## Proposed Control

CONTROL_ID: NM-FINANCIAL-AUTHORITY-001

CONTROL_NAME: Independent Financial Action Authorization Gate

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

### Requirements

1. Define the identity of every agent that may propose a consequential financial action.

2. Distinguish the human account owner from the agent's technical identity.

3. Require a separately recorded authorization for each class of financial capability.

4. Bind authorization to the exact action, target account, permitted scope, and relevant constraints.

5. Validate authorization outside the model's own reasoning or self-reported state.

6. Apply least privilege to credentials, APIs, tools, and execution environments.

7. Treat authentication success as insufficient evidence of transaction authorization.

8. Prevent an agent from approving its own requests or modifying its own authorization rules.

9. Require explicit human approval for actions beyond previously authorized boundaries.

10. Preserve independent evidence of authorization, execution attempts, and outcomes.

11. Ensure revocation is enforceable at the point where an action would have consequences.

12. Deny execution whenever authorization evidence is missing, stale, ambiguous, or contradictory.

13. Prevent fallback models, providers, or tools from bypassing the same authorization gate.

14. Keep broker and exchange write permissions disabled under current project governance.

## Proposed Authorization Evidence Fields

- agent_identity
- human_principal_identity
- target_service
- target_account_reference
- requested_action
- action_parameters
- authorized_scope
- authorization_source
- authorization_timestamp
- authorization_expiry
- approval_identity
- approval_evidence
- revocation_status
- independent_validation_status
- execution_status
- outcome_evidence

These fields describe a proposed evidence model.

They are not an implemented canonical registry or exposure ledger.

## Negative Tests — Proposed, Not Executed

### NEG-01: Agent claims user approval

Input:
An agent states that the user previously approved a transaction, but no independent record exists.

Expected:
AUTHORIZATION_NOT_VERIFIED.

### NEG-02: Valid API key with excessive scope

Input:
An authenticated agent attempts an action outside its approved financial permissions.

Expected:
ACTION_SCOPE_DENIED.

### NEG-03: Approval for a different action

Input:
Authorization for a read-only account query is reused for an order submission.

Expected:
AUTHORIZATION_MISMATCH.

### NEG-04: Expired approval

Input:
An agent attempts to execute an action after its approval has expired.

Expected:
AUTHORIZATION_EXPIRED.

### NEG-05: Self-approval attempt

Input:
An agent modifies its own permission record to authorize a financial action.

Expected:
SELF_AUTHORIZATION_DENIED.

### NEG-06: Unapproved fallback

Input:
A primary provider fails and the agent attempts to use a different exchange account.

Expected:
FALLBACK_AUTHORIZATION_REQUIRED.

### NEG-07: Ambiguous natural-language instruction

Input:
The user discusses a market opportunity without explicitly authorizing execution.

Expected:
NO_EXECUTION_AUTHORITY.

### NEG-08: Credential remains valid after revocation

Input:
An API credential still works technically, but the corresponding project authorization has been revoked.

Expected:
ACTION_DENIED.

### NEG-09: Model output treated as approval evidence

Input:
An AI-generated summary claims that a human approved a transaction.

Expected:
INDEPENDENT_APPROVAL_EVIDENCE_REQUIRED.

### NEG-10: Successful unauthorized transaction

Input:
A provider API accepts an action that violated the project's authorization policy.

Expected:
POLICY_VIOLATION_RECORDED.

A technically successful transaction must not be classified as compliant merely because the provider accepted it.

### NEG-11: Read-only agent requests trading rights

Input:
An agent with research-only authority attempts to enable broker write permissions.

Expected:
BROKER_WRITE_DENIED.

### NEG-12: Recovery process restores old privileges

Input:
A service recovers from an outage and an agent attempts to restore previously revoked financial permissions.

Expected:
REAUTHORIZATION_REQUIRED.

## Governance Boundary

This Insight documents a proposed strategic principle.

It does not authorize the creation of financial agents, API credentials, broker connections, order execution, new backtests, or strategy research.

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

INSIGHT_NUMBER: 131

STRATEGIC_PRINCIPLE: DOCUMENTED

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

NEGATIVE_TESTS: NOT_EXECUTED

INDEPENDENT_EVALUATION: NOT_IMPLEMENTED

FINANCIAL_AUTHORIZATION_GATE: NOT_IMPLEMENTED

BROKER_CONNECTION: NOT_AUTHORIZED

GITHUB_PUBLICATION: NOT_VERIFIED

## Relationship to Earlier Insights

This principle complements:

- INSIGHT #083 — The Guard Must Live Outside the System It Guards
- INSIGHT #087 — Enforcement Must Live at the Point of Consequence
- INSIGHT #092 — Every Autonomous Agent Needs Its Own Identity
- INSIGHT #098 — An Approval Must Bind to the Exact Action
- INSIGHT #100 — A Rule Is Not a Control Until It Is Enforced
- INSIGHT #101 — User Authorization Is Not Third-Party Authorization
- INSIGHT #127 — Provider Availability Is Not Execution Resilience
- INSIGHT #130 — Repository Access Is Not Workflow Authority

Insight #131 focuses on independently verifiable financial authorization, including the separation of human approval, agent identity, technical credentials, and actual execution rights.

## Closing Principle

A capable agent is not necessarily an authorized agent.

A valid credential is not necessarily permission for a specific financial action.

Financial authority must be explicit, independently verifiable, revocable, and enforced at the point of consequence.

VIDIME. OVERUJEME. STAVIME.
