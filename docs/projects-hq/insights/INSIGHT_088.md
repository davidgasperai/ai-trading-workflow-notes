# PROJECTS HQ INSIGHT #088

## Date
5. 10. 2026

## Title
# Measure Outcomes, Not Agent Activity

---

## Core Idea

Autonomous systems generate enormous amounts of visible activity.

They can:

    call tools
    browse sources
    write code
    spawn subagents
    generate files
    run tests
    send requests
    execute trades.

Activity feels like progress.

But activity is not the objective.

Therefore:

# ACTIVITY ≠ VALUE.

The correct question is not:

    "How much did the agent do?"

It is:

    "What validated outcome did the system produce?"

---

## The Activity Trap

Agent systems make motion extremely cheap.

A system may perform:

    100 tool calls
    20 searches
    15 code changes
    8 subagent runs

and still produce:

    no useful result.

If dashboards reward activity:

    the system can appear productive
    while accomplishing very little.

This is the:

# ACTIVITY TRAP.

---

## Human Analogy

A human employee who sends:

    100 emails

is not automatically more productive than one who sends:

    5 emails

and solves the problem.

Agentic systems need the same distinction.

Measure:

    resolved objective

not:

    visible motion.

---

## Trading Analogy

A trading system executes:

    500 trades.

Another executes:

    50 trades.

The first system is not automatically better.

What matters is:

    expectancy
    drawdown
    risk-adjusted return
    execution quality
    robustness
    transaction cost
    regime stability.

Therefore:

# TRADE COUNT ≠ EDGE.

---

## Tool Calls

A common future agent metric may be:

    tool_calls_per_task.

But alone this metric says almost nothing.

More tool calls may mean:

    deeper research

or:

    inefficient wandering.

Therefore tool usage must be evaluated against:

    validated outcome.

---

## Outcome Metric

For each autonomous task define:

    OBJECTIVE
    SUCCESS CRITERIA
    COST
    RISK BUDGET
    VALIDATION METHOD.

Then evaluate:

    DID THE OUTCOME OCCUR?

Only afterward ask:

    HOW MUCH ACTIVITY
    WAS REQUIRED?

---

## Validated Outcome

An outcome should not be accepted merely because:

    the agent reports success.

From #080:

    OBSERVED STATE
    >
    SELF-REPORTED STATE.

Therefore:

    AGENT:
        "Task completed."

must become:

    VALIDATOR:
        "Expected external state observed."

---

## Efficiency

Once outcome quality is known:

    efficiency

becomes meaningful.

Example:

    Agent A:
        success = yes
        cost = $2.10
        duration = 90 sec

    Agent B:
        success = yes
        cost = $0.31
        duration = 18 sec.

If outcome quality is equivalent:

    Agent B

is the superior system.

---

## Model Routing

Not every task needs:

    maximum intelligence.

Future Nekonečný Mír can route:

    simple extraction
        →
    low-cost model

    standard analysis
        →
    balanced model

    difficult reasoning
        →
    frontier model.

The objective:

# MINIMUM SUFFICIENT INTELLIGENCE.

Not:

# MAXIMUM AVAILABLE INTELLIGENCE.

---

## Cost per Validated Outcome

A useful metric:

    TOTAL COMPUTE COST
    ------------------
    VALIDATED OUTCOMES

or:

# COST PER VALIDATED OUTCOME.

This is more meaningful than:

    tokens consumed
    model calls
    agent steps.

---

## Trading Version

For a trading agent:

    compute cost
    market data cost
    spread
    fees
    slippage
    opportunity cost

must eventually be compared with:

    validated trading edge.

A strategy that earns:

    $1

while consuming:

    $2

of infrastructure is not autonomous alpha.

It is:

    expensive activity.

---

## Research Agent

Research Agent should not be rewarded for:

    number of articles read.

It should be evaluated on:

    relevant evidence found
    source quality
    contradiction detection
    uncertainty reduction
    decision usefulness.

---

## Coding Agent

Coding Agent should not be rewarded for:

    lines of code.

It should be evaluated on:

    requirement satisfaction
    tests passed
    regression avoidance
    maintainability
    verified behavior.

---

## Risk Agent

Risk Agent should not be rewarded for:

    number of warnings.

It should be evaluated on:

    material risks detected
    false positives
    prevented failures
    preserved opportunity.

---

## Trading Agent

Trading Agent should not be rewarded for:

    number of trades.

It should be evaluated on:

    expectancy
    risk-adjusted return
    drawdown
    execution quality
    policy compliance.

---

## Agent Swarms

Multi-agent systems make the activity trap worse.

Ten agents can generate:

    ten times the conversation

without generating:

    ten times the value.

Therefore:

# MORE AGENTS ≠ MORE INTELLIGENCE.

Agent count should increase only when:

    specialization
    parallelism
    independent verification

produce measurable improvement.

---

## Subagent Budget

Every spawned subagent should have:

    task
    budget
    deadline
    output schema
    termination condition.

Otherwise agent swarms can become:

    recursive bureaucracy.

---

## Stop Condition

A capable autonomous system must know when:

    enough evidence exists.

Without a stop condition:

    research can continue forever.

Therefore:

    additional work

should require:

    expected information gain
        >
    expected cost.

---

## Marginal Value

For every additional step ask:

    What new uncertainty
    can this step reduce?

If answer is:

    none,

then:

    STOP.

This converts autonomous reasoning from:

    unlimited exploration

into:

    bounded optimization.

---

## Evidence Saturation

Suppose Research Agent has:

    3 independent high-quality sources

confirming the same fact.

Reading another:

    30 articles

may produce little additional value.

The system should recognize:

# EVIDENCE SATURATION.

Then move forward.

---

## Quality Before Efficiency

Important:

Do not optimize cost before validating quality.

Correct sequence:

    1. PROVE OUTCOME QUALITY
    2. MEASURE COST
    3. REDUCE COST
    4. REVALIDATE QUALITY.

Otherwise cheap failure can appear:

    efficient.

---

## Cheapest Failure Is Still Failure

A $0.01 agent that gives:

    wrong answer

is not better than a $1 agent that reliably solves:

    a $100 problem.

Therefore optimization target is not:

    MINIMUM COST.

It is:

# MINIMUM COST
# SUBJECT TO REQUIRED QUALITY.

---

## Relationship to #077

#077:

    WHEN INTELLIGENCE BECOMES CHEAP,
    VERIFICATION BECOMES
    THE SCARCE RESOURCE.

#088:

    once outcomes are verified,
    measure the cost required
    to produce them.

Together:

    INTELLIGENCE
        ↓
    OUTCOME
        ↓
    VERIFICATION
        ↓
    ECONOMICS.

---

## Relationship to #080

#080:

    RECORD OBSERVED EFFECTS.

#088:

    use those observed effects
    as the denominator
    of productivity.

---

## Relationship to #085

#085:

    REPLAY THE EVIDENCE.

#088:

    reconstruct not only
    why the system acted,
    but whether the action
    produced value.

---

## Relationship to #087

#087:

    VERIFY → AUTHORIZE
    → EXECUTE → OBSERVE.

#088 adds:

    OBSERVE
        ↓
    EVALUATE
        ↓
    MEASURE VALUE
        ↓
    MEASURE COST.

Safety tells us:

    whether the action was allowed.

Verification tells us:

    what actually happened.

Economics tells us:

    whether it was worth doing.

---

## Future Nekonečný Mír

Future architecture:

    OBJECTIVE
        ↓
    AGENT PLAN
        ↓
    BOUNDED EXECUTION
        ↓
    OBSERVED EFFECT
        ↓
    OUTCOME VALIDATOR
        ↓
    VALUE MEASUREMENT
        ↓
    COST MEASUREMENT
        ↓
    LEARNING LOOP.

The system should optimize:

    validated value

not:

    autonomous activity.

---

## Proposed Metrics

Future Projects HQ metrics may include:

    task_success_rate

    verified_outcome_rate

    cost_per_validated_outcome

    tool_calls_per_success

    tokens_per_success

    latency_per_success

    human_interventions_per_success

    risk_events_per_success

    false_positive_rate

    marginal_information_gain.

For trading:

    expectancy

    profit_factor

    max_drawdown

    Sharpe / Sortino

    slippage

    fees

    compute_cost

    net_value_after_all_costs.

---

## Anti-Metric

Never optimize:

    number_of_agent_actions.

It is diagnostic information.

Not:

    the objective function.

---

## Projects HQ Principle

> Autonomous systems should be evaluated by validated outcomes rather than visible activity. Measure whether the intended external state was actually achieved, then compare its quality, risk, latency and total cost. Tool calls, tokens, subagents, lines of code and trade counts are means—not objectives.

Shortest version:

# ACTIVITY ≠ VALUE.

Operational version:

# OUTCOME → VERIFY → VALUE → COST.

---

## Builds On

#077 — When Intelligence Becomes Cheap, Verification Becomes the Scarce Resource  
#080 — Intent Logs Are Not Enough — Record Observed Effects  
#085 — Every Consequential Action Must Be Forensically Reconstructable  
#087 — Enforcement Must Live at the Point of Consequence

---

## Future Applications

Model Routing · Agent Economics · Multi-Agent Budgeting · Research Stop Conditions · Trading Evaluation · Cost Control · Outcome Validation · Agent Benchmarking · Compute Allocation

---

## Origin

Daily AI Trading Brief — 5. 10. 2026

Inspired by increasingly capable models that can autonomously coordinate tools and subagents, alongside the rapidly growing economic cost of AI infrastructure.

The generalized lesson for Nekonečný Mír is that increasing autonomous activity is useful only when it produces more validated value.

---

## Status

🟢 Active strategic principle

---

## Tags

Projects HQ · Nekonečný Mír · AI Agents · Agent Economics · Model Routing · Validation · Trading · Efficiency · Cost · Multi-Agent Systems

---

## Revision

v1.0 — 5. 10. 2026
