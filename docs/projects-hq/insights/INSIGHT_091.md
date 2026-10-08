# PROJECTS HQ INSIGHT #091

## Date
8. 10. 2026

## Title
# Numbers Are Not Comparable Until Their Measurement Contracts Match

---

## Core Idea

Autonomous systems consume numerical evidence.

Examples:

    market prices
    ETF flows
    liquidation totals
    volatility
    model benchmarks
    trading performance
    risk exposure.

Numbers appear objective.

But two numbers can describe
different realities while sharing
the same label.

Therefore:

# SAME LABEL ≠ SAME METRIC.

Before comparing measurements,
verify that they describe
the same quantity under
compatible conditions.

---

## The Measurement Problem

Imagine two data providers.

Provider A reports:

    BTC ETF NET FLOW:
        -77 million USD

Provider B reports:

    BTC ETF NET FLOW:
        +119 million USD

Both claim to describe:

    October 6, 2026.

Which is correct?

We do not yet know.

Possible explanations:

    different reporting cutoffs
    different fund coverage
    preliminary versus revised data
    different accounting conventions
    missing observations
    delayed settlements
    data errors.

The correct response is not:

    choose the more convenient number.

Nor:

    average the two values.

The correct response is:

# VERIFY THE MEASUREMENT CONTRACT.

---

## Measurement Contract

Every consequential numerical metric
should have a defined contract.

Minimum fields:

    METRIC_ID
    METRIC_DEFINITION
    UNIT
    POPULATION
    TIME_WINDOW
    TIMEZONE
    AS_OF_TIMESTAMP
    SOURCE
    METHODOLOGY
    REVISION_STATUS
    DATA_QUALITY_STATE.

Without these fields,
comparability may be unknown.

---

## Example: ETF Flows

A valid comparison requires:

    same funds
    same market
    same trading date
    same currency
    same flow definition
    compatible reporting cutoff
    compatible revision state.

Otherwise:

    PROVIDER_A.VALUE

and:

    PROVIDER_B.VALUE

may not be measurements
of the same object.

---

## Example: Model Benchmarks

Model A reports:

    SUCCESS_RATE = 80%.

Model B reports:

    SUCCESS_RATE = 75%.

Can we conclude:

    A > B?

Not necessarily.

We must inspect:

    benchmark version
    test sample
    tool availability
    reasoning budget
    time limit
    pass criteria
    evaluation method
    number of attempts.

Without compatible conditions:

# BENCHMARK COMPARISON = UNRESOLVED.

---

## Example: Trading Performance

Strategy A:

    PROFIT_FACTOR = 1.50

Strategy B:

    PROFIT_FACTOR = 1.30

Before comparing:

    same market?
    same period?
    same fees?
    same slippage?
    same position sizing?
    same execution assumptions?
    same data quality?
    same sample selection?

A better headline number
does not automatically mean
a better trading strategy.

---

## Three Evidence States

A consequential metric should
have an explicit comparison state.

### 1. COMPARABLE

Definitions and conditions
are sufficiently compatible.

Comparison is permitted.

### 2. NON_COMPARABLE

Definitions or populations
materially differ.

Direct comparison is prohibited.

### 3. UNRESOLVED

Required information is missing
or conflicting.

Comparison must be suspended
until the uncertainty is resolved.

---

## Conflict Is Information

When sources disagree,
the disagreement itself
is valuable evidence.

Do not erase it.

Record:

    source A
    value A
    source B
    value B
    difference
    suspected causes
    verification status.

Therefore:

# CONFLICT IS A DATA STATE.

Not merely:

    an inconvenience.

---

## No Silent Averaging

Suppose:

    SOURCE_A = +100

    SOURCE_B = -100.

A naive system calculates:

    AVERAGE = 0.

But zero may be supported
by neither source.

Averaging contradictory values
can manufacture false certainty.

Therefore:

# DO NOT AVERAGE AWAY
# UNRESOLVED DISAGREEMENT.

---

## Source Count Is Not Independence

Five websites may report
the same incorrect number.

Why?

Because all five copied:

    one upstream provider.

Therefore:

    five agreeing articles

may represent:

    one underlying observation.

Independent verification requires
independent measurement lineage,
not merely multiple URLs.

---

## Measurement Lineage

Each numerical artifact should reference:

    original provider
    collection method
    processing steps
    transformation rules
    revision history.

This extends #089:

    PROVENANCE MUST TRAVEL
    WITH THE ARTIFACT.

For numerical artifacts,
provenance must also describe:

    HOW THE NUMBER WAS MEASURED.

---

## As-Of Discipline

A number without time context
can become misleading.

Example:

    BTC_PRICE = 83,000.

Questions:

    At what timestamp?
    Which exchange?
    Spot or futures?
    Last trade or midpoint?
    Which quote currency?

For live trading:

    stale data

can be more dangerous than:

    missing data.

---

## Revisions

Some data changes after publication.

Therefore distinguish:

    PRELIMINARY
    FINAL
    REVISED.

Never silently overwrite
a consequential historical value.

Preserve:

    original observation
    revised observation
    revision timestamp
    revision reason.

This supports reproducible research.

---

## Conflict Resolution

Desired process:

    INGEST
        ↓
    NORMALIZE DEFINITIONS
        ↓
    COMPARE CONTRACTS
        ↓
    DETECT CONFLICT
        ↓
    INVESTIGATE
        ↓
    RESOLVE OR PRESERVE
        ↓
    VALIDATED EVIDENCE.

A conflict may be resolved by:

    correcting time alignment
    checking original sources
    identifying revised data
    comparing fund coverage
    reproducing the calculation.

If unresolved:

    retain the uncertainty.

---

## Trading Safety Rule

A consequential trading decision
must not depend on an unresolved
material measurement conflict.

Example:

    ETF_FLOW_STATE = UNRESOLVED.

Then:

    ETF_FLOW_SIGNAL = DISABLED.

Other independently validated
signals may remain usable.

The system does not need
to stop everything.

It must stop the decision path
that depends on unreliable evidence.

---

## Avoid Global Paralysis

Not every disagreement
requires system-wide shutdown.

Classify:

    MATERIAL CONFLICT

versus:

    NON-MATERIAL CONFLICT.

Materiality depends on:

    decision sensitivity
    exposure
    uncertainty
    possible loss
    availability of alternatives.

Only the affected decision path
needs to be blocked.

---

## Confidence Is Not a Substitute

A model may say:

    "I am 95% confident."

But confidence does not repair
incompatible measurement definitions.

Therefore:

# CONFIDENCE ≠ COMPARABILITY.

First establish what was measured.

Then evaluate reliability.

---

## Future Nekonečný Mír

Proposed research architecture:

    RAW MARKET DATA
        ↓
    SOURCE PROVENANCE
        ↓
    MEASUREMENT CONTRACT
        ↓
    COMPATIBILITY CHECK
        ↓
    CONFLICT DETECTION
        ↓
    DATA QUALITY GATE
        ↓
    FEATURE ENGINEERING
        ↓
    REGIME MODEL
        ↓
    STRATEGY EVALUATION.

No unverified numerical claim
should silently become
a trusted strategy feature.

---

## DB1 Application

DB1 research must preserve:

    market
    timeframe
    strategy version
    test period
    data source
    fee assumptions
    slippage assumptions
    trade count
    execution assumptions.

Results produced under
different contracts
must not be treated
as directly comparable.

---

## EF2 Application

EF2 has historical
and out-of-sample results.

These must remain separated.

Do not combine them
into one attractive statistic
without clearly defining:

    period
    sample
    selection rules
    transaction costs.

A valid comparison requires
compatible evaluation conditions.

---

## Model Routing Application

When evaluating AI models:

    cost per task
    success rate
    latency
    tool calls

must use comparable workloads.

Otherwise model routing
may optimize a misleading metric.

---

## Proposed Data Quality States

    VALIDATED

    PRELIMINARY

    REVISED

    STALE

    CONFLICTED

    NON_COMPARABLE

    UNRESOLVED

    REJECTED.

Every consequential metric
should carry one explicit state.

---

## Proposed Conflict Record

    CONFLICT_ID
    METRIC_ID
    OBSERVATION_A
    OBSERVATION_B
    SOURCE_A
    SOURCE_B
    CONTRACT_A
    CONTRACT_B
    MATERIALITY
    OWNER
    STATUS
    RESOLUTION_EVIDENCE
    RESOLVED_AT.

A conflict without resolution
must remain visible.

---

## Relationship to #080

#080:

    OBSERVED STATE
    >
    SELF-REPORTED STATE.

#091:

    observations must be
    defined consistently
    before they are compared.

---

## Relationship to #085

#085:

    RECONSTRUCT CONSEQUENTIAL ACTIONS.

#091:

    preserve the measurement
    assumptions that informed them.

---

## Relationship to #086

#086:

    DATA ≠ AUTHORITY.

#091:

    a numerical claim
    must not become
    decision authority merely
    because it looks precise.

---

## Relationship to #089

#089:

    PROVENANCE MUST TRAVEL
    WITH THE ARTIFACT.

#091:

    the measurement contract
    must travel with
    numerical evidence.

Provenance answers:

    WHERE DID IT COME FROM?

Measurement contract answers:

    WHAT EXACTLY DOES IT MEAN?

---

## Relationship to #090

#090:

    REVOKED ≠ POWERLESS.

#091:

    a revoked or invalidated
    data source must not continue
    supplying trusted evidence
    through cached downstream metrics.

---

## Projects HQ Principle

> Numerical evidence is comparable only when its
> definitions, populations, units, time windows,
> methodologies and revision states are compatible.
> Conflicting measurements must be explicitly
> investigated, resolved or preserved as uncertainty.
> Never manufacture agreement by silently selecting,
> averaging or relabeling incompatible data.

Shortest version:

# SAME LABEL ≠ SAME METRIC.

Operational version:

# DEFINE → COMPARE → DETECT → RESOLVE → USE.

---

## Future Applications

Market Data Quality · ETF Flows · Model Benchmarks ·
Backtesting · Performance Attribution ·
Agent Evaluation · Regime Classification ·
Risk Management · Research Reproducibility ·
Data Provenance · Evidence Conflict Resolution

---

## Origin

Daily AI Trading Brief — 8. 10. 2026

Inspired by inconsistent reported Bitcoin ETF flow
figures and the broader challenge of comparing
numerical claims across independent data providers.

The generalized lesson for Nekonečný Mír:

A number becomes useful evidence only when
we understand exactly what it measures.

---

## Status

🟢 Active strategic principle

---

## Tags

Projects HQ · Nekonečný Mír · Data Quality ·
Measurement Contracts · Evidence · Trading ·
AI Agents · Reproducibility · Verification ·
Benchmarking · Risk Management

---

## Revision

v1.0 — 8. 10. 2026
