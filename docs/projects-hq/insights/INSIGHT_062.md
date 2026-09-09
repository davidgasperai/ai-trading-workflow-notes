🐸 PROJECTS HQ INSIGHT #062

Date: 08. 09. 2026

Title

Research Throughput Must Not Dilute Evidence Standards

Core Idea

AI agents can dramatically increase the speed at which hypotheses are generated, coded and tested.

That is valuable.

But higher research throughput creates a statistical danger:

More experiments create more opportunities to discover results that look meaningful purely by chance.

Therefore:

Automation may increase research speed.
It must not automatically lower the evidence required for acceptance.

Why It Matters

Imagine a human researcher can test:

10 strategy ideas / month

One accidentally excellent backtest may appear occasionally.

Now an AI Research Agent can test:

10,000 strategy ideas / month

Even if every strategy has zero genuine edge, some will inevitably look extraordinary.

For example:

PF = 2.4

Win rate = 71%

Beautiful equity curve

Low drawdown

The agent may report:

Excellent candidate discovered.

But the correct question is:

How many candidates were searched before this one appeared?

A result cannot be interpreted independently of the process that selected it.

Automation Changes the Search Space

Traditional research:

Human idea

↓

Manual implementation

↓

Backtest

↓

Review

The friction naturally limits the number of trials.

Agentic research:

Generate hypotheses

↓

Generate code

↓

Run thousands of tests

↓

Rank results

↓

Present top performers

This is enormously productive.

But the ranking step creates a powerful selection effect.

The best result among 10,000 random strategies will usually look much better than the best result among 10 random strategies.

That does not mean it contains more edge.

It may simply have won a larger lottery.

The Dangerous Shortcut

Bad system:

More agent productivity

↓

More backtests

↓

More attractive candidates

↓

More strategies approved

This silently converts:

research throughput

into:

deployment authority.

From #056:

CAPABILITY ≠ AUTHORITY.

Today we add:

THROUGHPUT ≠ EVIDENCE.

Correct Architecture

The Research Agent may have broad authority to:

GENERATE hypothesis

WRITE research code

RUN backtests

SUMMARIZE results

But it should not automatically have authority to:

CHANGE validation criteria

SELECT only favorable periods

REMOVE failed experiments

REDEFINE success after seeing results

APPROVE strategy

DEPLOY live

The research process remains governed by the Research Constitution.

Experiment Registry

Every experiment should ideally receive an identity:

EXP-000001

with:

Hypothesis

Created at

Strategy version

Parameters

Dataset

IS period

OOS period

Success criteria

Failure criteria

Result

Status

This means the system remembers not only the winner.

It remembers:

the denominator.

Instead of:

We found a strategy with PF 1.8.

we can say:

This candidate was one of 2,431 preregistered experiments; it passed IS and untouched OOS criteria defined before execution.

Those are very different evidence statements.

Failed Experiments Are Valuable

AI makes it cheap to create thousands of failures.

That sounds bad.

It can actually be extremely valuable — if failures remain visible.

From #060:

Failure evidence must survive the failure.

The Experiment Registry therefore should not contain only:

PROMISING

and:

APPROVED.

It should preserve:

FAILED

REJECTED

PARKED

INVALID

DUPLICATE

DATA_ERROR

INCONCLUSIVE

Otherwise the system develops survivorship bias in its own memory.

Preregistration Becomes More Important, Not Less

Before running an experiment:

Hypothesis

Parameters

Evaluation period

Primary metric

Minimum sample

Success threshold

Kill rule

should be fixed where practical.

Then:

RUN

Only afterward:

RESULT.

This prevents the agent from repeatedly modifying the question until the historical data answers:

YES.

DB1 and EF2 Example

Our existing approach already points in the right direction.

DB1:

OOS → observed

No re-optimization

Not confirmed / not rejected prematurely

EF2:

IS positive

but:

OOS negative

↓

PARKED

That is exactly the behavior an autonomous Research Agent must preserve.

A faster agent should not respond to EF2’s OOS failure by automatically searching 500 parameter combinations until one makes OOS green.

That would not repair the evidence.

It would consume the OOS set as training data.

OOS Is a Consumable Resource

This gives us another important concept.

An untouched OOS period has informational value precisely because the strategy has not been selected against it.

Once repeatedly inspected and optimized against:

OOS

gradually becomes:

IS.

Therefore the system could eventually track:

Dataset exposure count

or:

Validation contamination state.

Example:

OOS_2025_2026

Exposure = 1

Status = CLEAN

After repeated adaptive tuning:

Exposure = 47

Status = CONTAMINATED

The file itself has not changed.

Its epistemic role has.

Scaling Evidence With Search

As search throughput increases, validation may need to become stronger through combinations of:

untouched OOS

walk-forward testing

minimum sample size

multiple-testing correction

parameter stability

regime diversity

economic rationale

paper trading

forward observation

independent replication

Not every experiment needs every control.

But:

more search freedom should never silently imply less proof.

Human Review Cannot Scale Linearly

If an agent runs:

10,000 experiments/day

David cannot manually inspect all 10,000. 😂🐸

Therefore human approval alone is not a scalable research-control architecture.

We need automated filtering that preserves governance:

Research Agent

↓

Experiment Registry

↓

Automated Validation

↓

Evidence Package

↓

only strongest candidates:

Risk / Human Review

This keeps human attention focused where consequences increase.

Relationship to Existing Projects HQ

#052 — Confidence Can Change Without Changing the Strategy

prevents premature reoptimization.

#054 — Map Dependencies Before Trusting Metrics

helps identify correlated evidence.

#055 — Control Costs Are Part of the Cost of Autonomy

reminds us that validation consumes resources.

#056 — Capability ≠ Authority

separates intelligence from permission.

#059 — Evidence Should Change State Through Defined Transitions

defines how research results alter canonical state.

#060 — Failure Evidence Must Survive the Failure

preserves rejected experiments.

And now:

#062 — Research Throughput Must Not Dilute Evidence Standards.

Proposed Research Flow

Hypothesis

↓

PREREGISTER

↓

Experiment ID

↓

RUN

↓

STORE ALL RESULTS

↓

VALIDATE

↓

one of:

REJECT

PARK

REPLICATE

PROMOTE TO OOS

↓

EVIDENCE PACKAGE

↓

only then:

STRATEGY CANDIDATE

The agent can accelerate every step.

But it cannot silently skip one.

Projects HQ Principle

The faster we can search, the more carefully we must distinguish discovery from evidence.

Shortest version:

THROUGHPUT ≠ EVIDENCE.

And my favourite operational version for Nekonečný Mír:

Automation may accelerate experiments. It must never automate self-deception.

Future Applications

Research Constitution v1.0 · Experiment Registry · preregistration · OOS contamination tracking · multiple-testing controls · strategy lineage · Evidence Package · automated validation · DB1 · EF2 · Research Agent · Quant Agent · GitHub research history

Origin

Daily AI Trading Brief — 08. 09. 2026

Inspired by OpenAI’s September 6 research-acceleration report, which says coding agents are contributing to substantially more code and experiments inside OpenAI while also cautioning that several variables—including increased compute—affect the observed acceleration. The general lesson for autonomous quantitative research is that dramatically higher experimental throughput increases productivity, but also increases the need to preserve rigorous evidence standards and the full history of unsuccessful trials. 

Status

🟢 Active strategic principle

Tags

Projects HQ · Nekonečný Mír · AI Agents · Research · Experiments · Evidence · OOS · Validation · Trading

Revision

v1.0 — 08. 09. 2026
