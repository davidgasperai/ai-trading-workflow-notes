🐸 PROJECTS HQ INSIGHT #061

Date: 07. 09. 2026

Title

Recovery Must Be Gated by Reconciliation

Core Idea

Stopping a failing autonomous system prevents additional consequences.

It does not prove that the system is safe to restart.

Therefore:

Containment may be immediate. Recovery must be evidence-gated.

Why It Matters

Imagine:

Trading Agent detects anomaly

↓

KILL SWITCH

↓

New orders blocked

Excellent.

But what is the current position?

Internal state says:

Long 0.20 BTC

Broker says:

Long 1.20 BTC

One pending order may still exist.

A partially filled order may not have been recorded.

The last market-data snapshot may be stale.

The Risk Agent may be calculating P&L from an incorrect position.

If we simply execute:

RESTART

because the original error disappeared, we restore authority into an unknown state.

From #053:

UNKNOWN ≠ SAFE.

Containment and Recovery Solve Different Problems

Containment asks:

How do we prevent more damage right now?

Recovery asks:

What evidence proves the system can safely regain authority?

These operations therefore require different logic.

Containment may be:

fast

automatic

conservative

Recovery should be:

deliberate

evidence-based

reconciled

auditable

For live capital, potentially:

human-approved.

Proposed Recovery State Machine

NORMAL

↓

ANOMALY DETECTED

↓

CONTAINED

↓

EVIDENCE SEALED

↓

RECONCILIATION

↓

one of:

STATE VERIFIED

STATE CONFLICT

STATE UNKNOWN

Only:

STATE VERIFIED

may proceed to:

RECOVERY ELIGIBLE

↓

AUTHORIZATION

↓

LIMITED RESUME

↓

MONITORED NORMAL

Neither:

STATE CONFLICT

nor:

STATE UNKNOWN

should restore execution authority.

What Must Be Reconciled?

Before live execution resumes:

Capital

Broker balance

vs.

Internal balance

Positions

Broker positions

vs.

Internal positions

Orders

Open broker orders

vs.

Expected orders

Execution

Fills

vs.

Internal trade ledger

Risk

Current exposure

Daily P&L

Available margin

Configuration

Strategy hash

Risk-policy hash

Model version

Permission state

Infrastructure

Market-data freshness

Broker connectivity

Kill-switch state

Clock synchronization

If a critical comparison fails:

RECOVERY = DENY

Why “The Error Is Gone” Is Not Enough

Suppose market feed A fails.

The system stops.

Five minutes later feed A begins producing prices again.

Bad recovery logic:

Feed available → restart

Better recovery logic:

Feed available

↓

compare against independent feed

↓

verify timestamps

↓

verify no missing interval corrupted position/risk state

↓

reconcile broker

↓

then:

RECOVERY ELIGIBLE

Availability returning is an observation.

Verified state is evidence.

Limited Resume

Even successful reconciliation does not require an immediate jump from:

OFF

to:

FULL AUTHORITY.

Recovery can be staged:

KILLED

↓

READ ONLY

↓

PAPER / SHADOW MODE

↓

LIMITED LIVE

↓

NORMAL LIVE

For example:

Normal maximum position:

1.00% capital

After recovery:

0.10% capital

until:

N successful reconciliations

and:

no new anomalies

Then authority can return gradually.

This is another application of #056:

Capability ≠ Authority.

And specifically:

Recovered capability ≠ automatically recovered authority.

Recovery Authority Must Be Separate

From #057:

Never let the agent own its kill switch.

Today we add:

Never let the failed component declare itself recovered.

The Trading Agent may report:

I am operating normally.

Useful information.

But not sufficient authorization.

Recovery status should come from:

Independent Reconciliation

Policy

when required:

Human approval.

Relationship to #060

Yesterday:

Failure evidence must survive the failure.

Why?

Because today we need that evidence for reconciliation.

The sequence now becomes:

ANOMALY

↓

CONTAIN

↓

PRESERVE EVIDENCE

↓

RECONCILE

↓

VERIFY

↓

AUTHORIZE

↓

LIMITED RECOVERY

↓

NORMAL

That is substantially safer than:

ERROR → RESTART. 😂🐸

Recovery Failure Is Information

Suppose reconciliation fails.

That is not merely an inconvenience.

It is new evidence:

EXPECTED STATE ≠ OBSERVED STATE

The correct response is not to force the states together until the warning disappears.

It is:

STATE CONFLICT

↓

investigate

↓

preserve both observations

↓

determine canonical truth.

This is exactly where #058 applies:

Critical controls need independent evidence.

Incident Connection

The Liquid Network incident illustrates the general distinction. After roughly $320 million was withdrawn, stopping new transactions limits further exposure, but the system still needs to establish the actual state of assets, permissions and affected users before normal operation can safely resume. 

The architecture lesson is broader than Liquid or crypto:

stopping protects the future; reconciliation reconstructs the present.

Projects HQ Principle

A stopped system is not necessarily a safe system.

And our operational rule:

Recovery must be gated by reconciliation.

Builds On

#053 — Uncertainty Can Be a Valid Reason to Stop
#056 — Capability Must Not Automatically Expand Authority
#057 — The Safety Layer Must Sit Outside the Authority It Controls
#058 — Critical Controls Need Independent Evidence
#060 — Failure Evidence Must Survive the Failure

Future Applications

Recovery Protocol · Incident Registry · position reconciliation · broker-state verification · staged authority restoration · shadow mode · kill switch · Evidence Package · Policy Gateway · Risk Agent · human live-trading approval

Origin

Daily AI Trading Brief — 07. 09. 2026

Inspired by today’s disclosure that the Bitcoin-based Liquid Network halted new transactions after roughly $320 million was withdrawn from its federation wallet. The general lesson for autonomous systems is that containment prevents further consequences but does not itself establish a trustworthy current state. Recovery should therefore follow independent reconciliation and explicit authorization. 

Status

🟢 Active strategic principle

Tags

Projects HQ · Nekonečný Mír · AI Agents · Recovery · Reconciliation · Risk · Kill Switch · Execution Safety

Revision

v1.0 — 07. 09. 2026
