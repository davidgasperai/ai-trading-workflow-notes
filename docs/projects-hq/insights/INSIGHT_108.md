# PROJECTS HQ INSIGHT #108

## Date
2026-10-25

## Title
Risk Reduction Is Not Risk Acceptance

---

## Core Principle

A system can become
less dangerous
without becoming
acceptably safe.

Therefore:

RISK REDUCED
!=
RISK ACCEPTABLE.

Relative improvement
must never substitute
for an independently defined
risk acceptance threshold.

---

## The Problem

Consider an autonomous agent
evaluated against
a security benchmark.

Before mitigation:

90.5% success
on a prohibited
capability test.

After mitigation:

81.0% success
on the same benchmark.

The measured result
has improved.

However,
the remaining capability
may still be unacceptable.

A lower risk score
does not automatically
authorize deployment.

---

## Three Separate Questions

### 1. Did Risk Decrease?

Compare the results
before and after
the mitigation.

### 2. Is Residual Risk Acceptable?

Compare the remaining risk
against an independently
approved acceptance threshold.

### 3. Is the Evidence Sufficient?

Determine whether
the evaluation method,
sample size,
coverage,
and independence
support the conclusion.

All three questions
require explicit answers.

---

## Absolute Versus Relative Risk

A relative improvement
can be meaningful.

But it does not establish
an acceptable absolute
risk level.

For example:

BASELINE_SCORE:
90.5%

MITIGATED_SCORE:
81.0%

ABSOLUTE_CHANGE:
-9.5 percentage points

This comparison
does not prove
that the mitigated system
is safe to deploy.

The benchmark itself
must also be understood.

---

## Predefined Acceptance Criteria

Risk acceptance criteria
must be defined
before evaluating
the proposed mitigation.

The criteria should specify:

RISK_CATEGORY

SEVERITY_LEVEL

ACCEPTANCE_THRESHOLD

TEST_METHOD

TEST_SCOPE

REQUIRED_SAMPLE_SIZE

CONFIDENCE_REQUIREMENTS

EVALUATION_OWNER

APPROVAL_AUTHORITY

POLICY_VERSION.

The agent under evaluation
must not choose
its own acceptance threshold.

---

## Independent Evaluation

A system developer
may prepare a mitigation.

However,
the developer must not be
the sole authority
declaring the remaining
risk acceptable.

Independent evaluation
should examine:

- Test validity
- Measurement uncertainty
- Coverage limitations
- Critical failure modes
- Residual capabilities
- Previously unseen scenarios
- Possible regression
- Operational constraints.

---

## Risk Acceptance States

Proposed states:

RISK_NOT_EVALUATED

RISK_REDUCED

RISK_ABOVE_THRESHOLD

RISK_WITHIN_THRESHOLD

EVIDENCE_INSUFFICIENT

ACCEPTANCE_PENDING

ACCEPTED_WITH_CONDITIONS

REJECTED.

RISK_REDUCED
is not equivalent to
ACCEPTED_WITH_CONDITIONS.

---

## Unknown Is Not Acceptable

If the evaluation
does not cover
a critical failure mode,
the system must not
silently classify
that risk as acceptable.

Unknown exposure
requires an explicit
assessment or restriction.

Missing evidence
must not become
positive evidence.

---

## Acceptance Authority

The agent may:

IDENTIFY_RISK

PROPOSE_MITIGATION

EXECUTE_AUTHORIZED_TESTS

COMPARE_RESULTS

REPORT_RESIDUAL_RISK.

The agent must not:

DEFINE_ITS_OWN_THRESHOLD

WEAKEN_ACCEPTANCE_CRITERIA

EXCLUDE_FAILED_TESTS

APPROVE_ITS_OWN_DEPLOYMENT

ACCEPT_UNREVIEWED_RISK

EXPAND_ITS_OWN_AUTHORITY.

Risk acceptance
requires separate
authorized approval.

---

## Negative Tests

A future test suite
should simulate:

1. Large relative improvement
   with unacceptable
   residual risk.

2. Small improvement
   presented as complete
   risk elimination.

3. Missing critical
   test scenarios.

4. Acceptance threshold
   changed after results
   become known.

5. Developer approving
   its own mitigation.

6. Benchmark contamination.

7. Insufficient
   evaluation samples.

8. Unknown residual
   capabilities.

9. Safety regression
   outside the primary
   benchmark.

10. Deployment requested
    without independent
    acceptance evidence.

Expected result:

ACCEPTANCE DENIED
when required conditions
are not satisfied.

---

## Evidence Contract

A proposed risk
acceptance record
should include:

RISK_ID

MITIGATION_ID

BASELINE_EVIDENCE

MITIGATED_EVIDENCE

ABSOLUTE_RISK_METRIC

RELATIVE_CHANGE

ACCEPTANCE_THRESHOLD

THRESHOLD_VERSION

EVALUATION_SCOPE

TEST_LIMITATIONS

RESIDUAL_RISK

INDEPENDENT_VERIFIER

APPROVAL_STATUS

AUDIT_REFERENCE.

Unknown fields
must remain explicitly
unknown.

---

## Relationship to #084

#084:

Authority must decay
unless it is revalidated.

#108:

A reduction in risk
does not automatically
create new authority.

---

## Relationship to #099

#099:

A strategy must not
choose its own exam.

#108:

A mitigated system
must not choose
its own passing threshold.

---

## Relationship to #100

#100:

A rule is not a control
until it is enforced.

#108:

A risk acceptance threshold
is not a control
until it can block
unauthorized deployment.

---

## Relationship to #105

#105:

A patch is not complete
until exposure is closed.

#108:

A mitigation is not
an accepted safety state
until residual risk
has been evaluated
against predefined criteria.

---

## Proposed Control

CONTROL_ID:
NM-RISK-ACCEPT-001

REQUIREMENT:
Risk acceptance must be
independent of relative
mitigation improvement.

NEGATIVE_TEST:
Reduce a simulated
critical failure rate
while leaving it above
the approved threshold.

EXPECTED_RESULT:
Risk improvement
is recorded.

Residual risk
remains unacceptable.

Deployment authorization
is denied.

Audit evidence
is preserved.

---

## Projects HQ Principle

> Improvement is evidence
> of progress.
>
> It is not evidence
> of sufficient safety.
>
> A system becomes
> acceptable only when
> independently evaluated
> against previously approved
> risk criteria.

---

## Shortest Version

RISK REDUCED
!=
RISK ACCEPTABLE.

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

Security Evaluations

Model Deployment

Risk Acceptance

Independent Verification

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

v1.0 — 2026-10-25
