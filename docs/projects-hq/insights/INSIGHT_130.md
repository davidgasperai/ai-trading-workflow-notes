
# PROJECTS HQ INSIGHT #130

Date: 2026-11-16
Title: Repository Access Is Not Workflow Authority
Revision: v1.0
Status: STRATEGIC_DOCUMENTATION_ONLY

## Observation

On 14 November 2026, reporting on the wfx-loot campaign described a large-scale attack against GitHub repositories and automation workflows.

According to the published security research, attackers used compromised GitHub accounts to probe repositories and attempted to introduce malicious execution paths through pull requests, workflow modifications, and package installation mechanisms.

The reported objective included access to repository secrets, cloud credentials, SSH keys, and other sensitive configuration data.

The reported scope and attribution remain dependent on the cited investigation. No evidence was established in this Insight that our own repositories were compromised.

This incident illustrates a critical governance distinction:

Access to a repository does not imply authority to execute code with secrets or privileged infrastructure credentials.

### Sources

- https://www.techradar.com/pro/security/thousands-of-github-repositories-targeted-in-widespread-attack-4-800-accounts-already-compromised-to-steal-cloud-credentials
- https://github.blog/changelog/2026-11-12-secret-scanning-adds-a-detector-for-cloudflare/
- https://github.blog/changelog/2026-10-13-secret-scanning-blocks-anthropic-keys-by-default-adds-salesforce/

## Core Principle

REPOSITORY_ACCESS != WORKFLOW_AUTHORITY

PULL_REQUEST_CREATED != CODE_TRUSTED

CONTRIBUTOR_AUTHENTICATED != CONTRIBUTION_AUTHORIZED

WORKFLOW_TRIGGERED != SECRET_ACCESS_APPROVED

SECRET_SCANNING_ENABLED != SECRET_EXPOSURE_IMPOSSIBLE

SUCCESSFUL_CI_RUN != SUPPLY_CHAIN_INTEGRITY_VERIFIED

A repository is a collaboration boundary.

A workflow is an execution boundary.

A secret is a privileged capability.

These boundaries must not be collapsed into one implicit trust decision.

## Proposed Control

CONTROL_ID: NM-WORKFLOW-TRUST-001

CONTROL_NAME: Repository Workflow Authority Gate

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

### Requirements

1. Maintain an explicit inventory of executable workflows and their triggers.

2. Record which repository events may initiate each workflow.

3. Separate untrusted pull-request content from privileged execution contexts.

4. Deny access to secrets unless a specific workflow has explicit authorization.

5. Minimize the default permissions of automation tokens.

6. Require independent review of changes to workflow definitions and execution permissions.

7. Treat dependency installation scripts and third-party actions as executable supply-chain inputs.

8. Pin and verify external dependencies where appropriate, without assuming pinning alone eliminates compromise risk.

9. Preserve evidence of workflow changes, approvals, execution context, and relevant security alerts.

10. Prevent an agent from granting itself additional repository, cloud, broker, or exchange permissions.

11. Require explicit human authorization for any proposed activation or modification of privileged automation.

12. Keep all broker and exchange write capabilities disabled under the current project governance.

## Proposed Evidence Fields

- repository_id
- workflow_id
- workflow_file_path
- workflow_revision
- triggering_event
- initiating_identity
- contribution_trust_status
- effective_token_permissions
- secrets_access_scope
- dependency_provenance
- reviewer_identity
- approval_record
- execution_environment
- security_alert_status
- independent_verification_status
- authorization_status

These fields are proposed documentation only.

They are not an implemented canonical registry or evidence ledger.

## Negative Tests — Proposed, Not Executed

### NEG-01: Compromised contributor account

Input:
A previously trusted contributor account submits a malicious pull request.

Expected:
CONTRIBUTION_NOT_IMPLICITLY_TRUSTED.

### NEG-02: Pull request requests secrets

Input:
An untrusted pull request attempts to execute a workflow with privileged secrets.

Expected:
SECRET_ACCESS_DENIED.

### NEG-03: Workflow permission escalation

Input:
A workflow modification requests write permissions beyond its approved scope.

Expected:
HUMAN_REVIEW_REQUIRED.

### NEG-04: Malicious dependency install hook

Input:
A dependency update introduces an unexpected installation script.

Expected:
SUPPLY_CHAIN_REVIEW_REQUIRED.

### NEG-05: Third-party action changes behavior

Input:
An external action changes without corresponding validation of its executable revision.

Expected:
DEPENDENCY_REVALIDATION_REQUIRED.

### NEG-06: Agent modifies its own enforcement

Input:
An AI agent attempts to change the workflow that governs its permissions.

Expected:
SELF_AUTHORIZATION_DENIED.

### NEG-07: Secret scanner reports no findings

Input:
A workflow has broad access to secrets, but secret scanning reports no alert.

Expected:
LEAST_PRIVILEGE_REVIEW_REQUIRED.

### NEG-08: Workflow logs disappear

Input:
Execution records are deleted or unavailable after suspicious activity.

Expected:
FORENSIC_EVIDENCE_INCOMPLETE.

### NEG-09: Successful CI execution

Input:
A workflow completes successfully but its dependency provenance is uncertain.

Expected:
EXECUTION_SUCCESS_ONLY.

### NEG-10: Trading automation activation

Input:
A repository workflow attempts to activate broker or exchange write operations.

Expected:
EXECUTION_DENIED.

## Incident Response Principle

If credible evidence of repository compromise is discovered:

1. Preserve relevant evidence.
2. Identify affected identities, workflows, and execution environments.
3. Determine which secrets or credentials were accessible.
4. Suspend or revoke affected credentials through approved procedures.
5. Assess whether external systems were affected.
6. Require independent verification before restoring privileged automation.
7. Never treat a clean repository view alone as proof that exposure has ended.

This is a proposed response principle, not a report of actions taken.

## Governance Boundary

This Insight documents a strategic security control proposal.

It does not authorize repository modifications, new workflows, dependency installation, agent deployment, strategy research, backtests, or trading.

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

INSIGHT_NUMBER: 130

STRATEGIC_PRINCIPLE: DOCUMENTED

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

NEGATIVE_TESTS: NOT_EXECUTED

REPOSITORY_SECURITY_AUDIT: NOT_PERFORMED

INCIDENT_IMPACT_ON_OUR_REPOSITORIES: NOT_ESTABLISHED

INDEPENDENT_EVALUATION: NOT_IMPLEMENTED

GITHUB_PUBLICATION: NOT_VERIFIED

## Relationship to Earlier Insights

This principle complements:

- INSIGHT #083 — The Guard Must Live Outside the System It Guards
- INSIGHT #087 — Enforcement Must Live at the Point of Consequence
- INSIGHT #092 — Every Autonomous Agent Needs Its Own Identity
- INSIGHT #100 — A Rule Is Not a Control Until It Is Enforced
- INSIGHT #107 — A Sandbox Is Only as Strong as Its Egress Boundaries
- INSIGHT #127 — Provider Availability Is Not Execution Resilience
- INSIGHT #129 — Service Restoration Is Not Risk Resolution

Insight #130 focuses on the execution authority created by repository automation and the need to separate collaboration privileges from privileged workflow capabilities.

## Closing Principle

A trusted repository is not automatically a trusted execution environment.

An authenticated contributor is not automatically an authorized operator.

No workflow may gain privileged authority merely because its code entered the repository.

VIDIME. OVERUJEME. STAVIME.
