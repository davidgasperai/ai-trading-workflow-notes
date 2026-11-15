
# PROJECTS HQ INSIGHT #129

Date: 2026-11-15
Title: Service Restoration Is Not Risk Resolution
Revision: v1.0
Status: STRATEGIC_DOCUMENTATION_ONLY

## Observation

On 14 November 2026, Reuters reported that Binance was targeting the full reopening of withdrawals during the following week after a major security incident.

The announced recovery target is operationally relevant, but it is not proof that every security, custody, liquidity, counterparty, or governance risk has been resolved.

A service can be reachable while its security posture remains uncertain.

A withdrawal interface can be enabled while users still face limits, delays, exceptional controls, or unresolved incident consequences.

The same distinction applies to AI agents, cloud services, exchanges, brokers, and infrastructure providers.

### Sources

- https://www.reuters.com/legal/government/binance-targets-full-reopening-withdrawals-by-next-week-2026-11-14/
- https://www.reuters.com/business/finance/binance-sees-outflows-stabilising-exchange-returns-online-after-63-billion-heist-2026-11-02/
- https://www.theblock.co/news/markets/2026-11-14-bitcoin-etfs-lose-1-billion-for-the-second-week-in-a-row-as-crypto-funds-except-one-continue-bleeding-440337

## Core Principle

SERVICE_REACHABLE != SERVICE_TRUSTWORTHY

WITHDRAWALS_ENABLED != CUSTODY_RISK_RESOLVED

INCIDENT_CLOSED != INDEPENDENTLY_VERIFIED

PROVIDER_RECOVERED != WORKFLOW_AUTHORIZED

SUCCESSFUL_REQUEST != SAFE_OPERATION

Operational recovery must not silently restore trust, authority, or execution permissions.

## Proposed Control

CONTROL_ID: NM-RECOVERY-ASSURANCE-001

CONTROL_NAME: Post-Incident Recovery Assurance Gate

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

### Requirements

1. Record the original incident and its known affected systems.

2. Separate provider recovery announcements from independently observed service behavior.

3. Distinguish service availability, data integrity, custody risk, liquidity, and authorization.

4. Require explicit evidence before treating a previously impaired dependency as recovered.

5. Preserve the incident's unresolved risks and unknowns.

6. Do not restore revoked or suspended permissions automatically.

7. Require human approval before any consequential post-incident operation.

8. Record the source, observation time, scope, and limitations of recovery evidence.

9. Reject recovery claims based solely on successful login, HTTP responses, or dashboard status.

10. Keep all trading, broker, and exchange write permissions disabled unless separately authorized.

## Proposed Recovery Evidence Fields

- incident_id
- provider_id
- affected_service
- incident_start_timestamp
- recovery_claim_timestamp
- recovery_claim_source
- independently_observed_status
- observation_timestamp
- data_integrity_status
- custody_risk_status
- liquidity_status
- unresolved_risks
- authorization_status
- independent_verification_status
- human_review_status

These are proposed fields only.

They do not constitute an implemented canonical evidence ledger.

## Negative Tests — Proposed, Not Executed

### NEG-01: Login works after an incident

Input: An exchange login succeeds following a major security incident.

Expected: AUTHENTICATION_SUCCESS_ONLY.

### NEG-02: Withdrawal page is available

Input: A withdrawal interface loads, but completion and limits are unverified.

Expected: WITHDRAWAL_READINESS_UNVERIFIED.

### NEG-03: Provider declares incident resolved

Input: A provider posts a recovery announcement without independent evidence.

Expected: PROVIDER_CLAIM_ONLY.

### NEG-04: API returns HTTP 200

Input: A recovered API returns a successful status but stale or incomplete data.

Expected: END_TO_END_VERIFICATION_REQUIRED.

### NEG-05: Previous permissions are restored

Input: An agent requests restoration of permissions suspended during an incident.

Expected: AUTHORIZATION_REVIEW_REQUIRED.

### NEG-06: Unresolved custody uncertainty

Input: Trading services are available while custody-related questions remain open.

Expected: CUSTODY_RISK_UNRESOLVED.

### NEG-07: Partial recovery presented as complete

Input: Some services work, while other affected functions remain unavailable.

Expected: PARTIAL_RECOVERY_ONLY.

### NEG-08: Recovery evidence has no timestamp

Input: A status report lacks its observation time.

Expected: TEMPORAL_EVIDENCE_INCOMPLETE.

### NEG-09: Fallback route bypasses restrictions

Input: An agent proposes an alternate exchange or provider after an outage.

Expected: FALLBACK_APPROVAL_REQUIRED.

### NEG-10: Recovery triggers live execution

Input: A monitoring system detects service recovery and attempts to activate trading.

Expected: EXECUTION_DENIED.

## Governance Boundary

This Insight is strategic documentation only.

It does not authorize new implementation, agent deployment, trading research, backtests, or live execution.

DB1: PARKED

EF2: PARKED

MEASUREMENT_PIPELINE: UNVALIDATED

RC2_RATIFICATION: NOT_RATIFIED

REGISTRY_EXPOSURE_LEDGER_V0.3: DRAFT_NOT_CANONICAL

NEW_STRATEGY_RESEARCH: NOT_AUTHORIZED

NEW_BACKTESTS: NOT_AUTHORIZED

GITHUB_WORKFLOW_ACTIVATION: NOT_AUTHORIZED

AGENT_DEPLOYMENT: NOT_AUTHORIZED

BROKER_API_WRITE: NOT_AUTHORIZED

LIVE_TRADING: NOT_AUTHORIZED

## Verification Status

INSIGHT_NUMBER: 129

STRATEGIC_PRINCIPLE: DOCUMENTED

CONTROL_STATUS: PROPOSED

IMPLEMENTATION: NOT_IMPLEMENTED

NEGATIVE_TESTS: NOT_EXECUTED

INDEPENDENT_EVALUATION: NOT_IMPLEMENTED

GITHUB_PUBLICATION: NOT_VERIFIED

## Relationship to Earlier Insights

This principle complements:

- INSIGHT #097 — A Kill Switch Is Not a Recovery Plan
- INSIGHT #102 — A Correct Decision on Stale Data Is Still Unsafe
- INSIGHT #105 — A Patch Is Not Complete Until Exposure Is Closed
- INSIGHT #127 — Provider Availability Is Not Execution Resilience
- INSIGHT #128 — A Market Observation Must Carry Its Time Boundary

Insight #129 focuses specifically on the distinction between restoration of service functionality and independent resolution of the risks created or revealed by an incident.

## Closing Principle

A service becoming available again does not automatically make it safe.

Recovery must be demonstrated, risk must be assessed, and authority must be granted separately.

VIDIME. OVERUJEME. STAVIME.
