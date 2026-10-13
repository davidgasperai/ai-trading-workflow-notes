# PROJECTS HQ INSIGHT #096

## Date
2026-10-13

## Title
A Known Event Is Not a Known Outcome

---

## Core Principle

A scheduled event may be known
well before it occurs.

Its actual outcome
is not yet known.

A trading system must never
confuse these two information states.

Therefore:

# KNOWN EVENT ≠ KNOWN OUTCOME.

A research system must preserve
the difference between:

    what was scheduled

    what was expected

    what actually happened

    what the market did afterward.

---

## The Problem

Suppose an AI agent knows:

    US CPI RELEASE:
    October 14, 2026.

It also knows:

    MARKET EXPECTATION:
    Inflation around 3.6–3.7%.

The agent does not know:

    ACTUAL CPI RESULT.

Nor does it know:

    BTC PRICE REACTION.

A forecast must not be treated
as an observed outcome.

---

## Example: Token Unlock

Suppose:

    TOKEN = ARB

    EVENT = TOKEN UNLOCK

    DATE = 2026-10-16

    EXPECTED QUANTITY =
    92.65 MILLION ARB.

The event schedule is known.

But the system does not know:

    how many tokens will be sold

    when holders will act

    which venues will receive tokens

    how liquidity will respond

    how the market will price the event.

Therefore:

# TOKEN UNLOCK
# ≠ AUTOMATIC SELL SIGNAL.

---

## Event Information States

Every event should have
an explicit information state.

### SCHEDULED

The event is expected
to occur in the future.

### EXPECTED

A forecast or estimate exists.

### RELEASED

The official outcome
has been published.

### VERIFIED

The outcome has been checked
against an authoritative source.

### REVISED

Previously published information
has been corrected or updated.

### CANCELLED

The event will not occur
as originally scheduled.

### UNRESOLVED

The available evidence
is incomplete or contradictory.

---

## Required Event Record

Each tracked event should include:

    EVENT_ID

    EVENT_TYPE

    ASSET_SCOPE

    SCHEDULED_AT

    TIMEZONE

    SOURCE

    SOURCE_PUBLISHED_AT

    EXPECTED_VALUE

    ACTUAL_VALUE

    INFORMATION_STATE

    LAST_VERIFIED_AT

    REVISION_STATUS.

The system must distinguish
event metadata from market data.

---

## Point-in-Time Integrity

Historical research must use
only information that was available
at the simulated decision time.

Example:

    BACKTEST_TIME =
    2026-10-13.

The strategy may know:

    CPI is scheduled tomorrow.

It must not know:

    tomorrow's actual CPI result.

Using future information
would invalidate the test.

---

## Look-Ahead Bias

Look-ahead bias occurs when
a historical strategy uses
information unavailable
at the time of the decision.

Examples:

    future economic releases

    revised historical data

    later token unlock changes

    future order-book information

    post-event price reactions.

The research system must prevent
future information from silently
entering historical decisions.

---

## Expectations Are Not Facts

An analyst estimate
is a forecast.

A consensus estimate
is an aggregation of forecasts.

Neither is an observed result.

Store separately:

    CONSENSUS_FORECAST

    OFFICIAL_RESULT

    MARKET_REACTION.

Never overwrite the original
forecast with the later result.

---

## Event Calendar

A future Nekonečný Mír
research calendar may track:

    CPI

    central bank decisions

    employment reports

    token unlocks

    protocol upgrades

    governance votes

    exchange maintenance

    major market closures.

Events must have
verified timestamps
and explicit timezones.

---

## Event Risk Classification

A scheduled event
may receive a provisional
risk classification.

Example:

    LOW

    MEDIUM

    HIGH

    UNRESOLVED.

Classification should consider:

    historical volatility

    market liquidity

    asset exposure

    event uncertainty

    execution sensitivity.

The classification
is a risk assessment.

It is not a price forecast.

---

## Independent Event Risk Gate

Proposed architecture:

    VERIFIED EVENT CALENDAR
            ↓
    EVENT RISK ASSESSMENT
            ↓
    INDEPENDENT RISK GATE
            ↓
    PERMISSION DECISION.

The Trading Agent
must not change
its own event restrictions.

---

## Event Windows

Future policies may define
restricted trading windows
around certain events.

For example:

    BEFORE_EVENT

    DURING_EVENT

    AFTER_EVENT.

Possible controls:

    reduced exposure

    no new positions

    stricter liquidity checks

    deferred execution.

Exact thresholds and windows
must be supported by evidence
and approved before deployment.

This Insight does not authorize
any specific trading restriction.

---

## No Automatic Directional Bias

A high-risk event
does not necessarily imply:

    BUY.

Nor does it imply:

    SELL.

The correct response
may simply be:

    WAIT.

Event awareness should improve
risk management without inventing
a directional trading edge.

---

## Market Reaction

After an event occurs,
record:

    official outcome

    release timestamp

    market price before release

    market price after release

    spread

    volatility

    liquidity

    execution conditions.

Avoid assuming
that the event caused
every observed price movement.

Correlation and timing
are not sufficient
to establish causation.

---

## Research Protocol

For each event category:

1. Define the hypothesis.

2. Define the event dataset.

3. Preserve point-in-time values.

4. Define measurement windows.

5. Include execution costs.

6. Separate development
   and out-of-sample periods.

7. Measure event-conditioned
   strategy performance.

8. Report uncertainty.

9. Apply preregistered
   acceptance criteria.

10. Reject unsupported conclusions.

---

## DB1 Application

DB1 remains a research strategy.

Future analysis may investigate
whether performance changes
around major scheduled events.

Do not modify DB1 parameters
based on individual news stories.

Do not assume
event filters improve results
without independent testing.

---

## EF2 Application

EF2 Espresso Frog
remains parked.

An event calendar
must not become a pretext
for retrospective optimization.

Any future hypothesis
must be preregistered
before additional testing.

---

## ARB Research Application

For the October 2026
ARB events, preserve:

    original unlock schedule

    scheduled quantity

    source timestamp

    governance proposal status

    actual confirmed changes

    observed market reaction.

Do not interpret:

    proposed allocation

as:

    approved expenditure.

Do not interpret:

    unlocked supply

as:

    executed market sales.

---

## Failure Conditions

The event system should fail closed
when a critical event record has:

    unknown timezone

    conflicting timestamps

    unverified source

    stale status

    missing revision history.

A failed verification
must not silently become
permission to trade.

---

## Acceptance Tests

1. Future outcomes are unavailable
   to historical simulations.

2. Forecasts and actual results
   remain separate.

3. Event timestamps
   use explicit timezones.

4. Revised data preserves
   previous versions.

5. Cancelled events
   are correctly identified.

6. An event schedule
   cannot generate an automatic
   directional signal.

7. Agents cannot alter
   independent risk policies.

8. Unverified event data
   cannot authorize live action.

9. Market reactions
   are measured with
   documented windows.

10. Strategy changes require
    separate validation
    and human authorization.

---

## Relationship to #091

#091:

NUMBERS ARE NOT COMPARABLE
UNTIL THEIR MEASUREMENT
CONTRACTS MATCH.

#096:

Forecast values and actual results
must remain distinct
and point-in-time correct.

---

## Relationship to #093

#093:

A SIMULATION MUST NEVER
HAVE PRODUCTION AUTHORITY.

#096:

A historical simulation
must never have access
to future information.

These are different boundaries.

---

## Relationship to #094

#094:

A STRATEGY IS NOT SAFE
IF ITS EXIT ASSUMES LIQUIDITY.

#096:

Scheduled events may create
conditions in which liquidity
changes rapidly.

Event risk must therefore
be considered alongside
execution risk.

---

## Relationship to #095

#095:

SMALL ACTIONS MUST BE GOVERNED
BY AGGREGATE EXPOSURE.

#096:

Event risk should be evaluated
against total portfolio exposure,
not only isolated positions.

---

## Projects HQ Principle

> Knowing that an event
> will occur does not mean
> knowing its outcome.
>
> Autonomous trading systems
> must preserve point-in-time
> information, distinguish
> forecasts from observations,
> and treat scheduled events
> as risk context rather than
> automatic trading signals.

---

## Shortest Version

# KNOWN EVENT ≠ KNOWN OUTCOME.

---

## Operational Formula

# SCHEDULE
    ↓
# VERIFY
    ↓
# CLASSIFY RISK
    ↓
# WAIT FOR OUTCOME
    ↓
# RECORD
    ↓
# TEST
    ↓
# DECIDE.

---

## Future Applications

Nekonečný Mír
DB1
EF2 Espresso Frog
BTC Research
ARB Research
Economic Calendars
Token Unlocks
Governance Events
Market Regimes
Risk Gate
Backtesting
Point-in-Time Data
AI Research Agents
Trading Agents

---

## Origin

Daily AI Trading Brief
2026-10-13

Inspired by:

US CPI scheduled for October 14.

ArbitrumDAO governance vote
scheduled from October 15.

ARB token unlock
scheduled for October 16.

The broader lesson:

A known schedule
does not reveal
a future outcome.

---

## Status

ACTIVE STRATEGIC PRINCIPLE

Implementation status:
NOT YET IMPLEMENTED

No strategy changes authorized.

No live trading authority granted.

---

## Revision

v1.0 — 2026-10-13
