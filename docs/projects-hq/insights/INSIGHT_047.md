🐸 PROJECTS HQ INSIGHT #047

Date: 24. 08. 2026

Title

Authority Should Be Bounded, Not Merely Granted

Core Idea

Permission does not need to be binary.

An agent may legitimately require access to a resource while still requiring strict limits on how much of that resource it can consume or affect.

Therefore authority should often be expressed as a bounded budget rather than a simple:

ALLOW / DENY

Why It Matters

Traditional permission systems answer questions such as:

Can this agent access the internet?

Can this agent write to GitHub?

Can this agent submit an order?

These questions are necessary.

But they are incomplete.

A safer system also asks:

How many requests?

Which repository paths?

How much compute?

How much capital?

How large an order?

How much cumulative exposure?

For how long?

Under which market state?

An agent that legitimately needs a capability does not necessarily need unlimited access to that capability.

Impact on Nekonečný Mír

Future permissions should support at least three states:

DENIED

The agent cannot perform the action.

BOUNDED

The agent may perform the action within deterministic limits.

STEP-UP AUTHORIZATION

The agent must obtain additional independent approval before exceeding the normal boundary.

Examples:

Research Agent:

Internet = BOUNDED → 100 requests/run

Quant Agent:

Compute = BOUNDED → €5/experiment

Documentation Agent:

GitHub Write = BOUNDED → /docs only

Trading Agent:

Order Size = BOUNDED → max 0.25 BTC

Trading Agent:

Daily Loss = BOUNDED → hard account limit

Trading Agent:

Beyond limit = STEP-UP / DENY

Proposed Permission Model

Identity

↓

Capability requested

↓

Permission

↓

Scope

↓

Budget / limit

↓

Current-state risk

↓

Authorization

↓

Execution

↓

Usage accounting

↓

Audit receipt

Projects HQ Principle

Do not ask only whether an agent may act. Define how far its authority extends.

Builds On

#039 — Risk Controls Must Assume the Model Is Wrong
#042 — New Capability Requires New Validation
#044 — Permission Must Exist at the Point of Consequence
#045 — Optimize for Failure Magnitude, Not Only Failure Frequency
#046 — The Researcher May Adapt. The Test Must Not.

Future Applications

AGENT_PERMISSION_MATRIX.md · API request budgets · compute budgets · scoped GitHub write access · experiment budgets · maximum order size · maximum exposure · daily-loss caps · credential scopes · human step-up authorization · policy gateway · audit receipts

Origin

Daily AI Trading Brief — 24. 08. 2026

Inspired by practical agent spending-control patterns and the broader principle that autonomous capabilities should be constrained by independently enforced resource limits. 

Status

🟢 Active strategic principle

Tags

Projects HQ · Nekonečný Mír · AI Agents · Permissions · Risk Management · Least Privilege · Budgets · Governance

Revision

v1.0 — 24. 08. 2026
