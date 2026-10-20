# PROJECTS HQ INSIGHT #103

## Date
2026-10-20

## Title
A Refactor Must Prove Behavioral Equivalence

---

## Core Principle

Improving the structure
of a software system
does not automatically preserve
its operational behavior.

Therefore:

CLEANER CODE
!=
EQUIVALENT BEHAVIOR.

A refactor is not validated
until its intended
behavioral contract
has been tested.

---

## The Problem

Consider a trading strategy
that has already completed
a documented research evaluation.

An AI coding agent
is asked to improve:

- readability
- performance
- modularity
- error handling.

The agent changes the code.

The program compiles.

Its unit tests pass.

Execution becomes faster.

However, a small change
in candle indexing
moves trade entry signals
one bar earlier.

The resulting backtest
shows improved performance.

But the improvement
may be caused by
changed strategy behavior.

The refactor has silently
become a new experiment.

---

## Two Different Operations

### Refactoring

Changes implementation
while preserving
defined external behavior.

### Strategy Modification

Intentionally changes
the trading logic
or decision contract.

These operations
must not be confused.

A strategy modification
requires a new
research decision.

---

## Behavioral Contract

Before a significant refactor,
the system should record
the behavior expected
to remain unchanged.

For trading research:

STRATEGY_VERSION

DATASET_VERSION

CONFIGURATION_HASH

SIGNAL_TIMESTAMPS

ENTRY_CONDITIONS

EXIT_CONDITIONS

POSITION_SIZING

FEE_MODEL

SLIPPAGE_MODEL

ORDER_ASSUMPTIONS

RISK_LIMITS

TRADE_OUTPUT_SCHEMA.

The contract must identify
which differences,
if any,
are explicitly permitted.

---

## Reference Implementation

Preserve the original
implementation as
an immutable reference.

The reference should include:

SOURCE_COMMIT

DEPENDENCY_LOCKFILE

TEST_DATA_VERSION

CONFIGURATION

EXECUTION_ENVIRONMENT

REFERENCE_OUTPUTS.

Do not overwrite
the reference implementation
before validation.

---

## Golden-Master Tests

Run both implementations
against the same
frozen input dataset.

Compare:

1. Generated signals.

2. Signal timestamps.

3. Entry and exit decisions.

4. Position sizes.

5. Order requests.

6. Fee calculations.

7. Risk decisions.

8. Trade logs.

9. Equity curves.

10. Final evaluation metrics.

A matching final profit
does not establish
behavioral equivalence.

---

## Numerical Precision

Some implementation changes
may alter floating-point results.

Therefore,
the comparison policy
must define whether
each output requires:

EXACT MATCH

or:

PREDEFINED NUMERICAL TOLERANCE.

Tolerance must be justified
before testing.

The coding agent
must not expand tolerances
to make its changes pass.

---

## Time-Series Integrity

Special attention
must be given to:

CANDLE_ALIGNMENT

TIMEZONE_HANDLING

BAR_CLOSURE

MISSING_DATA

WARMUP_PERIODS

LOOKAHEAD_PREVENTION

EVENT_ORDERING.

A one-bar shift
can invalidate
a trading experiment.

---

## Negative Tests

The validation suite
should deliberately introduce
known behavioral defects.

Examples:

- Shift signals one candle.

- Change fee assumptions.

- Remove one risk check.

- Alter position sizing.

- Replace closed candles
  with incomplete candles.

- Change missing-data handling.

- Modify exit ordering.

The comparison system
should detect
these deviations.

---

## AI Agent Responsibilities

A coding agent may:

PROPOSE_REFACTOR

IMPLEMENT_CHANGE

RUN_TESTS

REPORT_DIFFERENCES.

It must not independently:

CHANGE_REFERENCE_OUTPUTS

RELAX_ACCEPTANCE_CRITERIA

REDEFINE_STRATEGY_INTENT

APPROVE_ITS_OWN_RESULTS

PROMOTE_TO_LIVE_TRADING.

---

## Independent Evaluation

Behavioral equivalence
should be evaluated
outside the coding agent's
approval authority.

Proposed decision states:

EQUIVALENT

APPROVED_DIFFERENCE

UNEXPECTED_DIFFERENCE

INSUFFICIENT_EVIDENCE

VALIDATION_FAILED.

Only an authorized
independent review
may accept
intentional differences.

---

## When Behavior Changes

An unexpected difference
must not be silently accepted
because performance improves.

Instead:

STOP THE REFACTOR GATE.

CLASSIFY THE DIFFERENCE.

RECORD THE CHANGE.

DECIDE WHETHER
A NEW EXPERIMENT
IS REQUIRED.

A better backtest
is not proof
of a better strategy.

---

## Acceptance Criteria

A refactor may pass
only when:

1. The reference is preserved.

2. The comparison dataset
   is frozen.

3. The behavioral contract
   is explicit.

4. All required tests pass.

5. Unexpected differences
   are absent.

6. Permitted differences
   were approved in advance.

7. Audit evidence is retained.

8. Independent review
   confirms the result.

---

## Relationship to #091

#091:

Numbers are not comparable
until their measurement
contracts match.

#103:

Software versions
are not behaviorally equivalent
until their output contracts
have been compared.

---

## Relationship to #099

#099:

A strategy must not
choose its own exam.

#103:

A coding agent must not
choose the acceptance criteria
for its own refactor.

---

## Relationship to #100

#100:

A rule is not a control
until it is enforced.

#103:

Behavioral equivalence
must become
an enforced validation gate.

---

## Relationship to #102

#102:

Data freshness
is part of data validity.

#103:

A refactor must preserve
the time-series semantics
defined by the research contract.

---

## Projects HQ Principle

> Better code is valuable.
>
> But implementation quality
> and strategy validity
> are different questions.
>
> A refactor must preserve
> the agreed behavior,
> or be treated
> as an intentional change
> requiring new evaluation.

---

## Shortest Version

CLEANER CODE
!=
EQUIVALENT BEHAVIOR.

---

## Proposed Workflow

FREEZE REFERENCE
       |
       v
DEFINE BEHAVIORAL CONTRACT
       |
       v
IMPLEMENT REFACTOR
       |
       v
RUN IDENTICAL TEST INPUTS
       |
       v
COMPARE OUTPUTS
       |
       v
INDEPENDENT REVIEW
       |
       v
ACCEPT OR REJECT.

Unexpected difference:

STOP.

---

## Future Applications

Project Nekonečný Mír

DB1

EF2 Espresso Frog

Codex

Claude Code

Research Agents

Quant Agents

Backtest Infrastructure

Evaluation Gate

Risk Gate

GitHub CI

Experiment Registry

---

## Status

ACTIVE STRATEGIC PRINCIPLE

Implementation:
NOT YET IMPLEMENTED

Independent equivalence gate:
PROPOSED

Live trading:
NOT AUTHORIZED

---

## Revision

v1.0 — 2026-10-20
