🐸 PROJECTS HQ INSIGHT #066

Date: 12. 09. 2026

Title

Consequence Should Determine the Strength of the Control

Core Idea

Yesterday we introduced an Authority Ladder:

NORMAL
↓
CAUTION
↓
RESTRICTED
↓
MANAGE ONLY
↓
KILL

But this raises a new question:

How strong should a control be?

Not every uncertain situation deserves a kill switch.

Not every action deserves human approval.

Not every error deserves the same response.

The missing variable is:

CONSEQUENCE

A system should therefore ask two separate questions:

How uncertain are we?

and:

What happens if we are wrong?

This gives us today’s principle:

The strength of a control should scale with the consequence of being wrong.

⸻

Why This Matters

Imagine two actions.

Action A

Generate a Markdown summary.

The agent is wrong.

Consequence:

Bad paragraph.

We can delete it.

Action B

BUY BTC with live capital.

The agent is wrong.

Consequence:

Real financial loss.

These actions may originate from the same model.

They may even have identical uncertainty.

But they should not receive identical controls.

⸻

Risk Is More Than Probability

A useful simplification:

RISK
≈
PROBABILITY OF ERROR
×
CONSEQUENCE OF ERROR

Suppose:

Probability of error = 1%

For a documentation action:

Maximum consequence = trivial

For an unrestricted live order:

Maximum consequence = large

Same probability.

Completely different risk.

Therefore:

Low uncertainty does not justify unlimited consequence.

⸻

This Extends #045

We previously said:

Optimize for failure magnitude, not only failure frequency.

Today we connect that directly to authority.

The control system should care about:

Probability

but also:

Exposure
Reversibility
Blast radius
Time to detection
Time to recovery

⸻

Consequence Classes

A future Nekonečný Mír architecture could classify actions.

CLASS 0 — INFORMATIONAL

Examples:

Read market data
Read GitHub
Search research
Generate summary

Potential controls:

Identity
Basic audit
Rate limit

⸻

CLASS 1 — REVERSIBLE CHANGE

Examples:

Create draft
Create research file
Create Git branch
Generate experiment

Potential controls:

Identity
Permission
Version history
Audit
Automated validation

⸻

CLASS 2 — SYSTEM CHANGE

Examples:

Modify strategy code
Change configuration
Update research dataset
Modify agent workflow

Potential controls:

Identity
Bounded permission
Tests
Diff review
Version control
Rollback
Independent validation

⸻

CLASS 3 — FINANCIAL CONSEQUENCE

Examples:

Submit paper/live order
Change position
Allocate capital

Potential controls:

Verified identity
Valid mandate
Policy Gateway
Risk limits
Independent market evidence
Execution receipt
Position reconciliation
Kill Switch

⸻

CLASS 4 — HIGH / IRREVERSIBLE CONSEQUENCE

Examples:

Increase live risk limits
Change broker credentials
Enable withdrawals
Disable safety layer
Override Kill Switch

Potential controls:

Agent authority = DENY
Human authorization
Strong identity verification
Multi-step approval
Immutable audit
Time delay where appropriate

Some actions may simply remain permanently outside agent authority.

⸻

Reversibility Changes the Control Requirement

Suppose an agent creates:

bad_report.md

We can revert it.

Suppose it sends:

market BUY

After execution, we cannot truly undo it.

We can place the opposite trade.

But that is a new market transaction, at a new price, with new fees and new risk.

Therefore:

Compensation is not the same as reversibility.

This distinction matters enormously for live trading.

⸻

Blast Radius

Consider two mistakes.

Mistake A

Wrong position size
Max order = 0.10%

Maximum damage is bounded.

Mistake B

Wrong position size
Broker credential allows unrestricted account exposure.

Same logical error.

Different architecture.

Different consequence.

Therefore a crucial safety principle remains:

Assume components can fail. Bound what their failure can reach.

⸻

Authority Should Follow Consequence

Yesterday’s Authority Ladder can now interact with today’s Consequence Classes.

For example:

NORMAL

Class 0 → ALLOW
Class 1 → ALLOW
Class 2 → BOUNDED
Class 3 → BOUNDED
Class 4 → HUMAN ONLY

CAUTION

Class 0 → ALLOW
Class 1 → ALLOW
Class 2 → RESTRICTED
Class 3 → REDUCED
Class 4 → HUMAN ONLY

RESTRICTED

Class 0 → ALLOW
Class 1 → BOUNDED
Class 2 → DENY NEW CHANGES
Class 3 → RISK REDUCTION ONLY
Class 4 → DENY

MANAGE ONLY

Observe
Reconcile
Reduce risk
Preserve evidence

KILL

No new consequential action

Now authority depends on both:

SYSTEM STATE
×
ACTION CONSEQUENCE

That is much more powerful than a single permission bit.

⸻

Permission Matrix Evolves

Our future Agent Permission Matrix may therefore eventually become more than:

Trading Agent
Broker = ALLOW

It could express:

Trading Agent
READ MARKET DATA
Consequence = 0
Authority = ALLOW
SUBMIT ORDER
Consequence = 3
Authority = BOUNDED
CHANGE RISK LIMIT
Consequence = 4
Authority = DENY
WITHDRAW FUNDS
Consequence = 4
Authority = DENY

This makes permissions semantic.

They reflect what the action can do to the real world.

⸻

Verification Should Also Scale With Consequence

From #063:

Automation must not outrun verification.

But verification cost should not be equal for every action.

For:

Generate Markdown

maybe:

schema check

is enough.

For:

Live trade

we may require:

Strategy state valid
↓
Market data fresh
↓
Position reconciled
↓
Risk limit valid
↓
Authority state valid
↓
Mandate valid
↓
Broker response verified
↓
Position reconciled again

Therefore:

Verification depth should scale with consequence.

⸻

Human Attention Is Scarce

If David must approve:

every research query
every Markdown file
every backtest

then automation becomes useless. 😂🐸

But if David approves nothing:

we have uncontrolled autonomy.

The solution is not:

HUMAN APPROVAL = ALWAYS

or:

HUMAN APPROVAL = NEVER.

Instead:

Human attention
→
highest-consequence decisions

This makes human approval a scarce safety resource.

Use it where its value is highest.

⸻

This Connects to #064 Identity

High-consequence actions require stronger identity assurance.

For example:

READ README.md

may tolerate a normal authenticated agent session.

But:

CHANGE LIVE RISK LIMIT

may require:

verified human identity
+
specific mandate
+
short expiry

Therefore identity assurance itself can be consequence-sensitive.

⸻

This Connects to #065 Throttle

Yesterday:

THROTTLE BEFORE KILL.

Today we can make throttling selective.

Suppose:

AUTHORITY = CAUTION

We do not need to slow:

Documentation Agent

because CPI was high. 😂🐸

But we may throttle:

Trading Agent → Class 3 actions

while allowing:

Research Agent → Class 0/1 actions

to continue normally.

This creates targeted degradation rather than shutting down the entire system.

⸻

Failure of One Domain Should Not Freeze Everything

Example:

Broker reconciliation unavailable

Correct response:

Live Trading → KILL

But perhaps:

Research → NORMAL
Documentation → NORMAL
Historical Backtests → NORMAL

This is another benefit of explicit consequence classes and dependency mapping.

The system can degrade locally.

⸻

A Useful Future Formula

Conceptually:

Required Control Strength
=
f(
  consequence,
  uncertainty,
  reversibility,
  blast_radius,
  dependency_health
)

We do not need to turn this into a numeric formula today.

Its purpose is architectural.

It tells the system:

Do not ask only whether an action is permitted.

Ask:

How much proof is appropriate before permitting this particular consequence under this particular state?

⸻

Today’s CPI Example

Before CPI:

Uncertainty = HIGH

For:

Research note

Consequence low.

Result:

ALLOW

For:

Open leveraged BTC position

Consequence high.

Result might be:

THROTTLE

or:

DENY

After CPI:

uncertainty about the number disappears.

But new evidence says:

Fed hike probability ↑

The control state is recomputed.

This illustrates something subtle:

An event resolving uncertainty does not automatically reduce risk.

Sometimes new knowledge tells us the environment is worse.

⸻

Projects HQ Principle

Controls should scale with the consequence of being wrong.

Shortest form:

CONSEQUENCE → CONTROL

And the Nekonečný Mír version:

The more reality an agent can change, the more evidence it should need before we let it act.

⸻

Builds On

#045 — Optimize for Failure Magnitude, Not Only Failure Frequency
#047 — Authority Should Be Bounded, Not Merely Granted
#053 — UNKNOWN ≠ SAFE
#056 — Capability ≠ Authority
#057 — Safety Must Sit Outside the Authority It Controls
#063 — Automation Must Not Outrun Verification
#064 — Authority Requires Verifiable Identity
#065 — A Safe System Needs a Throttle, Not Only a Kill Switch

⸻

Future Applications

Consequence Classes · Agent Permission Matrix · Authority State Machine · Risk Agent · Policy Gateway · human approval · broker permissions · GitHub permissions · short-lived credentials · verification depth · blast-radius controls · targeted degradation

⸻

Origin

Daily AI Trading Brief — 12. 09. 2026

Inspired by the contrast between two developments this week: increasingly consequential AI systems entering regulated financial workflows, and the market’s reaction to a known high-impact event—the August U.S. CPI release. The generalized lesson is that the appropriate safety response cannot be determined from uncertainty alone; it must also account for the consequence, reversibility and blast radius of the action being considered. 

Status

🟢 Active strategic principle

Tags

Projects HQ · Nekonečný Mír · AI Agents · Consequence · Authority · Risk · Verification · Permissions · Trading

Revision

v1.0 — 12. 09. 2026
