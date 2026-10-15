# PROJECTS HQ INSIGHT #098

## Date
2026-10-15

## Title
An Approval Must Bind to the Exact Action

---

## Core Principle

Human approval is not
an unlimited authorization.

Approving an intention
does not automatically approve
every action an autonomous agent
might take to achieve it.

Therefore:

# APPROVED INTENT
# ≠ APPROVED EXECUTION.

Consequential actions must be
bound to specific, verifiable
approval conditions.

---

## The Problem

Suppose a Trading Agent requests:

    BUY BTC

    MAX NOTIONAL = 100 USD

    MARKET = BTCUSDT

    VENUE = APPROVED EXCHANGE

    ACCOUNT = PAPER TRADING.

A human approves.

The agent subsequently changes:

    MAX NOTIONAL = 150 USD.

The original approval
must no longer authorize
the modified transaction.

The same applies if the agent
changes the account,
venue, instrument,
order type, or leverage.

---

## Approval Is a Bounded Permission

An approval should specify
exactly what it permits.

It should not be interpreted as:

    permission to improvise

    permission to increase risk

    permission to change accounts

    permission to change assets

    permission to repeat actions

    permission to bypass controls.

An agent must not expand
the meaning of an approval.

---

## Proposed Approval Object

Each consequential approval
should contain:

    APPROVAL_ID

    REQUESTING_AGENT_ID

    APPROVER_ID

    ACTION_TYPE

    TARGET_ACCOUNT

    TARGET_ENVIRONMENT

    TARGET_VENUE

    TARGET_INSTRUMENT

    ALLOWED_ORDER_TYPE

    MAX_NOTIONAL

    MAX_QUANTITY

    LEVERAGE_LIMIT

    PRICE_CONSTRAINTS

    EXPIRATION_TIME

    MAX_EXECUTIONS

    POLICY_VERSION

    ACTION_PAYLOAD_HASH.

The exact required fields
depend on the action category.

---

## Immutable Action Binding

The proposed action
should be converted
into a canonical representation.

Example:

    ACTION_PAYLOAD =
    {
        "environment": "paper",
        "account": "research_01",
        "venue": "approved_exchange",
        "symbol": "BTCUSDT",
        "side": "BUY",
        "order_type": "LIMIT",
        "max_notional_usd": 100,
        "leverage": 1
    }

A cryptographic digest
of the canonical payload
is then associated
with the approval.

The digest must use
a documented canonicalization
and serialization method.

Changing any material field
invalidates the approval
unless the change is explicitly
allowed by the approved policy.

---

## Exact Values and Bounded Values

Not every approval
must authorize one exact price.

Some approvals may contain
explicitly bounded flexibility.

For example:

    MAX_NOTIONAL = 100 USD

    MAX_SLIPPAGE = 0.10%

    EXPIRATION = 60 SECONDS.

The important requirement
is that all permitted variation
is defined before approval.

An agent cannot invent
new tolerances afterward.

---

## Time-Bounded Authority

Approvals must expire.

Example:

    APPROVED_AT = T0

    EXPIRES_AT = T0 + 60 SECONDS.

After expiration:

    EXECUTION = DENIED.

An expired approval
must not be revived
by restarting the agent.

---

## Single-Use Authorization

For high-risk actions,
the default should be
single-use approval.

Example:

    MAX_EXECUTIONS = 1.

The execution gate
must atomically consume
the approval before or as part
of authorizing the action.

Concurrent requests
must not consume
the same approval twice.

---

## Approval Cannot Bypass Risk Limits

Human approval
does not replace
independent risk controls.

A valid approval
must still pass:

    RISK GATE

    BUDGET GATE

    AUTHORITY GATE

    ENVIRONMENT CHECK

    EXECUTION POLICY.

If any required gate rejects:

    EXECUTION = DENIED.

Approval grants permission
within policy.

It does not override policy.

---

## Separation of Duties

The requesting agent
must not approve
its own consequential action.

The approval service
must be independent
of the requesting agent.

The execution service
must independently validate
the approval.

The agent must not be able
to modify the approval record.

---

## Approval Workflow

Proposed architecture:

    RESEARCH AGENT
          |
          v
    TRADING AGENT
          |
          v
    ACTION PROPOSAL
          |
          v
    INDEPENDENT RISK CHECK
          |
          v
    HUMAN APPROVAL
          |
          v
    IMMUTABLE APPROVAL RECORD
          |
          v
    EXECUTION-TIME VALIDATION
          |
          v
    ATOMIC AUTHORIZATION
          |
          v
    EXECUTION SERVICE.

No individual agent
controls the entire chain.

---

## Execution-Time Validation

Immediately before execution,
the independent gate verifies:

1. Approval exists.

2. Approval is authentic.

3. Approval has not expired.

4. Approval has not been revoked.

5. Approval belongs
   to the correct agent.

6. The requested action
   matches the approved scope.

7. The target environment
   is correct.

8. Risk and budget limits
   remain satisfied.

9. The approval has not
   already been consumed.

10. The action remains permitted
    under the current policy.

Any failed check:

    DENY EXECUTION.

---

## Time-of-Check / Time-of-Use Risk

Conditions may change
between approval
and execution.

Examples:

    account balance changes

    another position opens

    liquidity deteriorates

    risk budget is consumed

    credentials are revoked

    policy changes.

Therefore:

# APPROVAL-TIME VALIDITY
# ≠ EXECUTION-TIME VALIDITY.

The execution gate
must revalidate
all dynamic constraints.

---

## No Approval Laundering

An agent must not transform
a denied or expired action
into a permitted one
through superficial changes.

Examples:

    splitting one order
    into many smaller orders

    switching agent identities

    changing the action label

    routing through another tool

    reusing an earlier approval.

The system must evaluate
the effective consequence,
not merely the submitted label.

---

## Revocation

Every unconsumed approval
must support revocation.

Revocation should invalidate
all future execution attempts.

If an action has already
been sent externally,
revocation cannot be assumed
to undo that action.

External state reconciliation
may be required.

---

## Unknown Execution State

If an approved action
is submitted but its outcome
cannot be confirmed:

    ACTION_STATE = UNKNOWN.

The approval must not
automatically become reusable.

The system must reconcile
external state before
any further execution.

---

## Human Approval Interface

A future approval interface
should clearly display:

    WHAT WILL HAPPEN

    WHICH ACCOUNT IS AFFECTED

    MAXIMUM FINANCIAL EXPOSURE

    EXPIRATION TIME

    IMPORTANT RISK LIMITS

    WHETHER THE ACTION
    CAN BE REPEATED.

The interface must not hide
material conditions
inside vague summaries.

---

## Audit Evidence

Every approval should produce:

    APPROVAL_ID

    PROPOSAL_ID

    ACTION_PAYLOAD_HASH

    APPROVER_ID

    APPROVAL_TIMESTAMP

    EXPIRATION_TIMESTAMP

    POLICY_VERSION

    VALIDATION_RESULT

    EXECUTION_ID

    FINAL_EXTERNAL_OUTCOME.

The record should permit
independent reconstruction
of the authorized action.

---

## Acceptance Tests

1. Increasing the approved
   order size is rejected.

2. Changing the instrument
   is rejected.

3. Changing from paper trading
   to live trading is rejected.

4. Changing the target account
   is rejected.

5. Expired approval is rejected.

6. Revoked approval is rejected.

7. A single-use approval
   cannot be consumed twice.

8. Concurrent execution attempts
   cannot bypass consumption.

9. A valid approval
   cannot bypass risk limits.

10. The requesting agent
    cannot approve itself.

11. Changed market conditions
    trigger fresh risk checks.

12. An unknown execution state
    cannot trigger blind reuse.

13. A system restart
    does not restore
    expired authority.

14. The approval record
    can be independently audited.

15. No live trading authority
    exists without explicit
    production authorization.

---

## Relationship to #085

#085:

Every consequential action
must be forensically
reconstructable.

#098:

Every consequential approval
must be reconstructable
and bound to the action
that was actually executed.

---

## Relationship to #087

#087:

Enforcement must live
at the point of consequence.

#098:

Approval validation
must occur at the independent
execution boundary.

---

## Relationship to #090

#090:

Revocation is not complete
until residual authority is gone.

#098:

Revoked approvals
must lose execution authority
immediately.

---

## Relationship to #095

#095:

Small actions must be governed
by aggregate exposure.

#098:

Approval of one action
must not authorize
unbounded repetition
or transaction splitting.

---

## Relationship to #097

#097:

A kill switch
is not a recovery plan.

#098:

Restarting after recovery
must not silently restore
expired or consumed approvals.

---

## Projects HQ Principle

> Human approval must authorize
> a clearly defined action
> within explicit limits.
>
> An autonomous agent
> must not expand,
> reinterpret,
> repeat,
> or silently modify
> that authorization.
>
> Independent execution controls
> must verify that the action
> remains permitted
> at the moment of consequence.

---

## Shortest Version

# APPROVED INTENT
# ≠ APPROVED EXECUTION.

---

## Operational Formula

# PROPOSE
    ↓
# DEFINE LIMITS
    ↓
# VALIDATE RISK
    ↓
# APPROVE
    ↓
# BIND AUTHORIZATION
    ↓
# REVALIDATE
    ↓
# EXECUTE ONCE
    ↓
# VERIFY OUTCOME
    ↓
# AUDIT.

---

## Future Applications

Nekonečný Mír
DB1
EF2 Espresso Frog
Research Agents
Trading Agents
Risk Gate
Authority Gate
Budget Gate
Human Approval Interface
Exchange APIs
Order Management
Credential Management
Audit Infrastructure
Agent Governance

---

## Origin

Daily AI Trading Brief
2026-10-15

Inspired by the Financial
Stability Board's final
Sound Practices for Responsible
Adoption of Artificial Intelligence.

Published:
2026-10-15

The broader architectural lesson:

Human oversight is meaningful
only when approval is specific,
independent, time-bounded,
and technically enforceable.

---

## Status

ACTIVE STRATEGIC PRINCIPLE

Implementation status:
NOT YET IMPLEMENTED

No live trading authority granted.

No automatic execution
authorization granted.

---

## Revision

v1.0 — 2026-10-15
