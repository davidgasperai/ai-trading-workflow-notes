🐸 PROJECTS HQ INSIGHT #059

Date: 05. 09. 2026

Title

Evidence Should Change State Through Defined Transitions

Core Idea

A new observation should not automatically rewrite the system’s entire understanding of the environment.

New evidence should enter through a defined state-transition process.

Therefore:

Observation ≠ confirmed state change.

Why It Matters

Consider the last 24 hours.

Evidence A:

Fed official signals possible hold

Market response:

Hike probability ↓

BTC → $82k

A naïve adaptive system might immediately conclude:

REGIME = RISK-ON

Then new evidence arrives.

Evidence B:

Payrolls = 162k

Expected = 56k

Market response:

Hike probability ↑

Yields ↑

BTC < $80k

The same system immediately concludes:

REGIME = RISK-OFF

Nothing about this process is truly adaptive.

It is merely reactive.

Fast State vs Confirmed State

Future Nekonečný Mír could distinguish two layers.

Fast State

Responds immediately to new evidence.

Example:

Macro shock detected

Confidence reduced

Position sizing restricted

New entries paused

But separately:

Confirmed State

changes only when predefined evidence requirements are met.

Example:

REGIME_CHANGE_PENDING

↓

additional observations

↓

confirmation criteria

↓

REGIME_CHANGE_CONFIRMED

This allows the system to react quickly without pretending it already understands the new environment.

Example

Before payrolls:

Confirmed Macro State = NEUTRAL

Waller comments arrive:

Fast State = DOVISH SHIFT DETECTED

But:

Confirmed Macro State = NEUTRAL

remains.

Then payrolls arrive:

Fast State = HAWKISH COUNTER-SIGNAL

Now the evidence conflicts.

Correct output:

Confirmed Macro State = NEUTRAL

Confidence = LOWER

Evidence = CONFLICTING

Not:

BULL → BEAR → BULL → BEAR

every few hours.

State Transitions Should Be Explicit

A future regime engine might use:

STABLE

↓

NEW_EVIDENCE

↓

PENDING_CHANGE

↓

one of:

CONFIRMED_CHANGE

REJECTED_CHANGE

INSUFFICIENT_EVIDENCE

CONFLICTING_EVIDENCE

This makes state history auditable.

We can later answer:

Why did the system change regime?

instead of:

Because the model felt differently at 14:32. 😂🐸

Evidence Has Time

Evidence should not only contain:

value

and:

source

but also:

observed_at

effective_at

fresh_until

superseded_by

confidence

Example:

Fed hike probability = 50%

may have been completely correct Thursday evening.

After payrolls:

it becomes historically correct but operationally stale.

That distinction matters enormously.

A fact does not become false merely because newer evidence exists.

But it may become:

unsafe to use for the current decision.

Impact on Nekonečný Mír

For future:

Evidence Package

could store:

Evidence ID

Source

Observed At

Value

Confidence

Freshness

Dependencies

Supersedes

Affected State

Then the State Engine determines whether the evidence:

updates confidence

creates pending state

confirms transition

or:

does nothing.

The LLM should therefore interpret evidence.

It should not have unrestricted authority to directly rewrite the canonical system state.

Why This Matters for AI Agents

LLMs are exceptionally good at constructing coherent interpretations of the newest information.

That strength can become a weakness.

The newest explanation often feels compelling precisely because the model can explain it so well.

Therefore:

narrative confidence must not equal transition authority.

The system should require predefined transition logic for consequential states.

Trading Example

Bad architecture:

News → LLM → REGIME = BULL

Better architecture:

News

↓

Evidence Extractor

↓

Evidence Package

↓

Fast State

↓

Confirmation Rules

↓

Canonical Regime State

↓

Risk / Trading Agents

The agent may say:

Strong evidence suggests a potential bullish transition.

But the canonical state remains:

PENDING

until the transition requirements are satisfied.

Relationship to Existing Projects HQ

#050 — Validate the Environment Behind the Result

tells us environment matters.

#052 — Confidence Can Change Without Changing the Strategy

allows us to react without rewriting code.

#053 — UNKNOWN ≠ SAFE

lets uncertainty reduce authority.

#054 — Map Dependencies Before Trusting Metrics

tells us where evidence comes from.

#058 — Critical Controls Need Independent Evidence

strengthens important observations.

And now #059 defines:

how evidence should be allowed to change system state.

Proposed Rule

Evidence may immediately change confidence.
Evidence should change canonical state only through an explicit transition.

This gives us an elegant hierarchy:

Observation

↓

Evidence

↓

Confidence

↓

Pending State

↓

Confirmed State

↓

Authority / Action

Each step has a different meaning.

And critically:

none should be silently skipped.

Projects HQ Principle

Do not let the newest evidence become the entire state.

Shortest version:

Observation ≠ State Transition.

Future Applications

Evidence Package · Regime Engine · State Machine · macro-event processing · Risk Agent · confidence state · data freshness · superseded_by tracking · event calendar · audit trail · live trading

Origin

Daily AI Trading Brief — 05. 09. 2026

Inspired by the rapid reversal in U.S. rate expectations around Fed Governor Christopher Waller’s comments and the following August payroll report. Both observations were legitimate when received, yet their implications changed rapidly as new evidence arrived. The lesson for autonomous trading is that fresh evidence should affect confidence immediately but should alter canonical system state only through explicit, auditable transitions. 

Status

🟢 Active strategic principle

Tags

Projects HQ · Nekonečný Mír · AI Agents · Evidence · State Machine · Regime · Risk · Trading

Revision

v1.0 — 05. 09. 2026
