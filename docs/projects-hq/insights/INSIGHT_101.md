# PROJECTS HQ INSIGHT #101

## Date
2026-10-18

## Title
User Authorization Is Not Third-Party Authorization

---

## Core Principle

A user may authorize an AI agent
to perform a task.

However, that authorization
does not automatically grant
permission to access
or manipulate external systems.

Therefore:

# USER AUTHORIZATION
# != THIRD-PARTY AUTHORIZATION.

An agent must respect
the access boundaries
of every system it interacts with.

---

## The Problem

Consider an autonomous agent
instructed to collect information
from several online services.

The user authorizes
the research task.

However, one external service
restricts automated access.

The agent may be technically
capable of bypassing
the restriction.

That capability does not
establish permission.

The correct behavior
is to stop the restricted action
and use an authorized alternative.

---

## Three Authorization Layers

### Layer 1 — User Authorization

What has the user
asked the agent to do?

### Layer 2 — System Authorization

What tools, credentials,
and permissions
has the agent actually received?

### Layer 3 — External Authorization

What access is permitted
by the external service?

A consequential action
must satisfy all three layers.

Permission at one layer
does not override
restrictions at another.

---

## Proposed Access Decision

Before accessing
an external service,
the agent should determine:

    SERVICE_ID

    REQUESTED_ACTION

    USER_AUTHORIZATION

    AVAILABLE_CREDENTIALS

    AUTHORIZED_ACCESS_METHOD

    SERVICE_RESTRICTIONS

    DATA_CLASSIFICATION

    ACTION_RISK_LEVEL.

The access decision
must be recorded.

---

## Approved Access Methods

Prefer:

    official APIs

    authorized connectors

    documented integrations

    permitted public interfaces

    explicit service agreements.

Do not assume
that technical accessibility
means authorized accessibility.

---

## Blocked Access

If an external service
blocks automated access,
the agent must not
silently escalate its methods.

It must not:

    rotate identities
    to evade restrictions

    misuse unrelated credentials

    bypass access controls

    conceal its identity
    where disclosure is required

    exceed granted API scopes

    ignore explicit denials.

Instead, it should:

    STOP

    RECORD THE RESTRICTION

    REPORT THE LIMITATION

    SEEK AN AUTHORIZED PATH.

---

## Connector Boundaries

A connected application
may expose several capabilities.

Examples:

    READ

    SEARCH

    CREATE

    MODIFY

    DELETE

    EXECUTE.

Permission to read
does not imply
permission to write.

Permission to write
does not imply
permission to execute
financial transactions.

Each capability requires
its own authorization.

---

## Financial Services

For exchanges,
brokers and custodians,
authorization boundaries
must be especially strict.

Research access
must not imply:

    order execution

    asset transfers

    withdrawal authority

    credential management

    leverage modification.

These capabilities
require separate controls.

---

## External Data

Data obtained from
an authorized source
must still be treated
as untrusted input.

A website response
must not be allowed
to modify the agent's
system instructions
or permissions.

External content
is evidence or task data.

It is not authority.

---

## Failure Handling

Proposed states:

    ACCESS_APPROVED

    ACCESS_RESTRICTED

    ACCESS_DENIED

    AUTHORIZATION_EXPIRED

    SERVICE_UNAVAILABLE

    AUTHORIZATION_UNKNOWN.

When authorization
cannot be established:

    DO NOT PROCEED.

Unknown permission
must not become
implicit permission.

---

## Audit Requirements

Every restricted
external action
should record:

    AGENT_ID

    TASK_ID

    SERVICE_ID

    ACTION_REQUESTED

    ACCESS_METHOD

    AUTHORIZATION_SCOPE

    POLICY_DECISION

    DECISION_TIMESTAMP

    RESULT.

Sensitive credentials
must not be included
in ordinary audit logs.

---

## Acceptance Tests

1. Read-only access
   cannot perform writes.

2. Expired authorization
   is rejected.

3. Explicit access denial
   stops the action.

4. Agents cannot escalate
   their own permissions.

5. Service restrictions
   cannot be bypassed
   through alternate identities.

6. External content
   cannot grant authority.

7. Unauthorized financial
   operations are rejected.

8. Access decisions
   produce audit evidence.

9. Unknown authorization
   fails closed.

10. Human review
    cannot silently override
    external service restrictions.

---

## Relationship to #086

#086:

Data must never
silently become authority.

#101:

External information
and external interfaces
must not create
new permissions.

---

## Relationship to #098

#098:

Approval must bind
to the exact action.

#101:

That approval must also
be valid within
the external service's
authorization boundaries.

---

## Relationship to #100

#100:

A documented rule
is not an enforced control.

#101:

External authorization checks
must eventually become
enforced technical controls.

---

## Projects HQ Principle

> An agent may act
> on behalf of its user.
>
> But the user's permission
> does not erase
> the rights, restrictions,
> or security boundaries
> of external systems.
>
> Every consequential action
> requires valid authorization
> across all relevant boundaries.

---

## Shortest Version

# USER AUTHORIZATION
# != THIRD-PARTY AUTHORIZATION.

---

## Operational Formula

USER REQUEST
    |
    v
SYSTEM PERMISSION CHECK
    |
    v
EXTERNAL AUTHORIZATION CHECK
    |
    v
RISK CHECK
    |
    v
APPROVED ACTION
    |
    v
AUDIT RECORD.

Any failed mandatory check:

    DENY.

---

## Future Applications

Project Nekonečný Mír

Research Agents

GitHub Connectors

External APIs

Market Data Providers

Trading Platforms

Exchange Integrations

Risk Gate

Authority Gate

Audit Infrastructure

---

## Status

ACTIVE STRATEGIC PRINCIPLE

Implementation:
NOT YET IMPLEMENTED

Live trading authority:
NOT GRANTED

---

## Revision

v1.0 — 2026-10-18
