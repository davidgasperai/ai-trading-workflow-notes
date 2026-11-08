# PROJECTS HQ INSIGHT #122

## Date
2026-11-08

## Title
Parallel Agent Throughput Is Not Merge Correctness

---

## Core Principle

The ability to process many concurrent Git pushes
is an infrastructure performance property.

It is not proof that independently generated
changes are mutually compatible, authorized,
reviewed, or semantically correct.

PARALLEL_AGENT_THROUGHPUT
!=
MERGE_CORRECTNESS.

---

## Triggering Observation

On 2026-11-05, GitHub described a new Git
storage architecture and reported internal tests
with 5,000 concurrent agents and 7,200 pushes
per second to one repository.

GitHub distinguished immutable Git object writes
from reference updates that require ordering.

Primary source:
https://github.blog/engineering/architecture-optimization/inside-githubs-new-git-storage-architecture/

These are GitHub-reported infrastructure tests.
They do not demonstrate the semantic correctness
of the code produced by those agents.

---

## The Problem

Two agents read the same repository baseline.

AGENT_A changes a risk-limit definition.
AGENT_B changes the related permission matrix.

Each change appears locally valid.

If one is merged without reviewing the other,
the repository can enter a logically inconsistent
state even when every Git operation succeeds.

A successful push proves neither system-wide
consistency nor approval to change risk policy.

---

## Critical Distinctions

GIT_PUSH_ACCEPTED
!=
CHANGE_REVIEWED.

REFERENCE_UPDATE_ORDERED
!=
CROSS_FILE_INVARIANT_PRESERVED.

MERGE_CONFLICT_FREE
!=
SEMANTICALLY_COMPATIBLE.

AGENT_OUTPUT_VALID
!=
AUTHORIZED_POLICY_CHANGE.

HIGH_THROUGHPUT
!=
PRODUCTION_READINESS.

---

## Proposed Evidence Contract

CHANGE_ID
AGENT_ID
TASK_ID
SOURCE_BRANCH
BASE_COMMIT_SHA
EXPECTED_TARGET_HEAD_SHA
ACTUAL_TARGET_HEAD_SHA
FILES_TOUCHED
DECLARED_INVARIANTS
DEPENDENT_CHANGE_IDS
AUTHORIZATION_SCOPE
REVIEW_STATUS
VALIDATION_RESULTS
MERGE_DECISION
MERGED_COMMIT_SHA
AUDIT_REFERENCE

Unknown fields remain UNKNOWN.

---

## Proposed Control

CONTROL_ID:
NM-AGENT-MERGE-001

REQUIREMENT:

Agent-generated changes must not be promoted
into canonical governance or executable code
without a current-baseline check, dependency
review, explicit authorization, and independent
validation of relevant cross-file invariants.

CONTROL_STATUS:
PROPOSED

IMPLEMENTATION:
NOT_IMPLEMENTED

---

## Proposed Safe Process

1. Give each agent an isolated branch or workspace.
2. Record the exact base commit and task scope.
3. Keep proposed changes reviewable and small.
4. Recheck the target branch before integration.
5. Detect stale baselines and overlapping edits.
6. Validate cross-file and policy invariants.
7. Require human approval for governance changes.
8. Merge only after all required checks pass.
9. Preserve the original proposal and audit trail.
10. Do not infer permission from a successful push.

These are design proposals, not enabled workflows.

---

## Proposed Negative Test

TEST_ID:
NM-AGENT-MERGE-001-NEG-01

SCENARIO:

BASE_COMMIT:
C0

AGENT_A:
Proposes reducing a hypothetical risk cap
in a simulated policy file.

AGENT_B:
Independently proposes a permission rule
based on the old risk cap, also from C0.

Both proposals are syntactically valid.
AGENT_A is reviewed and integrated first.
AGENT_B is then evaluated against the new HEAD.

EXPECTED RESULT:

STALE_BASE_DETECTED:
TRUE

CROSS_FILE_INVARIANT_CHECK:
REQUIRED

AUTOMATIC_POLICY_MERGE:
BLOCKED

HUMAN_APPROVAL:
REQUIRED

CANONICAL_POLICY_CHANGED_BY_AGENT_B:
FALSE

AUDIT:
PRESERVED

LIVE_CAPITAL:
NOT_EXPOSED

TEST_STATUS:
NOT_EXECUTED

---

## Relationship to Previous Insights

#117: An event trigger is not a trust grant.
#118: Model-generated data is not trusted input.
#119: A published aggregate is not a verified sum.
#120: A safety benchmark is not authorization.
#121: A positive return is not equity recovery.
#122: Parallel writes are not merge correctness.

---

## Projects HQ Principle

> Agents may work in parallel.
> Governance decisions must remain coherent.
> Infrastructure throughput is not evidence
> of semantic correctness or permission.

---

## Governance Boundary

Strategic documentation only.

NOT AUTHORIZED:

NEW_STRATEGY_RESEARCH
NEW_FAMILY_DEVELOPMENT
NEW_BACKTESTS
PINE_DEVELOPMENT
TRADINGVIEW_EXPERIMENTS
GITHUB_WORKFLOW_ACTIVATION
UNREVIEWED_AUTOMATION
PRODUCTION_DEPLOYMENT
BROKER_API_WRITE
LIVE_TRADING

Existing operational handoff and measurement
restrictions remain unchanged.

---

## Status

STRATEGIC_PRINCIPLE:
DOCUMENTED

CONTROL_STATUS:
PROPOSED

IMPLEMENTATION:
NOT_IMPLEMENTED

NEGATIVE_TESTS:
NOT_EXECUTED

INDEPENDENT_EVALUATION:
NOT_IMPLEMENTED

LIVE_TRADING:
NOT_AUTHORIZED

---

## Revision

v1.0 — 2026-11-08
