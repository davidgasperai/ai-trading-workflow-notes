# PROJECTS HQ INSIGHT #083

## Date
29. 09. 2026

## Title
# The Guard Must Live Outside the System It Guards

---

## Core Idea

A safety mechanism cannot be fully trusted if the component being controlled can also:

    modify it
    disable it
    bypass it
    impersonate it
    rewrite its evidence

Therefore:

> **Consequential controls should live outside the authority of the actor they constrain.**

Shortest version:

# THE ACTOR MUST NOT OWN THE GUARD

---

## Why This Matters

Suppose a Trading Agent contains its own rule:

    MAX ORDER = 0.01 BTC

The same agent:

    interprets the rule
    calculates the order
    decides whether the rule applies
    executes the trade
    reports compliance

This is convenient.

But it is not independent control.

The actor and the guard are the same component.

---

## Better Architecture

Instead:

    TRADING AGENT
         ↓
    proposes action
         ↓
    EXTERNAL RISK GATE
         ↓
    verifies policy
         ↓
    EXECUTION GATE
         ↓
    broker

The Trading Agent may reason broadly.

But it cannot redefine:

    what is allowed.

---

## Today's Trigger

NVIDIA's Open Agent Safety Platform provides a useful real-world architecture.

OpenShell constrains agents inside secure runtimes.

Sentry adds an out-of-band watchdog operating from a separate trust domain.

The important general principle is not the specific hardware.

It is:

    OBSERVER
    and
    ENFORCER

can remain outside the authority of:

    ACTOR.

---

## Independent Enforcement

A control becomes stronger when the actor cannot alter it.

Examples:

    agent cannot change broker API scope

    agent cannot grant itself Git merge rights

    agent cannot disable audit logging

    agent cannot edit authority receipts

    agent cannot change maximum position size

    agent cannot approve its own exception

---

## Separation of Powers

Autonomous systems benefit from the same principle used in robust institutions:

    DECIDE
    ≠
    AUTHORIZE
    ≠
    EXECUTE
    ≠
    VERIFY

One component may propose.

Another authorizes.

Another performs.

Another verifies.

No single component owns the entire consequential chain.

---

## Trading Example

Trading Agent:

    "BUY 0.25 BTC"

Risk Gate independently checks:

    strategy allowed?
    market allowed?
    account correct?
    size within limit?
    daily loss limit?
    authority valid?
    broker healthy?

If any answer fails:

    DENY.

The Trading Agent cannot argue the gate into changing policy.

---

## Policy Must Be Outside the Prompt

A prompt may tell the agent:

    "Never exceed 0.01 BTC."

Useful behavioral guidance.

But the actual execution gateway should enforce:

    quantity <= 0.01 BTC

independently.

Therefore:

    PROMPT RULE
    = guidance

    EXECUTION RULE
    = control.

---

## External Risk Gate

Future Nekonečný Mír could have:

    Research Agent
    Quant Agent
    Trading Agent

all proposing consequential actions.

But a separate:

    RISK GATE

owns:

    exposure limits
    order-size limits
    drawdown limits
    strategy permissions
    account permissions
    kill conditions.

Agents may read those rules.

They may not modify them.

---

## External Authority Gate

Similarly:

    AUTHORITY GATE

owns:

    who may act
    on what
    for which task
    for how long.

The actor cannot create:

    its own authority receipt.

---

## External Credential Broker

Credentials are another form of power.

Instead of giving an agent:

    permanent broker API key

the agent requests:

    ACTION X
    on
    RESOURCE Y.

A credential broker can expose only the minimum capability required.

The agent never owns the master credential.

---

## External Audit Trail

From #080:

    OBSERVE THE EFFECT.

Today we add:

    THE ACTOR MUST NOT CONTROL
    THE OBSERVATION RECORD.

Critical evidence should be written to storage the actor cannot rewrite.

---

## External Kill Switch

A kill switch controlled by the same agent it is intended to stop is weak.

The shutdown path should remain available even if:

    agent process fails
    agent becomes confused
    agent ignores instruction
    sandbox is compromised.

Therefore:

    STOP AUTHORITY

belongs outside the actor.

---

## Out-of-Band Control

This creates the concept:

# OUT-OF-BAND CONTROL

A safety channel that does not depend on the normal agent decision path.

If the normal path behaves unexpectedly:

    out-of-band control
    can still observe
    restrict
    quarantine
    revoke
    stop.

---

## Software Is Enough to Start

Nekonečný Mír does not need specialized hardware on day one.

The architectural principle can begin with:

    separate process
    separate service
    separate credentials
    separate OS permissions
    separate Git protection
    separate broker scope

The important property is:

    DIFFERENT AUTHORITY DOMAIN.

---

## Failure Independence

Two components are not independent merely because they have different names.

If:

    Trading Agent
    and
    Risk Agent

use:

    same prompt
    same context
    same credentials
    same writable policy file

their failures may be highly correlated.

Independence requires different control boundaries.

---

## Verifier Independence

From #077:

    MODEL = WITNESS, NOT ORACLE.

A second model can help verification.

But a second model alone is not necessarily an independent security boundary.

For consequential enforcement:

    machine-verifiable infrastructure

should dominate:

    model opinion.

---

## Policy Change

Who may change the guard?

Not the guarded actor.

A policy change should require a different path:

    PROPOSE CHANGE
    ↓
    VERIFY CHANGE
    ↓
    AUTHORIZE CHANGE
    ↓
    APPLY
    ↓
    RUN BOUNDARY TESTS

This directly extends #082.

---

## Policy Prover

A future Policy Prover could test:

    Does this change expand authority?

    Which resources become reachable?

    Which actions become possible?

    Does any deny rule disappear?

    Does blast radius increase?

If yes:

    stronger approval required.

---

## Authority Diff

Before applying a policy change:

    OLD AUTHORITY
    vs
    NEW AUTHORITY

should produce:

# AUTHORITY DIFF

Example:

    + WRITE feature/*
    + CREATE paper order
    - READ production secrets

Now authority changes become reviewable like code changes.

---

## Git Analogy

Git already gives us a familiar model.

Agent may:

    create branch
    write files
    commit

But branch protection outside the agent controls:

    merge to main.

The agent can propose.

It cannot redefine:

    who may merge.

That is the pattern we want elsewhere.

---

## Broker Analogy

Trading Agent may eventually possess:

    READ MARKET
    READ ACCOUNT
    PROPOSE ORDER

Execution Gateway owns:

    CREATE LIVE ORDER.

Withdrawal authority can remain:

    NEVER EXPOSED TO AGENT.

The strongest boundary is a capability that simply does not exist inside the actor's authority domain.

---

## Fail Closed

If the external guard becomes unavailable:

    UNKNOWN
    ≠
    AUTHORIZED.

Therefore consequential action should:

    STOP

rather than:

    bypass the guard.

---

## Guard Health

The guard itself needs monitoring.

We should know:

    running?
    policy loaded?
    version correct?
    audit channel healthy?
    credential broker reachable?
    clock synchronized?

A dead guard should not silently become:

    permission granted.

---

## Guard Version

Every consequential action should eventually be attributable to:

    agent version
    policy version
    guard version
    authority version.

Then incidents can be reconstructed precisely.

---

## Relationship to #078

#078:

    CAN ≠ MAY.

#083 asks:

    WHO ENFORCES MAY?

Answer:

    not the actor alone.

---

## Relationship to #080

#080:

    OBSERVE THE EFFECT.

#083:

    observation should exist
    outside the actor's authority.

---

## Relationship to #082

#082:

    TEST THE BOUNDARY.

#083:

    the actor being tested
    should not control
    the boundary test or its enforcement.

Together:

    EXTERNAL GUARD
    ↓
    TESTED BOUNDARY
    ↓
    INDEPENDENT OBSERVATION
    ↓
    VERIFIABLE CONTROL.

---

## Future Nekonečný Mír

A mature execution path might become:

    TRADING AGENT
    ↓
    TRADE PROPOSAL
    ↓
    AUTHORITY GATE
    ↓
    RISK GATE
    ↓
    EXECUTION GATE
    ↓
    BROKER
    ↓
    INDEPENDENT OBSERVER
    ↓
    RECONCILIATION

The Trading Agent participates in the chain.

It does not own the chain.

---

## Projects HQ Principle

> **Consequential safety controls should exist outside the authority domain of the autonomous actor they constrain. Separate proposal, authorization, execution and verification; keep policy, credentials, audit evidence and shutdown capability independently enforceable; and never allow the guarded component to become the sole judge of whether its own actions are permitted.**

Shortest version:

# THE ACTOR MUST NOT OWN THE GUARD

---

## Builds On

**#058** — Critical Controls Need Independent Evidence  
**#064** — Authority Requires Verifiable Identity  
**#069** — A Policy Is Not a Control Until the System Can Enforce It  
**#070** — Control Latency Must Be Shorter Than Risk Propagation  
**#073** — Authority Must Be Bound to Verifiable Scope  
**#074** — Trust Must Not Propagate Automatically Across Agent Chains  
**#077** — When Intelligence Becomes Cheap, Verification Becomes the Scarce Resource  
**#078** — Capability Must Never Determine Permission  
**#079** — Stronger Capability Requires Narrower Default Authority  
**#080** — Intent Logs Are Not Enough — Record Observed Effects  
**#081** — Memory Must Never Become an Unverified Authority Channel  
**#082** — A Control Is Not Proven Until the Boundary Has Been Tested

---

## Future Applications

`External Risk Gate` · `Authority Gate` · `Execution Gateway` · `Credential Broker` · `Out-of-Band Watchdog` · `Independent Audit Trail` · `Kill Switch` · `Policy Prover` · `Authority Diff` · `Broker Guard`

---

## Origin

**Daily AI Trading Brief — 29. 09. 2026**

Inspired by NVIDIA's Open Agent Safety Platform, particularly its separation of agent execution from independent policy enforcement and its out-of-band Sentry watchdog.

The generalized lesson for autonomous trading is that the component proposing consequential actions should not control the mechanism deciding whether those actions are permitted.

---

## Status

🟢 Active strategic principle

---

## Tags

`Projects HQ` · `Nekonečný Mír` · `AI Agents` · `Independent Enforcement` · `Risk Gate` · `Authority` · `Out-of-Band Control` · `Verification` · `Trading Safety` · `Git`

---

## Revision

**v1.0 — 29. 09. 2026**
