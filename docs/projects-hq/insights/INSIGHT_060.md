🐸 PROJECTS HQ INSIGHT #060

Date: 06. 09. 2026

Title

Failure Evidence Must Survive the Failure

Core Idea

A system cannot reliably learn from a failure if the evidence describing that failure can be altered, lost or destroyed by the same process that caused it.

Therefore:

Failure evidence must survive independently of the component that failed.

Why It Matters

Imagine a Trading Agent:

Generates order

↓

Executes unexpectedly large position

↓

Creates loss

The system later asks:

Why did this happen?

But the agent’s local logs contain only:

Trade executed successfully.

The relevant tool trajectory was overwritten.

The input market-data snapshot expired.

The risk calculation was never persisted.

The exact strategy version cannot be reconstructed.

We now know what happened financially.

But we cannot know why it happened technically.

Without trustworthy failure evidence:

root-cause analysis becomes speculation.

A Failure Has Two Outputs

Every consequential action should conceptually produce:

Operational Output

Trade

and separately:

Audit Output

Evidence describing how the trade came to exist

These must not share identical failure paths.

For example:

Trading Agent

↓

Execution Gateway

↓

Broker

while simultaneously:

Trading Agent / Gateway / Risk

↓

Append-only Audit Store

The trading component can contribute records.

But it should not be able to silently rewrite historical records after the consequence occurred.

What Should Survive?

For consequential actions:

Timestamp

Agent/model version

Strategy/version hash

Input evidence IDs

Market-data snapshot references

Position state before action

Risk verdict

Policy verdict

Requested action

Executed action

Broker response

Position state after action

Errors / retries

Kill-switch state

Relevant configuration version

Not every internal token needs permanent storage.

But enough evidence must survive to reconstruct:

what the system knew, what it believed, what it was allowed to do and what actually happened.

The Crucial Distinction

A normal application log asks:

What did the software do?

An autonomous-system audit record asks:

Why was this action permitted to reach the point of consequence?

That requires joining evidence across several components.

Example:

Trading Agent: BUY

Risk Agent: ALLOW

Policy Gateway: ALLOW

Execution Gateway: SENT

Broker: FILLED

Position Reconciliation: MATCH

If the final position later proves wrong, we can trace the exact chain.

Logs Must Be Outside Agent Authority

From #057:

The controlled component must not own its control.

The same applies here.

Bad architecture:

Trading Agent → READ/WRITE/DELETE audit history

Better architecture:

Trading Agent → APPEND event

Audit Service → owns canonical record

Trading Agent → cannot alter historical event

The goal is not to distrust the agent emotionally.

It is to prevent a technical dependency:

the evidence should not disappear when the observed component fails.

Why This Matters for AI Agents

Traditional deterministic software often fails reproducibly.

Agentic systems can fail through:

* context interactions,
* tool sequencing,
* unexpected environmental state,
* model nondeterminism,
* stale evidence,
* emergent planning,
* retries,
* multi-agent interactions.

Reproducing the exact failure later may therefore be impossible.

That makes first-occurrence evidence extremely valuable.

If an unusual trajectory disappears, the only example of the failure may disappear with it.

Failure Taxonomy

Nekonečný Mír could eventually classify incidents:

DATA_FAILURE

MODEL_FAILURE

POLICY_FAILURE

RISK_FAILURE

EXECUTION_FAILURE

BROKER_FAILURE

RECONCILIATION_FAILURE

PERMISSION_FAILURE

UNKNOWN_FAILURE

Then severity:

INFO

WARNING

CRITICAL

And lifecycle:

DETECTED

↓

CONTAINED

↓

EVIDENCE_SEALED

↓

ROOT_CAUSE_PENDING

↓

ROOT_CAUSE_CONFIRMED

↓

REMEDIATED

↓

VALIDATED

↓

CLOSED

Notice:

EVIDENCE_SEALED comes before root-cause analysis.

Because analysis performed on disappearing evidence is not reliable analysis.

Connection to #059

Yesterday:

Observation

↓

Evidence

↓

Pending State

↓

Confirmed State

Today we extend the loop:

Confirmed State

↓

Action

↓

Outcome

↓

Audit Evidence

↓

Learning

↓

future:

Policy / Model / Strategy Improvement

This gives us a complete feedback cycle.

Without Audit Evidence:

Outcome → Learning

becomes guesswork.

Recovery Must Preserve Evidence

If a critical incident triggers:

KILL

the first instinct may be to restart everything immediately.

But the safer order can be:

CONTAIN

↓

PRESERVE EVIDENCE

↓

RECONCILE

↓

DIAGNOSE

↓

RECOVER

A restart may destroy volatile state that explains the failure.

Therefore:

Recovery must not erase the reason recovery was needed.

Minimal Incident Bundle

A future INCIDENT_BUNDLE could include:

incident_id
detected_at
severity
affected_components
model_versions
strategy_hash
evidence_ids
position_snapshot_before
position_snapshot_after
risk_verdict
policy_verdict
execution_response
logs_reference
data_freshness_state
kill_switch_state
containment_action 

The key property:

immutable after sealing, except for clearly versioned investigation notes.

Projects HQ Principle

If the evidence disappears with the failure, the system cannot reliably learn from the failure.

Shortest form:

Failure evidence must survive the failure.

Builds On

#053 — Uncertainty Can Be a Valid Reason to Stop
#054 — Map Dependencies Before Trusting Metrics
#057 — The Safety Layer Must Sit Outside the Authority It Controls
#058 — Critical Controls Need Independent Evidence
#059 — Evidence Should Change State Through Defined Transitions

Future Applications

Incident Registry · append-only audit trail · immutable event log · Evidence Package · Risk Agent · Policy Gateway · Execution Gateway · position reconciliation · post-mortems · model/version registry · kill switch · live-trading recovery protocol

Origin

Daily AI Trading Brief — 06. 09. 2026

Inspired by OpenAI’s disclosure of a previously unreported wiki incident involving unintended agent behavior, together with the company’s broader effort to improve transparency and monitoring around agent misalignment. The generalized lesson for autonomous trading is that incident evidence must remain available independently of the component whose behavior is under investigation. 

Status

🟢 Active strategic principle

Tags

Projects HQ · Nekonečný Mír · AI Agents · Audit · Incidents · Evidence · Risk · Execution Safety

Revision

v1.0 — 06. 09. 2026
