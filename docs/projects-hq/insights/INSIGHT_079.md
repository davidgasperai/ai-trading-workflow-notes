# PROJECTS HQ INSIGHT #079

## Date

25. 09. 2026

## Title

# Stronger Capability Requires Narrower Default Authority

---

## Core Idea

Yesterday we established:

> Capability must never determine permission.

Today we add an important consequence.

As an agent becomes more capable, the number of things it could potentially do increases.

That does not justify broader authority.

It argues for the opposite.

> **The stronger the capability, the narrower its default authority should be.**

---

## Capability Creates Optionality

A weak tool may be able to:

    READ ONE FILE

A stronger agent may be able to:

    browse
    execute code
    discover endpoints
    modify files
    call APIs
    use credentials
    interact with Git
    operate external systems

Its:

    ACTION SPACE

has expanded dramatically.

Therefore its potential:

    BLAST RADIUS

has expanded too.

---

## Capability ↑ Does Not Mean Trust ↑

A common intuition is:

    smarter agent
    →
    more autonomy.

But safety suggests:

    smarter agent
    →
    more possible actions
    →
    more possible failure paths
    →
    stronger boundaries required.

Therefore:

    CAPABILITY ↑
    ≠
    AUTHORITY ↑

---

## Default Authority Should Shrink

A highly capable agent should begin with:

    MINIMUM NECESSARY AUTHORITY

and receive additional authority only when:

    identity is verified
    mandate is valid
    scope is explicit
    consequence is understood
    policy permits it

This is:

# CAPABILITY-RISK INVERSION

The more the agent could do,
the less we should assume it may do.

---

## Today's Real-World Trigger

OpenAI is reportedly preparing a cybersecurity-focused GPT-6 model.

A strong cybersecurity model could potentially:

    discover vulnerabilities
    reason about exploits
    inspect systems
    automate defensive work
    identify attack paths

Those capabilities can be extremely valuable.

But they are also dual-use.

Therefore deployment architecture matters as much as raw capability.

---

## Powerful Tool, Small Box

A useful mental model:

    STRONG MODEL
    +
    SMALL SANDBOX

may be safer than:

    WEAKER MODEL
    +
    BROAD SYSTEM ACCESS.

The model does not need weaker intelligence.

It needs narrower authority.

---

## Capability and Authority Are Separate Axes

Imagine:

                    AUTHORITY
                       ↑
                       |
        dangerous      |      dangerous
        mismatch       |      if unnecessary
                       |
    -------------------+----------------→ CAPABILITY
                       |
        limited        |      desirable
        usefulness     |      architecture
                       |
                       ↓

The goal is not:

    LOW CAPABILITY.

The goal is:

    HIGH CAPABILITY
    +
    PRECISE AUTHORITY.

---

## Cybersecurity Example

A Cyber Agent may be excellent at discovering vulnerabilities.

It may receive:

    READ repository
    RUN sandbox scanner
    ANALYZE dependency graph
    PROPOSE patch

It does not automatically need:

    PUBLIC INTERNET ATTACK ACCESS
    PRODUCTION CREDENTIALS
    DEPLOY RIGHTS
    SECRET ACCESS
    ADMIN ACCOUNT

Its intelligence remains powerful.

Its blast radius remains bounded.

---

## Trading Example

Future Nekonečný Mír may use a frontier model capable of:

    market research
    strategy reasoning
    coding
    risk analysis
    order construction

That does not mean it should receive:

    broker withdrawal rights.

Or even:

    unrestricted live-order rights.

Capability and authority remain independent.

---

## Smart Research Agent

Imagine:

    Research Agent
    =
    frontier model.

It may understand trading better than every other component.

Still:

    BROKER WRITE = DENIED.

Why?

Because:

    research competence
    ≠
    execution mandate.

---

## Intelligence Is Not Credential

This gives us another compact rule:

# INTELLIGENCE IS NOT A CREDENTIAL

Being able to understand an action does not authorize performing it.

Being able to predict an outcome does not authorize risking capital.

Being able to find a vulnerability does not authorize exploiting it.

---

## Dynamic Authority

Authority can expand temporarily.

Example:

    default:
      filesystem = read_only

    task:
      approved code patch

    temporary:
      write = branch_X

    expiry:
      20 minutes

Then:

    write permission revoked.

Powerful capability remains available.

Authority changes only around the verified task.

---

## Capability Escrow

Conceptually, high-risk capabilities may remain behind:

    AUTHORITY GATE.

The agent can request:

    CREATE LIVE ORDER

but the capability is not exposed until:

    mandate
    risk
    scope
    state

are verified.

This is similar to:

# CAPABILITY ESCROW

The capability exists.

The agent does not permanently possess it.

---

## Just-in-Time Permission

Future architecture could use:

    JUST-IN-TIME AUTHORITY

instead of:

    ALWAYS-ON AUTHORITY.

Example:

    Agent needs Git write.

    REQUEST
    ↓
    VERIFY TASK
    ↓
    GRANT BRANCH WRITE
    ↓
    ACTION
    ↓
    VERIFY RESULT
    ↓
    REVOKE

This dramatically reduces standing privilege.

---

## Standing Privilege Is Latent Risk

An unused permission is still risk.

Suppose Trading Agent has:

    WITHDRAW_FUNDS

but never uses it.

That does not make the permission harmless.

It means the system carries:

    LATENT AUTHORITY

without operational need.

Therefore:

> **Unused authority should be removed, not merely ignored.**

---

## Default Deny

For powerful agents:

    UNKNOWN ACTION
    →
    DENY / ESCALATE

not:

    ALLOW UNLESS FORBIDDEN.

This is the practical meaning of:

    DEFAULT DENY.

---

## Capability Discovery

A powerful agent may discover:

    new endpoint
    new tool behavior
    unexpected filesystem path
    undocumented API

From #078:

    DISCOVERY
    ≠
    PERMISSION.

Today we add:

    MORE DISCOVERY ABILITY
    →
    MORE NEED FOR DEFAULT DENY.

---

## Security Model Must Assume Creativity

Traditional permissions may assume predictable software.

Agentic systems may generate novel paths toward a goal.

Therefore safety architecture should not depend on predicting every path the agent might invent.

Instead:

    constrain resources
    constrain actions
    constrain credentials
    constrain side effects

at enforcement boundaries.

---

## Goal Alignment Is Not Enough

Suppose an agent sincerely pursues:

    HELP DAVID IMPROVE STRATEGY.

It might discover that it can:

    alter production configuration.

The goal may be aligned.

The action may still be unauthorized.

Therefore:

    GOOD GOAL
    ≠
    SAFE ACTION.

---

## Intent ≠ Permission

This gives us another distinction:

    INTENT
    ≠
    AUTHORITY.

Security cannot depend on deciding whether the agent "meant well."

It should depend on whether:

    ACTION WAS AUTHORIZED.

---

## Verification Before Capability Release

For high-consequence actions:

    REQUEST
    ↓
    VERIFY IDENTITY
    ↓
    VERIFY MANDATE
    ↓
    VERIFY SCOPE
    ↓
    VERIFY STATE
    ↓
    RELEASE CAPABILITY
    ↓
    ACTION
    ↓
    REVOKE
    ↓
    RECONCILE

This is stronger than giving the capability permanently and asking the agent not to misuse it.

---

## Git Example

Our coding agents may eventually have:

    READ REPOSITORY

by default.

For a task:

    WRITE FEATURE BRANCH

may be granted.

But:

    MERGE MAIN

remains unavailable.

Then:

    RELEASE / DEPLOY

requires another authority boundary.

The agent can be extremely capable.

Git authority remains narrow.

---

## Broker Example

Similarly:

    READ MARKET
    READ ACCOUNT

may be standing capabilities.

But:

    CREATE LIVE ORDER

may be just-in-time.

And:

    WITHDRAW FUNDS

may remain:

    NEVER AVAILABLE TO AGENT.

Capability architecture should reflect consequence.

---

## Verification Agent

Ironically, one of the best uses for increasingly powerful models may be:

    LESS AUTHORITY
    +
    MORE VERIFICATION.

A frontier model can inspect:

    code
    strategy
    logs
    permissions
    anomalies

without being allowed to execute consequential actions.

This connects directly to #077.

---

## Strong Intelligence Behind Read-Only Access

A surprisingly powerful pattern may be:

# FRONTIER INTELLIGENCE + READ-ONLY WORLD

The model can understand almost everything.

But changing the world requires separate gates.

This preserves much of the intelligence benefit while reducing blast radius.

---

## Authority Expansion Needs Evidence

If an agent requests more authority:

    WHY?
    FOR WHAT TASK?
    FOR WHICH RESOURCE?
    FOR HOW LONG?
    WHAT CONSEQUENCE?
    WHAT RECOVERY PATH?

Authority expansion should be an auditable event.

---

## Authority Receipt

Conceptually:

    authority_grant_id

    agent_identity

    capability_requested

    resource

    mandate

    scope

    granted_at

    expires_at

    approver

    policy_version

Then later we can answer:

    Why could this agent perform that action?

with evidence.

---

## Revocation Must Be Faster Than Expansion

Granting authority may require:

    verification.

Revoking authority should be:

    immediate.

Therefore:

    GRANT = DELIBERATE

    REVOKE = FAST

This connects to:

    FAST CONTAINMENT
    DELIBERATE RECOVERY.

---

## The Capability Paradox

As AI gets better:

    we can trust it with more complex reasoning.

But simultaneously:

    we should trust infrastructure,
    not model obedience,
    to enforce consequential boundaries.

This is not distrust of intelligence.

It is good systems engineering.

---

## The Emerging Pattern

Our recent Insights now form:

    IDENTITY
    ↓
    SCOPE
    ↓
    TRUST BOUNDARY
    ↓
    INCIDENT SIGNAL
    ↓
    OWNER
    ↓
    VERIFICATION
    ↓
    CAPABILITY
    ↓
    PERMISSION
    ↓
    JUST-IN-TIME AUTHORITY
    ↓
    ACTION
    ↓
    RECONCILIATION

The agent becomes smarter.

The architecture becomes stricter.

Both can happen simultaneously.

---

## Projects HQ Principle

> **The stronger the capability, the narrower its default authority should be.**

Shortest version:

# POWERFUL AGENT, SMALL DEFAULT BOX

And the Nekonečný Mír version:

> **Do not reward greater model capability with permanent broader authority. As agents become more capable of discovering, reasoning about and executing possible actions, reduce standing privilege, expose consequential capabilities only when a verified mandate requires them, grant authority narrowly and temporarily, and revoke it immediately after use. Intelligence may be broad; authority should remain precise.**

---

## Builds On

**#053** — UNKNOWN ≠ SAFE  
**#058** — Critical Controls Need Independent Evidence  
**#064** — Authority Requires Verifiable Identity  
**#066** — Consequence Should Determine the Strength of the Control  
**#068** — Less Human Supervision Requires More Machine-Verifiable Evidence  
**#069** — A Policy Is Not a Control Until the System Can Enforce It  
**#070** — Control Latency Must Be Shorter Than Risk Propagation  
**#073** — Authority Must Be Bound to Verifiable Scope  
**#074** — Trust Must Not Propagate Automatically Across Agent Chains  
**#075** — Incident Signals Must Cross Boundaries Without Transferring Authority  
**#076** — Every Consequential Safety Signal Needs an Acknowledged Owner  
**#077** — When Intelligence Becomes Cheap, Verification Becomes the Scarce Resource  
**#078** — Capability Must Never Determine Permission

---

## Future Applications

`Just-in-Time Authority` · `Capability Escrow` · `Standing Privilege Reduction` · `Default Deny` · `Read-Only Frontier Agent` · `Authority Receipt` · `Temporary Scope` · `Automatic Revocation` · `Git Authority Gate` · `Broker Authority Gate`

---

## Origin

**Daily AI Trading Brief — 25. 09. 2026**

Inspired by reports that OpenAI is preparing a cybersecurity-focused GPT-6 model, against the backdrop of recent incidents showing increasingly capable autonomous agents discovering and acting through unintended external-system paths.

The generalized lesson for autonomous trading is that increasing intelligence should not automatically expand standing authority. More capable agents can operate inside smaller, more precisely enforced permission boundaries while still providing greater analytical and verification value.

---

## Status

🟢 Active strategic principle

---

## Tags

`Projects HQ` · `Nekonečný Mír` · `AI Agents` · `Capability` · `Authority` · `Least Privilege` · `Just-in-Time Access` · `Verification` · `Git` · `Safety` · `Trading`

---

## Revision

**v1.0 — 25. 09. 2026**
