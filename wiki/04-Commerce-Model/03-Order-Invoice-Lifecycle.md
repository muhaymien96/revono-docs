# Order and Invoice Lifecycle

This document defines the lifecycle of commercial transactions in Revono.

The lifecycle governs how value moves from intent
to fulfillment to financial record — safely and explicitly.

---

## Lifecycle Philosophy

Revono separates:
- **Intent**
- **Commitment**
- **Fulfillment**
- **Financial record**

This separation prevents premature inventory changes,
accidental charges, and silent side effects.

---

## Quotes (Non-Financial)

Quotes represent **intent only**.

Properties:
- Non-binding
- Non-financial
- Do not affect inventory
- Do not affect accounting

Quotes may be:
- Created
- Reviewed
- Converted
- Cancelled

Quotes never trigger execution.

---

## Orders (Commitment to Fulfill)

Orders represent a **commitment to fulfill product offerings**.

Properties:
- Product-focused
- Inventory-aware
- Non-financial on their own

Order rules:
- Orders may reserve inventory
- Orders do not charge customers
- Orders do not generate revenue

Orders exist to protect inventory integrity.

---

## Invoices (Financial Record)

Invoices represent a **financial obligation**.

Properties:
- Financially authoritative
- Customer-facing
- Accounting-relevant

Invoice rules:
- Invoices require explicit human confirmation
- Invoices may include products, services, or both
- Invoices may reference orders (for products)
- Invoices do not auto-charge customers

Invoices define money owed — nothing more.

---

## Payments

Payments represent **settlement of invoices**.

Rules:
- Payments are explicit
- Payments are never inferred
- Payments are never retried silently
- Payments require confirmation

Payment failure does not alter fulfillment state automatically.

---

## Product Lifecycle Flow

Typical product flow:

1. Quote (optional)
2. Order (inventory commitment)
3. Invoice (financial obligation)
4. Payment
5. Fulfillment (inventory deduction)

Each step requires explicit confirmation.

---

## Service Lifecycle Flow

Typical service flow:

1. Quote (optional)
2. Invoice (financial obligation)
3. Payment
4. Service delivery

Services never create orders and never touch inventory.

---

## Hybrid Lifecycle Flow

Hybrid transactions combine both flows:

- Product line items:
  - Order → Invoice → Payment → Fulfillment
- Service line items:
  - Invoice → Payment → Service delivery

Each line item follows its correct path independently.

---

## Cancellation and Correction

Cancellations:
- Must be explicit
- Must be auditable
- Must not leave partial state

Corrections:
- Require new actions
- Do not silently modify history
- Preserve audit trails

---

## Lifecycle Guarantees

This lifecycle guarantees:
- No premature inventory deduction
- No silent financial actions
- No ambiguous state transitions
- No inferred behavior

All transitions are explicit, confirmed, and auditable.

---

## Summary

Revono treats commerce as a sequence of explicit commitments.

By separating intent, fulfillment, and finance:
- Inventory remains correct
- Money remains traceable
- Trust remains intact
