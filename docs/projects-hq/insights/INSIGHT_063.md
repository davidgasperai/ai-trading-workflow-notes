🐸 PROJECTS HQ INSIGHT #063

Date: 09. 09. 2026

Title

Automation Must Not Outrun Verification

Core Idea

Automation can dramatically increase the number of actions a system is capable of performing.

But every consequential action creates a verification burden.

If action throughput increases faster than verification throughput, the system accumulates unverified state.

Therefore:

Automation should scale only as fast as verification can scale with it.

Why It Matters

Imagine:

Human research workflow:

20 experiments / week

Validation capacity:

20 experiments / week

Everything can be reviewed.

Now introduce an AI Research Agent:

2,000 experiments / week

But validation capacity remains:

20 experiments / week.

At first this looks like:

100× productivity.

In reality:

2,000 generated

minus:

20 verified

equals:

1,980 unverified experiments.

The system has not created 2,000 trustworthy research outputs.

It has created:

20 verified results + 1,980 claims waiting for evidence.

That difference is fundamental.

Capability Creates Verification Debt

We can define a useful concept:

Verification Debt

as:

the accumulated set of consequential outputs whose correctness has not yet been established to the required standard.

Example:

Agent-generated strategies = 500

Validated strategies = 12

Then:

Verification Debt = 488

Not every backlog item is dangerous.

But if those unverified outputs begin influencing:

canonical state

risk rules

live decisions

or:

capital allocation

verification debt becomes operational risk.

The Dangerous Shortcut

When automation becomes much faster than review, there is pressure to say:

The agent is usually right, so let’s approve more automatically.

That converts a capacity problem into a governance failure.

The correct response is not necessarily:

lower verification standards.

It may instead be:

* better automated validation,
* stronger filtering,
* reduced experiment scope,
* prioritized review,
* independent checking,
* or simply accepting that not every generated result should be promoted.

From #062

Yesterday:

THROUGHPUT ≠ EVIDENCE.

Today we extend it:

THROUGHPUT also creates downstream verification demand.

A faster Research Agent therefore requires a stronger:

Validation Agent

Evidence Pipeline

Experiment Registry

and eventually:

Risk Gate.

Otherwise one component evolves while the rest of the system remains human-speed.

AI Operator Example

Consider a future agent able to:

read email

change calendar

execute payment

modify GitHub

run code

query broker

submit order

Its capability may be extraordinary.

But after each action the system must establish:

Did the correct action occur?

Did the external system accept it?

Was the resulting state expected?

Was the action permitted?

Did any hidden side effect occur?

If the agent can perform:

1,000 actions/minute

but the system can verify:

10 actions/minute

then autonomy is scaling faster than trust.

Action Completion ≠ Verified Outcome

This distinction is crucial.

Agent reports:

Payment sent successfully.

That is:

Agent Output.

Bank confirms:

Transaction ID 8472 settled for £100 to intended recipient.

That is:

External Evidence.

Internal ledger updates and matches bank state.

That is:

Reconciled State.

These three states are not interchangeable.

Similarly:

Agent:

Order submitted

Broker:

Order filled

Position reconciliation:

Position matches intended exposure

Only the final step tells us that the consequence is consistent with system state.

Proposed State Chain

For consequential actions:

PROPOSED

↓

AUTHORIZED

↓

EXECUTED

↓

OBSERVED

↓

VERIFIED

↓

RECONCILED

Only after:

VERIFIED / RECONCILED

should downstream systems treat the result as trustworthy canonical state.

Verification Can Be Automated Too

The solution is not to manually inspect everything.

That would destroy the economic value of automation.

Instead:

automate the controls around automation.

Example:

Research Agent

↓

10,000 experiments

↓

Automated statistical validation

↓

500 survive

↓

Independent replication

↓

40 survive

↓

Evidence Package

↓

5 human-review candidates

David sees five serious candidates instead of ten thousand raw outputs. 😂🐸

That is scalable autonomy.

Independent Verification

From #058:

Critical controls need independent evidence.

Verification therefore should not simply ask the same agent:

Did you do the task correctly?

Agent:

Yes. 😂

A stronger pattern is:

Agent A performs

↓

External system returns state

↓

Verifier independently checks

↓

Reconciliation confirms

The verifier does not need to be another LLM.

Often the best verification source is deterministic:

broker API

database

hash

test suite

ledger

price source

schema validation

recomputed metric.

Verification Budget

From #055:

Control Costs Are Part of the Cost of Autonomy.

Every automated action has:

Execution Cost

plus:

Verification Cost.

Therefore:

True Automation Cost

should be considered:

Execution

Monitoring

Validation

Reconciliation

Audit

Incident Recovery.

A cheap agent that generates huge amounts of low-confidence work can be more expensive than a slower, better-controlled agent.

Backpressure

Software systems use backpressure when a downstream component cannot process input fast enough.

The same concept can protect autonomous research.

If:

Verification Queue > threshold

then:

Research Throughput ↓

or:

New experiments paused.

This prevents automation from creating an endlessly growing pile of unverifiable work.

Future example:

verification_queue = 1,000
maximum_safe_queue = 500

STATE = VERIFICATION_BACKLOG

new_experiment_generation = PAUSED 

That is much safer than:

Keep generating because compute is available.

Risk-Based Verification

Not every action deserves the same verification cost.

Low consequence:

Generate research note

may need minimal checking.

Medium consequence:

Modify strategy code

needs tests and version history.

High consequence:

Change risk limit

needs independent review.

Very high consequence:

Send live broker order

needs policy validation + broker confirmation + reconciliation.

Therefore verification should scale with:

consequence × uncertainty × reversibility.

Reversibility Matters

An action that is easy to undo:

create draft

can tolerate weaker pre-action verification.

An action that is difficult or impossible to reverse:

execute market order

needs stronger assurance before consequence.

This gives us:

Low consequence + reversible

→ faster autonomy.

High consequence + irreversible

→ stronger gates.

That is a much better way to allocate control cost than treating every agent action equally.

Relationship to Existing Projects HQ

#055 — Control Costs Are Part of the Cost of Autonomy

taught us that autonomy has hidden operating costs.

#056 — Capability ≠ Authority

prevents better models receiving automatic permissions.

#058 — Critical Controls Need Independent Evidence

defines the source of trustworthy checks.

#060 — Failure Evidence Must Survive the Failure

preserves incident information.

#061 — Recovery Must Be Gated by Reconciliation

verifies post-failure state.

#062 — Research Throughput Must Not Dilute Evidence Standards

protects statistical validity as experiment generation accelerates.

And now:

#063 — Automation Must Not Outrun Verification

protects the entire downstream system from accumulating unverified consequences.

Proposed Architecture

Agent Action

↓

Policy Gate

↓

Execution

↓

External Result

↓

Verification

↓

Reconciliation

↓

Canonical State

Meanwhile:

Verification Queue Monitor

↓

if backlog excessive:

BACKPRESSURE

↓

reduce agent throughput.

This creates an important feedback loop:

automation speed becomes bounded by trustworthy processing capacity.

Projects HQ Principle

An action is not complete merely because the agent finished acting.

It is complete when:

the resulting state has been independently verified to the required standard.

Shortest form:

AUTOMATION ≠ VERIFIED AUTONOMY.

And my favourite version for Nekonečný Mír:

Never automate consequences faster than you can verify reality.

Future Applications

Research Agent · Validation Agent · Experiment Registry · verification queue · backpressure · broker reconciliation · deterministic checks · Risk Agent · Policy Gateway · action state machine · Evidence Package · live trading · GitHub CI/testing

Origin

Daily AI Trading Brief — 09. 09. 2026

Inspired by two developments: Meta’s rollout of a general-purpose agent capable of acting across consequential external applications, and OpenAI’s demonstration of GPT‑5.6 Sol/Codex directly operating parts of an experimental laboratory workflow. Both illustrate the rapid transition from AI that produces information to AI that produces external state changes. The generalized lesson for autonomous trading is that execution capability should scale together with independent verification capacity. 

Status

🟢 Active strategic principle

Tags

Projects HQ · Nekonečný Mír · AI Agents · Automation · Verification · Backpressure · Risk · Trading · Execution Safety

Revision

v1.0 — 09. 09. 2026
