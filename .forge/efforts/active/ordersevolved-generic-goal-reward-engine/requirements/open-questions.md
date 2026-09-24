# Open Questions — ordersEvolved — Generic Goal/Reward Engine

---

## OQ-1: What specific fields and format does finance require for reconciliation and audit?

*Layer:* Functional / Data model
*Relates to:* FR-7
*Context:* Finance currently reports directly off the orders/transactions table. FR-7 is a placeholder — the exact schema, delivery mechanism (table, view, ledger event, API), required fields, and audit trail depth need to be validated with Daniell Kellogg and HongMei.

**Action needed:** resolve in finance discovery session before forge:plan runs.

---

## OQ-2: Does finance require an immutable audit trail (every state change) or only final reward issuance state?

*Layer:* Functional / Technical
*Relates to:* FR-7
*Context:* Affects whether we need an append-only event log vs. a point-in-time record. Compliance obligation (SOX, GAAP, internal policy) may dictate this. To be resolved with finance team.

**Action needed:** resolve in finance discovery session before forge:plan runs.

---

## OQ-3: How does finance categorize non-monetary rewards (e.g. game achievements, subscription bonuses) for accounting purposes?

*Layer:* Functional / Data model
*Relates to:* FR-7
*Context:* Cashback has a clear dollar value. Non-monetary rewards may have a cost-to-company value, a face value, or require a different accounting treatment. Finance must define how each reward type maps to their chart of accounts.

**Action needed:** resolve in finance discovery session before forge:plan runs.
