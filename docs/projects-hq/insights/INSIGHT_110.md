# PROJECTS HQ INSIGHT #110

## Date
2026-10-27

## Title
A Verified Proof Is Not a Validated Specification

---

## Core Principle

A formally verified proof
establishes a result
within a defined
formal system.

It does not automatically
establish that the formal
specification correctly
describes the real-world
system of interest.

Therefore:

PROOF VERIFIED
!=
SPECIFICATION VALIDATED.

---

## The Problem

Consider a future
Trading Risk Agent.

A formal specification
states:

Every live order
must pass an approved
risk authorization gate.

A machine-checked proof
establishes that all orders
within the specified model
pass that gate.

The proof may be correct.

However, the real system
might contain:

- An undocumented API route.
- An unmodeled execution path.
- A stale authorization cache.
- A manual override.
- A missing order category.
- An external broker behavior
  absent from the model.

The formal proof
does not establish
that these possibilities
are impossible.

It establishes a property
of the system
as formally specified.

---

## Four Separate Questions

### 1. Is the Formal Statement Correct?

Does the theorem express
the intended requirement?

### 2. Is the Proof Valid?

Does the proof checker
accept the derivation
under the declared axioms
and assumptions?

### 3. Is the Specification Faithful?

Does the formal model
represent the relevant
real-world behavior?

### 4. Is the Evidence Current?

Does the specification
still match the system
being evaluated?

These questions
must remain separate.

---

## Required Evidence

A proposed verification
record should identify:

CLAIM_ID

FORMAL_STATEMENT

SPECIFICATION_VERSION

ASSUMPTIONS

AXIOMS

PROOF_ARTIFACT

PROOF_CHECKER_VERSION

PROOF_CHECK_RESULT

IMPLEMENTATION_VERSION

ENVIRONMENT_SCOPE

MODEL_LIMITATIONS

SPECIFICATION_VALIDATOR

VALIDATION_EVIDENCE

APPROVAL_REFERENCE.

Unknown fields
must remain explicitly
unknown.

---

## Verification Boundaries

A formal proof
may establish
a mathematical property.

It does not necessarily
establish:

REAL_WORLD_APPLICABILITY

DATA_QUALITY

MODEL_COMPLETENESS

OPERATIONAL_RELIABILITY

EXTERNAL_SYSTEM_BEHAVIOR

ECONOMIC_VALIDITY

PRODUCTION_AUTHORIZATION.

These require
their own evidence.

---

## Assumption Register

Every consequential proof
should expose
its material assumptions.

Examples:

ALL_ORDER_PATHS_MODELED

RISK_GATE_CANNOT_BE_BYPASSED

INPUT_DATA_IS_VALID

EXPOSURE_LEDGER_IS_COMPLETE

BROKER_ACKNOWLEDGMENTS_ARE_RELIABLE

NO_UNMODELED_EXTERNAL_ACTIONS.

An assumption
must not silently become
an observed fact.

---

## Independent Validation

The agent that generated
the specification
must not be the sole
authority validating
its real-world coverage.

Independent review
should compare:

FORMAL_MODEL

IMPLEMENTED_SYSTEM

OBSERVED_BEHAVIOR

EXTERNAL_DEPENDENCIES.

Material discrepancies
must invalidate
the corresponding
deployment claim.

---

## Negative Tests

A future authorized
test suite should include:

1. A correct proof
   over an incomplete model.

2. A theorem whose wording
   differs from the intended
   safety requirement.

3. An undocumented
   execution path.

4. A missing
   exposure category.

5. An outdated
   specification version.

6. A proof relying
   on an unverified
   environmental assumption.

7. A valid model
   with an implementation
   that violates it.

8. A proof artifact
   presented without
   its assumptions.

9. An external dependency
   whose behavior changed
   after verification.

10. A request for
    deployment approval
    based only on
    proof-checker success.

Expected result:

PROOF_VALIDITY_RECORDED.

SPECIFICATION_VALIDATION
REMAINS SEPARATE.

NO AUTOMATIC
DEPLOYMENT AUTHORITY.

---

## Proposed Control

CONTROL_ID:
NM-FORMAL-SCOPE-001

REQUIREMENT:

Consequential formal
verification claims
must identify the exact
property proved
and the assumptions
under which it holds.

Real-world applicability
requires independent
specification validation.

---

## Proposed Negative Test

TEST_ID:
NM-FORMAL-SCOPE-001-NEG-01

SCENARIO:

A formal proof
correctly establishes
that every modeled order
passes a risk gate.

A simulated execution
environment contains
an additional order route
not represented
in the specification.

EXPECTED_RESULT:

The proof remains
recorded as valid
within its formal scope.

The specification
is rejected as incomplete.

Production authorization
is denied.

The discrepancy
is preserved
for independent review.

---

## Relationship to #091

#091:

Numbers are not comparable
until their measurement
contracts match.

#110:

A verified theorem
must be connected
to the correct
real-world specification.

---

## Relationship to #099

#099:

A strategy must not
choose its own exam.

#110:

A system must not
validate its own
specification solely
by proving properties
of that specification.

---

## Relationship to #103

#103:

A refactor must prove
behavioral equivalence.

#110:

Any equivalence claim
must define the exact
behavioral scope
being compared.

---

## Relationship to #109

#109:

An agent's explanation
is not proof
of compliance.

#110:

A valid formal proof
is not evidence
that its specification
fully captures reality.

---

## Projects HQ Principle

> Formal verification
> can establish
> that a conclusion
> follows from
> a specification.
>
> Independent validation
> must establish
> that the specification
> describes the system
> we actually intend
> to govern.

---

## Shortest Version

PROOF VERIFIED
!=
SPECIFICATION VALIDATED.

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

Formal Verification

Proof Assistants

Specification Review

Exposure Control

Execution Infrastructure

Audit Evidence

---

## Status

STRATEGIC PRINCIPLE:
DOCUMENTED

IMPLEMENTATION:
NOT IMPLEMENTED

SPECIFICATION VALIDATION:
NOT IMPLEMENTED

NEGATIVE TESTS:
NOT EXECUTED

CONTROL STATUS:
PROPOSED

LIVE TRADING:
NOT AUTHORIZED

---

## Revision

v1.0 — 2026-10-27
