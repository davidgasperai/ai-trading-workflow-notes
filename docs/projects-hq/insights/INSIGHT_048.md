🐸 PROJECTS HQ INSIGHT #048

Date: 25. 08. 2026

Title

Optimize the Workflow, Not the Agent

Core Idea

The performance of an autonomous system is not determined by model intelligence alone.

It emerges from the combination of:

model + context + workflow + tools + boundaries + evaluation.

Therefore improving the model is only one way to improve the system.

Often, improving the process around the model can produce greater gains in reliability, cost and useful output.

Why It Matters

A powerful agent operating inside a weak workflow can:

* repeat unnecessary work,
* consume excessive compute,
* optimize the wrong objective,
* make changes before requirements are clear,
* produce results that are difficult to reproduce,
* or move too quickly from idea to consequence.

A structured workflow can constrain these failure modes before additional intelligence is required.

The important optimization target is therefore not:

How intelligent is the agent?

but:

How efficiently does the complete system transform resources into validated useful outcomes?

Impact on Nekonečný Mír

* Do not evaluate agents only by benchmark scores.
* Measure cost per validated experiment.
* Measure time per validated experiment.
* Separate hypothesis generation from validation.
* Define requirements before implementation.
* Introduce checkpoints before irreversible stages.
* Prefer structured context over repeated free-form prompting.
* Keep evaluation independent from candidate generation.
* Record failed experiments as useful output.
* Measure reproducibility, not merely speed.
* Allow different models for different workflow stages.
* Avoid using frontier models where cheaper models pass the required eval.
* Optimize the entire research pipeline rather than individual model performance.

Proposed Efficiency Metric

Instead of:

Tokens consumed

or:

Experiments generated

prefer:

Validated useful outcomes

÷

Cost + compute + time + human attention

This is not yet a formal project metric.

It is a design direction for future experimentation.

Example Future Workflow

Research question

↓

Research Contract

↓

Hypothesis Agent

↓

Candidate specification

↓

Quant implementation

↓

Sealed evaluator

↓

Validation evidence

↓

Decision

↓

Experiment Registry

↓

Persistent knowledge

Each stage can use the least expensive model that reliably satisfies its own evals.

Projects HQ Principle

Do not optimize how impressive the agent looks. Optimize how reliably the system produces evidence you can trust.

Builds On

#037 — Speed Must Never Bypass Evidence
#041 — A Benchmark Is Evidence Only for the Environment It Measured
#046 — The Researcher May Adapt. The Test Must Not.
#047 — Authority Should Be Bounded, Not Merely Granted

Future Applications

Research Constitution v1.0 · Experiment Registry · Research Contract · model routing · cost accounting · eval-driven model selection · sealed evaluator · Research Agent · Quant Agent · Documentation Agent

Origin

Daily AI Trading Brief — 25. 08. 2026

Inspired by OpenAI and AWS’s GPT‑5.6/Kiro work showing how structured requirements, technical designs, checkpoints and testing can materially change the economics of agentic coding rather than relying on model capability alone. 

Status

🟢 Active strategic principle

Tags

Projects HQ · Nekonečný Mír · AI Agents · Research Constitution · Workflow · Efficiency · Validation · Cost

Revision

v1.0 — 25. 08. 2026
