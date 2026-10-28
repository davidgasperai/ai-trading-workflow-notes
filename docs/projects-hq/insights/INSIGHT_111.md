# PROJECTS HQ INSIGHT #111

## Date
2026-10-28

## Title
Automated Permission Approval Must Be Independently Bounded

---

## Core Principle

An AI-based permission classifier
may reduce unnecessary
human approval requests.

However:

AUTO-APPROVED
!=
INDEPENDENTLY SAFE.

A classification decision
must not create authority
beyond an independently
approved permission boundary.

---

## The Problem

Consider an autonomous
Research Agent.

The agent requests
permission to execute
a command.

A separate AI classifier
evaluates the request.

The classifier returns:

SAFE_TO_RUN.

The execution environment
automatically proceeds.

This can improve
workflow efficiency.

However, the classifier
may misunderstand:

- The command's side effects.
- The target environment.
- The sensitivity of a file.
- The meaning of an API call.
- The current permission scope.
- The consequences of
  combining multiple actions.

A false-safe classification
may authorize an action
that should have been denied.

---

## Three Separate Decisions

### 1. Classification

Is the requested action
likely to be safe?

### 2. Authorization

Is the action permitted
under the applicable
independent policy?

### 3. Enforcement

Will the execution boundary
actually prevent
unauthorized behavior?

These decisions
must remain distinct.

---

## Classification Is Advisory

An AI classifier may:

IDENTIFY_LOW_RISK_ACTIONS

RECOMMEND_APPROVAL

RECOMMEND_HUMAN_REVIEW

FLAG_UNCERTAINTY

REPORT_POTENTIAL_SIDE_EFFECTS.

It must not independently:

EXPAND_PERMISSION_SCOPE

OVERRIDE_EXPLICIT_DENIALS

AUTHORIZE_LIVE_TRADING

GRANT_PRODUCTION_WRITE_ACCESS

RELEASE_SECRETS

DISABLE_AUDIT_CONTROLS

APPROVE_ITS_OWN_POLICY_CHANGES.

---

## Independent Permission Ceiling

Every automated approval
must remain inside
a predefined
permission ceiling.

The ceiling must be
established by
an authorized controller.

It must not be changed
by the agent requesting
the action.

It must not be changed
by the classifier
evaluating that request.

---

## Required Decision Contract

A proposed permission
decision record
should include:

REQUEST_ID

AGENT_ID

ACTION_TYPE

TARGET_RESOURCE

EXECUTION_ENVIRONMENT

CLASSIFIER_ID

CLASSIFIER_VERSION

CLASSIFICATION_RESULT

CLASSIFICATION_CONFIDENCE

POLICY_VERSION

INDEPENDENT_POLICY_RESULT

HUMAN_APPROVAL_REQUIRED

FINAL_AUTHORIZATION_RESULT

ENFORCEMENT_RESULT

AUDIT_REFERENCE.

Unknown fields
must remain explicitly
unknown.

---

## False-Allow Risk

Permission automation
must be evaluated
for false approvals.

A false allow occurs
when an unsafe
or unauthorized action
is classified
as safe to execute.

The evaluation
must distinguish:

FALSE_ALLOW

FALSE_DENY

CORRECT_ALLOW

CORRECT_DENY

INSUFFICIENT_EVIDENCE.

A low overall error rate
does not automatically
establish acceptable safety.

Critical false allows
may require
a stricter threshold
than ordinary mistakes.

---

## Risk-Based Boundaries

Low-risk operations
may be candidates
for automated approval
when independently authorized.

Consequential operations
must retain stronger controls.

Examples include:

PRODUCTION_MODIFICATION

CREDENTIAL_ACCESS

EXTERNAL_DATA_TRANSFER

PERMISSION_ESCALATION

BROKER_API_WRITE

ORDER_SUBMISSION

CAPITAL_TRANSFER

RISK_LIMIT_MODIFICATION.

A classifier's
SAFE label
must never override
a mandatory approval
for these categories.

---

## Unknown Must Fail Closed

If the classifier
cannot reliably determine
the consequences
of an action:

DO_NOT_AUTO_APPROVE.

If the policy version
is unavailable:

DO_NOT_AUTO_APPROVE.

If the execution environment
is unknown:

DO_NOT_AUTO_APPROVE.

If required audit evidence
cannot be produced:

DO_NOT_AUTO_APPROVE.

Uncertainty
must not silently become
permission.

---

## Independent Evaluation

The permission classifier
must not be the sole authority
evaluating its own accuracy.

Independent tests
should examine:

- False-safe classifications.
- Context-dependent commands.
- Chained tool operations.
- Hidden side effects.
- Environment confusion.
- Policy version mismatches.
- Prompt injection.
- Permission escalation.
- Audit record integrity.
- Attempts to bypass
  human approval.

---

## Negative Tests

A future authorized
test suite should include:

1. A harmless-looking command
   with prohibited side effects.

2. A read request
   that exposes credentials.

3. A command valid
   in a test environment
   but prohibited
   in production.

4. A classifier approving
   an action explicitly
   denied by policy.

5. An agent splitting
   a prohibited operation
   into individually
   low-risk steps.

6. An outdated classifier
   using stale policy context.

7. A prompt injection
   attempting to influence
   the classifier.

8. Missing audit evidence
   after automated approval.

9. An ambiguous action
   receiving a confident
   safe classification.

10. A request to authorize
    live trading
    without human approval.

Expected result:

NO AUTOMATIC AUTHORITY
BEYOND THE APPROVED
PERMISSION CEILING.

---

## Proposed Control

CONTROL_ID:
NM-PERM-CLASS-001

REQUIREMENT:

AI-assisted permission
classification must remain
subordinate to independently
enforced authorization policy.

A safe classification
must never override
an explicit denial
or mandatory human approval.

---

## Proposed Negative Test

TEST_ID:
NM-PERM-CLASS-001-NEG-01

SCENARIO:

A permission classifier
labels a simulated
production-write action
as safe.

The independent policy
prohibits production writes.

EXPECTED_RESULT:

CLASSIFICATION:
SAFE

POLICY:
DENY

FINAL_AUTHORIZATION:
DENY

EXECUTION:
BLOCKED

AUDIT:
PRESERVED.

---

## Relationship to #083

#083:

The guard must live outside
the system it guards.

#111:

An AI permission classifier
must remain subordinate
to an independently
enforced policy boundary.

---

## Relationship to #092

#092:

Every autonomous agent
needs its own identity.

#111:

An identified agent
still requires
independent authorization
for each consequential action.

---

## Relationship to #098

#098:

An approval must bind
to the exact action.

#111:

Automated classification
must not substitute
for mandatory authorization.

---

## Relationship to #108

#108:

Risk reduction
is not risk acceptance.

#111:

Fewer manual approvals
do not prove
that permission automation
has acceptable residual risk.

---

## Projects HQ Principle

> Automation can classify
> an action as safe.
>
> Only independent policy
> can establish
> whether that action
> is authorized.
>
> Enforcement must remain
> effective even when
> the classifier is wrong.

---

## Shortest Version

AUTO-APPROVED
!=
INDEPENDENTLY SAFE.

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

Permission Classification

Authorization Gateway

Codex Governance

GitHub Governance

Audit Infrastructure

Human Approval

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

v1.0 — 2026-10-28
