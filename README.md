# ordersEvolved — Generic Goal/Reward Engine

## Problem

The current order processing system is built around a rigid ecommerce data model (network → merchant → order → reward). Emerging transaction types — games, gift cards, subscription events — don't fit this model cleanly and are being shoe-horned in across multiple services, creating fragility and escalating maintenance cost.

This initiative replaces that model with a **generic goal/reward engine**: goals are arbitrary user objectives (purchase, play a game, subscribe, reach a level) and rewards are arbitrary outcomes (cashback, event emission, etc.). Any transaction type can be supported without model-specific code changes.

## Functional Requirements

| ID | Requirement |
|----|-------------|
| FR-1 | **Event-to-goal matching** — incoming member events are evaluated against all active goals; matching goals are identified regardless of event type |
| FR-2 | **Reward issuance** — when a goal is satisfied, the configured reward is issued; reward type is set by goal config, not by the triggering event |
| FR-3 | **Idempotent processing** — duplicate events (retries, re-submissions) are detected and discarded without side effects |
| FR-4 | **Goal type configuration** — operators define goals (event type, criteria, reward) via configuration, no deployment required |
| FR-5 | **Goal lifecycle management** — operators activate, deactivate, and time-bound goals without deployment; expired/inactive goals never match |
| FR-6 | **Campaign association** — goals are linked to campaigns or offers for eligibility, budget, and reporting scoping |
| FR-7 | **Finance-readable reward record** — every reward issuance produces a record sufficient for financial reconciliation and audit (schema TBD with finance) |

## Current Status

**Phase:** Discovery — requirements elaborated, pending finance session to close open questions before planning begins.

### Open Questions (blocking `forge:plan`)

| ID | Question | Owner |
|----|----------|-------|
| OQ-1 | What fields and format does finance require for reconciliation and audit? (FR-7 schema, delivery mechanism) | Daniell Kellogg / HongMei |
| OQ-2 | Does finance require an immutable audit trail (every state change) or only final reward issuance state? | Daniell Kellogg / HongMei |
| OQ-3 | How does finance categorize non-monetary rewards for accounting purposes? | Finance team |

## Stakeholders

- **Product:** Miko, Gregg Dessen
- **Finance:** Daniell Kellogg, HongMei

## Repository Layout

```
.forge/efforts/active/ordersevolved-generic-goal-reward-engine/
  requirements/        # Functional requirements and open questions
  spec/                # Architecture, ADRs, interface contracts (added post-discovery)
  plan/                # Implementation task plan (added post-planning)
  meetings/            # Session transcripts and summaries
  validation/          # Discovery validation report
```

## Getting Started

This repository follows the [Forge](https://github.com/anthropics/forge) AI-accelerated development framework. See `CLAUDE.md` for navigation guidance and standards locations.
