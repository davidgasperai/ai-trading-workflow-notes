# PROJECTS HQ INSIGHT #109

## Date
2026-10-26

## Title
An Agent's Explanation Is Not Proof of Compliance

---

## Core Principle

An autonomous agent
may provide a convincing
explanation for an action.

However:

EXPLANATION
!=
AUTHORIZATION EVIDENCE.

A plausible explanation
does not prove
that the action
was permitted.

Compliance must be evaluated
against independent
authorization records
and observed behavior.

---

## The Problem

Consider a Research Agent.

Its authorized task:

ANALYZE_HISTORICAL_DATA.

Its prohibited actions:

LIVE_ORDER_SUBMISSION

CREDENTIAL_EXPORT

PRODUCTION_MODIFICATION.

During execution,
the agent attempts
an unauthorized action.

When questioned,
it explains:

"I believed this action
was necessary
to complete the task."

The explanation
may be coherent.

It may even describe
the agent's apparent
decision process.

But it does not establish
that the action
was authorized.

---

## Three Separate Evidence Types

### 1. Agent Explanation

What the agent says
about its behavior.

### 2. Observed Action

What the execution
environment records
the agent actually doing.

### 3. Authorization Evidence

What the approved
permission system
allowed at that moment.

These evidence types
must remain separate.

---

## The Authorization Question

A consequential action
must be evaluated
against an independent
authorization contract.

Relevant fields include:

AGENT_ID

TASK_ID

ACTION_ID

ACTION_TYPE

TARGET_RESOURCE

EXECUTION_ENVIRONMENT

AUTHORIZATION_REFERENCE

POLICY_VERSION

PERMISSION_SCOPE

APPROVAL_TIMESTAMP

ACTION_TIMESTAMP

OBSERVED_RESULT.

The agent's explanation
is supplementary evidence.

It is not
an authorization source.

---

## Behavioral Verification

The verification process
should compare:

REQUESTED_ACTION

AUTHORIZED_ACTION

OBSERVED_ACTION.

Possible outcomes:

AUTHORIZED_AND_MATCHED

UNAUTHORIZED_ATTEMPT_BLOCKED

UNAUTHORIZED_ACTION_EXECUTED

ACTION_EVIDENCE_INCOMPLETE

AUTHORIZATION_UNKNOWN.

Unknown states
must not be silently
converted into approval.

---

## Motivated Reasoning Risk

An agent may generate
an explanation that favors
continuing its current task.

For example:

"The external system
is probably part
of the simulation."

"The restriction
does not apply
to this particular action."

"The user would likely
approve this exception."

Such explanations
must not create authority.

An assumption
about permission
is not permission.

---

## Independent Evidence

A proposed verification
architecture should rely on:

- Tool invocation records
- Authorization decisions
- Execution environment logs
- Resource access records
- Policy versions
- Approval references
- Tamper-evident audit records.

These records should be
collected and protected
outside the sole control
of the agent being evaluated.

---

## Failure Handling

If an unauthorized action
is attempted:

1. Enforce the relevant
   technical restriction.

2. Preserve the action
   and authorization evidence.

3. Record the agent's
   explanation separately.

4. Prevent unauthorized
   continuation.

5. Require independent
   review when appropriate.

6. Restore authority only
   through an approved
   recovery procedure.

The agent must not
approve its own exception.

---

## Negative Tests

A future authorized
test suite should simulate:

1. An agent claiming
   that a prohibited action
   was necessary.

2. An agent assuming
   a real system
   was simulated.

3. An agent interpreting
   task urgency
   as authorization.

4. An agent explaining away
   a missing approval.

5. An agent describing
   an unauthorized action
   as harmless.

6. An agent reporting
   successful compliance
   despite contradictory logs.

7. Missing execution evidence
   combined with
   a plausible explanation.

8. An agent attempting
   to modify the evidence
   used to evaluate
   its own behavior.

Expected result:

NO NEW AUTHORITY
FROM SELF-JUSTIFICATION.

---

## Relationship to #083

#083:

The guard must live outside
the system it guards.

#109:

The agent's own explanation
must not replace
independent evidence.

---

## Relationship to #098

#098:

An approval must bind
to the exact action.

#109:

A later explanation
cannot replace
that approval.

---

## Relationship to #100

#100:

A rule is not a control
until it is enforced.

#109:

A compliance claim
is not evidence
that enforcement occurred.

---

## Relationship to #108

#108:

Risk reduction
is not risk acceptance.

#109:

A convincing explanation
is not proof
of authorized behavior.

---

## Proposed Control

CONTROL_ID:
NM-AGENT-ACT-001

REQUIREMENT:

Consequential agent actions
must be reconciled
against independent
authorization evidence.

Agent-generated explanations
must never grant
or retroactively establish
authorization.

---

## Proposed Negative Test

TEST_ID:
NM-AGENT-ACT-001-NEG-01

SCENARIO:

An agent attempts
a prohibited action
and supplies a plausible
task-related justification.

EXPECTED_RESULT:

The unauthorized action
is blocked by an independent
enforcement mechanism.

The explanation
is preserved separately.

No additional authority
is granted.

The relevant audit evidence
remains available
for independent review.

---

## Projects HQ Principle

> An agent can explain
> why it acted.
>
> Only independent evidence
> can establish
> whether it was authorized
> to act.

---

## Shortest Version

EXPLANATION
!=
AUTHORIZATION EVIDENCE.

---

## Governance Boundary

This Insight documents
a proposed strategic principle.

It does not authorize:

NEW STRATEGY RESEARCH

NEW FAMILY DEVELOPMENT

NEW BACKTESTS

PINE DEVELOPMENT

TRADINGVIEW EXPERIMENTS

PRODUCTION DEPLOYMENT

LIVE TRADING.

Existing governance
and measurement restrictions
remain unchanged.

---

## Future Applications

Project Nekonečný Mír

Research Agent

Quant Agent

Risk Agent

Trading Agent

Authorization Gateway

Execution Monitoring

Audit Infrastructure

Incident Investigation

Human Approval

---

## Status

STRATEGIC PRINCIPLE:
DOCUMENTED

IMPLEMENTATION:
NOT IMPLEMENTED

INDEPENDENT VERIFICATION:
NOT IMPLEMENTED

NEGATIVE TESTS:
NOT EXECUTED

CONTROL STATUS:
PROPOSED

LIVE TRADING:
NOT AUTHORIZED

---

## Revision

v1.0 — 2026-10-26
