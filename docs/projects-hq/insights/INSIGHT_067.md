🐸 PROJECTS HQ INSIGHT #067

Date: 13. 09. 2026

Title

A Control Must Have an Escalation Path

Core Idea

Yesterday we said:

CONSEQUENCE → CONTROL

But a control has limited value if it can detect a problem and then has nowhere to send that problem.

A monitoring system may notice:

ANOMALY

A validator may report:

EVIDENCE CONFLICT

A Risk Agent may detect:

POSITION MISMATCH

An independent evaluator may conclude:

SAFETY NOT ESTABLISHED

But then what?

If the controlled agent can simply ignore the warning, the control is informational rather than authoritative.

Therefore:

Every consequential control needs a defined escalation path to an authority capable of changing the system state.

⸻

Detection Is Not Control

Imagine:

Risk Agent:
"Exposure exceeds limit."

Trading Agent:

"Noted."

and continues trading.

😂🐸

We have monitoring.

We do not have control.

A real control needs:

DETECT
↓
ESCALATE
↓
CHANGE AUTHORITY

⸻

The Missing Chain

A stronger architecture looks like:

Observation
↓
Detection
↓
Classification
↓
Escalation
↓
Authority Decision
↓
Enforcement
↓
Verification

Each step answers a different question.

Observation

What happened?

Detection

Is something abnormal?

Classification

How serious is it?

Escalation

Who must now be involved?

Authority Decision

What state should the system enter?

Enforcement

Can that decision actually stop or limit the action?

Verification

Did the system obey?

⸻

Escalation Levels

A future Nekonečný Mír system might use something like:

LEVEL 0 — LOCAL

Routine anomaly.

component handles automatically

Example:

temporary API timeout

⸻

LEVEL 1 — CONTROL LAYER

Requires policy action.

Risk / Validation / Policy Gateway

Example:

spread exceeds threshold

Possible result:

NORMAL → CAUTION

⸻

LEVEL 2 — INDEPENDENT SAFETY

Potential systemic problem.

Independent Safety / Audit Layer

Example:

position reconciliation mismatch

Possible result:

CAUTION → MANAGE ONLY

⸻

LEVEL 3 — HUMAN AUTHORITY

High consequence or unresolved conflict.

David approval required

Examples:

change live risk limits
restore after critical incident
override safety policy

⸻

LEVEL 4 — EMERGENCY

Safety cannot be established.

KILL

No debate required from the controlled agent.

⸻

Why Independence Matters

Suppose:

Trading Agent

and:

Risk Agent

are actually the same model instance with the same prompt context.

The system appears to have two roles.

But failure correlation is extremely high.

If that model becomes confused, both roles may fail together.

Therefore the escalation target should become increasingly independent as consequence increases.

Conceptually:

Low consequence
→ local control acceptable
Medium consequence
→ separate control process
High consequence
→ independent authority
Critical consequence
→ external / human authority

This is graduated independence.

⸻

Today’s AI Parallel

Dario Amodei proposed independent evaluators embedded inside frontier labs with access comparable to employees, specifically so they can inspect safety practices rather than rely only on company self-reporting. Sam Altman publicly supported that model. 

The crucial architectural point is not merely:

another reviewer exists

It is:

reviewer has sufficient access
+
reviewer is organizationally independent
+
reviewer can trigger consequence

Without the third part, evaluation may become ceremonial.

⸻

Evaluator Without Authority

Bad pattern:

Independent Evaluator
↓
Report
↓
Controlled Team reads report
↓
Controlled Team decides whether report matters

The authority being evaluated still controls the outcome.

Better:

Independent Evaluator
↓
Defined Severity
↓
Automatic Escalation
↓
Independent Authority
↓
Throttle / Pause / Human Review / Kill

Now the evaluator can actually affect system state.

⸻

This Extends #057

We already said:

The safety layer must sit outside the authority it controls.

Today we add:

The safety layer must also have somewhere stronger to escalate when its own authority is insufficient.

Safety itself needs a hierarchy.

⸻

This Extends #065

#065 gave us:

NORMAL
↓
CAUTION
↓
RESTRICTED
↓
MANAGE ONLY
↓
KILL

#067 now answers:

Who may move the system down that ladder?

Potential example:

Trading Agent
cannot self-escalate upward
Risk Agent
may move:
NORMAL → CAUTION → RESTRICTED
Independent Safety
may move:
any state → MANAGE ONLY / KILL
Human Authority
may authorize staged recovery

Notice the asymmetry.

Agents may often be allowed to reduce their own authority.

They should not freely increase it.

⸻

Downward Authority Can Be Easier Than Upward Authority

This is important.

Suppose Trading Agent detects uncertainty.

It may be safe to permit:

NORMAL → CAUTION

without external approval.

But:

CAUTION → NORMAL

may require independent evidence.

Why?

Because reducing authority generally reduces blast radius.

Increasing authority increases possible consequence.

Therefore:

Authority reduction can be permissive. Authority restoration should be evidence-gated.

This connects directly to #061 Recovery.

⸻

Escalation Should Be Deterministic Where Possible

Bad pattern:

Agent feels concerned
→ maybe escalate

Better:

IF position_mismatch = TRUE
THEN escalate_to = Independent Safety
authority_state = MANAGE_ONLY

or:

IF market_data_stale > threshold
THEN new_orders = DENY

LLMs can contribute interpretation.

But critical escalation rules should preferably have deterministic components.

⸻

Conflicting Controls

What happens if:

Trading Agent says ALLOW

but:

Risk Agent says DENY

We should decide this before it happens.

Possible precedence:

Safety
>
Risk
>
Trading

Therefore:

ALLOW + DENY
=
DENY

for high-consequence execution.

This is effectively a control priority hierarchy.

⸻

No Majority Vote for Safety

Imagine:

Trading Agent = ALLOW
Research Agent = ALLOW
Documentation Agent = ALLOW
Risk Agent = DENY

😂🐸

Result should not be:

3 vs 1
ALLOW wins

because those agents do not have equal authority over trading risk.

Votes are not interchangeable.

Authority is role-specific.

This connects to our Dependency Graph and Authority Graph.

⸻

Escalation Must Be Auditable

Every escalation event should record:

event_id
timestamp
detector
severity
evidence
previous_state
requested_state
authority_decision
final_state
approver
reason

Then later we can reconstruct:

Why was live trading stopped at 14:07?

and receive a deterministic answer.

⸻

Escalation Failure Is Itself an Incident

Suppose:

Risk Agent requests KILL

but:

Execution Gateway continues accepting orders

The escalation mechanism failed.

That is not a minor software bug.

It is a control-plane incident.

Therefore future monitoring should test not only:

Is Risk Agent alive?

but also:

Can Risk Agent actually stop execution?

This suggests periodic control drills.

⸻

Safety Drills

Just as disaster recovery systems are tested, we may eventually test:

THROTTLE test
KILL test
credential revocation test
reconciliation failure test
human approval test

A control that has never been exercised may not actually work when needed.

⸻

Human Escalation Should Be Rare but Meaningful

David should not receive:

1000 alerts/day

or every event becomes noise.

😂🐸

Human escalation should be reserved for:

high consequence
unresolved uncertainty
policy override
recovery authorization
critical identity anomaly
critical control failure

This keeps human attention valuable.

⸻

Escalation + Consequence Classes

Yesterday’s consequence classes integrate naturally.

Class 0

Local handling.

Class 1

Automated control.

Class 2

Policy / Validation escalation.

Class 3

Independent Risk/Safety escalation.

Class 4

Human authorization or permanent DENY.

So the higher the consequence:

more independence
+
stronger escalation
+
higher evidence requirement

⸻

Future Policy Gateway

We are slowly defining something close to:

REQUEST
↓
IDENTITY
↓
ROLE
↓
PERMISSION
↓
MANDATE
↓
CONSEQUENCE CLASS
↓
SYSTEM AUTHORITY STATE
↓
RISK
↓
INDEPENDENT CONTROLS
↓
ESCALATION IF NEEDED
↓
EXECUTION / DENY
↓
VERIFICATION
↓
RECONCILIATION
↓
AUDIT

This is no longer just a collection of ideas.

It is beginning to resemble a genuine specification.

⸻

Projects HQ Principle

A control is only as real as its ability to escalate and enforce consequence.

Shortest version:

DETECT → ESCALATE → ENFORCE

And the Nekonečný Mír version:

Never let a warning depend on the permission of the system it is warning about.

⸻

Builds On

#057 — Safety Must Sit Outside the Authority It Controls
#058 — Critical Controls Need Independent Evidence
#061 — Recovery Must Be Gated by Reconciliation
#063 — Automation Must Not Outrun Verification
#064 — Authority Requires Verifiable Identity
#065 — A Safe System Needs a Throttle, Not Only a Kill Switch
#066 — Consequence Should Determine the Strength of the Control

⸻

Future Applications

Escalation Matrix · Policy Gateway · Risk Agent · Independent Safety Layer · human approval · Kill Switch · control priority · staged recovery · audit log · control drills · incident response

⸻

Origin

Daily AI Trading Brief — 13. 09. 2026

Inspired by Dario Amodei’s proposal for independent evaluators embedded within frontier AI firms and Sam Altman’s public support for the same model. The generalized lesson for autonomous trading is that independent evaluation only becomes an operational control when findings have a defined route to an authority capable of throttling, pausing or stopping consequential actions. 

Status

🟢 Active strategic principle

Tags

Projects HQ · Nekonečný Mír · AI Agents · Escalation · Independent Evaluation · Risk · Authority · Policy Gateway · Trading

Revision

v1.0 — 13. 09. 2026
