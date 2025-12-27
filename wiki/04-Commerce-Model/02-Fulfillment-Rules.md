# Fulfillment Rules

This document defines how Revono evaluates and executes fulfillment.

Fulfillment determines what real-world effects occur when something is sold.
Incorrect fulfillment logic leads directly to inventory corruption,
financial errors, and loss of trust.

---

## Fulfillment Is Explicit

Revono does not infer fulfillment behavior.

Fulfillment rules are:
- Explicit
- Declared
- Evaluated per line item

If fulfillment behavior is unclear, execution must not proceed.

---

## Per-Line-Item Evaluation

Fulfillment is evaluated **per line item**, not per transaction.

For each line item, the system determines:
- Whether inventory applies
- Whether time-based fulfillment applies
- Whether fulfillment has no stock implication

This prevents global assumptions and hybrid errors.

---

## Product Fulfillment Rules

For product line items:
- Inventory applies
- Stock may be reserved or deducted
- Batch and expiry rules may apply
- FIFO or equivalent allocation is enforced
- Inventory deduction occurs only after confirmation

Product fulfillment always results in a stock movement.

---

## Service Fulfillment Rules

For service line items:
- Inventory never applies
- No stock may be reserved or deducted
- Fulfillment is conceptual, not physical
- Completion may be time-based or outcome-based

If a service touches inventory, the system is broken.

---

## Hybrid Transaction Safety

Hybrid transactions contain both product and service line items.

Rules:
- Product lines are fulfilled as products
- Service lines are fulfilled as services
- Inventory logic applies only to product lines
- Fulfillment is never evaluated globally

Hybrid safety emerges from separation, not special cases.

---

## Fulfillment and Confirmation

Fulfillment effects must be:
- Declared in the proposal
- Shown in the Impact Summary
- Explicitly confirmed by a human

No fulfillment may occur without confirmation.

---

## Fulfillment and Execution

Execution applies fulfillment effects deterministically.

Execution:
- Does not infer fulfillment
- Does not branch dynamically
- Applies exactly what was approved

If fulfillment logic depends on context or UI state,
the design is invalid.

---

## Failure Handling

If fulfillment execution fails:
- No partial fulfillment occurs
- No partial inventory movement occurs
- No silent retries occur

Failures must leave the system unchanged.

---

## Summary

Fulfillment in Revono is:
- Explicit
- Line-item scoped
- Deterministic
- Confirmed
- Auditable

This guarantees inventory safety and commercial correctness,
even in complex hybrid scenarios.
