# How to Change the System

This document defines the **required process** for changing Revono.

Revono is safety-critical around:
- Money
- Inventory
- Customer communication
- Auditability

Changes must therefore be deliberate, explicit, and reviewable.

---

## Default Assumption

The default assumption for any change is:

> The change is unsafe until proven otherwise.

This posture protects the system over time.

---

## Step 1 — Identify the Impact

Before writing code, identify:
- What behavior is changing
- Which layer is affected
- Whether money, inventory, or communication is involved

If impact is unclear, stop.

---

## Step 2 — Check the Constitution

Before implementation, verify:
- No Core Principle is violated
- No System Invariant is weakened
- No Explicit Refusal is bypassed

If a change conflicts with the Constitution,
the change must be rejected or the Constitution must be updated **first**.

---

## Step 3 — Determine the Layer

Every change must clearly belong to one layer:
- Interface Layer
- Intelligence Layer (Reva)
- Execution Layer

If a change spans layers, it must be split.

---

## Step 4 — Preserve Boundaries

Ensure that:
- UI does not contain business logic
- Reva remains read-only
- Execution remains deterministic

Boundary crossings are defects.

---

## Step 5 — Declare Side Effects

All side effects must be:
- Explicit
- Declared
- Previewed
- Confirmed

Hidden side effects are forbidden.

---

## Step 6 — Update Documentation

If behavior changes:
- Update the relevant wiki document
- Do this before or alongside code changes

If documentation is not updated,
the change is incomplete.

---

## Step 7 — Review and Reflect

Before merging:
- Re-read the Constitution
- Re-read the Impact Summary
- Ask “what could go wrong?”

If unsure, do not merge.

---

## Summary

Safe changes in Revono are:
- Intentional
- Layered
- Explicit
- Documented
- Auditable

Speed is never a justification.
