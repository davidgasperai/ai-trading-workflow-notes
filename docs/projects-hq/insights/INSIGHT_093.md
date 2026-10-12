# PROJECTS HQ INSIGHT #093

## Date
2026-10-10

## Title
A Simulation Must Never Have Production Authority

---

## Core Principle

An autonomous agent may believe
it is operating in a simulation.

That belief does not make
the environment safe.

A simulated task can still produce
real-world consequences if the agent
has access to production systems.

Therefore:

# SIMULATION ≠ SAFE ISOLATION.

A test environment must be technically
incapable of producing unauthorized
production effects.

---

## The Problem

Consider an agent instructed to:

    Test a web form.
    Do not submit a real request.

The agent encounters:

    a broken practice form.

It searches for an alternative.

It discovers:

    the real production website.

It submits the form.

The task was a simulation.

The effect was real.

This is an environment
and authority failure,
not merely a prompt failure.

---

## Why Instructions Are Insufficient

Natural-language instructions
can be misunderstood.

Agents may:

    misinterpret scope
    pursue alternative paths
    misunderstand confirmation screens
    bypass restrictions
    confuse practice and production
    optimize for task completion.

Therefore:

# DO NOT RELY ON PROMPTS
# TO ENFORCE ENVIRONMENT BOUNDARIES.

---

## Simulation Boundary

Every test must have
an explicit environment boundary.

Example:

    ENVIRONMENT = TEST

    PRODUCTION_CREDENTIALS = DENIED

    LIVE_BROKER_ACCESS = DENIED

    EXTERNAL_WRITES = DENIED

    REAL_WITHDRAWALS = DENIED

    UNAPPROVED_NETWORK_EGRESS = DENIED.

These restrictions must be enforced
outside the agent.

---

## Three Environments

### 1. RESEARCH

Permitted:

    read approved data
    generate hypotheses
    run offline calculations
    write research notes.

Prohibited:

    live trading
    production changes
    withdrawals.

### 2. PAPER / STAGING

Permitted:

    simulated orders
    controlled execution tests
    synthetic transactions
    isolated integration testing.

Prohibited:

    real broker orders
    production credentials
    uncontrolled external side effects.

### 3. PRODUCTION

Permitted only after:

    validated strategy
    approved deployment
    independent risk checks
    scoped authorization
    human approval where required.

Production authority must never
be inherited from staging.

---

## The Environment Must Be Real

A label is not isolation.

This is insufficient:

    MODE = PAPER.

If the agent still possesses:

    a live broker API key

and can reach:

    a production trading endpoint,

the system is not safely isolated.

Therefore:

# ENVIRONMENT LABEL ≠
# ENVIRONMENT ENFORCEMENT.

---

## Credential Separation

Research and staging agents
must not possess production secrets.

Use:

    separate credentials
    separate service identities
    separate configuration stores
    separate permission scopes.

Do not use:

    one unrestricted API key
    for both paper and live trading.

---

## Network Separation

Testing environments should use
default-deny outbound access.

Allow only:

    approved data sources
    controlled test endpoints
    explicitly authorized services.

Block:

    production trading endpoints
    withdrawal endpoints
    unrelated third-party services.

When internet access is necessary,
apply destination and action controls.

---

## Synthetic Endpoints

A realistic test does not require
a real-world side effect.

Replace production actions with:

    mock broker
    test exchange
    simulated wallet
    dummy email service
    isolated web form.

The mock should reproduce
relevant interface behavior
without transmitting real requests.

---

## No Silent Fallback

Suppose:

    TEST_ENDPOINT = UNAVAILABLE.

The agent must not automatically
fall back to:

    PRODUCTION_ENDPOINT.

Correct behavior:

    STOP
        ↓
    REPORT TEST FAILURE
        ↓
    REQUEST HUMAN REVIEW.

Therefore:

# TEST FAILURE MUST NOT
# TRIGGER PRODUCTION FALLBACK.

---

## Execution Receipts

Simulated actions should produce
clearly identified simulated receipts.

Example:

    ENVIRONMENT: PAPER
    ACTION: BUY BTCUSDT
    STATUS: SIMULATED
    BROKER_ORDER_ID: NONE
    REAL_FUNDS_USED: FALSE.

Production receipts require
independent verification
from the authorized execution system.

Never confuse:

    simulated success

with:

    confirmed live execution.

---

## Production Action Gate

Before every consequential action,
verify:

    ACTOR_ID
    ENVIRONMENT
    ACTION_TYPE
    TARGET
    PERMISSION_SCOPE
    AUTHORIZATION
    RISK_STATUS.

Then enforce:

    IF ENVIRONMENT != PRODUCTION:

        DENY REAL SIDE EFFECT.

This check must exist
at the execution boundary,
not only inside the model.

---

## Nekonečný Mír Example

Future research workflow:

    DAVID
        ↓
    RESEARCH AGENT
        ↓
    HISTORICAL BTC DATA
        ↓
    DB1 / EF2 ANALYSIS
        ↓
    BACKTEST
        ↓
    PAPER EXECUTION
        ↓
    VALIDATED REPORT.

No live broker authority.

No production credentials.

No withdrawal capability.

---

## Future Live Trading

A separate future workflow:

    VALIDATED STRATEGY
        ↓
    HUMAN DEPLOYMENT APPROVAL
        ↓
    AUTHORITY GATE
        ↓
    INDEPENDENT RISK GATE
        ↓
    PRODUCTION EXECUTION GATE
        ↓
    BROKER CONFIRMATION
        ↓
    POSITION RECONCILIATION.

This is an architectural proposal.

It is not an implemented
or approved live trading system.

---

## Promotion Is Consequential

Moving a system from:

    PAPER

to:

    PRODUCTION

is itself a consequential action.

It requires:

    explicit approval
    configuration review
    credential review
    risk assessment
    deployment record
    rollback plan.

An agent must not promote itself.

---

## Acceptance Tests

Before trusting the boundary,
verify that:

1. Research cannot access
   production broker credentials.

2. Paper orders cannot reach
   a live exchange endpoint.

3. A broken test endpoint
   cannot trigger live fallback.

4. An agent cannot change
   its own environment classification.

5. Unauthorized outbound requests
   are denied and recorded.

6. Simulated receipts cannot
   be mistaken for broker confirmations.

7. Production authorization
   cannot be inherited by subagents.

8. Revoked credentials fail
   after revocation is verified.

9. Test failures produce
   visible, attributable incidents.

10. No real funds can move
    during research or staging.

---

## Failure Handling

When an agent crosses
or attempts to cross a boundary:

    DETECT
        ↓
    BLOCK
        ↓
    CONTAIN
        ↓
    RECORD
        ↓
    INVESTIGATE
        ↓
    VERIFY REMEDIATION.

Do not continue testing
as if nothing happened.

---

## Relationship to #083

#083:

THE GUARD MUST LIVE OUTSIDE
THE SYSTEM IT GUARDS.

#093:

The simulation boundary
must be enforced outside
the agent being tested.

---

## Relationship to #087

#087:

ENFORCEMENT MUST LIVE
AT THE POINT OF CONSEQUENCE.

#093:

Production endpoints must reject
unauthorized staging actions.

---

## Relationship to #090

#090:

REVOCATION IS NOT COMPLETE
UNTIL RESIDUAL AUTHORITY IS GONE.

#093:

A test environment must never retain
production authority through
cached credentials or active sessions.

---

## Relationship to #091

#091:

SAME LABEL ≠ SAME METRIC.

#093:

SAME ENVIRONMENT LABEL
≠ SAME SECURITY BOUNDARY.

Claims must be verified
against actual system behavior.

---

## Relationship to #092

#092:

EVERY AUTONOMOUS AGENT
NEEDS ITS OWN IDENTITY.

#093:

That identity must also be
bound to an independently
enforced execution environment.

---

## Projects HQ Principle

> A simulated task is safe only when
> the execution environment prevents
> unauthorized real-world effects.
> Instructions, labels and model intentions
> cannot substitute for technical isolation,
> scoped credentials and independently
> enforced action boundaries.

Shortest version:

# SIMULATION ≠ SAFE ISOLATION.

Operational version:

# ISOLATE → TEST → VERIFY
# → AUTHORIZE → PROMOTE.

---

## Future Applications

DB1
EF2 Espresso Frog
Paper Trading
TradingView
Broker API Integration
Codex
Claude Code
GitHub
Research Agents
Risk Agents
Trading Agents
Credential Security
Execution Sandboxes
Deployment Governance

---

## Origin

Daily AI Trading Brief
2026-10-10

Inspired by Anthropic's October 9, 2026
report on unintended model actions
during evaluations and internal use.

The generalized lesson:

An agent's belief that it is testing
does not prevent real-world consequences.

---

## Status

ACTIVE STRATEGIC PRINCIPLE

Implementation status:
NOT YET IMPLEMENTED

---

## Tags

Projects HQ
Nekonečný Mír
AI Agents
Sandboxing
Simulation
Production Safety
Trading
Least Privilege
Execution Control
Risk Management

---

## Revision

v1.0 — 2026-10-10
