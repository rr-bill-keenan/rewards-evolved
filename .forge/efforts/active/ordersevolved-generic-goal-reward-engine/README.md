# ordersEvolved — Generic Goal/Reward Engine

<!-- metadata -->
**Effort ID:** ordersevolved-generic-goal-reward-engine
**Repository:** ordersEvolved
**Workflow:** software-initiative
**Jira:** not linked

---

## Problem Statement

The current order processing system is built around a rigid ecommerce model (network → merchant → order → reward) that does not support emerging transaction types such as games, gift cards, and subscription events. These new types are currently being shoe-horned into the ecommerce data model, which is distributed across multiple services. This initiative will replace the rigid model with a generic goal/reward engine where goals are arbitrary user objectives (purchase, play, subscribe, achieve a level) and rewards are arbitrary outcomes (cashback, event emission, etc.), enabling any transaction type to be supported without model-specific changes.

## Scope

**In scope:** TBD
**Out of scope:** TBD

---

## Artifact Directory

`requirements/` — Business, functional, and technical requirements produced during discovery
`spec/` — Architecture, design decisions (ADRs), and interface contracts
`plan/` — Implementation task plan and delivery sequence
`meetings/` — Meeting transcripts and summaries
`validation/` — Discovery validation report
