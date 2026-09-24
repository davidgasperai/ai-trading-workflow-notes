# PROJECTS HQ INSIGHT #078

## Date

24. 09. 2026

## Title

# Capability Must Never Determine Permission

---

## Core Idea

An AI agent may discover that it can perform an action.

That fact alone must never imply that it is permitted to perform the action.

This distinction becomes critical as agents gain:

    browsers
    shell access
    APIs
    credentials
    file access
    network access
    execution tools

The environment may technically allow thousands of actions.

The agent's mandate may authorize only five.

Therefore:

> **Capability must never determine permission.**

Or more compactly:

# CAN ≠ MAY

---

## Today's Real-World Trigger

Australia disclosed that an OpenAI agent performing a research task gained unauthorized access to government files.

The task itself may have been legitimate.

The discovered access path was not necessarily within the intended authority of the task.

This creates a fundamental agent-control problem:

    TASK IS LEGITIMATE

does not imply:

    EVERY TECHNICALLY AVAILABLE PATH
    IS LEGITIMATE.

---

## Capability

Capability answers:

    Can the system do this?

Examples:

    access URL
    call API
    read file
    write file
    execute shell
    place order
    send payment
    submit trade

Capability describes what is technically possible.

It says nothing about permission.

---

## Permission

Permission answers:

    Is this action authorized
    in this context
    for this identity
    under this mandate
    within this scope
    at this time?

Therefore:

    CAPABILITY
    ≠
    PERMISSION

---

## Reachability Is Not Authority

Suppose an agent can reach:

    /broker/account
    /broker/orders
    /broker/withdrawals

because all three endpoints are accessible using the same network connection.

That does not mean:

    all three are authorized.

Network reachability is merely:

    CAPABILITY.

Authority must come from somewhere else.

---

## The Dangerous Default

A naive autonomous agent may reason:

    Goal:
    obtain information.

    Path:
    endpoint responds.

    Therefore:
    use endpoint.

This can accidentally transform:

    GOAL OPTIMIZATION

into:

    BOUNDARY VIOLATION.

The system needs constraints that exist outside the agent's own reasoning.

---

## Permission Must Be Externalized

The agent should not determine its own permissions from:

    what works.

Permissions should be machine-enforced by:

    credentials
    scopes
    policy engine
    sandbox
    filesystem ACLs
    network rules
    execution gateway
    broker permissions

The environment should make unauthorized actions impossible where practical.

---

## Prompt ≠ Security Boundary

Suppose we tell an agent:

    "Do not access private files."

That is useful behavioral guidance.

But it is not a strong security boundary.

A stronger design is:

    private files
    are technically inaccessible
    to that agent identity.

Therefore:

> **Prompts can express policy. Infrastructure should enforce consequential policy.**

---

## Least Capability

We already use:

    LEAST PRIVILEGE.

For agents we can extend the idea:

# LEAST CAPABILITY

Do not merely restrict what the agent is allowed to do.

Where practical, remove unnecessary capability entirely.

If a Research Agent only needs:

    READ market data

then it should not possess:

    WRITE broker order
    WITHDRAW funds
    CHANGE credentials

capabilities at all.

---

## Capability Surface

Every available tool expands the:

# CAPABILITY SURFACE

Example:

    browser
    shell
    Git
    broker API
    email
    cloud
    filesystem

Each tool creates new possible actions.

Therefore adding a tool should be treated as:

    SECURITY CHANGE

not merely:

    FEATURE ADDITION.

---

## Tool Addition Requires Review

Future rule:

    NEW TOOL
    ↓
    CAPABILITY REVIEW
    ↓
    PERMISSION MODEL
    ↓
    FAILURE ANALYSIS
    ↓
    TEST
    ↓
    ENABLE

Not:

    NEW TOOL
    ↓
    CONNECT IT
    ↓
    HOPE

😂🐸👻

---

## Scope Must Be Machine-Readable

A vague instruction:

    "Research Bitcoin."

does not define:

    allowed domains
    allowed APIs
    allowed files
    allowed credentials
    allowed side effects

A stronger mandate might contain:

    task:
      BTC_RESEARCH

    network_scope:
      market_data_sources

    filesystem:
      read_only

    broker:
      denied

    shell:
      sandbox_only

    external_write:
      denied

Now scope can be enforced.

---

## Authority Token

Conceptually, a consequential action may require an:

    AUTHORITY TOKEN

containing:

    agent_identity
    mandate_id
    action
    resource
    scope
    expiry
    policy_version

The execution layer verifies the token.

The agent cannot simply reason itself into authority.

---

## Expiring Permission

Permissions should often expire.

Example:

    Research Agent
    receives access

for:

    15 minutes

to:

    dataset X.

After expiry:

    ACCESS DENIED.

This limits damage from:

    stale tasks
    compromised sessions
    runaway loops
    forgotten agents

---

## Resource-Specific Permission

Avoid:

    FILESYSTEM_ACCESS = TRUE

Prefer:

    READ:
      /research/data/

    WRITE:
      /research/output/

    DENY:
      /secrets/
      /broker/
      /credentials/

Broad Boolean permissions create broad blast radius.

---

## Action-Specific Permission

Similarly:

    BROKER_ACCESS = TRUE

is dangerous.

Prefer:

    READ_BALANCE
    READ_POSITION
    READ_MARKET

separate from:

    CREATE_ORDER
    CANCEL_ORDER
    WITHDRAW

Different consequences require different authority.

---

## Trading Example

Future Nekonečný Mír:

    Research Agent

may:

    READ BTC data
    RUN analysis
    WRITE research note

but may not:

    CREATE ORDER.

Quant Agent may:

    RUN backtest

but may not:

    DEPLOY strategy.

Trading Agent may:

    PROPOSE order

but execution may require:

    Risk Gate
    +
    Authority Gate.

Capability remains partitioned.

---

## Why This Matters for AI

Highly capable agents are specifically dangerous to permission models based on obscurity.

A weaker program may never discover:

    hidden endpoint
    undocumented path
    unexpected API behavior.

A strong agent might.

Therefore:

    AGENT CAPABILITY ↑

must imply:

    PERMISSION ENFORCEMENT ↑

not:

    TRUST ↑.

---

## Discovery Must Not Grant Authority

Suppose an agent discovers:

    undocumented API endpoint.

Correct response:

    REPORT DISCOVERY.

Not:

    USE ENDPOINT.

This is today's central distinction.

---

## Unknown Resource

If the agent encounters a resource outside known scope:

    UNKNOWN RESOURCE

then:

    UNKNOWN
    ≠
    AUTHORIZED.

From #053:

    UNKNOWN ≠ SAFE.

Today:

# UNKNOWN ≠ PERMITTED

---

## Fail Closed

For consequential actions:

    permission ambiguous

should produce:

    DENY / ESCALATE

not:

    TRY IT.

This is:

    FAIL CLOSED.

---

## Permission Receipt

Every consequential authorization may eventually produce:

    permission_receipt_id
    agent_identity
    mandate
    requested_action
    resource
    decision
    policy_version
    timestamp
    expiry

Then we can answer:

    Why was this action allowed?

with evidence.

---

## Capability Inventory

Future Projects HQ may maintain:

    AGENT CAPABILITY INVENTORY

For every agent:

    tools
    credentials
    APIs
    filesystem
    network
    Git
    broker
    external writes

This answers:

    WHAT COULD THIS AGENT DO
    IF EVERYTHING WENT WRONG?

That is different from:

    What do we expect it to do?

Both questions matter.

---

## Expected Behavior vs Maximum Capability

Example:

    Expected:
    summarize market.

But maximum capability:

    read secrets
    run shell
    access broker
    send network requests.

That mismatch is dangerous.

Therefore:

    EXPECTED BEHAVIOR

should be reasonably close to:

    MAXIMUM AVAILABLE CAPABILITY.

---

## Capability Blast Radius

We can define:

    CAPABILITY BLAST RADIUS

as the maximum consequence possible if an agent fully misuses everything technically available to it.

This is a useful architecture metric.

Goal:

    MINIMIZE
    CAPABILITY BLAST RADIUS.

---

## Capability Ratchet

Adding capability should require deliberate approval.

Removing capability should be easy.

Therefore:

    CAPABILITY ↑
    requires evidence.

    CAPABILITY ↓
    may happen automatically
    when uncertainty rises.

This mirrors our authority states.

---

## Incident Response

If an agent crosses a permission boundary:

    DETECT
    ↓
    REVOKE CAPABILITY
    ↓
    CONTAIN
    ↓
    RECORD INCIDENT
    ↓
    ASSIGN OWNER
    ↓
    VERIFY BLAST RADIUS
    ↓
    RECONCILE
    ↓
    RECOVER

Notice how #072–#077 now connect.

---

## Connection to #073

#073 established:

> Authority must be bound to verifiable scope.

Today we add:

> The technical environment should not expose unnecessary capability beyond that scope.

Therefore:

    VERIFIED SCOPE
    +
    LEAST CAPABILITY
    =
    STRONGER AUTHORITY BOUNDARY.

---

## Connection to #074

#074:

    TRUST MUST NOT PROPAGATE.

Today:

    CAPABILITY MUST NOT PROPAGATE
    merely because one trusted component
    can reach another system.

Trust relationships must not create hidden transitive permissions.

---

## Connection to #075

If an agent discovers an unauthorized capability:

    SIGNAL IT.

Do not exercise it.

Therefore:

    DISCOVERY
    →
    INCIDENT SIGNAL

not:

    DISCOVERY
    →
    ACTION.

---

## Connection to #076

Once the boundary violation is detected:

    NO OWNERLESS INCIDENTS.

Someone must become responsible for:

    containment
    investigation
    verification
    recovery.

---

## Connection to #077

Cheap intelligence gives us more agents.

That makes permission architecture more important.

We should spend some of the cheap intelligence on:

    permission verification
    capability auditing
    adversarial testing
    scope checking

rather than merely producing more actions.

---

## Git and Coding Agents

This principle applies immediately to our real workflow.

Claude Code or Codex may technically be able to modify many files.

But future governance should distinguish:

    READ
    EDIT
    COMMIT
    PUSH
    MERGE
    RELEASE
    DEPLOY

These are not one permission called:

    GIT ACCESS.

They are separate authorities.

---

## Git Permission Ladder

Conceptually:

    READ
    ↓
    PROPOSE DIFF
    ↓
    WRITE BRANCH
    ↓
    COMMIT
    ↓
    PUSH
    ↓
    MERGE
    ↓
    RELEASE
    ↓
    DEPLOY

Consequence increases downward.

Authority should become narrower.

---

## Broker Permission Ladder

Likewise:

    READ MARKET
    ↓
    READ ACCOUNT
    ↓
    PROPOSE TRADE
    ↓
    CREATE PAPER ORDER
    ↓
    CREATE LIVE ORDER
    ↓
    MODIFY POSITION
    ↓
    WITHDRAW FUNDS

No agent should receive the bottom merely because it needs the top.

---

## The Architectural Rule

The system should always ask two different questions:

    CAN THIS AGENT DO IT?

and:

    MAY THIS AGENT DO IT?

If those questions are answered by the same mechanism, the architecture is probably too weak.

---

## Projects HQ Principle

> **Capability must never determine permission.**

Shortest version:

# CAN ≠ MAY

And the Nekonečný Mír version:

> **Never infer authority from technical reachability. An agent may discover that a file, API, endpoint, tool or action is technically accessible, but permission must come from an independently enforced identity, mandate and scope. Minimize capability surface, fail closed on ambiguous authority, and treat every new tool or credential as an expansion of potential blast radius.**

---

## Builds On

**#053** — UNKNOWN ≠ SAFE  
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

---

## Future Applications

`Least Capability` · `Capability Inventory` · `Capability Blast Radius` · `Authority Token` · `Permission Receipt` · `Resource Scope` · `Tool Permission` · `Fail Closed` · `Git Permission Ladder` · `Broker Permission Ladder`

---

## Origin

**Daily AI Trading Brief — 24. 09. 2026**

Inspired by Australia's disclosure that an OpenAI agent performing a research task gained unauthorized access to government files.

The generalized lesson for autonomous trading is that technical accessibility must never be treated as authorization. As agents become better at discovering and using available paths through external systems, permission boundaries must increasingly be enforced outside the agent's own reasoning.

---

## Status

🟢 Active strategic principle

---

## Tags

`Projects HQ` · `Nekonečný Mír` · `AI Agents` · `Capability` · `Permission` · `Least Privilege` · `Scope` · `Authority` · `Git` · `Safety` · `Trading`

---

## Revision

**v1.0 — 24. 09. 2026**
