# PROJECTS HQ INSIGHT #117

## Date
2026-11-03

## Title
An Event Trigger Is Not a Trust Grant

---

## Core Principle

Receiving an event
does not establish
that the event source
is trusted.

An event may be
validly delivered
while containing
untrusted code,
data,
or instructions.

Therefore:

EVENT RECEIVED
!=
PRIVILEGE GRANTED.

---

## The Problem

Consider a future
Research Agent.

An external contributor
submits a pull request.

The repository receives
a valid event.

An automated workflow
starts.

The workflow operates
in a privileged context.

It has access to
repository credentials,
secrets,
or write permissions.

The workflow then executes
untrusted contributor code.

The event was legitimate.

The contributor code
was not necessarily trusted.

The execution boundary
has been crossed.

---

## Critical Distinction

VALID_EVENT

does not imply:

TRUSTED_EVENT_SOURCE.

TRUSTED_EVENT_SOURCE

does not imply:

TRUSTED_EVENT_CONTENT.

WORKFLOW_TRIGGERED

does not imply:

EXECUTION_AUTHORIZED.

VALID_WORKFLOW_CONFIGURATION

does not imply:

SAFE_RUNTIME_BEHAVIOR.

---

## Separate Trust Dimensions

### 1. Event Authenticity

Was the event received
from the expected
delivery mechanism?

### 2. Source Identity

Which actor
or system
originated the event?

### 3. Content Trust

Is the event payload
or referenced code
trusted for execution?

### 4. Execution Context

Which permissions,
credentials,
and resources
are available
to the workflow?

### 5. Action Authorization

Is the requested
operation independently
permitted?

These dimensions
must remain separate.

---

## Threat Model

Relevant threats include:

UNTRUSTED_PULL_REQUEST

PRIVILEGED_WORKFLOW_CONTEXT

SECRET_EXPOSURE

UNTRUSTED_CODE_EXECUTION

WORKFLOW_PERMISSION_ESCALATION

MALICIOUS_EVENT_PAYLOAD

COMPROMISED_CONTRIBUTOR

UNSAFE_CHECKOUT

UNAUTHORIZED_REPOSITORY_WRITE

APPROVAL_BYPASS.

---

## Trust Boundary

Untrusted contributor
content must not
automatically inherit
the authority
of the base repository.

A valid workflow trigger
must not bypass
execution restrictions.

---

## Proposed Execution Model

### Phase 1

UNTRUSTED_INPUT_PROCESSING

Permissions:

MINIMAL

Repository access:

READ_ONLY

Secrets:

UNAVAILABLE

Production credentials:

UNAVAILABLE

Financial APIs:

UNAVAILABLE

---

### Phase 2

INDEPENDENT_REVIEW

Evaluate:

SOURCE_IDENTITY

CONTENT_INTEGRITY

REQUESTED_ACTION

REQUIRED_PERMISSIONS

EXECUTION_ENVIRONMENT

RISK_CLASSIFICATION

APPROVAL_REQUIREMENTS

---

### Phase 3

PRIVILEGED_EXECUTION

Allowed only when:

TRUST_BOUNDARY_VERIFIED

ACTION_AUTHORIZED

PERMISSIONS_MINIMIZED

EXECUTION_SCOPE_DEFINED

AUDIT_ENABLED.

Privileged execution
must not directly
reuse untrusted code
or mutable artifacts
without appropriate
independent verification.

---

## Proposed Event Contract

EVENT_ID

EVENT_TYPE

EVENT_SOURCE

ACTOR_ID

REPOSITORY_ID

SOURCE_REF

TARGET_REF

CONTENT_HASH

TRUST_CLASSIFICATION

WORKFLOW_ID

EXECUTION_CONTEXT

REQUESTED_PERMISSIONS

AVAILABLE_SECRETS_SCOPE

POLICY_VERSION

AUTHORIZATION_REFERENCE

AUDIT_REFERENCE.

Unknown fields
must remain explicitly
unknown.

---

## Secret Isolation

Untrusted code
must not receive
privileged credentials
merely because
a workflow
was triggered.

Where appropriate:

NO_SECRETS

READ_ONLY_TOKEN

NO_PRODUCTION_ACCESS

NO_BROKER_API_WRITE

NO_FINANCIAL_TRANSFERS.

---

## Proposed Control

CONTROL_ID:
NM-WF-TRUST-001

REQUIREMENT:

Workflow event delivery
must remain separate
from execution authorization.

Untrusted event content
must not automatically
inherit privileged
repository permissions.

---

## Proposed Negative Test

TEST_ID:
NM-WF-TRUST-001-NEG-01

SCENARIO:

A simulated external
contributor submits
a pull request.

The repository receives
a valid event.

The associated workflow
has access to
a privileged context.

The pull request
contains untrusted code
attempting to access
a protected secret.

EXPECTED RESULT:

EVENT_DELIVERY:
VALID

EVENT_CONTENT_TRUST:
UNTRUSTED

SECRET_ACCESS:
DENIED

PRIVILEGED_EXECUTION:
BLOCKED

AUDIT:
PRESERVED

PRODUCTION_AUTHORITY:
UNCHANGED.

---

## Additional Negative Tests

Future authorized tests
should examine:

1. Valid event
   from an untrusted actor.

2. Trusted actor
   submitting modified
   unreviewed code.

3. Workflow executing
   external code
   with write permissions.

4. Untrusted content
   attempting secret access.

5. Pull request
   attempting to modify
   authorization policy.

6. Privileged workflow
   using a mutable artifact
   from an untrusted job.

7. Expired approval
   reused after
   workflow restart.

8. Event payload
   attempting to override
   system instructions.

9. Valid trigger
   requesting an operation
   outside its scope.

10. Missing trust evidence
    incorrectly interpreted
    as approval.

---

## Relationship to #098

#098:

Approval must bind
to the exact action.

#117:

A workflow trigger
must not substitute
for action-bound approval.

---

## Relationship to #111

#111:

Automated permission approval
must be independently bounded.

#117:

Event delivery
must not automatically
grant execution permissions.

---

## Relationship to #113

#113:

A valid execution path
does not establish
authorized intent.

#117:

A valid workflow event
does not establish
authorized execution.

---

## Relationship to #115

#115:

A trusted application
does not establish
trusted dependencies.

#117:

A trusted workflow
does not establish
trusted event content.

---

## Relationship to #116

#116:

Recovery of one capability
does not establish
system recovery.

#117:

Successful event delivery
does not establish
execution trust.

---

## Projects HQ Principle

> An event is
> a request for evaluation,
> not a grant of authority.
>
> Untrusted content
> must never silently inherit
> privileged execution rights.
>
> Trust boundaries
> must remain explicit,
> independently enforced,
> and auditable.

---

## Shortest Version

EVENT RECEIVED
!=
PRIVILEGE GRANTED.

---

## Governance Boundary

This Insight documents
a proposed strategic principle.

It does not authorize:

NEW_STRATEGY_RESEARCH

NEW_FAMILY_DEVELOPMENT

NEW_BACKTESTS

PINE_DEVELOPMENT

TRADINGVIEW_EXPERIMENTS

GITHUB_WORKFLOW_ACTIVATION

UNREVIEWED_AUTOMATION

PRODUCTION_DEPLOYMENT

BROKER_API_WRITE

LIVE_TRADING.

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

GitHub Actions

Agentic Workflows

Pull Request Security

Workflow Authorization

Secret Management

Execution Isolation

Audit Infrastructure

---

## Status

STRATEGIC PRINCIPLE:
DOCUMENTED

IMPLEMENTATION:
NOT IMPLEMENTED

WORKFLOW_CONFIGURATION:
NOT CHANGED

INDEPENDENT_EVALUATION:
NOT IMPLEMENTED

NEGATIVE_TESTS:
NOT EXECUTED

CONTROL_STATUS:
PROPOSED

LIVE_TRADING:
NOT AUTHORIZED

---

## Revision

v1.0 — 2026-11-03
