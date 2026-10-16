# PROJECTS HQ INSIGHT #099

## Date
2026-10-16

## Title
A Strategy Must Not Choose Its Own Exam

---

## Core Principle

An autonomous research agent
may generate trading hypotheses.

It may design strategies.

It may optimize parameters
within an approved research protocol.

But it must not control
the independent evaluation
that determines whether
its own strategy has succeeded.

Therefore:

# THE STRATEGY MUST NOT
# CHOOSE ITS OWN EXAM.

Research and independent validation
must be separated.

---

## The Problem

Suppose an AI Research Agent
creates a trading strategy.

It performs 100 backtests.

Only three produce
attractive performance.

The agent selects
the best result.

It reports:

    PROFIT FACTOR = 2.50

    MAX DRAWDOWN = 4%

    WIN RATE = 68%.

The numbers may be correct
for the selected experiment.

But they do not prove
that the strategy has
a repeatable trading edge.

---

## Selection Bias

When many experiments
are performed,
some will appear successful
purely by chance.

The more combinations tested,
the greater the risk
of selecting an accidental winner.

A selected backtest result
must not be treated
as independent evidence.

---

## Proposed Architecture

    RESEARCH AGENT
          |
          v
    STRATEGY PROPOSAL
          |
          v
    RESEARCH REGISTRY
          |
          v
    FROZEN TEST PROTOCOL
          |
          v
    INDEPENDENT EVALUATION GATE
          |
          v
    EVIDENCE REPORT
          |
          v
    HUMAN REVIEW.

The Research Agent
must not control
the Evaluation Gate.

---

## Research Agent Authority

The Research Agent may:

    propose hypotheses

    write strategy code

    inspect approved
    development datasets

    perform exploratory backtests

    compare candidate strategies

    propose risk controls

    document limitations.

It may not:

    modify protected holdout data

    choose favorable holdout periods
    after observing outcomes

    erase failed experiments

    redefine acceptance criteria
    after seeing results

    promote its own strategy
    to production.

---

## Independent Evaluation Gate

The Evaluation Gate controls:

    protected evaluation datasets

    evaluation protocol

    acceptance criteria

    minimum sample requirements

    execution cost assumptions

    reporting requirements

    evaluation history.

It must operate independently
of the strategy proposer.

---

## Frozen Research Contract

Before protected evaluation,
the following should be recorded:

    EXPERIMENT_ID

    STRATEGY_VERSION

    CODE_COMMIT_HASH

    DATASET_VERSION

    DATA_CUTOFF

    MARKET

    TIMEFRAME

    PARAMETER_SET

    TRANSACTION_COST_MODEL

    SLIPPAGE_MODEL

    POSITION_SIZING_RULES

    RISK_LIMITS

    PRIMARY_METRIC

    SECONDARY_METRICS

    MINIMUM_SAMPLE_SIZE

    ACCEPTANCE_CRITERIA

    FAILURE_CRITERIA.

Material changes require
a new experiment version.

---

## Protected Holdout Data

A protected holdout
must remain independent
of the research process.

The Research Agent
must not repeatedly inspect
holdout results
and optimize against them.

If holdout results influence
subsequent strategy development,
the holdout is contaminated
for that development cycle.

A new independent evaluation
is then required.

---

## No Hidden Reoptimization

The following must be prohibited
during protected evaluation:

    changing parameters
    after seeing results

    removing losing periods

    selecting favorable assets

    changing cost assumptions

    changing entry conditions

    changing exit conditions

    modifying the evaluation window
    to improve performance.

Any such change
creates a new research candidate.

---

## Every Experiment Counts

Failed experiments
must remain in the registry.

Example:

    EXPERIMENTS_RUN = 100

    SUCCESSFUL_BACKTESTS = 3.

Reporting only the three
successful experiments
would hide important context.

The evaluation report
must preserve the complete
research history
where available.

---

## Sample Size Discipline

A small number of trades
cannot provide strong evidence
of a durable trading edge.

The minimum sample size
must be defined
before evaluation.

A strategy that fails
the minimum sample requirement
cannot receive
a full validation pass.

It may receive:

    INSUFFICIENT_EVIDENCE.

This is not equivalent
to failure or success.

---

## Evaluation Outcomes

Proposed states:

    NOT_TESTED

    TEST_PENDING

    TEST_RUNNING

    INSUFFICIENT_EVIDENCE

    FAILED

    CONDITIONAL_PASS

    PASSED

    INVALIDATED.

No state automatically grants
live trading authority.

---

## Cost Realism

Evaluation must include
realistic assumptions for:

    exchange fees

    bid-ask spread

    slippage

    partial fills

    latency

    funding costs
    where applicable.

A strategy profitable
before costs
may be unprofitable
after execution costs.

---

## Point-in-Time Integrity

Historical testing
must not use information
that was unavailable
at the decision timestamp.

This includes:

    revised economic data

    future market candles

    future indicator values

    later tokenomics updates

    later market classifications.

The Evaluation Gate
must test for look-ahead bias.

---

## Independent Metrics

The Research Agent
may propose performance metrics.

But it cannot redefine
the primary success metric
after seeing evaluation results.

The Evaluation Gate
must report both:

    favorable outcomes

and:

    unfavorable outcomes.

No selective presentation.

---

## Evaluation Evidence

Every protected test
should produce:

    EVALUATION_ID

    EXPERIMENT_ID

    EVALUATOR_VERSION

    DATASET_HASH

    CODE_HASH

    CONFIGURATION_HASH

    EXECUTION_TIMESTAMP

    TRADE_COUNT

    PERFORMANCE_METRICS

    RISK_METRICS

    COST_ASSUMPTIONS

    FAILURE_DETAILS

    FINAL_EVALUATION_STATE.

Results should be reproducible
by an independent reviewer.

---

## Relationship to DB1

DB1 remains
an unconfirmed research candidate.

Its existing historical results
do not establish
a durable trading edge.

No reoptimization
is authorized by this Insight.

---

## Relationship to EF2

EF2 Espresso Frog
remains parked.

Its negative
out-of-sample performance
must remain part
of the permanent evidence record.

A favorable earlier test
must not erase
a later unfavorable result.

---

## Human Approval

Even a strategy
that passes independent evaluation
must not automatically
receive live trading authority.

A separate process
must assess:

    operational readiness

    capital limits

    execution reliability

    risk controls

    monitoring

    recovery procedures

    human authorization.

---

## Acceptance Tests

1. Research agents cannot
   modify protected datasets.

2. Research agents cannot
   alter frozen acceptance criteria.

3. Failed experiments
   remain recorded.

4. Repeated holdout access
   is detected and controlled.

5. Contaminated holdouts
   cannot produce
   independent validation claims.

6. Insufficient sample sizes
   cannot produce full passes.

7. Execution costs
   are included.

8. Look-ahead bias
   is explicitly tested.

9. Evaluation reports
   preserve unfavorable results.

10. A successful evaluation
    does not grant
    live trading permission.

---

## Relationship to #089

#089:

Provenance must travel
with the artifact.

#099:

Evaluation evidence
must preserve the origin
of strategy code,
data and test results.

---

## Relationship to #091

#091:

Numbers are not comparable
until their measurement
contracts match.

#099:

The measurement contract
must be frozen
before independent evaluation.

---

## Relationship to #096

#096:

A known event
is not a known outcome.

#099:

A promising hypothesis
is not a validated strategy.

---

## Relationship to #098

#098:

An approval must bind
to the exact action.

#099:

A validation result
must bind
to the exact strategy version
and evaluation protocol.

---

## Projects HQ Principle

> An AI agent may discover
> promising trading ideas.
>
> But the agent that proposes
> a strategy must not control
> the independent evidence
> used to judge that strategy.
>
> Evaluation must be frozen,
> reproducible,
> independent,
> and resistant
> to selective reporting.

---

## Shortest Version

# THE STRATEGY MUST NOT
# CHOOSE ITS OWN EXAM.

---

## Operational Formula

# HYPOTHESIS
    ↓
# RESEARCH
    ↓
# FREEZE
    ↓
# INDEPENDENT TEST
    ↓
# VERIFY EVIDENCE
    ↓
# HUMAN REVIEW.

---

## Future Applications

Nekonečný Mír
DB1
EF2 Espresso Frog
Research Agents
Quant Agents
Evaluation Gate
Experiment Registry
Protected Holdout Datasets
Backtesting Infrastructure
Strategy Validation
Risk Gate
Authority Gate
Audit Infrastructure

---

## Status

ACTIVE STRATEGIC PRINCIPLE

Implementation status:
NOT YET IMPLEMENTED

No strategy approved
for live trading.

No automatic strategy
promotion authorized.

---

## Revision

v1.0 — 2026-10-16
