🐸 PROJECTS HQ INSIGHT #071

Date: 17. 09. 2026

Title

Every Consequential Action Needs an Expected State and an Observed State

⸻

Core Idea

Yesterday we introduced:

CONTROL LATENCY
<
RISK PROPAGATION TIME

But fast verification still needs something fundamental.

The system must know:

WHAT SHOULD HAVE HAPPENED?

and compare it with:

WHAT ACTUALLY HAPPENED?

Therefore:

Every consequential action should produce an expected state that can later be compared with independently observed reality.

⸻

The Missing Comparison

Imagine:

Trading Agent
↓
BUY 0.01 BTC
↓
Broker API returns SUCCESS

The agent reports:

DONE

😂🐸

But what exactly did we verify?

Only that the request received a successful response.

We still do not know:

Was the order accepted?
Was it filled?
At what price?
What position now exists?
Did fees change exposure?
Did another order execute simultaneously?
Does broker reality match internal state?

Therefore:

REQUEST SUCCESS
≠
OUTCOME VERIFIED

⸻

Expected State

Before execution, the system should be able to describe what reality should look like afterward.

For example:

CURRENT BTC POSITION
0.000 BTC
REQUEST
BUY 0.010 BTC
EXPECTED POSITION
0.010 BTC

This creates:

EXPECTED STATE

⸻

Observed State

After execution, a separate observation asks the real system:

BROKER POSITION?

Response:

0.010 BTC

This creates:

OBSERVED STATE

Now we can compare:

EXPECTED = 0.010
OBSERVED = 0.010

Result:

RECONCILED = TRUE

⸻

When Reality Disagrees

Suppose instead:

EXPECTED
0.010 BTC
OBSERVED
0.020 BTC

The correct response is not:

Probably fine.

😂🐸

It is:

STATE MISMATCH

And from our previous architecture:

STATE MISMATCH
↓
AUTHORITY ↓
↓
NO NEW EXPOSURE
↓
INVESTIGATE

⸻

Today’s OpenAI Parallel

OpenAI announced a framework for reporting unexpected or unauthorized model behavior and published six examples of misalignment. 

The underlying concept can be generalized.

Misalignment becomes observable only because there is some difference between:

INTENDED BEHAVIOUR

and:

OBSERVED BEHAVIOUR

Without an expected state, the system may observe activity but cannot reliably determine whether that activity is anomalous.

⸻

Expected Behaviour Is Not Only a Prompt

This is important.

Weak:

Prompt:
"Please behave safely."

Stronger:

EXPECTED:
agent may read file
FORBIDDEN:
agent may not upload file externally

Now behavior can be evaluated against a machine-readable boundary.

For trading:

EXPECTED:
position <= 0.5% risk
FORBIDDEN:
position > 0.5% risk

The more explicit the expected state, the easier verification becomes.

⸻

Intent → Expectation → Reality

We can now distinguish three things:

INTENT
What did the agent want to do?
EXPECTED STATE
What should happen if the action succeeds?
OBSERVED STATE
What actually exists?

These must not be collapsed into one variable.

⸻

Example: Limit Order

Agent requests:

BUY BTC
LIMIT 75,000
SIZE 0.010

Intent:

Acquire up to 0.010 BTC
only at <= 75,000

Immediate expected state may be:

ORDER = OPEN
POSITION = UNCHANGED

Later:

ORDER = FILLED
POSITION = +0.010 BTC

Verification therefore depends on lifecycle state.

⸻

State Transitions

This suggests another useful concept:

EXPECTED STATE TRANSITION

Instead of merely saying:

STATE = X

we define:

STATE A
↓
AUTHORIZED ACTION
↓
STATE B

Example:

NO POSITION
↓
BUY 0.010 BTC
↓
LONG 0.010 BTC

Only certain transitions are permitted.

⸻

Unexpected Transition

Suppose:

NO POSITION
↓
BUY 0.010 BTC
↓
LONG 0.020 BTC

The destination state is not the authorized destination.

Therefore:

TRANSITION INVALID

even if the API itself returned success.

⸻

This Is Stronger Than Logging

A log says:

BUY submitted 14:07:03

State reconciliation says:

Before:
0.000 BTC
Expected:
0.010 BTC
Observed:
0.020 BTC
Difference:
+0.010 BTC
Status:
MISMATCH

The second tells us whether reality agrees with the system’s model.

⸻

State Delta

We can represent the difference as:

STATE DELTA

Conceptually:

DELTA
=
OBSERVED STATE
-
EXPECTED STATE

For numerical values this may literally be calculated.

For categorical states:

EXPECTED:
ORDER_FILLED
OBSERVED:
ORDER_PENDING

we simply have:

DELTA = NONZERO

or:

RECONCILED = FALSE

⸻

Tolerance Matters

Reality is not always exact.

Suppose:

EXPECTED FILL
75,000
OBSERVED FILL
75,003

That may be perfectly acceptable.

Therefore controls may need:

EXPECTED STATE
+
TOLERANCE

Example:

MAX_SLIPPAGE = 10 bps

Then:

within tolerance
→ VERIFIED
outside tolerance
→ ANOMALY

⸻

Not Every Mismatch Means Catastrophe

This connects to #065.

Mismatch severity may determine authority reduction.

Example:

tiny acceptable rounding difference
→ NORMAL
unexpected slippage
→ CAUTION
position mismatch
→ MANAGE ONLY
unknown broker state
→ KILL NEW EXECUTION

Safety remains graduated.

⸻

Expected State Must Be Created Before Execution

This is crucial.

If the agent performs an action and afterward decides what it meant to happen, it can rationalize almost any outcome.

😂🐸

Therefore:

EXPECTED STATE

should ideally be committed before execution.

Then reality cannot rewrite history.

⸻

Pre-Commitment

Conceptually:

REQUEST
↓
EXPECTED STATE GENERATED
↓
POLICY VALIDATES
↓
EXPECTED STATE STORED
↓
EXECUTION
↓
OBSERVATION
↓
COMPARE

This creates a clean causal record.

⸻

Execution Receipt Evolves

Our #068 EXECUTION RECEIPT can now include:

receipt_id
timestamp
agent_identity
mandate_id
request
pre_execution_state
expected_post_execution_state
observed_post_execution_state
state_delta
tolerance
verification_status
evidence_refs

Now the receipt describes not merely what was requested.

It describes whether reality agreed.

⸻

Independent Observation Matters

The Trading Agent should not simply say:

I expected 0.010
and I observed 0.010.

😂🐸

Prefer:

Trading Agent
↓
REQUEST

then:

Broker / Independent Reconciliation Agent
↓
OBSERVED STATE

This separates actor from observer.

⸻

Actor ≠ Observer

This gives us another strong principle:

The component that changes reality should not be the sole authority describing what reality became.

For low consequence this may be unnecessary.

For high consequence it becomes valuable.

⸻

Today’s Fed Example

Yesterday before the Fed:

MARKET EXPECTATION:
+25 bp highly likely

Then reality arrived:

OBSERVED:
+25 bp

At first glance:

EXPECTED = OBSERVED

But that does not finish reconciliation.

The event contained additional state:

forward guidance
dot projections
vote distribution
inflation assessment
future hike expectations

The headline matched.

The full state changed more than the headline.

This is why event reconciliation must compare all relevant dimensions, not one number.

⸻

Trading Event Reconciliation

A future Event Agent might produce:

EXPECTED:
Fed +25 bp
Neutral guidance
OBSERVED:
Fed +25 bp
Hawkish guidance
16/18 expect another hike

Therefore:

RATE DECISION:
MATCH
POLICY PATH:
MISMATCH

Overall:

EVENT SURPRISE ≠ ZERO

That is much more useful than:

Fed did what expected.

⸻

Weak Signals Become State Deviations

Today’s OpenAI reporting story adds another layer.

A small unexpected action may not immediately be catastrophic.

But:

EXPECTED
↓
OBSERVED
↓
SMALL DELTA

repeated many times can create:

PATTERN

Therefore we should preserve even small meaningful mismatches.

Yesterday’s anomaly may explain tomorrow’s incident.

⸻

Incident Memory

Possible future flow:

STATE MISMATCH
↓
INCIDENT RECORD
↓
CLASSIFICATION
↓
ROOT CAUSE
↓
CONTROL CHANGE
↓
REGRESSION TEST

Now the system learns operationally.

⸻

Regression Test

After fixing an incident:

same condition
↓
same prohibited transition attempted
↓
control blocks it

Then:

FIX VERIFIED

Without regression testing, the incident may simply return later.

⸻

This Extends #061

#061 said:

Recovery Must Be Gated by Reconciliation.

Today we define reconciliation more precisely:

EXPECTED STATE
vs
OBSERVED STATE

Recovery becomes possible when:

STATE DELTA
=
ACCEPTABLE

⸻

This Extends #068

#068 said:

AUTONOMY ↑
→
EVIDENCE ↑

Now we know what part of that evidence should prove:

Reality
=
Authorized expectation

⸻

This Extends #070

#070 said:

RISK SPEED ↑
→
CONTROL LATENCY ↓

Today:

FAST OBSERVATION
+
NO EXPECTED STATE
=
FAST CONFUSION

😂🐸

Speed alone is insufficient.

The control loop needs a reference state.

⸻

State Reconciliation Loop

Our control loop becomes:

CURRENT STATE
↓
REQUEST
↓
EXPECTED STATE
↓
POLICY
↓
EXECUTION
↓
OBSERVED STATE
↓
COMPARE
↓
RECONCILE
↓
NEW CURRENT STATE

If:

EXPECTED ≠ OBSERVED

then:

AUTHORITY ↓
↓
ESCALATE

⸻

The Larger Principle

Autonomous systems interact with reality.

Reality can disagree with them.

APIs fail.

Orders partially fill.

Data arrives late.

Dependencies change.

Models misunderstand.

Humans intervene.

Therefore:

The internal model of the world must never be assumed to equal the world itself.

It must be checked.

⸻

Projects HQ Principle

Every consequential action needs an expected state and an observed state.

Shortest version:

EXPECT → ACT → OBSERVE → RECONCILE

And the Nekonečný Mír version:

Never let an agent conclude that an action succeeded merely because it executed. Success exists only when observed reality matches the authorized expected state within defined tolerance.

⸻

Builds On

#053 — UNKNOWN ≠ SAFE
#058 — Critical Controls Need Independent Evidence
#061 — Recovery Must Be Gated by Reconciliation
#063 — Automation Must Not Outrun Verification
#068 — Less Human Supervision Requires More Machine-Verifiable Evidence
#069 — A Policy Is Not a Control Until the System Can Enforce It
#070 — Control Latency Must Be Shorter Than Risk Propagation

⸻

Future Applications

Expected State · Observed State · State Delta · Expected State Transition · Execution Receipt · Reconciliation Agent · Incident Memory · Regression Testing · Event Reconciliation · Broker Verification

⸻

Origin

Daily AI Trading Brief — 17. 09. 2026

Inspired by OpenAI’s September 16 announcement of a formal framework for tracking, investigating and regularly disclosing unexpected or unauthorized model behaviour, together with six published misalignment cases. The generalized lesson for autonomous trading is that unexpected behaviour can only be detected reliably when the system has an explicit representation of what was supposed to happen and independently compares that expectation with observed reality. 

⸻

Status

🟢 Active strategic principle

⸻

Tags

Projects HQ · Nekonečný Mír · AI Agents · Expected State · Observed State · Reconciliation · State Delta · Execution Receipt · Verification · Trading

⸻

Revision

v1.0 — 17. 09. 2026
