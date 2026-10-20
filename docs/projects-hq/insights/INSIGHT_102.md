# PROJECTS HQ INSIGHT #102

## Date
2026-10-19

## Title
A Correct Decision on Stale Data Is Still Unsafe

---

## Core Principle

A decision may be logically correct
for the data it receives.

However, that data may no longer
represent the current environment.

Therefore:

# DATA FRESHNESS
# IS PART OF DATA VALIDITY.

A correct calculation
based on stale information
may produce an unsafe action.

---

## The Problem

Consider an autonomous
trading agent.

Its market data feed reports:

    BTCUSDT = 82,000 USD.

The strategy generates
a trading signal.

The Risk Gate calculates
acceptable position exposure.

The Authority Gate confirms
that the requested action
is within its permitted scope.

All checks appear successful.

However:

    LAST MARKET UPDATE:
    180 SECONDS AGO.

The feed has stopped updating.

The actual market price
may have changed significantly.

The calculation may be correct.

The information is not fresh.

The decision is unsafe.

---

## Proposed Architecture

    MARKET DATA SOURCE
            |
            v
    INGESTION SERVICE
            |
            v
    DATA QUALITY GATE
            |
            v
    FRESHNESS VALIDATION
            |
            v
    STRATEGY EVALUATION
            |
            v
    INDEPENDENT RISK GATE
            |
            v
    AUTHORITY GATE
            |
            v
    APPROVED ACTION.

The strategy must not
be able to bypass
the Data Quality Gate.

---

## Three Important Timestamps

Every time-sensitive observation
should preserve:

    SOURCE_EVENT_TIME

    INGESTION_TIME

    DECISION_TIME.

SOURCE_EVENT_TIME:

    When the event occurred
    according to its source.

INGESTION_TIME:

    When our system received
    the observation.

DECISION_TIME:

    When the observation
    was used for a decision.

These timestamps
must not be confused.

---

## Freshness Contract

Every critical data source
should have an explicit
freshness contract.

Suggested fields:

    SOURCE_ID

    DATA_TYPE

    INSTRUMENT

    SOURCE_EVENT_TIME

    INGESTION_TIME

    DECISION_TIME

    MAX_ACCEPTABLE_AGE

    EXPECTED_UPDATE_INTERVAL

    CLOCK_SKEW_TOLERANCE

    SEQUENCE_NUMBER

    QUALITY_STATUS

    DATA_VERSION.

The acceptable age
must depend on the task.

---

## Different Data, Different Rules

Examples:

    MARKET TICKS

    ORDER BOOK

    CLOSED CANDLES

    ECONOMIC RELEASES

    FUNDING RATES

    POSITION BALANCES

    EXCHANGE STATUS

    TOKENOMICS EVENTS.

These data categories
have different update patterns.

A single global freshness
threshold is insufficient.

---

## Market Data

For market-sensitive decisions,
the system should verify:

    the source is connected

    updates arrive as expected

    timestamps are plausible

    observations are ordered

    duplicate updates
    are handled correctly

    required market data
    are sufficiently recent.

If critical market data
are stale:

    DENY NEW EXECUTION.

---

## Closed Candles

A strategy using
five-minute candles
must distinguish between:

    OPEN CANDLE

and:

    CONFIRMED CLOSED CANDLE.

A partially formed candle
must not silently replace
a closed-candle observation.

The research protocol
must define which one
is permitted.

---

## Economic Data

Economic releases
require special treatment.

The system must distinguish:

    SCHEDULED RELEASE TIME

    INITIAL PUBLICATION

    REVISED VALUE

    CURRENT DATABASE VALUE.

Historical backtests
must use information
available at the relevant
historical decision time.

Later revisions
must not leak backward
into earlier decisions.

---

## Clock Integrity

Freshness checks depend
on trustworthy clocks.

The system should detect:

    excessive clock drift

    future-dated observations

    inconsistent timestamps

    time-zone errors

    daylight-saving transitions

    incorrect timestamp units.

A suspicious timestamp
must not be treated
as proof of freshness.

---

## Out-of-Order Data

A newly received message
may contain an older event.

Therefore:

    NEWLY RECEIVED
    != NEWLY OCCURRED.

Ingestion time alone
cannot establish freshness.

Sequence numbers
and source event timestamps
should be checked
where available.

---

## Feed Reconnection

After a disconnected
market data feed reconnects,
the system must not
immediately assume
its internal state is current.

It should:

    identify missing intervals

    obtain required snapshots

    reconcile sequence numbers

    verify market state

    confirm data freshness

    resume only when safe.

---

## Independent Enforcement

The Research Agent
may consume market data.

It must not control
the freshness policy
used to validate that data.

The Data Quality Gate
should be independently enforced.

An agent must not be able to:

    extend freshness limits

    forge source timestamps

    disable stale-data alerts

    silently replace a source

    suppress quality failures.

---

## Proposed Quality States

    FRESH

    DELAYED

    STALE

    OUT_OF_ORDER

    INCOMPLETE

    CLOCK_INVALID

    SOURCE_UNAVAILABLE

    QUALITY_UNKNOWN.

Critical decisions
must explicitly define
which states are acceptable.

---

## Fail-Closed Principle

For consequential actions:

    STALE DATA
        -> DENY.

    UNKNOWN FRESHNESS
        -> DENY.

    INVALID TIMESTAMP
        -> DENY.

    MISSING CRITICAL INPUT
        -> DENY.

    UNRECONCILED FEED
        -> DENY.

The system may continue
safe diagnostic operations.

It must not silently
convert missing information
into permission.

---

## Audit Requirements

Every consequential decision
should preserve:

    DECISION_ID

    DATA_SOURCE_ID

    DATA_VERSION

    SOURCE_EVENT_TIME

    INGESTION_TIME

    DECISION_TIME

    OBSERVED_DATA_AGE

    FRESHNESS_POLICY_VERSION

    QUALITY_GATE_RESULT

    ACTION_DECISION.

This evidence should allow
independent reconstruction
of the freshness check.

---

## Acceptance Tests

1. Stale market data
   cannot authorize
   new execution.

2. Missing timestamps
   are rejected.

3. Future timestamps
   trigger validation failures.

4. Out-of-order updates
   cannot silently replace
   newer observations.

5. Feed disconnection
   produces a visible
   quality-state change.

6. Reconnection requires
   appropriate reconciliation.

7. Unclosed candles
   cannot masquerade
   as confirmed candles.

8. Historical evaluations
   preserve point-in-time
   economic data integrity.

9. Agents cannot modify
   independent freshness limits.

10. Audit evidence records
    the actual data age
    at decision time.

---

## Relationship to #089

#089:

Provenance must travel
with the artifact.

#102:

Temporal provenance
must travel
with the observation.

---

## Relationship to #091

#091:

Numbers are not comparable
until their measurement
contracts match.

#102:

The measurement contract
must include
temporal validity.

---

## Relationship to #099

#099:

A strategy must not
choose its own exam.

#102:

Independent evaluation
must preserve
point-in-time data integrity.

---

## Relationship to #100

#100:

A documented rule
is not an enforced control.

#102:

Freshness requirements
must eventually become
enforced technical controls.

---

## Projects HQ Principle

> Correct reasoning
> cannot compensate
> for invalid information.
>
> A data point
> is not operationally valid
> merely because its value
> was once correct.
>
> Its source, timestamp,
> completeness and freshness
> must satisfy
> the decision contract.

---

## Shortest Version

# CORRECT CALCULATION
# + STALE DATA
# = UNSAFE DECISION.

---

## Operational Formula

    RECEIVE DATA
         |
         v
    VERIFY SOURCE
         |
         v
    VERIFY TIMESTAMPS
         |
         v
    VERIFY FRESHNESS
         |
         v
    VERIFY COMPLETENESS
         |
         v
    AUTHORIZE DATA USE.

Any critical failure:

    DENY CONSEQUENTIAL ACTION.

---

## Future Applications

Project Nekonečný Mír

DB1

EF2 Espresso Frog

Market Data Infrastructure

Research Agents

Quant Agents

Evaluation Gate

Data Quality Gate

Risk Gate

Authority Gate

Trading Agent

Audit Infrastructure

---

## Status

ACTIVE STRATEGIC PRINCIPLE

Implementation:
NOT YET IMPLEMENTED

No production Data Quality Gate
is claimed.

Live trading:
NOT AUTHORIZED

---

## Revision

v1.0 — 2026-10-19
