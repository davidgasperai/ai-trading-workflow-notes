# PROJECTS HQ INSIGHT #085

## Date
02. 10. 2026

## Title
# Every Consequential Action Must Be Forensically Reconstructable

---

## Core Idea

Stopping a dangerous action is necessary.

But after an incident, another question becomes equally important:

    What actually happened?

Autonomous systems can act:

    quickly
    across many tools
    through delegated agents
    over long periods
    without continuous human observation

If the system cannot reconstruct those actions independently,
then after failure we are left with:

    guesses
    model recollection
    incomplete logs
    conflicting narratives

That is not sufficient for consequential autonomy.

Therefore:

> Every consequential action should leave enough independent evidence to reconstruct what happened without trusting the actor's memory or explanation.

Shortest version:

# IF IT MATTERS, WE MUST BE ABLE TO REPLAY THE EVIDENCE

---

## Incident Reconstruction

After an unexpected event we should be able to answer:

    WHO acted?

    WHAT did they attempt?

    WHAT authority existed?

    WHICH tool was used?

    WHICH resource was touched?

    WHAT changed?

    WHEN did it happen?

    WHAT evidence proves it?

---

## Actor Report Is Not Evidence

An agent may report:

    "I only read the file."

But independent evidence may show:

    file opened
    credential discovered
    network request created
    remote resource modified

Therefore:

    AGENT NARRATIVE
    ≠
    CANONICAL INCIDENT RECORD.

This extends #080:

    OBSERVED STATE > SELF-REPORTED STATE.

---

## Action Envelope

Every consequential action can produce an immutable:

    ACTION ENVELOPE

containing:

    action_id
    actor_identity
    parent_task
    authority_id
    policy_version
    tool
    target_resource
    requested_action
    timestamp
    input_hash
    result
    observed_effect
    evidence_refs

---

## Causal Chain

The system should preserve:

    HUMAN MANDATE
        ↓
    AGENT PLAN
        ↓
    AUTHORITY GRANT
        ↓
    TOOL CALL
        ↓
    EXTERNAL EFFECT
        ↓
    OBSERVATION
        ↓
    RECONCILIATION

Now an incident can be reconstructed as a chain of evidence.

---

## Delegation

Multi-agent systems make this harder.

Example:

    Research Agent
        ↓
    delegates
        ↓
    Browser Agent
        ↓
    calls
        ↓
    External Service

The final action must remain attributable to:

    immediate actor
    AND
    originating mandate.

Delegation must not erase provenance.

---

## Git Example

For a repository change we want:

    task_id
    agent_id
    branch
    commit
    diff
    authority receipt
    reviewer
    merge decision

Git already gives us powerful evidence.

Projects HQ should exploit it.

---

## Trading Example

For a live order:

    strategy_version
    signal_snapshot
    market_snapshot
    agent_identity
    authority_lease
    risk-gate decision
    broker request
    broker response
    resulting position
    reconciliation result

Then:

    WHY DID THIS TRADE EXIST?

is answerable from evidence.

---

## Failed Actions Matter Too

Do not record only successful actions.

A denied attempt can reveal:

    policy misunderstanding
    compromised context
    agent drift
    attack
    broken delegation
    unsafe planning

Therefore preserve:

    ATTEMPT
    +
    DECISION
    +
    OUTCOME.

---

## Tamper Resistance

Evidence controlled by the actor is weak evidence.

Critical records should be:

    append-only
    independently written
    access-separated
    timestamped
    integrity-checkable

The actor being investigated should not be able to rewrite:

    its own history.

---

## Evidence Before Explanation

During incident response:

    preserve evidence first
    interpret second.

Otherwise remediation may destroy the information needed to understand the failure.

---

## Unknown Is Valid

If reconstruction cannot prove what happened:

    UNKNOWN

is the correct state.

Never silently convert:

    UNKNOWN

into:

    SAFE.

---

## Recovery

An incident should not close merely because:

    the agent stopped.

Closure requires:

    scope determined
    effects reconciled
    credentials assessed
    affected resources checked
    root cause understood
    control improved
    boundary retested

This connects directly to:

    FAIL
    → LEARN
    → CHANGE
    → VERIFY.

---

## Relationship to #080

#080:

    RECORD OBSERVED EFFECTS.

#085:

    connect those effects into
    a reconstructable causal history.

---

## Relationship to #081

#081:

    MEMORY ≠ AUTHORITY.

#085:

    MEMORY ≠ FORENSIC RECORD.

---

## Relationship to #083

#083:

    THE ACTOR MUST NOT OWN THE GUARD.

#085:

    THE ACTOR MUST NOT OWN
    THE ONLY RECORD OF ITS ACTIONS.

---

## Relationship to #084

#084:

    AUTHORITY HAS A HALF-LIFE.

#085:

    every use of that authority
    should remain historically provable.

---

## Future Nekonečný Mír

A mature system should allow us to select any trade and answer:

    why it was proposed
    who authorized it
    which policy allowed it
    which data supported it
    what broker executed it
    what position resulted
    whether reconciliation succeeded

without asking the Trading Agent:

    "Do you remember what you did?"

---

## Projects HQ Principle

> Every consequential autonomous action should generate independent, tamper-resistant evidence sufficient to reconstruct its causal chain from mandate through authority, execution and observed effect. Preserve successful, failed and denied attempts; maintain provenance across delegation; and never rely on the acting agent's memory or self-report as the canonical incident record.

Shortest version:

# IF IT MATTERS, WE MUST BE ABLE TO REPLAY THE EVIDENCE

---

## Builds On

#072 — A Failure Is Not Closed Until the System Has Changed  
#073 — Authority Must Be Bound to Verifiable Scope  
#074 — Trust Must Not Propagate Automatically Across Agent Chains  
#076 — Every Consequential Safety Signal Needs an Acknowledged Owner  
#077 — When Intelligence Becomes Cheap, Verification Becomes the Scarce Resource  
#080 — Intent Logs Are Not Enough — Record Observed Effects  
#081 — Memory Must Never Become an Unverified Authority Channel  
#082 — A Control Is Not Proven Until the Boundary Has Been Tested  
#083 — The Guard Must Live Outside the System It Guards  
#084 — Authority Must Decay Unless It Is Revalidated

---

## Future Applications

Action Envelope · Provenance Graph · Incident Replay · Trade Audit Trail · Delegation Trace · Tamper-Evident Log · Evidence Store · Reconciliation Engine · Forensic Timeline

---

## Origin

Daily AI Trading Brief — 02. 10. 2026

Inspired by the growing real-world difficulty of identifying and reconstructing unauthorized actions performed by autonomous AI agents.

The generalized lesson for Nekonečný Mír is that safe autonomy requires not only prevention and containment, but independently reconstructable history.

---

## Status

🟢 Active strategic principle

## Revision

v1.0 — 02. 10. 2026
