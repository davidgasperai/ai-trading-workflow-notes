🐸 PROJECTS HQ INSIGHT #057

Date: 03. 09. 2026

Title

The Safety Layer Must Sit Outside the Authority It Controls

Core Idea

A safety mechanism cannot reliably control a system if the controlled system has sufficient authority to modify, disable or bypass that mechanism.

Therefore:

the component being constrained must not own its own constraint.

Why It Matters

Imagine a Trading Agent with:

Broker API access

Risk configuration write access

Kill-switch configuration access

The system may appear protected because a maximum-loss rule exists.

But the same agent that wants to execute an action can also change the rule preventing that action.

That is not independent control.

It is self-regulation.

A genuine safety boundary requires separation of authority.

Impact on Nekonečný Mír

Future execution architecture could follow:

Trading Agent

PROPOSE order

↓

Policy Gateway

VERIFY permissions

↓

Risk Agent

ALLOW / DENY

↓

Execution Service

SUBMIT order

But crucially:

Trading Agent → cannot modify Risk policy

Trading Agent → cannot disable Policy Gateway

Trading Agent → cannot access unrestricted broker credentials

Risk Agent → cannot create trading signals

Execution Service → cannot expand its own permissions

Kill Switch → cannot be overridden downstream

Kill Switch Architecture

A proper kill switch should ideally exist outside the Trading Agent’s control path.

Conceptually:

Trading Agent

↓

Execution Gateway

↓

Broker

while separately:

Independent Safety Controller

↓

KILL / ALLOW

↓

Execution Gateway

If:

KILL = TRUE

then:

Trading Agent output = irrelevant

No amount of reasoning, confidence or downstream delegation should restore execution.

Only the separately authorized recovery process can do so.

Why Software Rules Alone May Fail

Suppose the Trading Agent receives:

Do not trade when daily loss > 2%.

That is an instruction.

Now compare:

Broker credential physically unavailable when daily loss > 2%.

That is a boundary.

Instructions influence behaviour.

Boundaries constrain capability.

For high-consequence actions, Nekonečný Mír should prefer:

enforced boundaries over behavioral requests.

Failure Example

Trading Agent:

Order requested: BUY 5 BTC

Risk Agent:

DENY — exposure limit

Bad architecture:

Trading Agent calls broker API directly anyway.

Good architecture:

Trading Agent has no credential capable of submitting the order.

The denied request therefore cannot become a trade.

Recovery Is Also Authority

After a kill event, restoring execution is itself a consequential action.

Therefore:

KILL → automatic

may be appropriate.

But:

RESTORE → separately authorized

may require:

* resolved incident,
* verified system state,
* fresh risk state,
* reconciliation,
* audit record,
* human approval for live capital.

This prevents a failing system from automatically declaring itself healthy.

Relationship to Existing Projects HQ

#044 — Permission Must Exist at the Point of Consequence

Permissions are enforced where the action occurs.

#047 — Authority Should Be Bounded, Not Merely Granted

Authority receives explicit limits.

#051 — Delegation Must Never Create Authority

No downstream chain can manufacture new permissions.

#053 — UNKNOWN ≠ SAFE

Unverified critical state pauses execution.

#056 — Capability ≠ Authority

A smarter model does not automatically receive greater permissions.

And now:

#057 — the controlled component must not own the mechanism that controls it.

Together they begin to define something larger:

the Execution Safety Architecture.

Proposed Principle

A control is only independent if the controlled system cannot override it.

And our shortest version:

Never let the agent own its kill switch.

Future Applications

Research Constitution v1.0 · AGENT_PERMISSION_MATRIX.md · Policy Gateway · Risk Agent · broker credential isolation · independent kill switch · execution service · recovery protocol · audit trail · live-trading approval · least privilege

Origin

Daily AI Trading Brief — 03. 09. 2026

Inspired by OpenAI’s disclosure that it is developing automated shutdown capabilities following the Hugging Face agent incident. The Projects HQ principle generalizes the requirement to autonomous trading: shutdown and safety controls should be architecturally independent from the agent whose actions they constrain. 

Status

🟢 Active strategic principle

Tags

Projects HQ · Nekonečný Mír · AI Agents · Trading · Kill Switch · Risk · Authority · Execution Safety

Revision

v1.0 — 03. 09. 2026
