# PROJECTS HQ INSIGHT #092

## Date
9. 10. 2026

## Title
# Every Autonomous Agent Needs Its Own Identity

---

## Core Idea

Autonomous agents increasingly act
inside real software systems.

They can:

    access repositories
    read documents
    modify code
    execute tools
    create files
    communicate with services
    submit transactions.

But when an agent acts,
the system must distinguish:

    WHO OWNS THE SYSTEM

from:

    WHO PERFORMED THE ACTION.

Therefore:

# AGENT IDENTITY ≠ HUMAN IDENTITY.

An autonomous agent should have
a distinct, verifiable identity
and explicitly delegated authority.

---

## The Borrowed Identity Problem

Imagine:

    DAVID
        ↓
    grants access to GitHub
        ↓
    CODING AGENT
        ↓
    modifies repository.

If the agent uses David's
unrestricted personal credentials,
the platform may record:

    DAVID MODIFIED THE REPOSITORY.

But the actual actor was:

    CODING AGENT.

The action occurred under
a borrowed identity.

This creates problems for:

    accountability
    auditing
    incident response
    permission management
    revocation
    forensic reconstruction.

---

## Ownership vs Execution

David is:

    PROJECT OWNER.

Coding Agent is:

    EXECUTION ACTOR.

Risk Agent is:

    RISK EVALUATOR.

Trading Agent is:

    STRATEGY ACTOR.

Execution Gateway is:

    CONTROLLED ACTION INTERFACE.

These roles must not collapse
into one unrestricted identity.

---

## Identity Is Not Authority

Knowing an agent's identity
does not mean the agent
has permission to act.

Therefore:

    IDENTITY
        =
    WHO IS ACTING?

    AUTHORITY
        =
    WHAT MAY THEY DO?

    PROVENANCE
        =
    WHERE DID THE OUTPUT COME FROM?

    AUDIT
        =
    WHAT ACTUALLY HAPPENED?

These are related,
but separate concepts.

---

## Agent Identity Record

Each persistent agent should have:

    AGENT_ID
    AGENT_NAME
    OWNER
    ROLE
    PURPOSE
    ENVIRONMENT
    CREDENTIAL_REFERENCE
    ALLOWED_RESOURCES
    PERMISSION_SCOPE
    CREATED_AT
    EXPIRES_AT
    STATUS.

Credentials must be stored securely,
not embedded in the record.

---

## Human Ownership

Every autonomous agent
must have an accountable owner.

For Nekonečný Mír:

    OWNER = DAVID.

The owner defines:

    objectives
    acceptable risk
    permission boundaries
    deployment decisions
    emergency controls.

The agent cannot redefine
its own authority.

---

## Dedicated Credentials

Where the platform supports it,
agents should use:

    dedicated service identities
    scoped application credentials
    short-lived tokens
    restricted OAuth grants.

Avoid:

    shared passwords
    unrestricted personal tokens
    permanent administrator access.

Credentials should follow:

# LEAST PRIVILEGE.

---

## GitHub Example

Future GitHub integration:

    DAVID
        ↓
    approves application access
        ↓
    CODING AGENT
        ↓
    permitted repository
        ↓
    feature branch
        ↓
    proposed changes
        ↓
    tests
        ↓
    human review
        ↓
    merge.

The agent should not automatically
receive permission to:

    modify every repository
    change security settings
    read unrelated secrets
    bypass protected branches.

---

## Important Limitation

Not every external service
supports separate agent identities.

When dedicated identity
is unavailable:

    use narrowly scoped delegation
    preserve agent attribution
    log the initiating principal
    enforce permissions externally.

Do not claim true identity separation
when the platform cannot provide it.

---

## Trading Example

Research Agent may:

    read historical market data
    generate research reports
    evaluate hypotheses.

It may not:

    place live orders.

Risk Agent may:

    inspect trade proposals
    calculate exposure
    reject unsafe requests.

It may not:

    secretly authorize itself
    to execute orders.

Trading Agent may:

    generate trade proposals.

Live execution requires:

    validated strategy
    independent risk checks
    explicit human authorization
    scoped execution permission.

---

## Identity Propagation

When Agent A delegates
a task to Agent B,
the system should preserve:

    ORIGINAL_OWNER
    DELEGATING_AGENT
    EXECUTING_AGENT
    TASK_ID
    AUTHORITY_SCOPE.

This creates an accountable
delegation chain.

---

## Subagents

Temporary subagents should not
automatically inherit
all parent permissions.

Example:

    RESEARCH AGENT
        ↓
    NEWS SUBAGENT.

The subagent needs:

    news access.

It does not need:

    broker credentials
    GitHub write access
    payment permissions.

Delegation should grant
only the capability required.

---

## Identity and Provenance

From #089:

    PROVENANCE MUST TRAVEL
    WITH THE ARTIFACT.

#092 adds:

    the creator identity
    must be independently
    attributable.

An artifact should identify:

    creator_agent_id
    owner_id
    parent_task_id
    execution_context
    authorization_reference.

---

## Identity and Revocation

From #090:

    REVOKED ≠ POWERLESS.

Dedicated agent identities
make revocation more precise.

Instead of disabling
David's entire account,
the system can revoke:

    one agent
    one credential
    one session
    one delegated capability.

Then verify that the agent
has lost effective access.

---

## Identity and Audit

An audit record should answer:

    Who requested the action?

    Which agent executed it?

    Which credentials were used?

    What permission authorized it?

    What external effect occurred?

    Was the action verified?

A single generic account
cannot always answer
these questions reliably.

---

## No Self-Issued Authority

An agent must not be able
to grant itself additional access.

For example:

    RESEARCH AGENT
        requests broker permission.

The system must require:

    external authorization.

Not:

    agent self-approval.

This reinforces:

# THE ACTOR MUST NOT OWN THE GUARD.

---

## Identity Lifecycle

Every agent identity
needs a lifecycle.

    CREATE
        ↓
    REGISTER
        ↓
    ASSIGN ROLE
        ↓
    GRANT LIMITED ACCESS
        ↓
    EXECUTE
        ↓
    MONITOR
        ↓
    REVALIDATE
        ↓
    REVOKE
        ↓
    VERIFY TERMINATION.

Identity management
must continue throughout
the agent's existence.

---

## Credential Exposure

If an agent credential
is accidentally exposed:

    revoke the credential
    investigate possible misuse
    issue a replacement
    verify the old credential fails
    preserve incident evidence.

Do not merely:

    delete the visible secret.

Once exposed,
the credential may already
have been copied.

---

## Future Nekonečný Mír

Proposed architecture:

    DAVID
      |
      | ownership
      v
    AUTHORITY MANAGER
      |
      | scoped delegation
      v
    AGENT IDENTITY REGISTRY
      |
      +---- RESEARCH AGENT
      |
      +---- CODING AGENT
      |
      +---- RISK AGENT
      |
      +---- TRADING AGENT
      |
      v
    EXTERNAL ENFORCEMENT GATES
      |
      v
    VERIFIED ACTIONS.

Each agent has:

    separate identity
    defined purpose
    minimum permissions
    attributable actions.

---

## Implementation Priority

Phase 1:

    document agent roles
    identify external resources
    map required permissions.

Phase 2:

    introduce scoped credentials
    separate development environments
    implement audit records.

Phase 3:

    automate permission validation
    introduce identity lifecycle controls
    test revocation.

Phase 4:

    evaluate production readiness
    before consequential autonomy.

---

## Acceptance Tests

A future implementation
should demonstrate:

    Agent A cannot access
    Agent B's private resources.

    Agent A cannot increase
    its own permissions.

    Agent actions can be
    attributed independently.

    Revoking Agent A does not
    disable unrelated agents.

    Revoked credentials cannot
    authorize new actions.

    Audit records preserve
    the delegation chain.

---

## Relationship to #083

#083:

    THE GUARD MUST LIVE
    OUTSIDE THE SYSTEM IT GUARDS.

#092:

    identity and permission controls
    must not be controlled
    solely by the agent.

---

## Relationship to #087

#087:

    ENFORCEMENT MUST LIVE
    AT THE POINT OF CONSEQUENCE.

#092:

    the enforcement gate
    must verify the identity
    of the actor requesting action.

---

## Relationship to #089

#089:

    PROVENANCE MUST TRAVEL
    WITH THE ARTIFACT.

#092:

    provenance should include
    verifiable actor identity.

---

## Relationship to #090

#090:

    REVOCATION IS NOT COMPLETE
    UNTIL RESIDUAL AUTHORITY IS GONE.

#092:

    separate identities allow
    targeted revocation
    and independent verification.

---

## Projects HQ Principle

> Autonomous agents should operate under
> distinct, verifiable identities rather
> than unrestricted human credentials.
> Every agent must have an accountable
> owner, defined purpose, limited permissions,
> attributable actions and a revocable
> authority lifecycle.

Shortest version:

# AGENT IDENTITY ≠ HUMAN IDENTITY.

Operational version:

# IDENTIFY → DELEGATE → EXECUTE
# → ATTRIBUTE → VERIFY → REVOKE.

---

## Future Applications

GitHub Integration
Codex
Claude Code
Research Agents
Risk Agents
Trading Agents
API Security
Credential Management
Multi-Agent Systems
Audit Trails
Incident Response
Authority Governance

---

## Origin

Daily AI Trading Brief — 9. 10. 2026

Inspired by Google's October 8 announcement
of autonomous coworker agents with
dedicated identities and permissions.

The generalized lesson for Nekonečný Mír:

Autonomy becomes safer when every actor
has a distinct identity and only the
authority required for its task.

---

## Status

Active strategic principle.

Not yet implemented.

---

## Tags

Projects HQ
Nekonečný Mír
AI Agents
Identity
Authentication
Authorization
Least Privilege
GitHub
Trading Safety
Governance

---

## Revision

v1.0 — 9. 10. 2026
