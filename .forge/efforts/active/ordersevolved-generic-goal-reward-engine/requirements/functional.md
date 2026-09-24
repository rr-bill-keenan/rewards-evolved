# Functional Requirements — ordersEvolved — Generic Goal/Reward Engine

*Effort: ordersevolved-generic-goal-reward-engine*
*Elaborated from: [business.md](business.md)*
*Created: 2026-09-24*

<!-- Functional Requirement framing guide:
  An FR states a specific system behavior required to satisfy one or more BRs.
  It answers "what must the system do?" — not why (that is the BR) and not how
  (that is the spec and ADRs).
-->

---

## FR-1: Event-to-Goal Matching

*No business.md present — run forge:prd to add BR traceability.*

When a member generates any qualifying event (purchase, game achievement, subscription activation, or any future event type), the system must evaluate that event against all active goals for that member and identify which goals, if any, it contributes to or satisfies.

---

## FR-2: Reward Issuance on Goal Completion

*No business.md present — run forge:prd to add BR traceability.*

When a member satisfies a goal, the system must issue the configured reward for that goal regardless of reward type (cashback, event emission, or any future reward type). The reward type is defined by the goal configuration, not by the event that triggered completion.

---

## FR-3: Idempotent Event Processing

*No business.md present — run forge:prd to add BR traceability.*

The system must guarantee that the same event cannot trigger the same goal completion or reward issuance more than once. Duplicate events — whether caused by retries, network errors, or partner re-submissions — must be detected and discarded without side effects.

---

## FR-4: Goal Type Configuration

*No business.md present — run forge:prd to add BR traceability.*

Operators must be able to define a goal by specifying: the event type that satisfies it, the criteria that must be met (e.g. minimum purchase amount, specific game level achieved, subscription product identifier), and the reward to issue upon completion. Goal definitions must not require a code deployment to create or modify.

---

## FR-5: Goal Lifecycle Management

*No business.md present — run forge:prd to add BR traceability.*

Operators must be able to activate, deactivate, and set time bounds (start date, expiry date) on any goal without a code deployment. A deactivated or expired goal must not match incoming events.

---

## FR-6: Campaign Association

*No business.md present — run forge:prd to add BR traceability.*

A goal must be associable with a campaign or offer, so that eligibility rules, budget constraints, and reporting can be scoped to a business initiative. The system must support multiple goals belonging to the same campaign.

---

## FR-7: Finance-Readable Reward Record

*No business.md present — run forge:prd to add BR traceability.*

For every reward issuance, the system must produce a record that is sufficient for financial reconciliation and audit. At minimum the record must capture: member identifier, reward type, monetary value or cost-equivalent for non-monetary rewards, the triggering event reference, and timestamp. The exact schema and delivery mechanism are to be determined with the finance team.
