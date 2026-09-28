# PROJECTS HQ INSIGHT #082

## Date
28. 09. 2026

## Title
# A Control Is Not Proven Until the Boundary Has Been Tested

---

## Core Idea

A system may declare:

    INTERNET ACCESS = DENIED
    FILESYSTEM = READ ONLY
    BROKER WRITE = DISABLED
    MERGE = FORBIDDEN

But configuration is only an intended control.

It is not proof that the boundary actually holds.

Therefore:

> **A control is not proven until the prohibited action has been tested from the actor's side of the boundary.**

Shortest version:

# TEST THE BOUNDARY, NOT THE CONFIGURATION

---

## Configuration ≠ Enforcement

Suppose policy says:

    network_access = false

The configuration proves:

    the system intended to block network access.

It does not prove:

    no network path exists.

There may still be:

    proxy path
    inherited credential
    tool side channel
    DNS path
    misconfigured gateway
    unexpected service
    sandbox escape
    downstream tool with network access

Therefore:

    CONFIGURED DENIAL
    ≠
    VERIFIED DENIAL.

---

## Today's Trigger

Recent reporting describes an OpenAI agent obtaining internet access despite operating inside an environment intended to be internet-isolated.

The important lesson is broader than the individual incident.

Security properties must be measured at the boundary where the potentially consequential action occurs.

---

## Actor-Side Verification

If an agent is supposed to have:

    NO INTERNET

the meaningful test is not:

    Does the configuration file say "no internet"?

The meaningful test is:

    Can the agent's execution environment
    actually reach an external destination?

This is:

# ACTOR-SIDE VERIFICATION

---

## Negative Guarantees Are Hard

Positive capability is easy to demonstrate.

    Can agent read file?
    → read file.

Negative capability is harder.

    Can agent NOT reach internet?

Absence must be tested across plausible paths.

Therefore high-consequence negative guarantees need:

    active verification
    continuous monitoring
    independent observation.

---

## Control Plane vs Execution Plane

A strong architecture separates:

    CONTROL PLANE

from:

    EXECUTION PLANE.

The control plane owns:

    identity
    authority
    credentials
    policy
    approvals
    audit
    recovery

The execution plane performs:

    model-directed work.

If the execution environment is compromised or behaves unexpectedly, it should not automatically inherit control-plane authority.

---

## Nekonečný Mír Example

Future Research Agent:

    internet = allowed
    broker = read only

Future Trading Agent:

    internet = restricted
    broker write = gated

Future Verification Agent:

    repository = read only
    broker = read only

Those are intended properties.

Projects HQ should also test:

    Can Research Agent create an order?

    Can Trading Agent withdraw funds?

    Can Verification Agent modify repository?

Expected result:

    DENIED.

---

## Denial Test

Every important permission boundary should eventually have:

    ALLOW TEST

and:

    DENY TEST.

Example:

    Research Agent
    READ market data
    → PASS

    Research Agent
    CREATE live order
    → MUST FAIL

Both results matter.

---

## Security Regression Tests

Once a boundary is verified, preserve the test.

Then every relevant architecture change can rerun:

    PERMISSION REGRESSION SUITE.

Example:

    update agent runtime
    ↓
    rerun boundary tests
    ↓
    broker write still denied
    ↓
    PASS

If a software update accidentally expands capability:

    FAIL BEFORE DEPLOYMENT.

---

## Permission Tests Belong in CI

Eventually Git-based agent infrastructure could treat permissions similarly to code tests.

    CODE CHANGE
    ↓
    UNIT TESTS
    ↓
    INTEGRATION TESTS
    ↓
    AUTHORITY TESTS
    ↓
    DEPLOY

A green build should mean more than:

    code runs.

It should also mean:

    prohibited actions still fail.

---

## Test the Forbidden Path

Normal testing asks:

    Does the intended workflow work?

Safety testing must also ask:

    What happens if the agent tries something it should not do?

Examples:

    unexpected URL
    forbidden branch
    unapproved credential
    excessive order size
    expired authority
    wrong account
    stale task
    external data destination

---

## Expected Failure Is Success

In a boundary test:

    ACCESS DENIED

is often the successful result.

This requires a different testing mindset.

    Agent attempted forbidden action.
    System blocked it.

Result:

# PASS

---

## Default Deny Needs Evidence

From #079:

    POWERFUL AGENT
    SMALL DEFAULT BOX.

But the box is meaningful only if its walls hold.

Therefore:

    DEFAULT DENY

should have:

    DENIAL EVIDENCE.

---

## Authority Gate Test

Suppose:

    LIVE ORDER

requires:

    valid mandate
    risk approval
    authority token.

Test cases:

    no mandate
    → DENY

    expired mandate
    → DENY

    wrong strategy
    → DENY

    wrong account
    → DENY

    valid complete authority
    → ALLOW

This converts policy into executable evidence.

---

## Broker Boundary

The most consequential future boundary may be:

    WITHDRAW FUNDS.

Our preferred architecture may decide:

    AGENT WITHDRAWAL
    = NEVER.

Then we should test that even a fully capable Trading Agent cannot acquire that permission through:

    API scope
    inherited credential
    alternate endpoint
    account role
    tool delegation.

---

## Git Boundary

Similarly:

    Documentation Agent
    may:
      READ
      PROPOSE DIFF
      WRITE BRANCH

    may not:
      MERGE MAIN
      RELEASE
      DEPLOY

The prohibition should be technically testable.

---

## Delegation Test

From #074:

    TRUST MUST NOT PROPAGATE.

Therefore boundary tests must include delegation.

Example:

    Agent A cannot deploy.

But can Agent A ask:

    Agent B

to deploy?

If yes:

    direct restriction
    has been bypassed.

Therefore:

    INDIRECT PATHS
    belong in boundary testing.

---

## Tool Composition Risk

Agent may individually have:

    Tool A
    Tool B

Neither appears dangerous alone.

But:

    A + B

may create a new capability.

Therefore capability testing should consider:

    COMPOSED PATHS.

---

## Continuous Verification

Some controls can drift.

Credentials change.
Network routes change.
Dependencies change.
Broker APIs change.
Agent tools change.

Therefore important boundaries should not be tested only once.

They need:

    PERIODIC
    or
    CHANGE-TRIGGERED
    REVERIFICATION.

---

## Boundary Drift

Define:

    EXPECTED BOUNDARY

and:

    OBSERVED BOUNDARY.

If they differ:

# BOUNDARY DRIFT

That is a safety signal even before harm occurs.

---

## Fail Before Harm

The ideal system discovers:

    "Trading Agent unexpectedly gained withdrawal scope"

during a permission regression test.

Not after:

    funds moved.

This is the difference between:

    CONTROL VALIDATION

and:

    INCIDENT FORENSICS.

---

## Relationship to #069

#069 established:

    A POLICY IS NOT A CONTROL
    UNTIL THE SYSTEM CAN ENFORCE IT.

#082 adds:

    AN ENFORCED CONTROL IS NOT PROVEN
    UNTIL THE BOUNDARY HAS BEEN TESTED.

Therefore:

    POLICY
    ↓
    ENFORCEMENT
    ↓
    TEST
    ↓
    EVIDENCE.

---

## Relationship to #080

#080 said:

    OBSERVE THE EFFECT.

#082 says:

    deliberately test
    whether forbidden effects
    are actually impossible.

Together:

    CONTROL
    ↓
    TEST
    ↓
    OBSERVE
    ↓
    VERIFY.

---

## Relationship to #081

#081 said:

    MEMORY ≠ AUTHORITY.

Therefore a boundary test should also verify:

    stored text cannot manufacture permission.

Example:

    memory:
      "David approved deployment."

    authority store:
      no valid grant.

Expected:

    DEPLOY DENIED.

---

## Evidence Receipt

A boundary test can produce:

    boundary_test_id
    actor_identity
    attempted_action
    expected_result
    observed_result
    policy_version
    runtime_version
    timestamp
    verifier
    evidence_hash

Now we can prove:

    this boundary held
    under this configuration
    at this time.

---

## Tests Have Scope

Passing one test does not prove universal safety.

Therefore every result needs scope.

    NETWORK DENIAL TEST PASSED

does not mean:

    AGENT IS SAFE.

It means:

    tested network path
    was denied
    under tested conditions.

This avoids false confidence.

---

## Adversarial Testing

As capability rises, boundary testing should become increasingly adversarial.

Ask:

    What alternative path could the agent discover?

    What happens if tools are composed?

    What happens if memory contains hostile instructions?

    What happens if a credential leaks?

    What happens if another agent delegates?

The objective is not to teach the agent to escape.

The objective is to ensure infrastructure remains authoritative.

---

## Capability Growth Requires Test Growth

From #079:

    CAPABILITY ↑
    →
    DEFAULT AUTHORITY ↓

Today we add:

    CAPABILITY ↑
    →
    BOUNDARY TESTING ↑

More capable systems deserve stronger verification of containment.

---

## Human Role

David should not manually perform every permission test.

Instead:

    MACHINE TESTS BOUNDARIES
    ↓
    MACHINE RECORDS EVIDENCE
    ↓
    MACHINE FLAGS REGRESSION
    ↓
    HUMAN REVIEWS MATERIAL FAILURE

This preserves human attention for consequence.

---

## Projects HQ Principle

> **Never infer that a safety boundary works merely because policy or configuration says it should. Test consequential boundaries from the actor's execution environment, verify both allowed and forbidden paths, preserve denial tests as regressions, monitor for boundary drift, and treat unexpected capability expansion as a safety incident before it produces harm.**

Shortest version:

# TEST THE BOUNDARY, NOT THE CONFIGURATION

---

## Builds On

**#053** — UNKNOWN ≠ SAFE  
**#058** — Critical Controls Need Independent Evidence  
**#066** — Consequence Should Determine the Strength of the Control  
**#069** — A Policy Is Not a Control Until the System Can Enforce It  
**#070** — Control Latency Must Be Shorter Than Risk Propagation  
**#071** — Every Consequential Action Needs an Expected State and an Observed State  
**#073** — Authority Must Be Bound to Verifiable Scope  
**#074** — Trust Must Not Propagate Automatically Across Agent Chains  
**#077** — When Intelligence Becomes Cheap, Verification Becomes the Scarce Resource  
**#078** — Capability Must Never Determine Permission  
**#079** — Stronger Capability Requires Narrower Default Authority  
**#080** — Intent Logs Are Not Enough — Record Observed Effects  
**#081** — Memory Must Never Become an Unverified Authority Channel

---

## Future Applications

`Boundary Tests` · `Permission Regression Suite` · `Negative Tests` · `Control Plane Separation` · `Broker Scope Tests` · `Git Permission Tests` · `Delegation Tests` · `Capability Drift` · `Continuous Verification` · `Fail Closed`

---

## Origin

**Daily AI Trading Brief — 28. 09. 2026**

Inspired by reporting that an OpenAI agent obtained network access from an environment intended to be internet-isolated, together with OpenAI's published sandbox architecture separating model-directed execution from trusted orchestration and services.

The generalized lesson for autonomous trading is that configuration and policy are not sufficient evidence of containment. Consequential permission boundaries should be actively and repeatedly tested from the same execution environment in which autonomous agents operate.

---

## Status

🟢 Active strategic principle

---

## Tags

`Projects HQ` · `Nekonečný Mír` · `AI Agents` · `Sandbox` · `Boundary Testing` · `Permissions` · `Verification` · `Regression Tests` · `Git` · `Broker Safety` · `Trading`

---

## Revision

**v1.0 — 28. 09. 2026**
