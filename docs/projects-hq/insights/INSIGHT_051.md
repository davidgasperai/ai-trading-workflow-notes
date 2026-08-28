🐸 PROJECTS HQ INSIGHT #051

Date: 28. 08. 2026

Title

Delegation Must Never Create Authority

Core Idea

An agent should not be able to obtain greater authority simply by delegating work to another agent.

Delegation may transfer or reduce existing authority.

It must never silently create new authority.

Why It Matters

Multi-agent systems introduce a problem that does not exist in isolated agents.

Suppose:

Research Agent

has internet access but no execution authority.

And:

Trading Agent

has bounded execution authority but no unrestricted internet access.

If these agents can freely delegate tasks and share capabilities, their combined workflow may effectively acquire:

internet + strategy modification + execution

even though no single agent was explicitly granted that complete authority.

Local permissions may therefore appear safe while the composed system is unsafe.

This is a form of authority amplification.

Impact on Nekonečný Mír

Every future delegation should preserve an explicit authority boundary.

A sub-agent should receive:

only the permissions required for the delegated task

and:

never more authority than the delegating workflow is permitted to exercise.

Consequential permissions should not propagate automatically.

Examples:

Research Agent
→ may delegate web research
→ may not delegate live trading.

Quant Agent
→ may delegate code analysis
→ may not grant a sub-agent access to production credentials.

Trading Agent
→ may delegate signal calculation
→ may not delegate the ability to increase its own position limit.

Risk Agent
→ may request independent analysis
→ may not transfer its authorization authority to the Trading Agent.

Proposed Delegation Rule

Parent Authority

↓

Requested Subtask

↓

Minimum Required Permission Subset

↓

Policy Check

↓

Temporary Scoped Delegation

↓

Execution

↓

Permission Expiry

↓

Audit Receipt

Formally:

Authority(sub-agent) ⊆ Authority(parent workflow)

unless a separate independent authority explicitly approves otherwise.

Authority Graph

A future governance system may need to record not only:

Agent → Permission

but also:

Agent → may delegate → Permission → to whom → under what scope → for how long

This creates an Authority Graph.

It could reveal dangerous paths that are invisible in a simple Permission Matrix.

Example:

Research Agent

Internet ✅

↓

delegates information

↓

Quant Agent

Code Write ✅

↓

delegates artifact

↓

Trading Agent

Execution ⚠️

The individual permissions may all be legitimate.

The complete trajectory still requires an independent authorization gate before consequence.

Projects HQ Principle

Delegation may distribute authority. It must never manufacture it.

Builds On

#044 — Permission Must Exist at the Point of Consequence
#045 — Optimize for Failure Magnitude, Not Only Failure Frequency
#047 — Authority Should Be Bounded, Not Merely Granted
#049 — Stable Contracts Enable Replaceable Intelligence

Future Applications

AGENT_PERMISSION_MATRIX.md · Authority Graph · sub-agent permissions · temporary credentials · scoped delegation tokens · permission expiry · cross-agent capability analysis · Policy Gateway · audit receipts · multi-agent regression evals

Origin

Daily AI Trading Brief — 28. 08. 2026

Inspired by OpenAI’s August 26 incident report and independent investigation of coordinated multi-agent behavior, which demonstrate that safety properties must be evaluated not only at the level of individual agents but also across the composed system. 

Status

🟢 Active strategic principle

Tags

Projects HQ · Nekonečný Mír · AI Agents · Multi-Agent Systems · Permissions · Delegation · Governance · Security

Revision

v1.0 — 28. 08. 2026
