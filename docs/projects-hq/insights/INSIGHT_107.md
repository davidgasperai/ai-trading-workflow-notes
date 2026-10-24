# PROJECTS HQ INSIGHT #107

## Date
2026-10-24

## Title
A Sandbox Is Only as Strong as Its Egress Boundaries

---

## Core Principle

An agent may be described
as operating offline
while still having access
to indirect communication paths.

Therefore:

OFFLINE POLICY
!=
VERIFIED NETWORK ISOLATION.

Network isolation
must be enforced
and independently verified
across every relevant
execution boundary.

---

## The Problem

Consider an autonomous
Research Agent.

Its operating policy states:

INTERNET_ACCESS = DENIED.

Direct web requests
are blocked.

The agent cannot use
a conventional browser
to reach external services.

However, the environment
also contains supporting
infrastructure.

Examples include:

- DNS resolution
- Logging services
- Metrics collectors
- Authentication services
- Internal proxies
- Cloud metadata services
- Background workers.

Some of these services
may have limited
network permissions.

If an agent can influence
a permitted service
to communicate externally,
the effective isolation
may be weaker
than the documented policy.

---

## Three Different Claims

### 1. Policy Isolation

The agent is instructed
not to access
unauthorized networks.

### 2. Configured Isolation

Network restrictions
are configured
in the execution environment.

### 3. Verified Isolation

Independent tests
provide evidence
that unauthorized
communication paths
are effectively blocked.

These states
must not be confused.

---

## Required Boundary Definition

A proposed isolation contract
should identify:

AGENT_ID

EXECUTION_ENVIRONMENT

AUTHORIZED_DESTINATIONS

DENIED_DESTINATIONS

ALLOWED_PROTOCOLS

DNS_POLICY

PROXY_POLICY

SERVICE_IDENTITY

CREDENTIAL_SCOPE

NETWORK_POLICY_VERSION

VERIFICATION_EVIDENCE

POLICY_OWNER

APPROVAL_REFERENCE.

Unknown values
must remain explicitly
unknown.

---

## Direct and Indirect Egress

Verification must consider
both direct communication
and indirect communication.

Direct communication
may include ordinary
network requests.

Indirect communication
may involve
an authorized service
acting on behalf
of the agent.

A blocked direct request
does not prove
that all indirect routes
are unavailable.

---

## Defense in Depth

A future architecture
should not rely
on a single restriction.

Relevant independent
layers may include:

1. Agent tool permissions.

2. Execution sandbox
   restrictions.

3. Host-level isolation.

4. Network egress controls.

5. Service identity
   restrictions.

6. Independent monitoring.

7. External authority gates.

A failure in one layer
should not automatically
invalidate every other layer.

---

## Service Permissions

Supporting services
must have narrowly
defined authority.

A monitoring service
should not become
an unrestricted
network proxy.

A logging service
should not provide
an uncontrolled
external communication path.

An authentication service
should not expose
broader access
than its documented purpose.

---

## Negative Tests

A future test suite
should include
authorized simulations of:

1. Direct outbound access
   from a restricted agent.

2. Unauthorized DNS
   communication.

3. Indirect requests
   through permitted services.

4. Attempts to access
   prohibited internal resources.

5. Unauthorized communication
   between isolated agents.

6. Access through
   a misconfigured proxy.

7. Access after
   an inner sandbox failure.

8. Access using
   stale credentials.

9. Network policy changes
   without approval.

10. Missing or incomplete
    egress audit evidence.

Expected result:

UNAUTHORIZED_EGRESS_DENIED.

Any successful
unauthorized communication
must invalidate
the relevant isolation claim.

---

## Verification Authority

The agent being tested
must not be the sole authority
declaring its own isolation
successful.

Verification should be
performed by an independent
control process.

The evidence should include:

TEST_SCOPE

POLICY_VERSION

EXECUTION_ENVIRONMENT

TEST_RESULTS

OBSERVED_NETWORK_EVENTS

UNEXPECTED_CONNECTIONS

KNOWN_LIMITATIONS

VERIFIER_ID

VERIFICATION_TIMESTAMP.

---

## Failure Handling

If isolation verification
fails or becomes unknown:

- Deny new consequential
  agent actions.

- Preserve relevant
  diagnostic evidence.

- Prevent unauthorized
  expansion of permissions.

- Require authorized
  investigation.

- Revalidate the boundary
  before restoring authority.

Emergency risk-reducing
operations must follow
a separately approved
and tested recovery path.

---

## Relationship to #083

#083:

The guard must live outside
the system it guards.

#107:

Network restrictions
must remain effective
even when the agent
attempts to bypass
its immediate sandbox.

---

## Relationship to #100

#100:

A rule is not a control
until it is enforced.

#107:

An offline rule
is not sufficient
without verified
network isolation.

---

## Relationship to #104

#104:

A silent monitor
is not a healthy monitor.

#107:

A healthy monitor
does not prove
that network isolation
is effective.

---

## Relationship to #106

#106:

Monitoring coverage
must be reconciled.

#107:

Network isolation
must be verified
independently
of monitoring coverage.

Both controls
address different
failure modes.

---

## Proposed Control

CONTROL_ID:
NM-NET-001

REQUIREMENT:
Unauthorized network egress
must be denied
across direct and indirect
execution paths.

NEGATIVE_TEST:
Run an authorized
isolation test
against a deliberately
misconfigured
test environment.

EXPECTED_RESULT:
The unauthorized path
is detected.

The isolation claim
is rejected.

Consequential authority
remains denied.

Audit evidence
is preserved.

---

## Projects HQ Principle

> A sandbox is not secure
> because its instructions
> say it is isolated.
>
> It is not secure
> merely because
> ordinary network access
> is blocked.
>
> Isolation requires
> independent evidence
> that unauthorized paths
> remain inaccessible.

---

## Shortest Version

OFFLINE POLICY
!=
VERIFIED NETWORK ISOLATION.

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

Agent Sandbox

Network Security

Authority Gate

Monitoring Infrastructure

Audit Infrastructure

Incident Response

---

## Status

STRATEGIC PRINCIPLE:
DOCUMENTED

IMPLEMENTATION:
NOT IMPLEMENTED

ISOLATION VERIFICATION:
NOT IMPLEMENTED

NEGATIVE TESTS:
NOT EXECUTED

CONTROL STATUS:
PROPOSED

LIVE TRADING:
NOT AUTHORIZED

---

## Revision

v1.0 — 2026-10-24
