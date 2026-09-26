# PROJECTS HQ INSIGHT #080

## Date

26. 09. 2026

## Title

# Intent Logs Are Not Enough — Record Observed Effects

---

## Core Idea

Recent agent incidents reveal a fundamental observability problem.

After an autonomous system acts, it may be difficult to reconstruct:

    what it accessed
    what it changed
    what it transmitted
    where data went
    which external systems responded

This creates a dangerous gap.

We may know:

    WHAT THE AGENT WAS ASKED TO DO.

We may even know:

    WHAT THE AGENT SAID IT DID.

But neither necessarily proves:

    WHAT ACTUALLY HAPPENED.

Therefore:

> **A system must record observed effects, not merely agent intent or self-reported actions.**

---

## Intent ≠ Reality

Suppose:

    TASK:
    research market data.

The agent reports:

    TASK COMPLETE.

But during execution it also:

    accessed unexpected endpoint
    wrote temporary file
    transmitted data externally
    created external resource

If our log records only:

    TASK COMPLETE

then the audit trail describes intent.

Not reality.

---

## Three Different Truths

For every consequential action we should distinguish:

    INTENDED ACTION

    REPORTED ACTION

    OBSERVED EFFECT

These may agree.

But architecture must assume they can diverge.

---

## Example

Agent says:

    "I wrote report.md."

Intent log:

    WRITE report.md

Agent report:

    SUCCESS

Observed filesystem:

    report.md created
    config.yaml modified

Now we have:

    INTENT
    ≠
    OBSERVED EFFECT.

That difference is evidence.

---

## Self-Reporting Is Not Independent Evidence

An agent should not be the sole authority on:

    what it did.

Why?

Because the same component may:

    misunderstand outcome
    miss side effects
    fail partially
    hallucinate success
    omit unexpected behavior

Therefore:

> **The actor should not be the only observer of the action.**

---

## Runtime Observability

A future Nekonečný Mír should independently observe consequential side effects.

Examples:

    filesystem writes
    Git changes
    API calls
    broker orders
    network egress
    credential use
    external messages
    process execution

The observer should exist outside the agent's reasoning loop.

---

## Command vs Effect

Consider:

    Agent:
    CREATE ORDER BTC BUY 0.01

Command log proves:

    request was sent.

It does not prove:

    broker accepted order
    order filled
    quantity correct
    price correct
    position changed

Therefore:

    COMMAND LOG
    ≠
    STATE EVIDENCE.

---

## Trading Example

Future Trading Agent:

    intended:
      BUY 0.01 BTC

Agent reports:

    executed successfully.

Observed broker state:

    BUY 0.10 BTC

This is not a small logging discrepancy.

It is a safety incident.

The observed state must dominate the agent's narrative.

---

## Observed State Wins

When:

    AGENT REPORT

conflicts with:

    VERIFIED EXTERNAL STATE

the system should prefer:

    VERIFIED EXTERNAL STATE.

Therefore:

# OBSERVED STATE > SELF-REPORTED STATE

---

## Git Gives Us a Primitive

This is one reason Git matters so much.

Agent says:

    "I changed one documentation file."

Git can independently show:

    EXACT DIFF.

Agent says:

    "Nothing else changed."

Git can help test that claim.

The repository state becomes evidence outside the model's memory.

---

## Filesystem Observer

Future coding-agent environment might record:

    file_created
    file_modified
    file_deleted
    hash_before
    hash_after
    timestamp
    process_identity

Now:

    "I edited strategy.py"

can be compared against:

    what actually changed.

---

## Network Egress Observer

Recent agent incidents highlight another important boundary:

    NETWORK EGRESS.

An agent may technically be able to send information to:

    API
    website
    image host
    cloud service
    external endpoint

Therefore the system should independently record:

    destination
    method
    data classification
    bytes transferred
    authority receipt
    timestamp

Sensitive egress may require blocking before transmission.

---

## Data Classification

Not every outbound byte has equal consequence.

Possible classes:

    PUBLIC
    INTERNAL
    CONFIDENTIAL
    SECRET
    CREDENTIAL

Policy can then say:

    PUBLIC
    → normal egress

    INTERNAL
    → approved destinations only

    CONFIDENTIAL
    → explicit authority

    SECRET
    → external egress denied

---

## Egress Is an Action

We often think of agent actions as:

    write file
    place trade
    send email

But:

    SEND DATA OUTSIDE TRUST BOUNDARY

is itself a consequential action.

Therefore:

# EGRESS NEEDS AUTHORITY

---

## Side Effects Must Be First-Class

A tool call may have:

    PRIMARY EFFECT

and:

    SIDE EFFECTS.

Example:

    install package

Primary:

    dependency installed.

Possible side effects:

    network request
    lockfile changed
    executable downloaded
    transitive dependencies added

A trustworthy system should observe important side effects, not merely primary intent.

---

## Effect Receipt

Future architecture could generate:

    effect_receipt_id

    action_id

    actor_identity

    resource

    observed_before

    observed_after

    side_effects

    timestamp

    observer_identity

Now an action has independent evidence of consequence.

---

## Action Receipt vs Effect Receipt

From previous Insights we already have concepts such as:

    authority receipt
    permission receipt
    verification receipt

Today we add:

    EFFECT RECEIPT.

Conceptually:

    AUTHORITY RECEIPT
    proves:
    MAY

    ACTION RECEIPT
    proves:
    REQUESTED / EXECUTED

    EFFECT RECEIPT
    proves:
    WHAT CHANGED

Different evidence answers different questions.

---

## Expected State vs Observed State

This directly strengthens #071:

    EXPECTED STATE
    vs
    OBSERVED STATE.

Today we add:

    the observed state
    should come from
    an independent observation path
    whenever consequence justifies it.

---

## Independent Observer

Possible architecture:

    AGENT
      ↓
    ACTION GATE
      ↓
    TOOL / EXTERNAL SYSTEM
      ↓
    EFFECT

Meanwhile:

    OBSERVER
      ↓
    captures effect
      ↓
    EFFECT RECEIPT

The agent does not control the observer.

---

## Observer Independence

If the agent can:

    disable observer
    edit logs
    delete receipts

then observability is weak.

Therefore critical observers should have:

    separate identity
    append-only storage
    restricted write authority
    tamper evidence

---

## Immutable Audit Trail

For high-consequence operations:

    LOG

should ideally be:

    APPEND ONLY

not:

    AGENT EDITABLE.

This does not mean every debug log needs blockchain 😂🐸.

It means the actor being audited should not be able to rewrite its own audit history.

---

## Observability Must Match Consequence

From #066:

    CONSEQUENCE ↑
    →
    CONTROL STRENGTH ↑

Today:

    CONSEQUENCE ↑
    →
    OBSERVABILITY ↑

A documentation edit may need:

    Git diff.

A live trade may need:

    order request
    broker acknowledgement
    fill
    position
    balance
    reconciliation

---

## Observation Latency

Observation must also be timely.

If a dangerous side effect is discovered:

    three months later

the log may help forensics.

It did not help containment.

Therefore:

    OBSERVATION LATENCY
    must be shorter than
    HARM PROPAGATION

for high-consequence actions.

---

## Real-Time Observer

For critical actions:

    ACTION
    ↓
    OBSERVE
    ↓
    COMPARE
    ↓
    CONTAIN IF DIVERGENT

should happen close to real time.

This connects to #070:

> Control latency must be shorter than risk propagation.

---

## Divergence Signal

Define:

    EXPECTED EFFECT

and:

    OBSERVED EFFECT.

If:

    EXPECTED ≠ OBSERVED

then:

    DIVERGENCE INCIDENT.

Example:

    expected:
      one Git file changed

    observed:
      seven files changed

Result:

    STOP
    ↓
    RESTRICT AUTHORITY
    ↓
    INVESTIGATE

---

## Unknown Effect

If the system cannot determine what happened:

    OBSERVED EFFECT = UNKNOWN

From #053:

    UNKNOWN ≠ SAFE.

Therefore for consequential actions:

    UNKNOWN EFFECT

should not automatically permit continued authority.

---

## Blast-Radius Reconstruction

After an incident we need to answer:

    WHICH RESOURCES?
    WHICH DATA?
    WHICH SYSTEMS?
    WHICH CREDENTIALS?
    WHICH EXTERNAL DESTINATIONS?
    WHICH DOWNSTREAM ACTIONS?

Good observability turns this from:

    forensic archaeology

into:

    queryable evidence.

---

## Incident Timeline

Future incident record might reconstruct:

    08:31:01
    Agent received task

    08:31:04
    Credential used

    08:31:06
    API endpoint accessed

    08:31:08
    External write attempted

    08:31:08
    Policy denied

    08:31:09
    Incident created

    08:31:10
    Owner assigned

Now we know what happened.

---

## Provenance Graph

Eventually effects may form:

    ACTION
      ↓
    RESOURCE CHANGE
      ↓
    DOWNSTREAM ACTION
      ↓
    EXTERNAL EFFECT

This is effectively:

    CONSEQUENCE PROVENANCE.

It lets us trace:

    what caused what.

---

## Trading Provenance

Imagine:

    SIGNAL
    ↓
    STRATEGY DECISION
    ↓
    RISK APPROVAL
    ↓
    ORDER
    ↓
    FILL
    ↓
    POSITION
    ↓
    P&L

Each transition should be observable.

Then a bad outcome can be traced to:

    bad signal
    bad decision
    bad sizing
    broker mismatch
    execution error

rather than guessed.

---

## Auditability Is Not Bureaucracy

For autonomous systems:

    audit trail

is not paperwork after the fact.

It is operational infrastructure.

Without it:

    autonomy ↑
    while
    explainability ↓.

That combination is dangerous.

---

## Human Review

David should not read every log.

That would defeat automation.

Instead:

    MACHINE OBSERVES EVERYTHING IMPORTANT
    ↓
    MACHINE COMPARES EXPECTED vs OBSERVED
    ↓
    HUMAN SEES MATERIAL DIVERGENCES

Human attention remains premium.

---

## Observability Budget

Just as #077 introduced:

    VERIFICATION BUDGET

we may eventually need:

    OBSERVABILITY BUDGET.

Storage, monitoring and reconciliation cost resources.

The strongest monitoring should follow the highest consequence.

---

## Privacy Matters Too

Observability can itself create risk.

Logs should not blindly duplicate:

    passwords
    API keys
    private data
    sensitive payloads

Therefore:

    OBSERVE EFFECT

does not mean:

    COPY EVERY SECRET INTO LOGS.

We need:

    metadata
    hashes
    redaction
    classification
    controlled evidence storage.

---

## The Architecture Now

Our recent chain becomes:

    IDENTITY
    ↓
    SCOPE
    ↓
    PERMISSION
    ↓
    AUTHORITY
    ↓
    ACTION
    ↓
    OBSERVED EFFECT
    ↓
    RECONCILIATION
    ↓
    INCIDENT IF DIVERGENT
    ↓
    OWNER
    ↓
    RECOVERY

This closes an important gap.

We no longer trust only:

    what the agent intended.

We verify:

    what the world became.

---

## Projects HQ Principle

> **A system must record observed effects, not merely agent intent or self-reported actions.**

Shortest version:

# OBSERVE THE EFFECT, NOT JUST THE COMMAND

And the Nekonečný Mír version:

> **Every consequential autonomous action should produce independently observable evidence of its real-world effect. Record intended action, reported action and observed state separately; compare them automatically; treat material divergence or unknown effects as safety signals; and keep critical audit evidence outside the authority of the agent being observed.**

---

## Builds On

**#053** — UNKNOWN ≠ SAFE  
**#058** — Critical Controls Need Independent Evidence  
**#066** — Consequence Should Determine the Strength of the Control  
**#068** — Less Human Supervision Requires More Machine-Verifiable Evidence  
**#070** — Control Latency Must Be Shorter Than Risk Propagation  
**#071** — Every Consequential Action Needs an Expected State and an Observed State  
**#072** — A Failure Is Not Closed Until the System Has Changed  
**#074** — Trust Must Not Propagate Automatically Across Agent Chains  
**#075** — Incident Signals Must Cross Boundaries Without Transferring Authority  
**#076** — Every Consequential Safety Signal Needs an Acknowledged Owner  
**#077** — When Intelligence Becomes Cheap, Verification Becomes the Scarce Resource  
**#078** — Capability Must Never Determine Permission  
**#079** — Stronger Capability Requires Narrower Default Authority

---

## Future Applications

`Effect Receipt` · `Runtime Observability` · `Network Egress Control` · `Filesystem Observer` · `Git Diff Verification` · `Broker Reconciliation` · `Expected vs Observed State` · `Immutable Audit Trail` · `Consequence Provenance` · `Divergence Detection`

---

## Origin

**Daily AI Trading Brief — 26. 09. 2026**

Inspired by OpenAI's disclosure that experimental agents transmitted user-derived images to external hosting services and by the difficulty of reconstructing the full scope of autonomous agent activity after the fact.

The generalized lesson for autonomous trading is that permission controls alone are insufficient. Autonomous systems also need independent runtime evidence of what their actions actually changed in files, repositories, networks, broker accounts and external systems.

---

## Status

🟢 Active strategic principle

---

## Tags

`Projects HQ` · `Nekonečný Mír` · `AI Agents` · `Observability` · `Audit Trail` · `Effect Receipt` · `Network Egress` · `Reconciliation` · `Git` · `Safety` · `Trading`

---

## Revision

**v1.0 — 26. 09. 2026**
