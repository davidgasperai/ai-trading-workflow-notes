
# PROJECTS HQ INSIGHT #132

Date: 2026-11-18
Title: A Model Upgrade Must Earn Its Place Through Independent Evaluation
Revision: v1.0
Status: STRATEGIC_DOCUMENTATION_ONLY

## Observation

On 17 November 2026, OpenAI released GPT-6.2 Astra and GPT-6.2 Sol.

On the same day, GitHub announced broader availability of these models in Copilot, expanded Copilot Fusion, and introduced Copilot Evals in public preview.

These announcements increase the number of available model choices and evaluation tools.

However, a new model release, a provider benchmark, or an automated routing recommendation does not establish that a model is better for our specific project.

A model may perform well on a public coding benchmark while performing poorly on repository-specific tasks, governance requirements, evidence preservation, or authorization boundaries.

A model may also be faster or cheaper without producing equally reliable results.

The operational risk is silently promoting model availability or benchmark performance into project approval.

### Sources

- https://help.openai.com/en/articles/9624314-model-release-notes
- https://deploymentsafety.openai.com/gpt-6-2-astra-sol/internal-deployment-of-gpt-6.2-astra-and-gpt-6.2-sol
- https://github.blog/changelog/month/11-2026/

## Core Principle

MODEL_AVAILABLE != MODEL_APPROVED

PROVIDER_BENCHMARK != PROJECT_VALIDATION

HIGHER_CAPABILITY != HIGHER_RELIABILITY

LOWER_COST != BETTER_TOTAL_OUTCOME

MODEL_ROUTED != MODEL_AUTHORIZED

EVALUATION_PASSED != DEPLOYMENT_AUTHORIZED

A model upgrade must be justified by evidence relevant to the intended workflow.

The model must not define its own success criteria, evaluate itself as the sole judge, or grant itself operational authority.

## Proposed Control

CONTROL_ID: NM-MODEL-EVALUATION-001

CONTROL_NAME: Independent Model Upgrade Evaluation Gate

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

### Requirements

1. Define the intended workflow and permitted task scope before evaluating a candidate model.

2. Record the exact model identifier, version, provider, and relevant configuration.

3. Establish evaluation criteria independently of the candidate model.

4. Use a documented task set appropriate to the actual workflow.

5. Separate provider-reported benchmarks from project-specific measurements.

6. Preserve the inputs, outputs, timestamps, tool permissions, and evaluation environment.

7. Measure correctness, reproducibility, evidence quality, latency, and total cost where relevant.

8. Evaluate authorization compliance and the handling of restricted actions.

9. Prevent the candidate model from approving its own deployment.

10. Record known limitations, failed cases, and unresolved uncertainties.

11. Require independent review before accepting a model for consequential work.

12. Treat automatic model routing as an additional dependency requiring provenance and authorization.

13. Require revalidation when the model, toolchain, prompt, or execution environment changes materially.

14. Preserve the current project's existing governance restrictions throughout any future evaluation.

## Proposed Evidence Fields

- evaluation_id
- candidate_model_id
- candidate_model_version
- provider_id
- intended_workflow
- evaluation_scope
- evaluation_dataset_reference
- evaluation_contract_version
- baseline_model_id
- tool_configuration
- permission_scope
- test_execution_timestamp
- correctness_result
- evidence_quality_result
- authorization_compliance_result
- latency_measurement
- cost_measurement
- failure_cases
- independent_reviewer
- approval_status
- deployment_authorization_status

These fields describe a proposed evidence model.

They are not an implemented canonical registry or evaluation system.

## Negative Tests — Proposed, Not Executed

### NEG-01: New model automatically replaces baseline

Input:
A provider releases a newer model and the workflow switches automatically.

Expected:
MODEL_CHANGE_REQUIRES_REVALIDATION.

### NEG-02: Provider benchmark treated as project proof

Input:
A candidate model scores highly on a public benchmark but has no project-specific evaluation.

Expected:
PROJECT_VALIDATION_MISSING.

### NEG-03: Model evaluates itself

Input:
The candidate model generates the test cases, grades its own answers, and declares success.

Expected:
INDEPENDENT_EVALUATION_REQUIRED.

### NEG-04: Cost reduction hides quality loss

Input:
A cheaper model produces more unsupported claims or incomplete evidence.

Expected:
QUALITY_REGRESSION_REVIEW_REQUIRED.

### NEG-05: Automatic routing changes model identity

Input:
A model router selects a different provider without preserving provenance.

Expected:
ROUTING_PROVENANCE_INCOMPLETE.

### NEG-06: Evaluation environment differs from production

Input:
A model passes tests with broader permissions than its intended deployment environment.

Expected:
ENVIRONMENT_MISMATCH.

### NEG-07: Safety compliance omitted

Input:
A candidate performs coding tasks correctly but attempts unauthorized tool calls.

Expected:
AUTHORIZATION_COMPLIANCE_FAILED.

### NEG-08: Prompt changes after evaluation

Input:
The production prompt differs materially from the evaluated prompt.

Expected:
REVALIDATION_REQUIRED.

### NEG-09: Evaluation results lack reproducibility

Input:
Reported success cannot be reconstructed from preserved evidence.

Expected:
EVALUATION_NOT_VERIFIED.

### NEG-10: Passing evaluation triggers deployment

Input:
A model passes its tests and attempts to activate an agent workflow automatically.

Expected:
DEPLOYMENT_AUTHORIZATION_REQUIRED.

### NEG-11: Model upgrade expands financial permissions

Input:
A newly available model requests broker or exchange write access.

Expected:
BROKER_WRITE_DENIED.

### NEG-12: Benchmark success reopens parked strategies

Input:
A stronger coding model proposes new backtests for DB1 or EF2.

Expected:
STRATEGY_RESEARCH_NOT_AUTHORIZED.

## Evaluation Boundary

This Insight does not authorize an evaluation run.

The proposed gate may only be implemented or tested after a separate, explicit governance decision.

Until then:

- No candidate model is approved by this document.
- No evaluation dataset is ratified.
- No benchmark execution is authorized.
- No model routing change is authorized.
- No agent deployment is authorized.
- No financial execution is authorized.

## Governance Boundary

DB1: PARKED

EF2: PARKED

MEASUREMENT_PIPELINE: UNVALIDATED

RC2_RATIFICATION: NOT_RATIFIED

REGISTRY_EXPOSURE_LEDGER_V0.3: DRAFT_NOT_CANONICAL

NEW_STRATEGY_RESEARCH: NOT_AUTHORIZED

NEW_BACKTESTS: NOT_AUTHORIZED

GITHUB_WORKFLOW_ACTIVATION: NOT_AUTHORIZED

AGENT_DEPLOYMENT: NOT_AUTHORIZED

BROKER_API_WRITE: NOT_AUTHORIZED

LIVE_TRADING: NOT_AUTHORIZED

## Verification Status

INSIGHT_NUMBER: 132

STRATEGIC_PRINCIPLE: DOCUMENTED

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

NEGATIVE_TESTS: NOT_EXECUTED

PROJECT_SPECIFIC_MODEL_EVALUATION: NOT_PERFORMED

INDEPENDENT_EVALUATION: NOT_IMPLEMENTED

MODEL_UPGRADE_APPROVAL: NOT_GRANTED

GITHUB_PUBLICATION: NOT_VERIFIED

## Relationship to Earlier Insights

This principle complements:

- INSIGHT #091 — Numbers Are Not Comparable Until Their Measurement Contracts Match
- INSIGHT #098 — An Approval Must Bind to the Exact Action
- INSIGHT #099 — A Strategy Must Not Choose Its Own Exam
- INSIGHT #103 — A Refactor Must Prove Behavioral Equivalence
- INSIGHT #109 — An Agent's Explanation Is Not Proof of Compliance
- INSIGHT #125 — New Model Availability Is Not Operational Approval
- INSIGHT #127 — Provider Availability Is Not Execution Resilience
- INSIGHT #131 — An Agent's Financial Authority Must Be Independently Verifiable

Insight #132 focuses specifically on evidence-based model selection, independent evaluation, and preventing a new model or routing mechanism from silently inheriting operational authority.

## Closing Principle

A newer model is a candidate, not an upgrade decision.

A benchmark result is evidence within a defined scope, not universal proof.

A successful evaluation is not permission to deploy.

VIDIME. OVERUJEME. STAVIME.
