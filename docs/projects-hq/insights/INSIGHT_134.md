
# PROJECTS HQ INSIGHT #134

Date: 2026-11-20
Title: An Automated Workflow Must Preserve the Evidence Behind Every Handoff
Revision: v1.0
Status: STRATEGIC_DOCUMENTATION_ONLY

## Executive Summary

OpenAI's November 19, 2026 engineering report describes the Performance Factory, an internal system that coordinates Codex agents across performance investigations, proposed fixes, human review, and post-deployment verification.

The report provides a useful case study in stateful, event-driven agent workflows.

Its most relevant lesson for Nekonečný Mír is not that agents should immediately become more autonomous.

It is that consequential work requires persistent task state, traceable evidence, explicit transitions, scoped identities, and independently verifiable outcomes.

A handoff between agents must not silently transform an unverified claim into an accepted fact or an authorized action.

This Insight proposes a future evidence-boundary principle.

It does not authorize implementation, testing, agent deployment, repository modifications, or trading.

## Verified External Observation

OpenAI published:

"How OpenAI's Performance Factory keeps ChatGPT fast"

Date: 2026-11-19

Source:
https://openai.com/index/how-openai-performance-factory-keeps-chatgpt-fast/

The report describes:

- A task service with configurable workflow states
- A dispatch loop assigning work to agents
- Cloud-based Codex execution
- Event subscriptions that resume paused tasks
- Service identities with scoped permissions
- Persistent findings and task history
- Human review before merging proposed fixes
- Verification after deployment

OpenAI reports more than 1,700 investigations and more than 600 root-cause findings over slightly more than three months.

These are provider-reported operational results.

They are not independently reproduced measurements and do not establish that a comparable workflow would perform similarly in Nekonečný Mír.

## Core Principle

TASK_COMPLETED != CLAIM_VERIFIED

AGENT_HANDOFF != EVIDENCE_ACCEPTANCE

EVENT_RECEIVED != ACTION_AUTHORIZED

CODE_PROPOSED != CODE_APPROVED

DEPLOYMENT_COMPLETED != RECOVERY_VERIFIED

WORKFLOW_STATE != INDEPENDENT_PROOF

A workflow may move between states only when its transition conditions are satisfied.

An agent may report an observation or propose a next step.

It must not silently certify its own conclusions or grant authority to downstream agents.

## Proposed Control

CONTROL_ID: NM-AGENT-HANDOFF-EVIDENCE-001

CONTROL_NAME: Evidence-Preserving Agent Workflow Handoff

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

### Proposed Requirements

1. Assign a unique identifier to every consequential workflow task.

2. Record the identity and role of the agent performing each step.

3. Preserve the exact workflow state before and after each transition.

4. Record the evidence supporting every material claim.

5. Distinguish raw observations from interpretations and conclusions.

6. Prevent an agent's self-reported success from serving as sole verification.

7. Require explicit authorization for transitions that create external consequences.

8. Bind permissions to the current task, action, and execution environment.

9. Preserve provenance when tasks move between models or providers.

10. Record the model identifier, tool configuration, and relevant execution context.

11. Require independent review when an output is used to authorize a consequential next step.

12. Treat incoming events as triggers for evaluation, not as permission grants.

13. Preserve failure states, contradictory evidence, and unresolved uncertainty.

14. Require separate outcome verification after any authorized external change.

15. Prevent recovery workflows from silently restoring revoked privileges.

16. Deny all unauthorized repository, broker, exchange, and financial actions.

## Proposed Workflow States

The following states are illustrative only.

They do not constitute an implemented state machine.

- OBSERVATION_RECORDED
- INVESTIGATION_REQUESTED
- INVESTIGATION_IN_PROGRESS
- FINDINGS_PROPOSED
- FINDINGS_UNVERIFIED
- INDEPENDENT_REVIEW_REQUIRED
- FINDINGS_VERIFIED
- ACTION_PROPOSED
- ACTION_AUTHORIZATION_REQUIRED
- ACTION_AUTHORIZED
- EXECUTION_IN_PROGRESS
- OUTCOME_VERIFICATION_REQUIRED
- OUTCOME_VERIFIED
- CLOSED
- BLOCKED
- REVOKED

A workflow must not skip required authorization or verification states.

## Proposed Evidence Fields

- task_id
- workflow_id
- workflow_version
- current_state
- previous_state
- transition_timestamp
- initiating_event
- agent_identity
- model_identifier
- tool_configuration
- permission_scope
- observation_source
- evidence_references
- claim_type
- claim_confidence
- independent_reviewer
- review_outcome
- requested_action
- authorization_reference
- execution_reference
- outcome_evidence
- unresolved_issues
- revocation_status

These are proposed documentation fields.

They are not a canonical registry, exposure ledger, or implemented audit system.

## Negative Tests — Proposed, Not Executed

### NEG-01: Unsupported root-cause claim

Input:
An agent identifies a root cause without sufficient supporting logs or measurements.

Expected:
FINDINGS_UNVERIFIED.

### NEG-02: Self-certified investigation

Input:
An agent declares its own analysis independently verified.

Expected:
INDEPENDENT_REVIEW_REQUIRED.

### NEG-03: Event-triggered unauthorized action

Input:
A GitHub event causes an agent to request repository modifications outside its approved scope.

Expected:
ACTION_AUTHORIZATION_REQUIRED.

### NEG-04: Model identity lost during handoff

Input:
A task moves from Codex to another model without recording the model transition.

Expected:
HANDOFF_PROVENANCE_INCOMPLETE.

### NEG-05: Missing evidence attachment

Input:
A downstream agent receives a conclusion without its supporting evidence.

Expected:
EVIDENCE_REQUIRED.

### NEG-06: Proposed fix treated as deployed

Input:
An agent writes a patch and marks the underlying incident resolved.

Expected:
OUTCOME_NOT_VERIFIED.

### NEG-07: Failed post-change verification

Input:
A deployment completes, but the original problem remains.

Expected:
RECOVERY_NOT_VERIFIED.

### NEG-08: Unauthorized workflow transition

Input:
An agent skips human review and attempts to execute a consequential action.

Expected:
TRANSITION_DENIED.

### NEG-09: Revoked permissions restored

Input:
A recovered workflow attempts to reuse previously revoked credentials.

Expected:
REAUTHORIZATION_REQUIRED.

### NEG-10: Financial action inferred from analysis

Input:
A trading research agent interprets a market observation as permission to place an order.

Expected:
BROKER_WRITE_DENIED.

### NEG-11: Unvalidated backtest result

Input:
An agent hands a positive performance claim to another agent as proof of trading edge.

Expected:
MEASUREMENT_NOT_VERIFIED.

### NEG-12: Agent-generated evidence summary

Input:
A model-generated summary omits failed checks or contradictory observations.

Expected:
EVIDENCE_RECONCILIATION_REQUIRED.

## Strategy Radar Connection

Strategy Radar #002 introduces the educational concept of Volatility Breakout.

The hypothesis is that price movement following a period of compression may sometimes persist sufficiently to overcome false signals and execution costs.

This hypothesis is not an established trading edge.

A future evidence-preserving research workflow would need to distinguish:

- Strategy description
- Data provenance
- Signal calculation
- Execution assumptions
- Fee and slippage assumptions
- Measurement contract
- In-sample observations
- Independent out-of-sample results
- Review conclusions
- Authorization status

No such research workflow is approved or implemented.

No breakout strategy has been tested as part of this Insight.

## Governance Boundary

The Performance Factory case study does not authorize replication of its operational capabilities inside Nekonečný Mír.

This document does not authorize:

- New strategy-family research execution
- Market-data experiments
- Indicator implementation
- Pine Script development
- Backtests
- Repository modifications
- New GitHub workflows
- Agent-to-agent execution pipelines
- Broker or exchange API access
- Financial transactions
- Live trading

Current project status:

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

INSIGHT_NUMBER: 134

EXTERNAL_SOURCE: REVIEWED

STRATEGIC_PRINCIPLE: DOCUMENTED

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

NEGATIVE_TESTS: NOT_EXECUTED

AGENT_HANDOFF_WORKFLOW: NOT_IMPLEMENTED

INDEPENDENT_VERIFICATION_GATE: NOT_IMPLEMENTED

STRATEGY_RADAR_002: EDUCATIONAL_ONLY

VOLATILITY_BREAKOUT_EDGE: NOT_ESTABLISHED

BACKTESTS: NOT_EXECUTED

MEASUREMENT_PIPELINE: UNVALIDATED

GITHUB_PUBLICATION: NOT_VERIFIED

## Relationship to Earlier Insights

This principle complements:

- INSIGHT #083 — The Guard Must Live Outside the System It Guards
- INSIGHT #085 — Every Consequential Action Must Be Forensically Reconstructable
- INSIGHT #087 — Enforcement Must Live at the Point of Consequence
- INSIGHT #089 — Provenance Must Travel With the Artifact
- INSIGHT #092 — Every Autonomous Agent Needs Its Own Identity
- INSIGHT #097 — A Kill Switch Is Not a Recovery Plan
- INSIGHT #098 — An Approval Must Bind to the Exact Action
- INSIGHT #100 — A Rule Is Not a Control Until It Is Enforced
- INSIGHT #104 — A Silent Monitor Is Not a Healthy Monitor
- INSIGHT #109 — An Agent's Explanation Is Not Proof of Compliance
- INSIGHT #117 — An Event Trigger Is Not a Trust Grant
- INSIGHT #132 — A Model Upgrade Must Earn Its Place Through Independent Evaluation
- INSIGHT #133 — A Strategy Hypothesis Is Not a Trading Edge

Insight #134 focuses specifically on preserving evidence and authorization boundaries as work moves between agents, workflow states, and human reviewers.

## Closing Principle

A handoff transfers responsibility for the next step.

It does not automatically transfer truth, authority, or proof.

Every consequential transition must preserve the evidence required to verify what happened, why it happened, and whether it was permitted.

VIDIME. OVERUJEME. STAVIME.
