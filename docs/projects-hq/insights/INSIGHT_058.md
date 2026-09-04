🐸 PROJECTS HQ INSIGHT #058

Date: 04. 09. 2026

Title

Critical Controls Need Independent Evidence

Core Idea

Separating the Trading Agent from the Risk Agent is necessary.

But organizational separation alone does not create true independence.

If both agents depend on the same incorrect input, they can agree for the same wrong reason.

Therefore:

A critical control should not only be independently authorized. Its critical evidence should also be independently verifiable.

Why It Matters

Imagine:

Trading Agent

reads:

BTC price = $81,000

from:

Market Feed A

It proposes an order.

The Risk Agent independently checks the order.

But its risk calculation also reads:

BTC price = $81,000

from:

Market Feed A.

Both agents agree.

The architecture appears to contain two independent components.

But in reality:

Feed A fails

↓

Trading Agent becomes wrong

and simultaneously:

Risk Agent becomes wrong.

We have two processes but only one failure domain.

Independence Has Layers

Future Nekonečný Mír should distinguish:

Authority Independence

Who can override whom?

Model Independence

Are different models/providers being used?

Data Independence

Do critical checks depend on different evidence?

Infrastructure Independence

Can one outage disable both primary and safety systems?

Credential Independence

Can one compromised credential defeat several boundaries?

True resilience therefore does not come from simply adding another agent.

It comes from reducing shared critical failure paths.

Trading Example

Primary market feed:

Feed A → BTC = $81,020

Independent control feed:

Feed B → BTC = $80,990

Difference:

0.04%

→ normal.

But:

Feed A → BTC = $81,020

Feed B → BTC = $76,900

Difference:

5.1%

Then:

UNKNOWN / DATA CONFLICT

↓

NO NEW ORDER

↓

reconcile data

↓

only then resume execution.

Neither feed needs to be declared immediately wrong.

The disagreement itself is evidence that current state is uncertain.

And from #053:

UNKNOWN ≠ SAFE.

Position State Is Even More Important

The same logic applies to capital.

Internal ledger:

Long 0.20 BTC

Broker:

Long 0.20 BTC

→ reconciled.

Internal ledger:

Long 0.20 BTC

Broker:

Long 1.20 BTC

→ execution must stop.

The Risk Agent should never trust the Trading Agent’s own internal belief about current exposure as its sole source of truth.

For consequential state:

verify against the system where the consequence actually exists.

What Should Be Independently Verified?

Not everything.

That would create unnecessary cost and complexity.

But high-consequence variables deserve stronger verification:

Current positions

Available balance

Open orders

Market price used for sizing

Daily realized/unrealized P&L

Risk limits

Strategy/version hash

Broker connectivity

Kill-switch state

Clock / data freshness

Relationship to #054 and #057

#054 — Map Dependencies Before Trusting Metrics

taught us to find shared dependencies.

#057 — The Safety Layer Must Sit Outside the Authority It Controls

separated control authority.

#058 now adds:

even an independent safety controller can fail if it sees the world only through the controlled system’s eyes.

Therefore:

independent authority + shared evidence ≠ fully independent control.

Proposed Architecture

Market Feed A

↓

Trading Agent

↓

PROPOSE

↓

Policy Gateway

Meanwhile:

Market Feed B

Broker State

Independent Risk Data

↓

Risk Agent

↓

ALLOW / DENY / UNKNOWN

↓

Execution Gateway

If:

Feed mismatch > tolerance

or:

Position mismatch

or:

Critical data stale

then:

UNKNOWN → PAUSE

Practical Principle

We do not need two of everything.

Redundancy should scale with consequence.

A research notebook can tolerate one public price API.

A live execution system controlling meaningful capital should not necessarily rely on one price source, one position representation and one model-generated interpretation for all critical decisions.

That connects beautifully to #055:

Control Costs Are Part of the Cost of Autonomy.

Independent evidence has a cost.

But so does a shared failure.

Projects HQ Principle

A safety system should not see the world only through the system it is protecting.

Shortest version:

Critical controls need independent evidence.

Builds On

#050 — Validate the Environment Behind the Result
#053 — Uncertainty Can Be a Valid Reason to Stop
#054 — Map Dependencies Before Trusting Metrics
#055 — Control Costs Are Part of the Cost of Autonomy
#057 — The Safety Layer Must Sit Outside the Authority It Controls

Future Applications

Risk Agent · Policy Gateway · multi-source market data · position reconciliation · broker-state verification · stale-data detection · data-conflict state · provider redundancy · kill-switch verification · Evidence Package · live trading

Origin

Daily AI Trading Brief — 04. 09. 2026

Inspired by the increasing importance of independent safeguards around highly capable AI systems, combined with today’s fast BTC repricing across macro, derivatives and spot-flow signals. The general lesson for autonomous trading is that separating the safety component is insufficient if critical decisions still inherit the same upstream failure source. 

Status

🟢 Active strategic principle

Tags

Projects HQ · Nekonečný Mír · AI Agents · Risk · Data · Redundancy · Validation · Execution Safety

Revision

v1.0 — 04. 09. 2026
