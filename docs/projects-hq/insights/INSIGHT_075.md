# PROJECTS HQ INSIGHT #075

## Date

21. 09. 2026

## Title

# Incident Signals Must Cross Boundaries Without Transferring Authority

---

## Core Idea

Yesterday we established:

> Trust must not propagate automatically across agent chains.

Today a new question follows.

If one component detects danger, how should that information travel through the system?

Imagine:

    Risk Agent
    ↓
    detects anomaly

It must be able to warn:

    Trading Agent
    Safety Agent
    Execution Gateway
    Human Operator

But the warning itself must not silently transfer the Risk Agent's authority to every recipient.

Therefore:

> **Incident signals should propagate quickly across relevant boundaries, while trust, authority and interpretation remain independently verified at each boundary.**

---

## Today's Real-World Parallel

During U.S.-China discussions in New York, the United States proposed a notification mechanism for serious AI incidents that could affect national security.

The idea is simple:

    INCIDENT
    ↓
    ONE PARTY DETECTS IT
    ↓
    OTHER PARTY IS NOTIFIED

But notification does not mean:

    the receiving party automatically trusts every claim

or:

    the notifying party gains authority over the receiver.

This distinction generalizes beautifully to multi-agent systems.

---

## Signal ≠ Authority

Suppose:

    Research Agent:
    "Market data may be corrupted."

That statement should be able to reach:

    Risk Agent
    Trading Agent
    Safety Agent

quickly.

But it should not mean:

    Research Agent now controls trading.

Therefore:

    INCIDENT SIGNAL
    ≠
    AUTHORITY TRANSFER

---

## Signal ≠ Truth

From #074:

    TRUST ≠ TRUTH

Today:

    ALERT ≠ VERIFIED FACT

An alert may be:

    correct
    partially correct
    stale
    duplicated
    misunderstood
    malicious
    false positive

Therefore the receiver should treat it as:

    EVIDENCE REQUIRING EVALUATION

not:

    ABSOLUTE TRUTH

---

## But Alerts Must Still Matter

There is an important balance.

If every recipient says:

    "I do not independently trust this alert,
    therefore I will ignore it."

then cross-system safety fails.

The better pattern is:

    RECEIVE
    ↓
    AUTHENTICATE
    ↓
    CLASSIFY
    ↓
    APPLY PRECAUTION
    ↓
    VERIFY
    ↓
    ESCALATE OR CLEAR

This allows fast containment without blind trust.

---

## Precaution Before Full Verification

Suppose:

    Market Data Agent
    reports:

    BTC FEED MAY BE CORRUPTED

Trading does not necessarily need to wait until the complete root cause is known.

It can temporarily move:

    NORMAL
    ↓
    CAUTION

or:

    RESTRICTED

while independent verification runs.

This connects directly to:

    FAST CONTAINMENT
    DELIBERATE RECOVERY

from #070.

---

## Alert Authentication

Before reacting strongly, the system should know:

    WHO SENT THE ALERT?

Therefore an incident signal may need:

    sender_identity
    timestamp
    incident_id
    affected_scope
    severity
    evidence_refs
    signature
    expiry

The receiving system can verify:

    AUTHENTIC SIGNAL

without yet concluding:

    VERIFIED INCIDENT

---

## Authenticity ≠ Accuracy

This distinction is critical.

A cryptographically valid message proves:

    Risk Agent sent this alert.

It does not prove:

    Risk Agent is correct.

Therefore:

    AUTHENTICITY
    ≠
    ACCURACY

Just as:

    TRUST
    ≠
    TRUTH.

---

## Incident Signal States

A future system might represent:

    RECEIVED
    ↓
    AUTHENTICATED
    ↓
    CLASSIFIED
    ↓
    VERIFICATION_PENDING
    ↓
    CONFIRMED

or:

    REJECTED

or:

    FALSE_POSITIVE

This prevents:

    message received

from becoming:

    incident confirmed.

---

## Severity Can Determine Immediate Response

Not every alert needs the same reaction.

Example:

    LOW:
    unusual research output

may produce:

    LOG + REVIEW

while:

    CRITICAL:
    broker position mismatch

may produce:

    IMMEDIATE NO-NEW-EXPOSURE

before full investigation.

Therefore:

    SEVERITY ↑
    →
    PRECAUTION SPEED ↑

---

## The Asymmetry of Safety

For high-consequence systems, it may be rational to temporarily reduce authority on incomplete evidence.

Why?

Because:

    false positive
    →
    temporary inconvenience

may be cheaper than:

    false negative
    →
    uncontrolled financial exposure

This does not mean every warning triggers KILL.

Our graduated authority states already solve this:

    NORMAL
    ↓
    CAUTION
    ↓
    RESTRICTED
    ↓
    MANAGE ONLY
    ↓
    KILL

---

## Cross-Agent Notification

Imagine future Nekonečný Mír:

    Market Data Agent
    ↓
    detects stale feed

It sends:

    INCIDENT_SIGNAL_4281

to:

    Risk Agent
    Safety Agent
    Trading Agent

Each recipient receives the same immutable incident reference.

No agent needs to paraphrase:

    "Someone told me something looked wrong."

😂🐸

They can all reference:

    incident_id = 4281

---

## Shared Incident ID

This is surprisingly important.

Without a shared identifier:

    Risk Agent:
    "feed incident"

    Trading Agent:
    "price issue"

    Safety Agent:
    "data anomaly"

may accidentally become three different incidents.

With:

    INCIDENT_ID = 4281

the system can correlate:

    alerts
    evidence
    decisions
    controls
    recovery

around one event.

---

## Incident Envelope

Conceptually:

    incident_id:
      4281

    issuer:
      market_data_agent_02

    detected_at:
      2026-09-21T07:14:03Z

    category:
      DATA_INTEGRITY

    severity:
      HIGH

    affected_scope:
      BTCUSDT_PRICE_FEED

    evidence:
      feed_A != feed_B

    recommended_precaution:
      NO_NEW_EXPOSURE

    status:
      UNVERIFIED

Notice:

    recommended_precaution

not:

    mandatory_command.

Why?

Because the sender may not possess authority over the receiver.

---

## Recommendation vs Command

This gives us another useful distinction:

    SIGNAL

says:

    something may be wrong.

    RECOMMENDATION

says:

    here is a proposed response.

    COMMAND

says:

    perform this action.

These require different authority.

A Research Agent may be allowed to:

    SIGNAL

but not:

    COMMAND EXECUTION.

---

## Authority Stays Local

Suppose:

    Market Data Agent
    recommends:
    KILL

The Safety Layer evaluates:

    signal authenticity
    severity
    policy
    evidence
    current authority state

Then the Safety Layer may independently decide:

    MANAGE ONLY

or:

    KILL

The response authority remains with the component authorized to make that decision.

---

## No Authority Smuggling

Without this separation, an unprivileged agent could write:

    CRITICAL INCIDENT!
    EXECUTION MUST STOP!

and effectively gain control over another component.

That would be:

# AUTHORITY SMUGGLING

😂🐸👻

The system must distinguish:

    right to report

from:

    right to command.

---

## Everyone May Report

A healthy safety architecture may allow many components to raise alerts.

For example:

    Research Agent
    Quant Agent
    Risk Agent
    Trading Agent
    Reconciliation Agent
    Broker Monitor

may all be able to say:

    SOMETHING IS WRONG.

This is useful.

Safety should not depend on one privileged observer noticing everything.

---

## Few Components May Command

But far fewer components should be able to:

    change authority state
    block execution
    close positions
    restore execution
    modify policy

Therefore:

    REPORTING AUTHORITY
    can be broad.

    EXECUTION AUTHORITY
    should remain narrow.

---

## Broad Detection, Narrow Control

This gives us today's compact architectural pattern:

# BROAD DETECTION → NARROW CONTROL

Many components may detect.

Few components may enforce.

And every enforcement action remains auditable.

---

## Incident Bus

Eventually, Nekonečný Mír might conceptually have an:

# INCIDENT BUS

Not necessarily a literal software bus yet.

The architectural idea is:

    Agent A
       ↓
    Incident Registry
       ↓
    Agent B
    Agent C
    Safety Layer
    Human

Instead of agents sending informal messages directly to each other.

The registry becomes the shared evidence surface.

---

## Why This Helps Trust

Yesterday:

    TRUST MUST NOT PROPAGATE AUTOMATICALLY

Today:

    SIGNALS MAY PROPAGATE
    WITHOUT TRUST PROPAGATING

This is powerful.

We want information to move quickly.

We do not want authority to move accidentally.

---

## Immutable Alert Record

Once emitted, a consequential alert should ideally preserve:

    original issuer
    original content
    original evidence
    original timestamp

Later agents may append:

    verification
    interpretation
    mitigation
    resolution

but should not silently rewrite the original signal.

This connects to #072:

    INCIDENT MEMORY
    +
    PROVENANCE

---

## Git Analogy

Our new Git workflow gives us a useful analogy.

Suppose Claude changes a file.

Git does not merely store:

    "Claude says the file changed safely."

Git preserves:

    BEFORE
    ↓
    DIFF
    ↓
    AFTER

Another agent can inspect the same evidence.

Likewise an incident system should preserve a common record rather than rely on agent-to-agent storytelling.

---

## Alert Deduplication

Multiple agents may notice the same incident.

Example:

    Market Data Agent:
    FEED ANOMALY

    Risk Agent:
    PRICE DIVERGENCE

    Trading Agent:
    SLIPPAGE ABNORMAL

These may all refer to one underlying event.

Future architecture may need:

    correlation
    deduplication
    incident linking

without deleting the independent observations.

Multiple independent observations may actually increase confidence.

---

## Independent Alerts Increase Evidence

Suppose:

    Agent A
    reports anomaly

and independently:

    Agent B
    reports same anomaly

Then:

    CONFIDENCE ↑

provided the observations are truly independent.

This connects to #058:

> Critical Controls Need Independent Evidence.

---

## Avoid Alert Cascades

There is also a danger.

If:

    Agent A alerts B
    B repeats alert to C
    C repeats alert to A

we may create:

    ALERT LOOP

or:

    FALSE CONSENSUS

because one original observation appears to become three independent reports.

Therefore provenance matters.

The system must know:

    independent observation

versus:

    forwarded signal.

---

## Provenance Prevents Fake Consensus

Example:

    SOURCE A
    ↓
    B forwards A
    ↓
    C forwards B

This is still:

    ONE ORIGINAL SOURCE

not:

    THREE SOURCES.

That distinction may be crucial for trading decisions.

---

## Recovery Signals Need Stronger Authority

An interesting asymmetry appears.

It may be acceptable for many agents to say:

    DANGER

and temporarily reduce authority.

But restoration should be harder.

From #061:

> Recovery Must Be Gated by Reconciliation.

Therefore:

    ALERT
    may reduce authority quickly.

But:

    ALL CLEAR
    should require stronger verification.

---

## Authority Ratchet

Conceptually:

    weak evidence
    may move:

    NORMAL → CAUTION

But returning:

    CAUTION → NORMAL

may require:

    independent verification
    reconciliation
    healthy controls
    fresh data

This prevents oscillation and premature recovery.

---

## Cross-System Safety

As agent ecosystems grow, we may eventually have:

    internal agents
    broker systems
    market-data providers
    external AI services
    cloud services
    coding agents

They cannot all share one trust domain.

But they may still need to exchange:

    incidents
    health signals
    revocations
    outages
    compromised credentials
    dependency failures

Therefore cross-system notification becomes part of resilience.

---

## The Emerging Architecture

Our safety architecture now gains another path.

Normal execution:

    IDENTITY
    ↓
    TRUST
    ↓
    MANDATE
    ↓
    VERIFIED SCOPE
    ↓
    AUTHORITY
    ↓
    POLICY
    ↓
    EXECUTION
    ↓
    OBSERVATION
    ↓
    RECONCILIATION

Parallel safety path:

    OBSERVER
    ↓
    INCIDENT SIGNAL
    ↓
    AUTHENTICATE
    ↓
    CLASSIFY
    ↓
    PRECAUTION
    ↓
    INDEPENDENT VERIFICATION
    ↓
    AUTHORITY DECISION
    ↓
    INCIDENT REGISTRY
    ↓
    RECOVERY GATE

The two paths interact.

But they do not collapse into each other.

---

## Projects HQ Principle

> **Incident signals must cross boundaries without transferring authority.**

Shortest version:

# PROPAGATE SIGNALS, NOT AUTHORITY

And the Nekonečný Mír version:

> **Allow safety information to travel rapidly across agents, tools and external systems, but never let the act of reporting an incident silently grant the reporter command authority or convert an unverified claim into truth. Authenticate the signal, preserve its provenance, apply consequence-appropriate precaution, verify independently, and keep enforcement authority explicitly bounded.**

---

## Builds On

**#053** — UNKNOWN ≠ SAFE  
**#058** — Critical Controls Need Independent Evidence  
**#061** — Recovery Must Be Gated by Reconciliation  
**#064** — Authority Requires Verifiable Identity  
**#066** — Consequence Should Determine the Strength of the Control  
**#067** — A Control Must Have an Escalation Path  
**#068** — Less Human Supervision Requires More Machine-Verifiable Evidence  
**#070** — Control Latency Must Be Shorter Than Risk Propagation  
**#071** — Every Consequential Action Needs an Expected State and an Observed State  
**#072** — A Failure Is Not Closed Until the System Has Changed  
**#073** — Authority Must Be Bound to Verifiable Scope  
**#074** — Trust Must Not Propagate Automatically Across Agent Chains

---

## Future Applications

`Incident Bus` · `Incident Envelope` · `Shared Incident ID` · `Alert Authentication` · `Alert Provenance` · `Alert Deduplication` · `Authority Smuggling Prevention` · `Cross-Agent Notification` · `Safety Signal` · `Recovery Gate`

---

## Origin

**Daily AI Trading Brief — 21. 09. 2026**

Inspired by the U.S. proposal during U.S.-China talks in New York for a notification mechanism covering serious AI incidents with national-security implications.

The generalized lesson for autonomous trading is that independent systems need a way to exchange urgent safety information without automatically extending trust, transferring authority or treating another system's interpretation as verified truth.

---

## Status

🟢 Active strategic principle

---

## Tags

`Projects HQ` · `Nekonečný Mír` · `AI Agents` · `Incident Signal` · `Incident Bus` · `Authority` · `Trust Boundary` · `Provenance` · `Safety` · `Trading`

---

## Revision

**v1.0 — 21. 09. 2026**
