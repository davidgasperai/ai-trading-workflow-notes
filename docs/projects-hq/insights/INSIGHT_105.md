# PROJECTS HQ INSIGHT #105

## Date
2026-10-22

## Title
A Patch Is Not Complete Until Exposure Is Closed

---

## Core Principle

A security patch
may be published,
approved or installed
without eliminating
the underlying exposure.

Therefore:

PATCH RELEASED
!=
EXPOSURE CLOSED.

A vulnerability
must not be considered
remediated until
the affected system
has been independently
verified as protected.

---

## The Problem

Consider a critical vulnerability
in a widely used dependency.

The maintainers
publish a security update.

An AI coding agent
updates the dependency
in the source repository.

The agent reports:

"Vulnerability fixed."

However:

- One deployed service
  still uses the old version.

- Another service
  has not been restarted.

- A third environment
  was omitted.

- The production artifact
  has not been verified.

The patch exists.

The exposure remains.

---

## Four Different States

1. PATCH_AVAILABLE

   A correction has been
   published by the maintainer.

2. PATCH_APPLIED

   The correction has been
   incorporated into
   a specific environment.

3. PATCH_VERIFIED

   Independent checks confirm
   that the affected component
   uses the intended correction.

4. EXPOSURE_CLOSED

   The required scope
   has been verified,
   residual exposure assessed,
   and closure authorized.

These states
must not be confused.

---

## Required Evidence

A remediation record
should identify:

VULNERABILITY_ID

AFFECTED_COMPONENT

AFFECTED_VERSION

FIXED_VERSION

ASSET_INVENTORY

DEPLOYMENT_SCOPE

PATCH_ARTIFACT_HASH

DEPLOYMENT_TIMESTAMP

RUNTIME_VERSION

VERIFICATION_METHOD

VERIFICATION_TIMESTAMP

RESIDUAL_RISK

APPROVER_ID

AUDIT_REFERENCE.

Unknown values
must remain explicitly
unknown.

---

## Inventory Before Closure

Before declaring remediation,
the system must establish
which environments
may be affected.

Potential locations include:

- Development machines
- CI runners
- Containers
- Production services
- Background workers
- Test environments
- Cached build artifacts
- Transitive dependencies.

A missing inventory entry
must not silently become
proof of safety.

---

## Independent Verification

The agent applying a patch
must not be the sole authority
confirming remediation.

Verification should compare:

EXPECTED_VERSION

ACTUAL_DEPLOYED_VERSION

RUNNING_PROCESS_VERSION

CONFIGURATION_STATE

DEPENDENCY_RESOLUTION

SECURITY_TEST_RESULTS.

A successful source commit
is not sufficient evidence.

---

## Runtime Verification

A patched file
may not be the code
currently executing.

Therefore,
the verification process
must consider:

SERVICE_RESTART

PROCESS_REPLACEMENT

CONTAINER_REDEPLOYMENT

CACHE_INVALIDATION

ROLLBACK_STATE.

The applicable checks
depend on the technology.

---

## Residual Risk

A patch may reduce risk
without eliminating
every relevant attack path.

The remediation process
must record:

KNOWN_LIMITATIONS

UNPATCHED_ASSETS

TEMPORARY_MITIGATIONS

REMAINING_EXPOSURE

ACCEPTED_EXCEPTIONS.

Exceptions require
explicit authorization.

An agent must not
accept residual risk
on its own authority.

---

## Negative Tests

The future test suite
should simulate:

1. Patch committed
   but not deployed.

2. Patched dependency
   with an old runtime.

3. One affected service
   omitted from inventory.

4. Incorrect dependency
   resolution.

5. A stale container image.

6. Failed service restart.

7. A rollback restoring
   the vulnerable version.

8. Agent reporting success
   without verification.

9. An unauthorized
   remediation exception.

10. Missing audit evidence.

Expected result:

CLOSURE DENIED.

---

## Agent Authority

A coding agent may:

IDENTIFY_EXPOSURE

PROPOSE_REMEDIATION

PREPARE_PATCH

RUN_AUTHORIZED_TESTS

REPORT_RESULTS.

It must not independently:

DECLARE_GLOBAL_CLOSURE

SUPPRESS_FAILED_CHECKS

ALTER_ACCEPTANCE_RULES

ACCEPT_RESIDUAL_RISK

EXPAND_DEPLOYMENT_SCOPE

APPROVE_ITS_OWN_PATCH.

Consequential deployment
requires separate authority.

---

## Relationship to #083

#083:

The guard must live outside
the system it guards.

#105:

Remediation verification
must not depend solely
on the agent performing
the remediation.

---

## Relationship to #100

#100:

A rule is not a control
until it is enforced.

#105:

A published security fix
is not a completed control
until deployment
and effectiveness
are verified.

---

## Relationship to #103

#103:

A refactor must prove
behavioral equivalence.

#105:

A security update
must also demonstrate
that required behavior
has not been unintentionally
broken by remediation.

---

## Relationship to #104

#104:

A silent monitor
is not a healthy monitor.

#105:

A reported patch
is not proof
of a protected runtime.

Both require
independent operational evidence.

---

## Proposed Control

CONTROL_ID:
NM-SEC-001

REQUIREMENT:
Security remediation closure
requires independent
deployment and runtime evidence.

NEGATIVE_TEST:
Update source dependencies
without updating
the deployed runtime.

EXPECTED_RESULT:
Remediation remains OPEN.

Closure authorization
is denied.

Audit evidence
is preserved.

---

## Projects HQ Principle

> Finding a vulnerability
> is not fixing it.
>
> Publishing a patch
> is not deploying it.
>
> Deploying a patch
> is not verifying it.
>
> Security closure
> requires evidence
> that the exposure
> has actually been addressed.

---

## Shortest Version

PATCH RELEASED
!=
EXPOSURE CLOSED.

---

## Governance Boundary

This Insight defines
a proposed strategic principle.

It does not authorize:

NEW STRATEGY RESEARCH

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

Coding Agents

Research Agents

Quant Agents

Dependency Management

GitHub CI

Security Monitoring

Runtime Verification

Audit Infrastructure

Incident Response

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

v1.0 — 2026-10-22
