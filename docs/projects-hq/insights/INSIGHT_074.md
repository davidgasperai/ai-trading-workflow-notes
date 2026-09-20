# PROJECTS HQ INSIGHT #074

## Date

20. 09. 2026

## Title

# Trust Must Not Propagate Automatically Across Agent Chains

---

## Core Idea

Yesterday we established:

> Authority must be bound to verifiable scope.

But modern agent systems rarely consist of one isolated actor.

They increasingly look like:

    Human
    ↓
    Orchestrator
    ↓
    Research Agent
    ↓
    Coding Agent
    ↓
    Tool
    ↓
    External API

or:

    Trading Agent
    ↓
    Risk Agent
    ↓
    Execution Gateway
    ↓
    Broker

This creates another important question:

    If Component A trusts Component B,
    and Component B trusts Component C,
    does A automatically trust C?

The answer should be:

    NO.

Therefore:

> **Trust must be evaluated at every consequential boundary and must never propagate automatically through an agent chain.**

---

## The Transitive Trust Problem

Imagine:

    David
    ↓
    authorizes
    Claude Code

Claude Code calls:

    Agent B

Agent B calls:

    Tool C

Tool C reaches:

    External Service D

A dangerous system may implicitly reason:

    David trusts Claude
    ↓
    Claude trusts B
    ↓
    B trusts C
    ↓
    C trusts D

therefore:

    David trusts D.

That conclusion does not follow.

---

## Trust Is Not Transitive

In mathematics:

    A trusts B

and:

    B trusts C

does not necessarily imply:

    A trusts C

For autonomous systems:

    TRUST(A,B)
    +
    TRUST(B,C)

must not automatically become:

    TRUST(A,C)

This becomes increasingly important as agent chains grow.

---

## Today's AI Context

Recent cybersecurity incidents involving frontier AI systems have repeatedly involved models interacting with:

    external websites
    credentials
    repositories
    other systems
    tools
    third-party infrastructure

At the same time, major AI labs are beginning to discuss shared safety approaches.

The architecture lesson is broader than any single incident.

Future systems will increasingly depend on components created by different actors.

Therefore trust cannot be inherited merely because one trusted component introduced another.

---

## Delegation Is Not Trust Transfer

Suppose:

    Research Agent

is allowed to delegate:

    data analysis

to:

    Quant Agent.

That does not mean the Quant Agent automatically receives every permission held by the Research Agent.

Instead:

    DELEGATED AUTHORITY
    <=
    REQUIRED TASK AUTHORITY

This extends #073:

    delegated_scope
    <=
    parent_scope

But today we add:

    delegated_trust
    must also be independently evaluated.

---

## Example: Nekonečný Mír

Imagine:

    David
    ↓
    Trading Orchestrator
    ↓
    Strategy Agent
    ↓
    Python Tool
    ↓
    package dependency
    ↓
    remote API

David may trust:

    Trading Orchestrator

but David has not necessarily evaluated:

    package dependency

or:

    remote API.

Therefore the orchestrator cannot treat downstream dependencies as trusted merely because they are reachable.

---

## Reachability ≠ Trust

Yesterday:

> If an agent can technically reach a consequential resource, that reachability is part of its effective authority.

Today:

> **Reachability must never be interpreted as trust.**

A component can be:

    reachable

while still being:

    untrusted
    restricted
    read-only
    sandboxed
    verification-required

---

## Explicit Trust Boundary

Every consequential transition should cross a:

# TRUST BOUNDARY

Conceptually:

    COMPONENT A
    ↓
    TRUST CHECK
    ↓
    COMPONENT B

The trust check may evaluate:

    identity
    provenance
    permissions
    integrity
    version
    scope
    freshness
    expected behaviour
    evidence

Only then does the interaction continue.

---

## Identity Before Trust

From #064:

    Authority Requires Verifiable Identity

Today:

    Trust also requires identity.

If the system cannot prove:

    WHO IS THIS COMPONENT?

then it cannot reliably know:

    WHAT TRUST POLICY APPLIES?

Therefore:

    UNKNOWN IDENTITY
    ↓
    UNKNOWN TRUST
    ↓
    REDUCED AUTHORITY

---

## Trust Must Be Contextual

A component should not simply have:

    TRUSTED = TRUE

That is too broad.

Instead:

    trusted_for:
      market_data_read

    not_trusted_for:
      trade_execution

The same component may be trusted for one operation and prohibited for another.

---

## Trust Tuple

Conceptually:

    subject:
      quant_agent_01

    trusted_for:
      read_market_data

    resource:
      BTCUSDT

    environment:
      research

    valid_until:
      2026-09-20T12:00:00Z

    evidence:
      verified_identity
      approved_version

This resembles yesterday's Authority Tuple.

That is intentional.

Trust and authority are related but not identical.

---

## Trust ≠ Authority

A component may be trusted but not authorized.

Example:

    Risk Agent

may be highly trusted.

But it may still lack authority to:

    place trades.

Likewise a component may possess limited authority without being broadly trusted.

Example:

    Exchange API

may be authorized to:

    return account state

but its response may still require reconciliation.

Therefore:

    TRUST
    ≠
    AUTHORITY

---

## Trust ≠ Truth

This distinction is even more important.

Suppose:

    Trusted Market Data Provider

returns:

    BTC = 81,000

Trusted source does not mean:

    DATA MUST BE TRUE.

It means:

    source satisfies our trust policy.

We may still require:

    freshness
    consistency
    cross-check
    tolerance

Therefore:

> **Trust determines how evidence may be used. It does not convert evidence into truth.**

---

## Independent Verification

For high-consequence state:

    Source A
    ↓
    claim

may require:

    Source B
    ↓
    independent observation

Example:

    Broker API:
    POSITION = 0.010 BTC

Independent reconciliation may compare:

    fills
    orders
    balances
    position endpoint

Trust does not eliminate verification.

---

## Agent-to-Agent Claims

Imagine:

    Strategy Agent:
    "Risk approved."

Execution Gateway should not simply accept that statement.

Instead:

    Strategy Agent
    ↓
    presents
    RISK_APPROVAL_RECEIPT

Execution Gateway verifies:

    issuer
    signature
    policy version
    scope
    timestamp
    authority state

Then:

    VALID
    or
    INVALID

The claim becomes machine-verifiable evidence.

---

## Never Trust Self-Declared Authority

Weak:

    Agent B:
    "Agent A authorized me."

😂🐸

Strong:

    Agent B:
    presents signed delegation receipt

System verifies:

    Agent A identity
    Agent A authority
    delegation scope
    expiry
    policy compatibility

Only then:

    DELEGATION VALID

---

## Trust Chain vs Evidence Chain

We should prefer:

    TRUST CHAIN

to become:

    EVIDENCE CHAIN

Instead of:

    A says B is okay
    B says C is okay
    therefore C is okay

we want:

    A identity verified
    B identity verified
    delegation verified
    C identity verified
    requested scope verified
    policy verified

Each boundary produces evidence.

---

## Trust Receipts

Future Nekonečný Mír might eventually produce something like:

    trust_receipt_id

    subject_identity

    verifier_identity

    allowed_context

    evidence_refs

    policy_version

    timestamp

    expiry

    verification_result

This should not become unnecessary bureaucracy for every harmless action.

Control strength still follows consequence.

---

## Consequence Determines Trust Verification

From #066:

    CONSEQUENCE ↑
    →
    CONTROL STRENGTH ↑

Today:

    CONSEQUENCE ↑
    →
    TRUST VERIFICATION ↑

Example:

    Agent asks another agent
    to summarize documentation

may require little verification.

But:

    Agent delegates
    LIVE TRADE EXECUTION

requires strong identity, scope and authority evidence.

---

## Trust Decays

Trust should not necessarily last forever.

Why?

    component updated
    credentials rotated
    policy changed
    model changed
    dependency changed
    compromise discovered

Therefore trust may have:

    TTL

or require:

    re-verification

after meaningful changes.

---

## Version Change Can Invalidate Trust

Suppose:

    Risk Agent v1.4
    VERIFIED

Then deployment changes to:

    Risk Agent v1.5

We should not automatically assume:

    TRUST(v1.4)
    =
    TRUST(v1.5)

The new version may require:

    regression tests
    policy tests
    evidence refresh

Trust belongs to an identified state, not merely a familiar name.

---

## Git Becomes Relevant

This is where our new Git workflow becomes especially interesting.

Git gives us:

    commit identity
    history
    diff
    version

Eventually an agent may operate against:

    commit SHA

rather than:

    "the current code."

That means evidence can say:

    tested:
    commit abc123

and execution can verify:

    running:
    commit abc123

Now trust can be attached to a reproducible software state.

---

## Trusted Commit ≠ Trusted Future Commit

This is fundamental.

Suppose:

    commit A
    passes safety tests.

Then:

    commit B

adds a new feature.

We cannot conclude:

    A trusted
    therefore B trusted.

Again:

    TRUST MUST NOT PROPAGATE AUTOMATICALLY.

A change creates a new evidence obligation.

---

## Git + Agents

Our emerging workflow:

    Insight
    ↓
    GitHub
    ↓
    Git commit
    ↓
    Coding Agent
    ↓
    code change
    ↓
    tests
    ↓
    new commit

can eventually become:

    PROPOSAL
    ↓
    CHANGE
    ↓
    DIFF
    ↓
    TEST
    ↓
    REVIEW
    ↓
    VERIFIED VERSION

This is exactly why Git is much more than storage for Nekonečný Mír.

It can become part of the evidence architecture.

---

## Tool Trust

Agents increasingly use:

    shell
    Git
    browser
    APIs
    Python
    external packages

Each tool has a different trust profile.

For example:

    Git read
    may be low consequence.

    Git push
    is higher consequence.

    Shell read
    differs from
    shell execute.

    Broker read
    differs from
    broker trade.

Trust should follow the specific operation.

---

## Least Trust

We already use:

    LEAST PRIVILEGE

Today we can add:

# LEAST TRUST

Meaning:

> Give a component only the trust assumptions necessary for the task, for only as long as required.

Do not assume:

    trusted once
    =
    trusted everywhere.

---

## Failure of a Trusted Component

Suppose a trusted component misbehaves.

From #072:

    FAIL
    ↓
    LEARN
    ↓
    CHANGE
    ↓
    VERIFY

Today we add:

    TRUST STATUS
    ↓

until investigation and re-verification are complete.

A serious incident should be able to revoke trust dynamically.

---

## Trust Revocation

Possible flow:

    anomaly detected
    ↓
    component trust revoked
    ↓
    downstream authority reduced
    ↓
    active dependencies identified
    ↓
    containment
    ↓
    investigation
    ↓
    re-verification
    ↓
    staged restoration

This connects trust directly to our Authority State Machine.

---

## Blast Radius

If trust propagates automatically:

    one compromised component
    ↓
    entire system compromised

If trust is bounded:

    one compromised component
    ↓
    local trust revoked
    ↓
    blast radius contained

Therefore trust boundaries are also blast-radius boundaries.

---

## Future Multi-Agent Architecture

Our future agents may include:

    Research Agent
    Quant Agent
    Risk Agent
    Documentation Agent
    Trading Agent
    Safety Agent

None should simply say:

    "Another agent told me."

For consequential actions the system should ask:

    WHO?
    UNDER WHAT AUTHORITY?
    FOR WHAT SCOPE?
    USING WHICH VERSION?
    BASED ON WHAT EVIDENCE?
    IS THAT EVIDENCE STILL VALID?

---

## The Emerging Chain

Our architecture now becomes:

    IDENTITY
    ↓
    TRUST
    ↓
    ROLE
    ↓
    PERMISSION
    ↓
    MANDATE
    ↓
    VERIFIED SCOPE
    ↓
    AUTHORITY
    ↓
    CONSEQUENCE
    ↓
    POLICY
    ↓
    ENFORCEMENT
    ↓
    EXECUTION
    ↓
    OBSERVATION
    ↓
    RECONCILIATION
    ↓
    EVIDENCE

Across every consequential boundary:

    VERIFY TRUST AGAIN

---

## Projects HQ Principle

> **Trust must not propagate automatically across agent chains.**

Shortest version:

# VERIFY EVERY CONSEQUENTIAL TRUST BOUNDARY

And the Nekonečný Mír version:

> **Never let one trusted agent silently convert another agent, tool, dependency, version or external service into a trusted component. Trust should be contextual, bounded, evidence-backed, revocable and re-evaluated whenever consequential authority crosses a boundary.**

---

## Builds On

**#053** — UNKNOWN ≠ SAFE  
**#056** — Capability ≠ Authority  
**#058** — Critical Controls Need Independent Evidence  
**#064** — Authority Requires Verifiable Identity  
**#066** — Consequence Should Determine the Strength of the Control  
**#068** — Less Human Supervision Requires More Machine-Verifiable Evidence  
**#069** — A Policy Is Not a Control Until the System Can Enforce It  
**#071** — Every Consequential Action Needs an Expected State and an Observed State  
**#072** — A Failure Is Not Closed Until the System Has Changed  
**#073** — Authority Must Be Bound to Verifiable Scope

---

## Future Applications

`Trust Boundary` · `Trust Receipt` · `Least Trust` · `Trust Revocation` · `Delegation Verification` · `Agent Identity` · `Commit Verification` · `Git Provenance` · `Dependency Trust` · `Blast Radius Control`

---

## Origin

**Daily AI Trading Brief — 20. 09. 2026**

Inspired by the growing number of documented agentic cybersecurity incidents across multiple AI systems, the emergence of cross-lab safety coordination, and the increasing importance of interactions between independently operated agents, tools and external systems.

The generalized lesson for autonomous trading is that trust granted to one component must never automatically propagate through the components it calls, delegates to or depends upon.

---

## Status

🟢 Active strategic principle

---

## Tags

`Projects HQ` · `Nekonečný Mír` · `AI Agents` · `Trust Boundary` · `Least Trust` · `Git` · `Provenance` · `Delegation` · `Safety` · `Trading`

---

## Revision

**v1.0 — 20. 09. 2026**
