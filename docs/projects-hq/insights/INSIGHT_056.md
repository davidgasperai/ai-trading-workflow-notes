🐸 PROJECTS HQ INSIGHT #056

Date: 02. 09. 2026

Title

Capability Must Not Automatically Expand Authority

Core Idea

A system becoming more capable does not imply that it should automatically receive more authority.

These are separate dimensions:

Capability = what the agent can do.

Authority = what the system permits the agent to do.

Increasing one should never silently increase the other.

Why It Matters

Consider two generations of a Trading Agent.

Agent v1

can identify simple signals.

Authorized maximum position:

0.10% portfolio

Then a new model arrives.

Agent v2

is dramatically better at reasoning, coding, market analysis and tool use.

A dangerous assumption would be:

The agent is smarter, therefore it should control more capital.

That conclusion does not follow.

The new model may also be better at:

finding unexpected tool paths, chaining actions, circumventing weak restrictions, creating convincing but incorrect explanations, or taking actions developers did not anticipate.

Therefore greater capability may initially justify:

equal or even lower authority

until new evidence supports expansion.

Capability × Authority Matrix

A future governance layer could explicitly separate both dimensions:

Capability	Authority	Interpretation
Low	Low	limited system
High	Low	powerful but contained
Low	High	dangerous mismatch
High	High	requires strongest evidence

The most dangerous state may not be:

high capability + low authority.

It may be:

insufficiently validated capability + high authority.

Impact on Nekonečný Mír

A new model version should trigger:

Capability Evaluation

↓

Safety / Research Evaluation

↓

Existing Authority remains unchanged

↓

Evidence Package

↓

Risk Review

↓

only then:

Authority Expansion Proposal

↓

Independent Approval

Authority should therefore be sticky downward.

A capability upgrade should not automatically move permissions upward.

Example

Current Trading Agent:

Market Data: READ

GitHub: READ

Paper Trading: WRITE

Live Trading: DENY

A new frontier model replaces it.

Even if benchmark performance improves dramatically:

Market Data: READ

GitHub: READ

Paper Trading: WRITE

Live Trading: DENY

remains unchanged.

Only a separate authorization process can change:

Live Trading: DENY

to:

Live Trading: LIMITED

And even then:

Max position size

Max daily loss

Allowed markets

Allowed order types

Allowed trading hours

should be independently bounded.

Why Model Upgrades Are Special

Traditional software upgrades usually aim to preserve behavior while fixing bugs.

Frontier-model upgrades can change:

reasoning, planning depth, tool-use strategy, persistence, interpretation of instructions and emergent behavior.

Therefore:

new model ≠ drop-in binary replacement

from a governance perspective.

It is a new capability profile.

Relationship to Our Existing Principles

#042 — New Capability Requires New Validation

tells us to test the new capability.

#047 — Authority Should Be Bounded, Not Merely Granted

tells us how authority should be structured.

#051 — Delegation Must Never Create Authority

prevents permissions expanding through other agents.

#053 — UNKNOWN ≠ SAFE

prevents uncertainty becoming implicit permission.

And now #056 adds:

capability growth itself must never become implicit permission.

Proposed Rule

For every model upgrade:

Capability ↑

does not imply:

Authority ↑

Instead:

Capability ↑

↓

Validation requirement ↑

↓

Authority unchanged

↓

Evidence

↓

possibly:

Authority ↑

Projects HQ Principle

Capability is not permission.

Or in full:

A more capable agent must earn additional authority independently of earning additional capability.

Future Applications

AGENT_PERMISSION_MATRIX.md · Authority Graph · Model Registry · capability tiers · Policy Gateway · model-upgrade procedure · Trading Agent · Risk Agent · maximum position limits · credential scopes · live-trading approval · regression evals

Origin

Daily AI Trading Brief — 02. 09. 2026

Inspired by OpenAI’s classification of Astra at the Critical cybersecurity capability threshold. Rather than treating increased capability as justification for unrestricted deployment, OpenAI is applying stronger safeguards and more restricted access. The Projects HQ principle generalizes this separation between capability and authority to autonomous trading systems. 

Status

🟢 Active strategic principle

Tags

Projects HQ · Nekonečný Mír · AI Agents · Authority · Capabilities · Permissions · Governance · Trading

Revision

v1.0 — 02. 09. 2026
