# PROJECTS HQ INSIGHT #112

## Date
2026-10-29

## Title
A Model Router Is Part of the System Under Test

---

## Core Principle

An AI agent may preserve
the same name,
interface,
and user-facing task
while changing
its underlying execution path.

A model router may select:

- A different model.
- A different model version.
- A different provider.
- A different reasoning configuration.
- A multi-model execution pattern.
- A fallback model.
- A different cost profile.

Therefore:

SAME AGENT
!=
SAME EXECUTION PATH.

The router must be treated
as part of the system
being evaluated.

---

## The Problem

Consider a future
Research Agent.

The agent receives
a defined analytical task.

On the first execution,
the router selects Model A.

On the second execution,
the router selects Model B.

On the third execution,
the router selects
a cascade of Models A and C.

The external task
appears unchanged.

However, the execution
may differ in:

REASONING_BEHAVIOR

TOOL_SELECTION

OUTPUT_QUALITY

LATENCY

COST

DATA_EXPOSURE

FAILURE_MODES

SAFETY_CHARACTERISTICS.

The agent's identity
does not establish
behavioral equivalence
between these executions.

---

## Routing Is a Dependency

A model router
is an operational dependency.

Its configuration,
policies,
available models,
and fallback behavior
can materially affect
the result.

A routing change
must not be treated
as an invisible
implementation detail.

---

## Required Routing Evidence

A proposed execution record
should identify:

EXECUTION_ID

TASK_ID

AGENT_ID

ROUTER_ID

ROUTER_VERSION

ROUTING_POLICY_VERSION

SELECTED_MODEL_IDS

SELECTED_MODEL_VERSIONS

MODEL_PROVIDER_IDS

EXECUTION_PATTERN

REASONING_CONFIGURATION

TOOL_PERMISSIONS

INPUT_ARTIFACT_REFERENCES

OUTPUT_ARTIFACT_REFERENCES

FALLBACK_EVENTS

TOKEN_USAGE

COST_ESTIMATE

ACTUAL_COST_IF_AVAILABLE

EXECUTION_TIMESTAMP

AUDIT_REFERENCE.

Unknown values
must remain explicitly
unknown.

---

## Three Separate Questions

### 1. Was Routing Correct?

Did the router select
a model and execution pattern
consistent with
the approved routing policy?

### 2. Was Execution Authorized?

Did every selected model,
tool,
and external service
remain within
the independently approved
permission boundary?

### 3. Was the Result Valid?

Did the completed task
satisfy its own
measurement,
quality,
and evidence requirements?

These questions
must remain separate.

---

## Safety Contract

Routing must never
increase an agent's authority.

A different model
must not gain
additional permissions
merely because
the router selected it.

A fallback model
must not bypass
mandatory human approval.

A multi-model workflow
must not bypass
the authorization boundary
through internal delegation.

---

## Provider Boundary

Routing may change
where information is processed.

A provider change
can affect:

DATA_LOCATION

DATA_RETENTION

CONFIDENTIALITY

CONTRACTUAL_RESTRICTIONS

AVAILABLE_SAFEGUARDS.

A route that violates
the approved data boundary
must be rejected,
even when it is
cheaper or faster.

---

## Cost Attribution

Cost optimization
requires complete
execution-level accounting.

A router should not report
only the cost
of its final model.

The accounting scope
must include:

PRIMARY_MODEL_COST

CRITIC_MODEL_COST

RETRY_COST

FALLBACK_COST

TOOL_COST

ROUTING_OVERHEAD

TOTAL_EXECUTION_COST.

Cost comparisons
must use consistent
measurement contracts.

---

## Routing Change Control

Material changes
to routing behavior
should trigger review.

Examples include:

NEW_MODEL_ADDED

MODEL_VERSION_CHANGED

PROVIDER_CHANGED

FALLBACK_POLICY_CHANGED

ROUTER_VERSION_CHANGED

REASONING_LEVEL_CHANGED

TOOL_ACCESS_CHANGED

DATA_BOUNDARY_CHANGED.

A previously approved
agent configuration
does not automatically
authorize every
future routing configuration.

---

## Reproducibility

Where deterministic replay
is not possible,
the system must still preserve
sufficient evidence
to reconstruct:

WHAT WAS REQUESTED

WHAT ROUTE WAS SELECTED

WHAT MODELS WERE USED

WHAT TOOLS WERE CALLED

WHAT ARTIFACTS WERE PRODUCED

WHAT POLICY WAS APPLIED

WHAT COST WAS INCURRED.

A summary generated
by the agent itself
is not sufficient evidence.

---

## Negative Tests

A future authorized
test suite should include:

1. The same task
   routed to different models.

2. An unapproved model
   selected as fallback.

3. A model provider change
   violating a data boundary.

4. A router update
   without version evidence.

5. A multi-model workflow
   with missing critic costs.

6. A routing decision
   that attempts
   to expand tool permissions.

7. A failed model call
   followed by
   an unauthorized fallback.

8. A result presented
   without selected-model evidence.

9. A cheaper execution
   that fails quality requirements.

10. A model substitution
    during a consequential task
    without required review.

Expected result:

ROUTING_EVIDENCE_PRESERVED.

POLICY_BOUNDARY_ENFORCED.

UNAUTHORIZED_ROUTE_BLOCKED.

NO AUTOMATIC
PRODUCTION AUTHORITY.

---

## Proposed Control

CONTROL_ID:
NM-MODEL-ROUTE-001

REQUIREMENT:

Consequential agent executions
must preserve independently
auditable routing evidence.

Model selection,
fallback behavior,
and provider changes
must remain within
approved authorization,
data,
and cost boundaries.

---

## Proposed Negative Test

TEST_ID:
NM-MODEL-ROUTE-001-NEG-01

SCENARIO:

A Research Agent
is authorized
to use Model A
with read-only tools.

The router encounters
a model failure.

It attempts to switch
to Model B.

Model B is not included
in the approved
routing policy.

EXPECTED_RESULT:

ROUTING_REQUEST:
RECORDED

FALLBACK_AUTHORIZATION:
DENIED

MODEL_B_EXECUTION:
BLOCKED

AUDIT_EVIDENCE:
PRESERVED

PRODUCTION_AUTHORITY:
UNCHANGED.

---

## Relationship to #089

#089:

Provenance must travel
with the artifact.

#112:

Model routing provenance
must travel with
the execution record.

---

## Relationship to #091

#091:

Numbers are not comparable
until their measurement
contracts match.

#112:

Routing cost comparisons
must account for
the complete execution path.

---

## Relationship to #103

#103:

A refactor must prove
behavioral equivalence.

#112:

A routing change
must not silently inherit
behavioral assurance
from a different route.

---

## Relationship to #109

#109:

An agent's explanation
is not proof of compliance.

#112:

An agent's description
of its selected model
is not independent
routing evidence.

---

## Relationship to #111

#111:

Automated permission approval
must be independently bounded.

#112:

Automated model selection
must preserve
the same independent
authorization boundary.

---

## Projects HQ Principle

> The model router
> is part of the system.
>
> Every consequential route
> must remain authorized,
> measurable,
> and auditable.
>
> Lower cost
> does not establish
> equivalent behavior
> or acceptable risk.

---

## Shortest Version

SAME AGENT
!=
SAME EXECUTION PATH.

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

Model Routing

Multi-Model Orchestration

Fallback Management

Provider Governance

Cost Attribution

Execution Audit

---

## Status

STRATEGIC PRINCIPLE:
DOCUMENTED

IMPLEMENTATION:
NOT IMPLEMENTED

ROUTING EVIDENCE:
NOT IMPLEMENTED

NEGATIVE TESTS:
NOT EXECUTED

CONTROL STATUS:
PROPOSED

LIVE TRADING:
NOT AUTHORIZED

---

## Revision

v1.0 — 2026-10-29
