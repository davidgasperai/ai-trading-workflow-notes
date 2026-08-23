🐸 PROJECTS HQ INSIGHT #046

Date: 23. 08. 2026

Title

The Researcher May Adapt. The Test Must Not.

Core Idea

Autonomous research becomes dangerous when the same adaptive system can modify both:

the candidate being tested

and

the rules used to judge it.

A research agent should be free to explore hypotheses.

It should not be free to redefine the evidence required for success.

Why It Matters

Self-improving research creates a subtle feedback problem.

Suppose an agent:

1. proposes a strategy,
2. tests it,
3. learns from the result,
4. modifies the strategy,
5. tests again.

This can be productive.

But if the agent can also alter:

* data splits,
* labels,
* preprocessing,
* evaluation windows,
* transaction-cost assumptions,
* success thresholds,
* or untouched holdout data,

then adaptation can gradually optimize the test itself.

The resulting backtest may become increasingly impressive while the underlying evidence becomes increasingly weak.

Therefore autonomous improvement needs an asymmetric architecture:

adaptive researcher + fixed experimental contract.

Impact on Nekonečný Mír

* Research agents may propose hypotheses.
* Agents may generate bounded strategy variants.
* Agents may learn from previously validated experiments.
* Research data and validation data must remain structurally separated.
* Untouched holdout data must be inaccessible during candidate generation.
* Evaluation code should sit outside the agent’s writable surface.
* Transaction-cost assumptions must not change opportunistically.
* Pass/fail criteria should be defined before seeing validation results.
* Failed experiments remain evidence and should not disappear.
* Only validated results may update persistent research knowledge.
* Strategy adaptation must not modify the definition of success.
* A new experimental contract requires a new experiment lineage.

Proposed Research Boundary

Research Agent

↓

Hypothesis

↓

Bounded candidate modification

↓

SEALED EVALUATION SANDBOX

* frozen data split
* frozen labels
* frozen evaluator
* frozen costs
* frozen success criteria
* inaccessible holdout

↓

Evidence

↓

Validation decision

↓

only validated evidence

↓

Persistent Research State

↓

Next hypothesis

Projects HQ Principle

The researcher may adapt. The test must not.

Builds On

#035 — If a Decision Cannot Be Reconstructed, It Cannot Be Trusted
#037 — Speed Must Never Bypass Evidence
#040 — Automate Only What You Can Explain
#041 — A Benchmark Is Evidence Only for the Environment It Measured
#043 — Validate the Boundary, Not Only the Average
#045 — Optimize for Failure Magnitude, Not Only Failure Frequency

Future Applications

* Research Constitution v1.0
* Experiment Registry
* sealed validation sandbox
* immutable evaluation code
* protected holdout datasets
* experiment lineage
* validated-evidence memory
* Quant Agent
* Research Agent
* automated walk-forward validation

Origin

Daily AI Trading Brief — 23. 08. 2026

Inspired by AQuA’s use of sealed experimental sandboxes and constrained autonomous iteration, in which agents may improve candidates while the data path and evaluator remain outside their adaptive surface. 

Status

🟢 Active strategic principle

Tags

Projects HQ · Nekonečný Mír · Research Constitution · AI Agents · Quant Research · Validation · Data Leakage · Experiment Integrity

Revision

v1.0 — 23. 08. 2026
