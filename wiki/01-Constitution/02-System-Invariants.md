# System Invariants

This document defines the **non-negotiable invariants** of Revono.

An invariant is a rule that must always hold:
- Regardless of feature additions
- Regardless of UI changes
- Regardless of AI capability
- Regardless of commercial pressure
- Regardless of team size

If any invariant is violated, the system is considered **incorrect** —
even if it appears functional.

---

## Invariant 1 — Single Mutation Authority

All state mutations must occur in one place only:
the **Deterministic Execution Layer**.

This applies to:
- Orders
- Quotes
- Invoices
- Inventory
- Payments
- Refunds
- Credits
- Schedules
- Communications
- Reports

UI, AI, tools, and workflows may **never** mutate state directly.

---

## Invariant 2 — Propose → Confirm → Execute

No mutation may occur without passing through all three stages:

1. Structured Proposal  
2. Explicit Human Confirmation  
3. Deterministic Execution  

There are **no exceptions**.

---

## Invariant 3 — AI Is Read-Only

Reva may:
- Interpret intent
- Resolve entities
- Analyze data
- Detect risk
- Explain consequences
- Propose actions

Reva may **never**:
- Write to the database
- Send emails
- Charge payments
- Deduct inventory
- Schedule jobs
- Trigger automations
- Execute workflows

This is enforced structurally, not by policy or prompt.

---

## Invariant 4 — Impact Summary Is Mandatory

Every proposal that can mutate state must include
an **Impact Summary** before confirmation.

The Impact Summary must explicitly declare:
- Financial impact
- Inventory impact (or explicit non-impact)
- External side effects (emails, schedules, exports)

No Impact Summary → No Confirmation → No Execution.

---

## Invariant 5 — Deterministic Execution Only

Execution functions must:
- Accept structured input only
- Perform predefined logic only
- Never interpret natural language
- Never call AI models
- Never branch probabilistically

Execution must be predictable, reproducible, and reviewable.

---

## Invariant 6 — Explicit Side Effects Only

Execution may perform **only** side effects
explicitly declared in the proposal and Impact Summary.

Forbidden:
- Hidden inventory deductions
- Implicit emails
- Background retries
- Secondary financial changes
- Cascading side effects

If it was not shown, it cannot happen.

---

## Invariant 7 — Per-Line-Item Fulfillment

Fulfillment is evaluated **per line item**, never globally.

Rules:
- Product line items may affect inventory
- Service line items must never affect inventory
- Hybrid transactions are handled safely by separation

Violations are critical defects.

---

## Invariant 8 — Financial Authority Is Human

All financial actions require explicit human intent.

This includes:
- Issuing invoices
- Charging payments
- Issuing refunds
- Applying credits
- Adjusting balances

AI inference or automation is never sufficient.

---

## Invariant 9 — Reporting Is Read-Only

Reporting and analytics must never mutate operational data.

Guarantees:
- Read-only data access
- Preview before export
- Confirmation before scheduling
- Full audit logging

Reports inform decisions — they do not make them.

---

## Invariant 10 — Failure Atomicity

If execution fails:
- No partial state persists
- No partial side effects occur
- No silent retries happen

Failures must leave the system unchanged.

---

## Invariant 11 — Audit Completeness

Every execution must emit an audit record containing:
- Tenant
- Approving user
- Action type
- Affected entities
- Timestamp
- Outcome

No mutation without an audit log is permitted.

---

## Invariant 12 — Onboarding Obeys All Invariants

Onboarding is **not** a sandbox.

During onboarding:
- Proposals are still generated
- Impact Summaries still render
- Confirmation is still required
- Cancellations are always possible
- Audit logs are still written

If onboarding bypasses safety, the system is broken.


---

## Invariant 13 — Delegated Automation Only

Revono allows automation **only** through explicit delegation by a human.

Automation is never inferred.
Automation is never decided by AI.
Automation is never implicit.

All automated execution must originate from
a clearly defined, human-approved delegation.

---

### Definition: Delegated Automation

Delegated automation is execution that occurs without per-action confirmation
**only because** a human has explicitly authorized a narrowly scoped rule in advance.

Delegation is a form of consent — not autonomy.

---

### Conditions for Delegated Automation

Delegated automation is permitted **only if all of the following are true**:

1. **Explicit Enablement**  
   A human has deliberately enabled the automation.
   It is never enabled by default.

2. **Narrow Scope**  
   The delegation applies to a clearly defined class of actions  
   (e.g. thresholds, limits, frequencies, specific entities).

3. **Deterministic Execution**  
   Execution logic is deterministic and predefined.  
   AI is never involved in the execution path.

4. **Previewed and Explainable**  
   The delegation was previewed and explained at the time of enablement,
   including its financial, inventory, and side-effect implications.

5. **Auditable and Revocable**  
   All delegated executions are audited,  
   and the delegation can be paused or revoked at any time.

If any condition is not met, automation is forbidden.

---

### AI and Delegated Automation

AI (Reva) may:
- Help define delegation rules
- Explain what a rule will do
- Simulate outcomes
- Warn about risk

AI (Reva) may **never**:
- Decide when a delegation applies
- Expand the scope of a delegation
- Override delegation boundaries
- Execute actions under delegation

Delegated automation is enforced by the execution layer,
not by AI reasoning.

---

### Enforcement Rule

If an automated action occurs and a human cannot clearly say:

> “I explicitly approved this exact behavior in advance”

then the automation is invalid and the system is incorrect.


---

## Non-Negotiable Enforcement

Any feature that:
- Bypasses confirmation (Aside from Delegated automation)
- Introduces implicit side effects
- Allows AI execution
- Hides financial or inventory impact

must be rejected, regardless of convenience or pressure.
