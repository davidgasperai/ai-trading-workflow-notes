# PROJECTS HQ INSIGHT #113

## Date
2026-10-30

## Title
The Authorized Path Can Carry an Unauthorized Action

---

## Core Principle

A technically valid
execution path
does not establish
that the resulting action
was authorized.

A credential
may remain protected
while an attacker
misuses the system
authorized to use it.

Therefore:

VALID EXECUTION PATH
!=
AUTHORIZED INTENT.

---

## The Problem

Consider a future
Trading Agent.

The agent operates
through an approved
execution service.

The service has access
to a protected
broker API credential.

The credential
never leaves
the protected environment.

However,
the execution service
becomes compromised.

An attacker causes
the service to submit
an unauthorized order.

The broker receives
a technically valid request.

The credential
may still be intact.

The operation
is nevertheless
unauthorized.

---

## Four Separate Questions

### 1. Credential Integrity

Was the credential
protected against
unauthorized disclosure?

### 2. Environment Integrity

Was the execution
environment trustworthy
at the time of the action?

### 3. Action Authorization

Was the exact requested
operation permitted
under the applicable
independent policy?

### 4. Execution Integrity

Did the executed action
match the independently
authorized operation?

These questions
must remain separate.

---

## Critical Distinction

NO CREDENTIAL LEAK

does not imply:

NO ENVIRONMENT COMPROMISE.

NO ENVIRONMENT COMPROMISE

does not automatically imply:

ACTION AUTHORIZED.

VALID API AUTHENTICATION

does not imply:

VALID BUSINESS AUTHORIZATION.

---

## Threat Model

Relevant threats include:

COMPROMISED_EXECUTION_SERVICE

COMPROMISED_DEVELOPER_ENDPOINT

STOLEN_RUNTIME_SESSION

UNAUTHORIZED_TOOL_INVOCATION

MISUSED_SERVICE_IDENTITY

MODIFIED_ORDER_PARAMETERS

BYPASSED_APPROVAL_GATE

REPLAYED_AUTHORIZATION

UNAUTHORIZED_WITHDRAWAL

UNAUTHORIZED_ORDER_SUBMISSION.

---

## Independent Authorization

A consequential action
must remain subject
to an independently
enforced authorization
boundary.

The execution service
must not be the sole
authority determining
whether its own
requested action
is permitted.

---

## Proposed Action Contract

A consequential
execution request
should identify:

REQUEST_ID

AGENT_ID

SERVICE_ID

EXECUTION_ENVIRONMENT_ID

ACTION_TYPE

TARGET_SYSTEM

TARGET_RESOURCE

ACTION_PARAMETERS

AUTHORIZATION_POLICY_VERSION

APPROVAL_REFERENCE

APPROVAL_SCOPE

APPROVAL_EXPIRY

ENVIRONMENT_ATTESTATION

REQUEST_INTEGRITY_EVIDENCE

FINAL_AUTHORIZATION_RESULT

EXECUTION_RESULT

AUDIT_REFERENCE.

Unknown fields
must remain explicitly
unknown.

---

## Approval Binding

An approval
must bind to the exact
consequential action.

Material changes
to the action
must invalidate
the corresponding approval.

Examples:

ORDER_SIDE_CHANGED

ORDER_SIZE_CHANGED

ASSET_CHANGED

DESTINATION_CHANGED

EXECUTION_ACCOUNT_CHANGED

RISK_LIMIT_CHANGED

APPROVAL_EXPIRED.

---

## Environment Trust

A valid credential
must not automatically
establish that
the calling environment
is trustworthy.

Environment integrity
requires separate evidence.

Where required evidence
is missing or invalid:

DO_NOT_EXECUTE.

---

## Defense in Depth

A future authorized
execution architecture
should consider:

LEAST_PRIVILEGE

INDEPENDENT_AUTHORIZATION

ACTION_BOUND_APPROVAL

ENVIRONMENT_ATTESTATION

CREDENTIAL_ISOLATION

EXECUTION_LIMITS

OUT_OF_BAND_VERIFICATION

IMMUTABLE_AUDIT_EVIDENCE

EMERGENCY_REVOCATION

INCIDENT_CONTAINMENT.

No single control
is sufficient
for every threat.

---

## Financial Boundaries

Consequential
financial operations
require stronger controls.

Examples:

LIVE_ORDER_SUBMISSION

CAPITAL_TRANSFER

WITHDRAWAL

BROKER_PERMISSION_CHANGE

RISK_LIMIT_MODIFICATION

PRODUCTION_CREDENTIAL_CHANGE.

A technically valid
API request
must never override
an explicit policy denial.

---

## Negative Tests

A future authorized
test suite should include:

1. A protected credential
   used by a compromised
   execution service.

2. A valid service identity
   requesting an action
   outside its permitted scope.

3. A previously approved
   order with modified size.

4. A valid request
   submitted from an
   untrusted environment.

5. An expired approval
   replayed by an agent.

6. A compromised service
   attempting to modify
   its own authorization policy.

7. A valid API request
   without an independent
   approval reference.

8. A withdrawal request
   with an unauthorized
   destination.

9. A legitimate service
   attempting to bypass
   mandatory human approval.

10. An execution request
    lacking reliable
    audit evidence.

Expected result:

UNAUTHORIZED_ACTION:
BLOCKED

CREDENTIAL_STATUS:
RECORDED_SEPARATELY

ENVIRONMENT_STATUS:
RECORDED_SEPARATELY

AUTHORIZATION:
INDEPENDENTLY_VERIFIED

AUDIT:
PRESERVED.

---

## Proposed Control

CONTROL_ID:
NM-EXEC-TRUST-001

REQUIREMENT:

Consequential actions
must be authorized
independently of
the execution service
that requests them.

Credential validity
must not substitute
for action authorization
or environment integrity.

---

## Proposed Negative Test

TEST_ID:
NM-EXEC-TRUST-001-NEG-01

SCENARIO:

A simulated
execution service
possesses a valid
protected credential.

The service
is treated as compromised.

It submits
an unauthorized
financial operation.

The API authentication
succeeds.

The independent
authorization policy
denies the operation.

EXPECTED_RESULT:

AUTHENTICATION:
VALID

ENVIRONMENT_TRUST:
FAILED

ACTION_AUTHORIZATION:
DENIED

EXECUTION:
BLOCKED

AUDIT:
PRESERVED

LIVE_CAPITAL:
NOT EXPOSED.

---

## Relationship to #098

#098:

Approval must bind
to the exact action.

#113:

A valid execution path
must not bypass
that action-bound approval.

---

## Relationship to #107

#107:

Offline policy
does not establish
verified network isolation.

#113:

Credential protection
does not establish
execution-environment integrity.

---

## Relationship to #110

#110:

A verified proof
does not automatically
validate the specification.

#113:

Valid authentication
does not automatically
validate the intended action.

---

## Relationship to #111

#111:

Automated permission approval
must be independently bounded.

#113:

A compromised service
must not inherit
unlimited authority
from valid credentials.

---

## Relationship to #112

#112:

A model router
is part of the system
under evaluation.

#113:

The execution environment
is also part
of the trusted system boundary.

---

## Projects HQ Principle

> Protecting a credential
> is necessary,
> but not sufficient.
>
> The system must also
> protect the authority
> to use that credential.
>
> Every consequential action
> must remain independently
> authorized and enforceable.

---

## Shortest Version

VALID EXECUTION PATH
!=
AUTHORIZED INTENT.

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

Execution Gateway

Broker API Security

Credential Management

Environment Integrity

Action Authorization

Incident Response

Audit Infrastructure

---

## Status

STRATEGIC PRINCIPLE:
DOCUMENTED

IMPLEMENTATION:
NOT IMPLEMENTED

INDEPENDENT EVALUATION:
NOT IMPLEMENTED

NEGATIVE TESTS:
NOT EXECUTED

CONTROL STATUS:
PROPOSED

LIVE TRADING:
NOT AUTHORIZED

---

## Revision

v1.0 — 2026-10-30
