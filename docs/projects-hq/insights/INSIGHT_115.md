# PROJECTS HQ INSIGHT #115

## Date
2026-11-01

## Title
A Trusted Application Can Load an Untrusted Dependency

---

## Core Principle

A trusted application
does not establish
that every dependency
loaded by that application
is trustworthy.

External code
may change independently
of the application
that consumes it.

Therefore:

TRUSTED APPLICATION
!=
TRUSTED DEPENDENCIES.

---

## The Problem

Consider a future
Research Agent.

The agent runs
an approved application.

The application
uses an external library
or remote service.

The dependency
was previously reviewed.

However,
its delivered code
changes unexpectedly.

The application
continues operating.

The agent may execute
new behavior
without any change
to its own source code.

The application
appears unchanged.

Its effective
execution environment
is not unchanged.

---

## Dependency Trust

Dependency trust
requires more than
recognizing a provider.

A dependency
must be evaluated
for its actual
executed content,
origin,
version,
integrity,
and permissions.

---

## Four Separate Questions

### 1. Source Trust

Is the dependency
obtained from
an approved source?

### 2. Version Integrity

Is the exact
executed version
known and recorded?

### 3. Content Integrity

Does the delivered content
match the independently
approved artifact?

### 4. Execution Authority

Can the dependency
perform only
the operations
it is authorized
to perform?

These questions
must remain separate.

---

## Critical Distinction

TRUSTED_PROVIDER

does not imply:

TRUSTED_CONTENT.

LOCKED_VERSION

does not imply:

SECURE_VERSION.

VALID_SIGNATURE

does not imply:

SAFE_BEHAVIOR.

APPROVED_APPLICATION

does not imply:

APPROVED_RUNTIME_DEPENDENCIES.

---

## Threat Model

Relevant threats include:

COMPROMISED_PACKAGE

COMPROMISED_CDN

COMPROMISED_REMOTE_SCRIPT

DEPENDENCY_SUBSTITUTION

MALICIOUS_UPDATE

TRANSITIVE_DEPENDENCY_ATTACK

SESSION_CONTEXT_ABUSE

UNAUTHORIZED_TOOL_EXECUTION

DEPENDENCY_PERMISSION_ESCALATION

SUPPLY_CHAIN_COMPROMISE.

---

## Dependency Inventory

A proposed dependency
inventory should identify:

DEPENDENCY_ID

DEPENDENCY_TYPE

PROVIDER_ID

SOURCE_LOCATION

VERSION_IDENTIFIER

CONTENT_HASH

SIGNATURE_REFERENCE

APPROVAL_REFERENCE

APPROVED_PERMISSIONS

NETWORK_REQUIREMENTS

DATA_ACCESS_SCOPE

EXECUTION_ENVIRONMENT

LAST_VERIFICATION_TIMESTAMP

AUDIT_REFERENCE.

Unknown values
must remain explicitly
unknown.

---

## Runtime Integrity

Build-time approval
does not automatically
establish runtime integrity.

A system may execute
different content
from the content
originally reviewed.

Where runtime integrity
is required,
the executed artifact
must match
the approved artifact.

---

## Dynamic Dependencies

Special attention
is required for:

REMOTE_JAVASCRIPT

BROWSER_EXTENSIONS

PACKAGE_INSTALL_SCRIPTS

RUNTIME_DOWNLOADS

EXTERNAL_PLUGINS

MCP_SERVERS

REMOTE_AGENT_TOOLS

DYNAMIC_MODULE_IMPORTS.

These dependencies
may introduce behavior
outside the application's
original review scope.

---

## Version Pinning

Version pinning
can reduce
unexpected dependency drift.

However:

PINNED
does not mean
SAFE.

A pinned dependency
may already contain
a vulnerability.

Pinning must therefore
be combined with
independent review
and appropriate
runtime controls.

---

## Transitive Dependencies

An approved dependency
may itself depend
on other components.

Those components
form part of
the effective
execution environment.

Trust must not stop
at the first
dependency boundary.

---

## Permission Boundaries

A dependency
must not inherit
unlimited authority
from its host application.

Where technically feasible,
dependencies should operate
within narrowly defined
permission boundaries.

Access to:

FILES

NETWORK

SECRETS

SESSION_DATA

EXECUTION_TOOLS

FINANCIAL_APIS

must be independently
restricted.

---

## High-Impact Operations

A compromised dependency
must not be able
to authorize:

LIVE_ORDER_SUBMISSION

CAPITAL_TRANSFER

WITHDRAWAL

BROKER_PERMISSION_CHANGE

PRODUCTION_CREDENTIAL_ACCESS

RISK_POLICY_MODIFICATION.

Independent authorization
remains mandatory.

---

## Proposed Control

CONTROL_ID:
NM-DEP-INTEGRITY-001

REQUIREMENT:

Consequential agent
executions must preserve
evidence of the identity
and integrity
of executed dependencies.

Unapproved dependency
substitution must not
silently inherit
the authority
of the host application.

---

## Proposed Negative Test

TEST_ID:
NM-DEP-INTEGRITY-001-NEG-01

SCENARIO:

A simulated Research Agent
runs an approved application.

The application
loads an external dependency.

The dependency's
delivered content
does not match
the approved content hash.

The dependency
attempts to execute
an unauthorized operation.

EXPECTED RESULT:

DEPENDENCY_IDENTITY:
RECORDED

CONTENT_INTEGRITY:
FAILED

UNAUTHORIZED_OPERATION:
BLOCKED

EXECUTION:
FAILED_CLOSED

AUDIT_EVIDENCE:
PRESERVED

PRODUCTION_AUTHORITY:
UNCHANGED.

---

## Additional Negative Tests

A future authorized
test suite should include:

1. Approved application
   with modified remote script.

2. Pinned dependency
   containing a known
   vulnerability.

3. Approved package
   with compromised
   transitive dependency.

4. Dependency downloaded
   from an unapproved source.

5. Runtime content
   differing from
   build-time content.

6. Dependency attempting
   unauthorized network access.

7. External tool
   attempting to access
   production credentials.

8. Compromised dependency
   attempting to modify
   authorization policy.

9. Valid signature
   on malicious code.

10. Dependency substitution
    without audit evidence.

---

## Relationship to #089

#089:

Provenance must travel
with the artifact.

#115:

Dependency provenance
must travel
with the execution evidence.

---

## Relationship to #103

#103:

A refactor must prove
behavioral equivalence.

#115:

A dependency update
must not silently inherit
assurance from
a previous version.

---

## Relationship to #111

#111:

Automated permission approval
must be independently bounded.

#115:

A dependency
must not inherit
unbounded authority
from its host application.

---

## Relationship to #112

#112:

A model router
is part of the system
under evaluation.

#115:

Runtime dependencies
are also part
of the evaluated
execution environment.

---

## Relationship to #113

#113:

A valid execution path
does not establish
authorized intent.

#115:

An approved application
does not establish
the integrity
of every dependency
executed through it.

---

## Relationship to #114

#114:

An asset balance
does not establish
accessible liquidity.

#115:

A trusted application
does not establish
trusted dependencies.

Both principles
reject unsupported
trust inheritance.

---

## Projects HQ Principle

> Trust does not
> automatically propagate
> through software
> dependencies.
>
> Every consequential
> execution boundary
> must preserve
> independently verifiable
> integrity evidence.
>
> Approval of the host
> is not approval
> of every component
> it may execute.

---

## Shortest Version

TRUSTED APPLICATION
!=
TRUSTED DEPENDENCIES.

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

UNREVIEWED_DEPENDENCY_INSTALLATION

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

Dependency Governance

GitHub Actions

Software Supply Chain

MCP Tool Security

Runtime Integrity

Execution Audit

---

## Status

STRATEGIC PRINCIPLE:
DOCUMENTED

IMPLEMENTATION:
NOT IMPLEMENTED

DEPENDENCY INVENTORY:
NOT IMPLEMENTED

RUNTIME VERIFICATION:
NOT IMPLEMENTED

NEGATIVE TESTS:
NOT EXECUTED

CONTROL STATUS:
PROPOSED

LIVE TRADING:
NOT AUTHORIZED

---

## Revision

v1.0 — 2026-11-01
