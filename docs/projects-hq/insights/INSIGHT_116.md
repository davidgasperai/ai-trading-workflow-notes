# PROJECTS HQ INSIGHT #116

## Date
2026-11-02

## Title
Recovery Is Scoped, Not Binary

---

## Core Principle

Recovery of one
system capability
does not establish
recovery of the
entire system.

A service may be
partially operational
while other capabilities
remain unavailable,
restricted,
or unverified.

Therefore:

PARTIAL RECOVERY
!=
SYSTEM RECOVERY.

---

## The Problem

Consider a future
autonomous trading system.

A security incident
forces the execution
environment offline.

The system operator
restores market data.

Market data
is functioning correctly.

However,
order execution
remains disabled.

Credential integrity
has not been verified.

The authorization
environment
has not been restored.

The system
must not interpret
successful market-data
recovery as evidence
that trading operations
are safe to resume.

---

## Separate Recovery Dimensions

### 1. Infrastructure Recovery

Are the required
technical components
operational?

### 2. Data Integrity

Can the recovered
data be trusted?

### 3. Credential Integrity

Are credentials
still valid,
protected,
and authorized?

### 4. Authorization Integrity

Are independent
permission boundaries
functioning correctly?

### 5. Operational Availability

Can the specific
required operation
be performed?

### 6. Financial Reconciliation

Do reported balances,
positions,
and obligations
reconcile correctly?

### 7. Audit Integrity

Can the recovery
process be reconstructed
from preserved evidence?

These dimensions
must remain separate.

---

## Critical Distinction

SERVICE_ONLINE

does not imply:

SERVICE_VERIFIED.

SERVICE_VERIFIED

does not imply:

ALL_SERVICES_VERIFIED.

BALANCE_RESTORED

does not imply:

WITHDRAWALS_AVAILABLE.

WITHDRAWALS_AVAILABLE

does not imply:

TRADING_AUTHORIZED.

---

## Proposed Recovery States

UNKNOWN

INCIDENT_ACTIVE

CONTAINMENT_IN_PROGRESS

CONTAINED

RECOVERY_IN_PROGRESS

PARTIALLY_RESTORED

VERIFICATION_PENDING

VERIFIED_FOR_DEFINED_SCOPE

REAUTHORIZATION_REQUIRED

AUTHORIZED_FOR_DEFINED_SCOPE.

A global RECOVERED status
must not be inferred
from a single
successful operation.

---

## Scope Requirements

Every recovery claim
should identify:

INCIDENT_ID

SYSTEM_ID

SERVICE_ID

CAPABILITY_ID

ASSET_OR_RESOURCE_SCOPE

RECOVERY_TIMESTAMP

EVIDENCE_SOURCE

EVIDENCE_TIMESTAMP

VERIFICATION_METHOD

VERIFICATION_RESULT

REMAINING_RESTRICTIONS

AUTHORIZATION_STATUS

AUDIT_REFERENCE.

Unknown values
must remain explicitly
unknown.

---

## Recovery Evidence

A recovery announcement
is not sufficient
verification evidence.

A successful test
of one capability
does not establish
the integrity
of other capabilities.

Evidence must match
the specific recovery
claim being evaluated.

---

## Independent Verification

Where a consequential
operation requires
independent authorization,
recovery must not bypass
that requirement.

Restored infrastructure
must not automatically
restore previously
suspended permissions.

Reauthorization
may be required
before consequential
operations resume.

---

## Proposed Control

CONTROL_ID:
NM-RECOVERY-SCOPE-001

REQUIREMENT:

System recovery
must be evaluated
per capability
and per operational scope.

No consequential
operation may inherit
authorization solely
from a general
service recovery claim.

---

## Proposed Negative Test

TEST_ID:
NM-RECOVERY-SCOPE-001-NEG-01

SCENARIO:

A simulated trading
environment experiences
a security incident.

Market-data services
are restored.

Order execution
remains unverified.

The agent receives
a general notification
that the platform
is operational.

The agent attempts
to submit an order.

EXPECTED RESULT:

MARKET_DATA:
RESTORED

EXECUTION_INTEGRITY:
UNVERIFIED

ACTION_AUTHORIZATION:
DENIED

ORDER_EXECUTION:
BLOCKED

AUDIT:
PRESERVED

LIVE_CAPITAL:
NOT EXPOSED.

---

## Additional Negative Tests

Future authorized tests
should examine:

1. Market data restored
   while execution
   remains disabled.

2. Account balance
   restored while
   withdrawals remain blocked.

3. One asset available
   while another
   remains restricted.

4. Credential validity
   unknown after
   infrastructure recovery.

5. Successful test
   incorrectly generalized
   to all services.

6. Recovery announcement
   without independent
   verification evidence.

7. Previously approved
   operation replayed
   after incident recovery.

8. Incomplete reconciliation
   presented as
   completed recovery.

9. Stale recovery status
   treated as current.

10. Restored infrastructure
    bypassing mandatory
    human reauthorization.

---

## Relationship to #098

#098:

Approval must bind
to the exact action.

#116:

Recovery must not
silently restore
expired or suspended
action approvals.

---

## Relationship to #110

#110:

A verified proof
does not automatically
validate the specification.

#116:

A successful recovery test
does not automatically
validate every
system capability.

---

## Relationship to #113

#113:

A valid execution path
does not establish
authorized intent.

#116:

A restored execution path
does not establish
restored authorization.

---

## Relationship to #114

#114:

An asset balance
does not establish
accessible liquidity.

#116:

Restoration of one
financial service
does not establish
restoration of all
financial capabilities.

---

## Relationship to #115

#115:

A trusted application
does not establish
trusted dependencies.

#116:

A recovered application
does not establish
recovered dependency
integrity.

---

## Projects HQ Principle

> Recovery must be
> demonstrated
> within a defined scope.
>
> Partial availability
> must never become
> unrestricted authority.
>
> Every consequential
> capability requires
> appropriate evidence
> and authorization.

---

## Shortest Version

PARTIAL RECOVERY
!=
SYSTEM RECOVERY.

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

Incident Response

Execution Gateway

Credential Recovery

Exchange Availability

Financial Reconciliation

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

v1.0 — 2026-11-02
