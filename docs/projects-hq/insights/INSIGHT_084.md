# PROJECTS HQ INSIGHT #084

## Date

30. 09. 2026

## Title

# Authority Must Decay Unless It Is Revalidated

---

## Core Idea

Traditional agent tasks are often short.

A request begins.

The agent acts.

The task ends.

But always-on autonomous agents change the architecture.

An agent may continue working for:

    hours
    days
    weeks

while:

    market conditions change
    account state changes
    risk limits change
    credentials change
    policy changes
    user intent changes

Therefore an authorization that was valid when a task began
may become unsafe while the task is still running.

> **Authority should decay over time unless current evidence revalidates it.**

Shortest version:

# AUTHORITY HAS A HALF-LIFE

---

## Permission Is Not Timeless

Suppose David says:

    Research BTC today.

At 09:00 this is valid.

At 09:05:

    still probably valid.

Three months later:

    the same remembered instruction
    should not automatically authorize
    an unlimited continuation of the task.

Time changes context.

Therefore:

    VALID ONCE
    ≠
    VALID FOREVER.

---

## Always-On Agents Change the Problem

A persistent agent may:

    watch
    wait
    resume
    delegate
    react to events
    continue after humans leave

The important security question becomes:

    WHEN DOES ITS MANDATE STOP BEING FRESH?

---

## Authority Lease

Instead of permanent permission:

    GRANT AUTHORITY

use:

    LEASE AUTHORITY.

A lease contains:

    identity
    mandate
    resource
    allowed actions
    scope
    issued_at
    expires_at
    renewal conditions

When:

    expires_at < now

the consequential capability disappears.

---

## Default

For consequential authority:

# EXPIRED = DENIED

Not:

    expired = probably still okay.

Not:

    expired = continue until somebody notices.

---

## Renewal

Renewal should not merely extend a timestamp.

It should ask whether the assumptions behind the authority remain true.

Example:

    strategy still enabled?
    account still correct?
    risk budget available?
    market allowed?
    broker healthy?
    incident state clear?
    policy version current?

Only then:

    RENEW.

---

## Revalidation

This creates:

    AUTHORITY
    ↓
    TIME PASSES
    ↓
    REVALIDATE
    ↓
    RENEW or REVOKE

The system continuously converts:

    historical permission

into:

    current permission

only when evidence supports it.

---

## Trading Example

At 10:00:

    Trading Agent receives authority
    to trade BTC
    using Strategy X
    with maximum exposure Y.

At 10:20:

    daily loss limit is reached.

Even if the original authority lease has not expired,
state-based revalidation should revoke it.

Therefore authority can end because of:

    TIME

or:

    STATE.

---

## Time Expiry

Possible rule:

    trade proposal authority:
    30 minutes

    live execution authority:
    one action

    research access:
    eight hours

    Git feature-branch write:
    task lifetime

    production deployment:
    single use

Different consequence deserves different lifetime.

---

## Single-Use Authority

Some permissions should have effectively zero standing lifetime.

Example:

    CREATE LIVE ORDER.

Authority can be:

    issued
    ↓
    used once
    ↓
    consumed.

This is stronger than:

    live trading enabled all day.

---

## State Expiry

Authority may also become invalid when:

    drawdown threshold crossed
    volatility regime changes
    broker incident occurs
    strategy disabled
    account balance changes materially
    verification fails
    new incident opens

This gives us:

# STATE-BOUND AUTHORITY

---

## Event-Driven Revocation

Important events can immediately invalidate active leases.

Example:

    BROKER INCIDENT
    ↓
    revoke execution authority.

    STRATEGY KILL RULE
    ↓
    revoke strategy authority.

    CREDENTIAL ROTATION
    ↓
    revoke old credential grants.

    POLICY UPDATE
    ↓
    revalidate existing leases.

---

## No Silent Renewal

An agent should not renew its own consequential authority merely because:

    it wants to continue.

Renewal must come from:

    external authority infrastructure

using:

    current evidence.

This extends #083:

    THE ACTOR MUST NOT OWN THE GUARD.

Today:

    THE ACTOR MUST NOT OWN
    THE CLOCK ON ITS AUTHORITY.

---

## Memory Cannot Renew Authority

From #081:

    MEMORY ≠ AUTHORITY.

Therefore a stored statement:

    "David approved this task yesterday."

cannot renew an expired grant.

Historical approval remains:

    HISTORY.

Current authority requires:

    CURRENT VALIDATION.

---

## Long-Running Task

Imagine a Research Agent working overnight.

At midnight:

    research mandate valid.

At 03:00:

    source access still valid.

At 06:00:

    policy changes.

The agent should not continue under:

    yesterday's policy snapshot.

It should cross a:

    REVALIDATION CHECKPOINT.

---

## Revalidation Checkpoint

Conceptually:

    TASK CONTINUES
         ↓
    CHECKPOINT
         ↓
    identity valid?
    mandate current?
    scope current?
    policy current?
    resource healthy?
    risk state acceptable?
         ↓
    YES → CONTINUE
    NO  → STOP / ESCALATE

---

## Continuous Does Not Mean Permanent

An always-on agent can be:

    continuously available

without having:

    continuously broad authority.

This distinction is crucial.

# ALWAYS ON
# DOES NOT MEAN
# ALWAYS AUTHORIZED

---

## Dormant Agent

When no active mandate exists:

    agent may remain alive

but consequential authority returns to:

    MINIMUM.

This is safer than retaining the privileges of the last task.

---

## Authority Decay

We can think of authority as having a half-life.

The longer it exists without fresh evidence:

    confidence ↓

Eventually:

    authority → zero.

The decay rate depends on consequence.

---

## High Consequence = Short Half-Life

Low consequence:

    read public research
    → longer lease.

High consequence:

    live trade
    → short lease.

Very high consequence:

    withdraw funds
    → no autonomous lease.

Therefore:

    CONSEQUENCE ↑
    →
    AUTHORITY HALF-LIFE ↓

---

## Freshness Receipt

A renewed authority grant could produce:

    authority_id
    original_mandate
    revalidated_at
    evidence_checked
    state_snapshot
    policy_version
    expires_at
    verifier

Now we can prove not merely:

    permission once existed

but:

    permission was fresh
    when action occurred.

---

## Action-Time Check

Before consequential execution:

    now < expires_at?

    state conditions valid?

    authority not revoked?

    policy version acceptable?

If any answer is:

    NO

then:

    DENY.

---

## Clock Security

Time itself becomes security-relevant.

The authority system needs:

    trusted clock
    consistent timestamps
    clear expiry semantics.

An agent should not be able to alter the clock used to decide whether its own authority remains valid.

---

## Relationship to #079

#079:

    STRONGER CAPABILITY
    →
    NARROWER DEFAULT AUTHORITY.

#084 adds:

    STRONGER CONSEQUENCE
    →
    SHORTER AUTHORITY LIFETIME.

---

## Relationship to #081

#081:

    MEMORY ≠ AUTHORITY.

#084:

    even genuine historical authority
    does not automatically remain current.

---

## Relationship to #082

#082:

    TEST THE BOUNDARY.

Boundary tests should include:

    expired authority
    → DENY.

    revoked authority
    → DENY.

    stale policy
    → DENY.

---

## Relationship to #083

#083:

    THE ACTOR MUST NOT OWN THE GUARD.

#084:

    external authority infrastructure
    also owns expiry,
    renewal,
    and revocation.

---

## Future Nekonečný Mír

A mature live-trading path could become:

    SIGNAL
    ↓
    TRADE PROPOSAL
    ↓
    REQUEST AUTHORITY
    ↓
    VERIFY CURRENT STATE
    ↓
    ISSUE SHORT-LIVED LEASE
    ↓
    RISK GATE
    ↓
    EXECUTE ONE ACTION
    ↓
    CONSUME / REVOKE LEASE
    ↓
    VERIFY EFFECT

There is no permanent:

    LIVE_TRADING = TRUE.

Instead:

    CURRENT ACTION
    has
    CURRENT AUTHORITY.

---

## Why This Is Better

Standing authority creates:

    latent risk.

Short-lived authority creates:

    bounded opportunity for harm.

If something unexpected happens,
the system naturally returns toward:

    LESS AUTHORITY.

That is the safe direction of failure.

---

## Projects HQ Principle

> **Consequential authority should decay unless current evidence revalidates it. Bind permissions to time and state, use short-lived or single-use grants for high-impact actions, re-check mandate and policy during long-running tasks, revoke authority when assumptions change, and never allow historical approval or persistent memory to silently become permanent permission.**

Shortest version:

# AUTHORITY HAS A HALF-LIFE

Operational version:

# ALWAYS ON ≠ ALWAYS AUTHORIZED

---

## Builds On

**#066** — Consequence Should Determine the Strength of the Control  
**#069** — A Policy Is Not a Control Until the System Can Enforce It  
**#073** — Authority Must Be Bound to Verifiable Scope  
**#074** — Trust Must Not Propagate Automatically Across Agent Chains  
**#078** — Capability Must Never Determine Permission  
**#079** — Stronger Capability Requires Narrower Default Authority  
**#080** — Intent Logs Are Not Enough — Record Observed Effects  
**#081** — Memory Must Never Become an Unverified Authority Channel  
**#082** — A Control Is Not Proven Until the Boundary Has Been Tested  
**#083** — The Guard Must Live Outside the System It Guards

---

## Future Applications

`Authority Lease` · `Authority Half-Life` · `Single-Use Permission` · `State-Bound Authority` · `Mandate Renewal` · `Revalidation Checkpoint` · `Event-Driven Revocation` · `Freshness Receipt` · `Trading Authority TTL` · `Fail Closed`

---

## Origin

**Daily AI Trading Brief — 30. 09. 2026**

Inspired by OpenAI's launch of dots: persistent, always-on agents capable of working across projects, applications and long periods without step-by-step human direction.

The generalized lesson for autonomous trading is that long-lived agents should not imply long-lived privilege. As agent lifetime increases, consequential authority should remain temporary, state-aware and continuously revalidated.

---

## Status

🟢 Active strategic principle

---

## Tags

`Projects HQ` · `Nekonečný Mír` · `AI Agents` · `Authority` · `Time-Bounded Permissions` · `Revalidation` · `Revocation` · `Always-On Agents` · `Risk Gate` · `Trading Safety`

---

## Revision

**v1.0 — 30. 09. 2026**
