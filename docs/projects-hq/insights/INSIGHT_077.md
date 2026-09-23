# PROJECTS HQ INSIGHT #077

## Date

23. 09. 2026

## Title

# When Intelligence Becomes Cheap, Verification Becomes the Scarce Resource

---

## Core Idea

Today OpenAI and Anthropic are both pushing capable AI toward lower operating cost.

This changes the economics of agent systems.

Historically, we might ask:

    Can we afford another model call?

Increasingly, the better question may become:

    What should the additional model call verify?

As intelligence becomes cheaper, we can create:

    more agents
    more analysis
    more proposals
    more code
    more decisions
    more actions

But none of those automatically creates:

    more truth.

Therefore:

> **When intelligence becomes cheap, verification becomes the scarce resource.**

---

## Cheap Intelligence Changes the Bottleneck

Imagine:

    One strong agent
    costs 100 units.

We can afford:

    1 agent.

Later:

    capable agent
    costs 10 units.

Now we can afford:

    10 agents.

The naive response is:

    10× MORE ACTION.

The safer response may be:

    4× ACTION
    +
    3× VERIFICATION
    +
    2× RED TEAM
    +
    1× RECONCILIATION

Cheaper intelligence should not only increase throughput.

It should increase assurance.

---

## Capability Supply Can Explode

Suppose future Nekonečný Mír can cheaply run:

    Research Agent
    Quant Agent
    Risk Agent
    Trading Agent
    Safety Agent
    Reconciliation Agent
    Documentation Agent
    Red-Team Agent

This is exciting.

But it creates a new problem.

Each agent can produce:

    claims
    recommendations
    code
    alerts
    evidence
    actions

The number of outputs may grow faster than David's ability to inspect them.

Therefore:

    AGENT OUTPUT ↑↑
    HUMAN ATTENTION ≠ ↑↑

The bottleneck moves.

---

## The New Scarcity

In early AI systems:

    INTELLIGENCE
    was scarce.

In mature agent systems:

    TRUSTWORTHY VERIFICATION
    may become scarce.

Why?

Because generating an answer can be cheap.

Determining whether the answer deserves authority may still require:

    independent evidence
    provenance
    testing
    reconciliation
    policy evaluation
    human judgment

---

## Generation ≠ Verification

An agent can cheaply produce:

    "DB1 is profitable."

But verification may require:

    exact dataset
    exact code version
    exact parameters
    exact fees
    exact slippage
    exact date range
    exact trade log
    independent recomputation

Therefore:

    CHEAP CLAIM
    ≠
    CHEAP TRUTH

---

## More Agents Can Create False Confidence

Imagine:

    Agent A:
    BUY

    Agent B:
    BUY

    Agent C:
    BUY

We may think:

    THREE AGENTS AGREE.

But suppose:

    all three use
    the same market feed
    the same prompt
    the same model family
    the same flawed assumption.

Then:

    3 votes
    may still equal
    1 failure mode.

---

## Diversity Matters

Independent verification requires more than:

    another agent.

It may require:

    different model
    different data source
    different method
    different code path
    different assumption set

Therefore:

> **Agent count is not evidence diversity.**

---

## Cheap Agents Should Fund Independence

If model cost falls, we can spend the savings on:

    cross-model verification
    adversarial review
    independent calculation
    data-source comparison
    regression testing
    reconciliation

This may produce more value than simply increasing execution frequency.

---

## The Verification Budget

Future Nekonečný Mír could conceptually allocate:

    COMPUTE BUDGET

into:

    PRODUCTION COMPUTE

and:

    VERIFICATION COMPUTE

Example:

    60%
    research / strategy / execution

    40%
    validation / risk / reconciliation / red team

The exact percentages are not important today.

The principle is.

Verification should have an explicit budget.

---

## Verification Is Work

A dangerous assumption is:

    verification happens automatically.

It does not.

Verification consumes:

    compute
    latency
    data
    attention
    engineering
    money

Therefore it must be designed as a first-class system function.

---

## Consequence Determines Verification Budget

From #066:

    CONSEQUENCE ↑
    →
    CONTROL STRENGTH ↑

Today:

    CONSEQUENCE ↑
    →
    VERIFICATION BUDGET ↑

Example:

    Documentation summary

may need:

    lightweight check.

But:

    LIVE TRADE

may require:

    identity verification
    scope verification
    risk verification
    market-state freshness
    broker-state reconciliation
    execution receipt

---

## Verification Can Be Cheaper Than Failure

Suppose:

    additional verification
    costs $0.05.

A bad live trade may cost:

    $50
    $500
    or more.

Then:

    VERIFYING MORE

may be economically rational even before considering safety.

Cheaper models strengthen this argument.

---

## Multi-Model Verification

Today's model competition suggests an interesting architecture.

Future system:

    Model A
    ↓
    produces strategy claim

    Model B
    ↓
    challenges assumptions

    deterministic code
    ↓
    recomputes metrics

    Risk Agent
    ↓
    evaluates consequence

    Reconciliation Agent
    ↓
    verifies observed state

No single model becomes the oracle.

---

## Models Are Witnesses, Not Oracles

This gives us a useful mental model.

An AI model can be treated as:

    WITNESS

It can report:

    what it observed
    what it inferred
    what it recommends

But a witness does not automatically determine reality.

Therefore:

# MODEL = WITNESS, NOT ORACLE

---

## Evidence Hierarchy

Different claims deserve different evidence.

Example:

    "This documentation is clear."

may rely on:

    model judgment.

But:

    "The broker position is zero."

should preferably rely on:

    broker state
    fills
    balances
    reconciliation

The more objective the state, the less we should substitute model opinion for direct evidence.

---

## Deterministic Verification

Cheap AI does not mean every verifier should be AI.

Often the strongest verifier is:

    deterministic code.

Example:

    Strategy Agent:
    PF = 1.42

Verifier:

    Python recomputation
    from immutable trade log.

This may be stronger than asking another model:

    "Does 1.42 look right?"

😂🐸

---

## Use AI Where Judgment Is Needed

AI verification is useful for:

    ambiguity
    reasoning
    semantic conflict
    adversarial review
    edge-case discovery

Deterministic verification is useful for:

    arithmetic
    schema
    hashes
    limits
    signatures
    state equality

The system should use each where it is strongest.

---

## Verification Routing

A future Verification Router might ask:

    What kind of claim is this?

If:

    NUMERICAL

route to:

    deterministic recomputation.

If:

    EXTERNAL STATE

route to:

    independent source.

If:

    POLICY

route to:

    policy engine.

If:

    SEMANTIC / STRATEGIC

route to:

    independent model review.

If:

    HIGH CONSEQUENCE + AMBIGUOUS

route to:

    human.

---

## Human Attention Becomes Premium Verification

As agent output scales, David's attention becomes increasingly valuable.

Therefore human review should not be spent on:

    routine confirmations.

It should be reserved for:

    unresolved ambiguity
    high consequence
    policy changes
    recovery authorization
    novel failure modes

Human attention becomes:

# PREMIUM VERIFICATION

---

## Cheap Intelligence Should Reduce Human Noise

A badly designed agent system uses cheap AI to generate:

    more alerts
    more reports
    more dashboards
    more messages

and overwhelms the human.

A better system uses cheap AI to:

    filter
    correlate
    verify
    summarize
    escalate only what matters

Therefore:

    AI COST ↓

should ideally produce:

    HUMAN NOISE ↓

not:

    HUMAN NOISE ↑

---

## Verification Debt

Software has:

    technical debt.

Agent systems may accumulate:

# VERIFICATION DEBT

This happens when:

    claims are accepted
    without sufficient evidence

    shortcuts become permanent

    assumptions stop being checked

    temporary trust becomes inherited trust

    unverified outputs become dependencies

Eventually the system contains many beliefs nobody can prove.

---

## Verification Debt Compounds

Suppose:

    Claim A
    unverified

becomes input to:

    Claim B.

Then B becomes input to:

    Decision C.

Now checking C may require reconstructing:

    A
    B
    C

The cost of delayed verification grows.

Therefore:

> **Verify important assumptions close to where they enter the system.**

---

## Git Helps Again

Our Git workflow gives us a practical verification primitive.

An agent can say:

    "I changed the strategy."

Git can show:

    EXACT DIFF.

An agent can say:

    "This is the tested version."

Git can identify:

    EXACT COMMIT.

An agent can say:

    "Nothing else changed."

Git can help verify that claim.

This is why Git provenance matters.

---

## Commit-Based Evidence

Eventually:

    BACKTEST RESULT

should ideally reference:

    commit SHA
    dataset version
    configuration hash
    environment
    timestamp

Then:

    RESULT
    ↔
    REPRODUCIBLE STATE

The model's memory is no longer the evidence.

The system state is.

---

## Cheap Coding Agents Increase the Need for Git

If coding agents become cheaper:

    CODE CHANGE RATE ↑

Therefore:

    DIFF VOLUME ↑
    TEST VOLUME ↑
    REVIEW NEED ↑

Git becomes more valuable, not less.

Cheap code generation without provenance would create chaos faster.

---

## Verification Through Reproduction

One of the strongest forms of verification is:

    REPRODUCE THE RESULT.

Agent A:

    DB1 PF = 1.42

Independent verifier:

    checks out commit
    loads dataset
    runs test
    obtains PF = 1.42

Now confidence rises substantially.

---

## Disagreement Is Valuable

Suppose:

    Agent A:
    PF = 1.42

    Independent run:
    PF = 1.17

That disagreement is not system failure.

It is:

    HIGH-VALUE INFORMATION.

The verification layer discovered hidden uncertainty before capital was exposed.

---

## Verification Should Be Able to Block

If verification is purely advisory:

    verifier:
    "I disagree."

    trading agent:
    "Thanks."
    BUY

😂👻

then verification is not a control.

From #069:

> A Policy Is Not a Control Until the System Can Enforce It.

Likewise:

> Verification is not a control unless consequential disagreement can affect authority.

---

## Verification Failure State

Possible rule:

    REQUIRED VERIFICATION
    =
    FAILED

then:

    AUTHORITY
    ↓

Example:

    NORMAL
    →
    RESTRICTED

or:

    NO NEW EXPOSURE

until conflict is resolved.

---

## Verification Receipt

Future system might record:

    verification_id

    claim_id

    verifier_identity

    verification_method

    evidence_refs

    result:
      PASS / FAIL / CONFLICT / UNKNOWN

    confidence

    timestamp

    policy_version

Now verification itself becomes auditable.

---

## Verification Provenance

Just as evidence needs provenance:

    verification
    needs provenance.

We must know:

    who verified
    how
    using what data
    against which version
    when

Otherwise:

    VERIFIED

is merely another unsupported claim.

---

## Recursive Verification Problem

Of course this creates a philosophical question:

    Who verifies the verifier?

We cannot recurse forever.

Therefore systems need:

    TRUST ROOTS

such as:

    cryptographic identity
    deterministic invariants
    immutable logs
    broker truth
    human authority
    independently controlled sources

Verification eventually anchors to evidence outside the reasoning chain.

---

## The Emerging Architecture

Our system increasingly looks like:

    AGENT
    ↓
    CLAIM / PROPOSAL / ACTION
    ↓
    CONSEQUENCE CLASSIFICATION
    ↓
    VERIFICATION ROUTER
    ↓
    ┌─────────────────────┐
    │ deterministic check │
    │ independent model   │
    │ external source     │
    │ policy engine       │
    │ human review        │
    └─────────────────────┘
    ↓
    VERIFICATION RECEIPT
    ↓
    AUTHORITY DECISION
    ↓
    EXECUTION
    ↓
    RECONCILIATION

Cheap intelligence makes this architecture increasingly affordable.

---

## Projects HQ Principle

> **When intelligence becomes cheap, verification becomes the scarce resource.**

Shortest version:

# SPEND CHEAP INTELLIGENCE ON VERIFICATION

And the Nekonečný Mír version:

> **As model and agent costs fall, do not spend every efficiency gain on generating more actions. Allocate increasing capacity to independent verification, adversarial review, deterministic recomputation, provenance and reconciliation. More intelligence should increase assurance, not merely throughput.**

---

## Builds On

**#058** — Critical Controls Need Independent Evidence  
**#066** — Consequence Should Determine the Strength of the Control  
**#068** — Less Human Supervision Requires More Machine-Verifiable Evidence  
**#069** — A Policy Is Not a Control Until the System Can Enforce It  
**#071** — Every Consequential Action Needs an Expected State and an Observed State  
**#072** — A Failure Is Not Closed Until the System Has Changed  
**#073** — Authority Must Be Bound to Verifiable Scope  
**#074** — Trust Must Not Propagate Automatically Across Agent Chains  
**#075** — Incident Signals Must Cross Boundaries Without Transferring Authority  
**#076** — Every Consequential Safety Signal Needs an Acknowledged Owner

---

## Future Applications

`Verification Budget` · `Verification Router` · `Multi-Model Verification` · `Deterministic Verification` · `Verification Receipt` · `Verification Debt` · `Premium Human Review` · `Commit-Based Evidence` · `Reproducible Backtests` · `Independent Recalculation`

---

## Origin

**Daily AI Trading Brief — 23. 09. 2026**

Inspired by the near-simultaneous release of lower-cost capable AI models from OpenAI and Anthropic, demonstrating the continuing decline in the cost of high-level machine intelligence.

The generalized lesson for autonomous trading is that as generating analysis, code and decisions becomes cheaper, the limiting resource shifts toward trustworthy verification of those outputs.

---

## Status

🟢 Active strategic principle

---

## Tags

`Projects HQ` · `Nekonečný Mír` · `AI Agents` · `Verification` · `Evidence` · `Multi-Model` · `Git` · `Provenance` · `Safety` · `Trading`

---

## Revision

**v1.0 — 23. 09. 2026**
