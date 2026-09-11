🐸 PROJECTS HQ INSIGHT #065

Date: 11. 09. 2026

Title

A Safe System Needs a Throttle, Not Only a Kill Switch

Core Idea

Our architecture already distinguishes normal operation from emergency containment.

But real-world risk rarely moves instantly from:

SAFE

to:

CATASTROPHE.

More often it deteriorates gradually.

Confidence weakens.

Evidence conflicts.

Volatility rises.

Data becomes stale.

An important event approaches.

Dependencies begin failing.

Therefore an autonomous system needs the ability to reduce authority before conditions become bad enough to justify a full stop.

Safety should be able to slow the system before it has to kill the system.

⸻

Binary Control Is Too Coarse

Imagine only two states:

TRADING = ON

or:

TRADING = OFF

The system encounters:

* CPI in 20 minutes,
* oil +12% in one week,
* Treasury yields near 5%,
* conflicting regime evidence.

Is everything definitely unsafe?

No.

Is normal unrestricted operation equally justified?

Also no.

Binary control forces a bad choice:

FULL SPEED

or:

EMERGENCY STOP.

We need intermediate states.

⸻

Proposed Authority Ladder

For example:

LEVEL 4 — NORMAL

Full validated bounded authority.

↓

LEVEL 3 — CAUTION

Reduced size.

No authority expansion.

Stricter validation.

↓

LEVEL 2 — RESTRICTED

No new high-risk positions.

Only defined strategies.

Lower exposure.

↓

LEVEL 1 — READ / MANAGE ONLY

May monitor.

May reduce existing risk.

Cannot create new risk.

↓

LEVEL 0 — KILL

No consequential execution.

This creates:

Authority degradation before emergency containment.

⸻

Why This Is Better Than Waiting

Suppose uncertainty rises gradually:

confidence
0.92
↓
0.78
↓
0.61
↓
0.43
↓
UNKNOWN

Bad architecture:

0.92 → FULL AUTHORITY
0.78 → FULL AUTHORITY
0.61 → FULL AUTHORITY
0.43 → FULL AUTHORITY
UNKNOWN → KILL

The system behaves identically across dramatically different evidence states until the final second.

Better:

0.92 → NORMAL
0.78 → CAUTION
0.61 → RESTRICTED
0.43 → MANAGE ONLY
UNKNOWN → KILL

Now authority reflects evidence continuously.

⸻

This Extends #052

We already said:

Confidence must adapt before the strategy does.

Today:

confidence should not exist only as a number inside a dashboard.

It should be able to influence authority.

Therefore:

Evidence
↓
Confidence
↓
Authority Level
↓
Available Actions

This creates a practical bridge between epistemology and execution.

⸻

Confidence Must Not Directly Control Everything

We should still avoid:

LLM confidence = 0.61
→ position size = 61%

😂🐸

Model self-confidence is not trustworthy enough.

Instead authority transitions should depend on explicit evidence:

Data freshness
Regime state
Volatility
Spread / liquidity
Upcoming events
Position reconciliation
Risk metrics
Dependency health
Independent validation

The system then assigns an Authority State.

Not the agent itself.

⸻

Example: CPI Day

Normal:

AUTHORITY = NORMAL

CPI approaching:

KNOWN_HIGH_IMPACT_EVENT = TRUE

System transitions:

NORMAL
↓
CAUTION

Potential effects:

max_position_size ↓
new_strategy_activation = DENY
new_live_agent_session = DENY
existing risk may be reduced

Five minutes before CPI:

RESTRICTED

After CPI:

do not immediately return to:

NORMAL.

Instead:

OBSERVE
↓
VERIFY DATA
↓
RECONCILE STATE
↓
CONFIRM ENVIRONMENT
↓
RESTORE AUTHORITY

That links directly to #061.

⸻

Throttle Is Different From Kill

Throttle

Purpose:

Reduce consequence while uncertainty increases.

Properties:

* reversible,
* graduated,
* often automatic,
* preserves observation,
* may permit risk reduction.

Kill Switch

Purpose:

Stop consequential action when safety cannot be established.

Properties:

* decisive,
* independent,
* fail-closed,
* stronger recovery requirement.

Therefore:

Throttle protects before failure. Kill contains after safety is lost.

⸻

Recovery Should Also Be Gradual

This gives #061 another extension.

We already had:

KILL
↓
RECONCILE
↓
VERIFY
↓
RECOVERY ELIGIBLE

Now instead of:

RECOVERY ELIGIBLE
→
FULL AUTHORITY

we can use:

RECOVERY ELIGIBLE
↓
READ ONLY
↓
RESTRICTED
↓
CAUTION
↓
NORMAL

Authority returns gradually as evidence accumulates.

The same ladder works in both directions.

That is elegant.

⸻

Hysteresis

There is another useful concept here:

hysteresis.

Suppose volatility threshold is:

VOL > 5
→ CAUTION

If volatility moves:

4.99
5.01
4.98
5.02

we do not want:

NORMAL
CAUTION
NORMAL
CAUTION
NORMAL

every few seconds.

😂🐸

Therefore entering and leaving a safety state may use different thresholds.

Example:

Enter CAUTION:
VOL > 5.0

but return to NORMAL only after:

VOL < 4.0
for 30 minutes

This prevents unstable authority oscillation.

⸻

Throttle Triggers

Potential future triggers:

Market

volatility spike

spread widening

liquidity deterioration

abnormal slippage

Evidence

confidence ↓

conflicting evidence

validation envelope boundary

Infrastructure

feed degradation

API instability

verification backlog

Risk

drawdown ↑

position mismatch

unexpected correlation

Events

CPI

FOMC

major exchange maintenance

known market event

Agent System

model version changed

permission uncertainty

verification debt ↑

identity anomaly

Each trigger need not kill the system.

Many should simply:

reduce authority.

⸻

Connection to #063

#063 said:

Automation must not outrun verification.

Suppose:

Verification Queue ↑

Instead of waiting until it completely collapses:

NORMAL
↓
CAUTION
↓
Research throughput reduced

If backlog keeps rising:

RESTRICTED
↓
New experiment generation paused

This is backpressure implemented as authority throttling.

Our Insights are beginning to join together.

⸻

Connection to #056

Capability ≠ Authority.

Now:

authority itself does not need to be binary.

A model can remain equally capable while its permitted operational envelope contracts.

Example:

Model capability = unchanged

but:

Authority:
NORMAL
↓
CAUTION
↓
RESTRICTED

because the environment changed.

That is crucial.

⸻

Who Controls the Throttle?

From #057:

The safety layer must sit outside the authority it controls.

Therefore Trading Agent must not be able to say:

Conditions look better now. I have restored myself to NORMAL.

😂🐸

Authority state should belong to:

Risk / Policy / Control Layer

based on independently observable evidence.

The controlled agent may provide information.

It should not own the canonical authority state.

⸻

Auditability

Every transition should record:

previous_authority_state
new_authority_state
timestamp
trigger
evidence_ids
policy_version
risk_state
approver_if_required

Then later we can answer:

Why was Trading Agent restricted at 13:28?

Not:

Something probably looked scary.

😂

⸻

The Deep Principle

A robust autonomous system should not maximize:

how much autonomy can we permit?

It should maximize:

how much autonomy can current evidence safely justify?

These are different optimization goals.

The first encourages permanent expansion.

The second permits:

expand

and:

contract.

Real trust requires both.

⸻

Today’s OpenAI Connection

Today’s report that OpenAI is willing to consider slowing development if safety requires it illustrates the same generalized principle at a much larger scale: capability development does not have to proceed at maximum attainable speed when confidence in safe operation becomes the limiting resource. 

For Nekonečný Mír:

we do not need to choose between:

AUTONOMOUS

and:

OFF.

We can design:

autonomy that contracts as uncertainty rises.

⸻

Projects HQ Principle

Authority should degrade before safety fails.

Shortest version:

THROTTLE BEFORE KILL.

And my favourite Nekonečný Mír version:

A safe system knows how to slow itself before someone has to stop it.

⸻

Builds On

#052 — Confidence Must Adapt Before the Strategy Does
#053 — UNKNOWN ≠ SAFE
#056 — Capability ≠ Authority
#057 — Safety Must Sit Outside the Authority It Controls
#059 — Evidence Changes State Through Defined Transitions
#061 — Recovery Must Be Gated by Reconciliation
#063 — Automation Must Not Outrun Verification
#064 — Authority Requires Verifiable Identity

⸻

Future Applications

Authority State Machine · Risk Agent · Policy Gateway · event-risk handling · reduced-size mode · read-only mode · verification backpressure · staged recovery · volatility controls · live execution · human approval · Kill Switch

⸻

Origin

Daily AI Trading Brief — 11. 09. 2026

Inspired by today’s report that OpenAI is willing to slow AI development if safety considerations require it, together with the current macro environment in which rapidly rising energy prices and Treasury yields are materially changing the risk backdrop ahead of a major U.S. inflation release. The generalized lesson is that consequential autonomous systems should be able to reduce operational authority as uncertainty rises rather than operating at full speed until emergency shutdown becomes necessary. 

Status

🟢 Active strategic principle

Tags

Projects HQ · Nekonečný Mír · AI Agents · Authority · Throttle · Risk · Kill Switch · Backpressure · Trading

Revision

v1.0 — 11. 09. 2026
