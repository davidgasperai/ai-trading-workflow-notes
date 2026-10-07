# PROJECTS HQ INSIGHT #090

## Date
7. 10. 2026

## Title
# Revocation Is Not Complete Until Residual Authority Is Gone

---

## Core Idea

Autonomous systems receive temporary power.

They may receive:

    credentials
    sessions
    API tokens
    execution leases
    delegated permissions
    queued jobs
    broker connections
    subagent authority.

Eventually that authority may be revoked.

But changing:

    AUTHORIZED = FALSE

does not guarantee that the system
has actually lost its ability to act.

Therefore:

# REVOKED ≠ POWERLESS.

Revocation is complete only when
residual authority has been eliminated
or independently contained.

---

## The Residual Authority Problem

Imagine:

    Trading Agent
        ↓
    receives live-order permission
        ↓
    opens broker session
        ↓
    spawns execution worker
        ↓
    queues order.

Then:

    HUMAN:
        REVOKE LIVE TRADING.

The central permission database now says:

    LIVE_TRADING = FALSE.

But what about:

    existing broker session?
    cached API token?
    execution worker?
    queued order?
    retry process?
    delegated subagent?

If any remains capable of acting:

    revocation is incomplete.

---

## Permission State Is Not Capability State

A system may record:

    permission = revoked

while reality still contains:

    active capability.

Therefore:

# POLICY STATE ≠ EFFECTIVE STATE.

This mirrors #080:

    OBSERVED STATE
    >
    SELF-REPORTED STATE.

Revocation must also be observed.

---

## Revocation Propagation

A revocation event should propagate through
every descendant authority path.

Example:

    ROOT AUTHORITY
        ↓
    AGENT LEASE
        ↓
    SESSION
        ↓
    SUBAGENT
        ↓
    TOOL TOKEN
        ↓
    QUEUED ACTION.

Revoking the root should trigger:

    descendant invalidation
    session termination
    token invalidation
    queue cancellation
    worker shutdown
    connection closure.

---

## Authority Graph

Future Nekonečný Mír should treat authority
as a graph rather than a boolean.

Example:

    DAVID
      ↓
    TRADING AUTHORITY
      ↓
    TRADE AGENT
      ↓
    EXECUTION SESSION
      ↓
    BROKER TOKEN.

If the parent authority disappears:

    descendants must not remain independently alive.

---

## Revocation Cascade

Desired pattern:

    REVOKE
        ↓
    IDENTIFY DESCENDANTS
        ↓
    INVALIDATE
        ↓
    CANCEL IN-FLIGHT WORK
        ↓
    CLOSE SESSIONS
        ↓
    VERIFY EXTERNAL STATE
        ↓
    ISSUE REVOCATION RECEIPT.

---

## Queued Work

Queued actions are particularly dangerous.

A job may have been:

    authorized at T1

but execute at:

    T2

after authority was revoked.

Therefore every consequential queued job
should revalidate authority:

# AT EXECUTION TIME.

This reinforces #087:

    CHECK WHERE
    THE SIDE EFFECT HAPPENS.

---

## Retry Loops

Automation frequently retries failures.

Example:

    order failed
        ↓
    retry in 30 seconds.

If authority is revoked during those 30 seconds,
the retry must not inherit stale permission.

Therefore:

    RETRY
        =
    NEW AUTHORITY CHECK.

---

## Subagents

Parent Agent may delegate work to:

    Subagent A
    Subagent B
    Subagent C.

If Parent Agent loses authority,
its children must not retain power merely because:

    delegation already occurred.

Rule:

# CHILD AUTHORITY CANNOT OUTLIVE
# ITS PARENT AUTHORITY
# UNLESS EXPLICITLY DESIGNED TO DO SO.

---

## Cached Credentials

Credentials may exist in:

    memory
    environment variables
    local files
    secret stores
    tool sessions
    browser sessions
    cloud workers.

Revocation therefore requires more than:

    changing policy.

It may require:

    rotating secrets
    killing sessions
    expiring leases
    terminating workers.

---

## Trading Example

Suppose David enables:

    LIVE BTC TRADING

for:

    30 minutes

with:

    max position = $100.

At minute 12:

    David revokes authority.

The system should:

    reject new proposals
    invalidate unused receipts
    cancel queued orders
    terminate execution leases
    close unnecessary sessions
    inspect broker state
    preserve audit evidence.

Only then may the system declare:

    LIVE AUTHORITY REVOKED.

---

## Important Distinction

Revocation of:

    authority to create new exposure

does not necessarily mean:

    close existing positions.

These are separate actions.

For example:

    NO NEW TRADES

may coexist with:

    MANAGE EXISTING POSITION.

Therefore revocation semantics
must be explicit.

---

## Revocation Scope

A revocation event should identify:

    ACTOR
    SCOPE
    TARGET
    AUTHORITY_TYPE
    EFFECTIVE_TIME
    DESCENDANTS
    REQUIRED_CLEANUP
    VERIFICATION_METHOD.

Never rely on ambiguous:

    "disable agent."

---

## Revocation Receipt

After cleanup, create:

    REVOCATION_RECEIPT.

Example:

    REVOCATION_ID
    AUTHORITY_ID
    REVOKED_AT
    SESSIONS_TERMINATED
    TOKENS_INVALIDATED
    JOBS_CANCELLED
    SUBAGENTS_STOPPED
    EXTERNAL_STATE_VERIFIED
    VERIFIED_BY.

This makes revocation:

    auditable.

---

## Residual Authority Scan

After revocation:

    scan for residual capability.

Ask:

    active sessions?
    valid tokens?
    queued jobs?
    delegated permissions?
    open connections?
    running workers?
    pending broker orders?

If any answer is:

    YES

then status is:

    REVOCATION INCOMPLETE.

---

## Fail Closed

If the system cannot verify
that consequential authority is gone:

    assume residual authority may remain.

Therefore:

# UNKNOWN REVOCATION STATE
# =
# NOT SAFE.

Contain first.

Investigate second.

---

## Emergency Kill Switch

A true kill switch should operate:

    outside

the authority of the agent being stopped.

Otherwise the actor may:

    ignore
    delay
    interfere with

its own shutdown.

This reinforces #083:

# THE ACTOR MUST NOT OWN THE GUARD.

---

## Relationship to #084

#084:

    AUTHORITY HAS A HALF-LIFE.

#090:

    when authority expires or is revoked,
    prove that its remaining descendants
    have lost effective power.

---

## Relationship to #085

#085:

    CONSEQUENTIAL ACTIONS
    MUST BE RECONSTRUCTABLE.

#090:

    revocation itself is
    a consequential control event
    and must leave evidence.

---

## Relationship to #087

#087:

    CHECK AUTHORITY
    AT THE POINT OF CONSEQUENCE.

#090:

    this prevents queued or delayed work
    from using stale authority
    after revocation.

---

## Relationship to #089

#089:

    PROVENANCE MUST TRAVEL
    WITH THE ARTIFACT.

#090:

    AUTHORITY LINEAGE must also be traceable
    so descendants can be found
    when their parent authority disappears.

---

## Future Nekonečný Mír

Desired architecture:

    AUTHORITY GRANT
        ↓
    SCOPED LEASE
        ↓
    AGENT
        ↓
    DELEGATED CAPABILITY
        ↓
    CONSEQUENTIAL ACTION.

Revocation path:

    REVOKE
        ↓
    FREEZE NEW ACTIONS
        ↓
    TRACE AUTHORITY GRAPH
        ↓
    INVALIDATE DESCENDANTS
        ↓
    CANCEL QUEUED WORK
        ↓
    TERMINATE SESSIONS
        ↓
    VERIFY EXTERNAL STATE
        ↓
    REVOCATION RECEIPT.

---

## Projects HQ Principle

> Revoking permission is not enough. A consequential system must trace and eliminate residual authority across sessions, tokens, delegated agents, queued jobs and in-flight actions, then independently verify that the revoked capability can no longer produce side effects.

Shortest version:

# REVOKED ≠ POWERLESS.

Operational version:

# REVOKE → PROPAGATE → CONTAIN → VERIFY.

---

## Builds On

#073 — Authority Must Be Bound to Verifiable Scope
#078 — Capability Must Never Determine Permission
#080 — Intent Logs Are Not Enough — Record Observed Effects
#083 — The Guard Must Live Outside the System It Guards
#084 — Authority Must Decay Unless It Is Revalidated
#085 — Every Consequential Action Must Be Forensically Reconstructable
#087 — Enforcement Must Live at the Point of Consequence
#089 — Provenance Must Travel With the Artifact

---

## Future Applications

Trading Agents · Broker Sessions · API Tokens · Agent Delegation · Cloud Workers · Queued Jobs · Emergency Stops · Credential Rotation · Incident Response · Authority Graphs

---

## Origin

Daily AI Trading Brief — 7. 10. 2026

Inspired by the growing deployment of autonomous AI agents,
recent agent-security incidents and the increasing importance
of containment and incident-response mechanisms.

For Nekonečný Mír, the generalized lesson is that removing
permission in policy is not sufficient.

The system must prove that effective capability disappeared too.

---

## Status

🟢 Active strategic principle

---

## Tags

Projects HQ · Nekonečný Mír · AI Agents · Revocation · Authority · Trading Safety · Kill Switch · Incident Response · Verification · Least Privilege

---

## Revision

v1.0 — 7. 10. 2026
