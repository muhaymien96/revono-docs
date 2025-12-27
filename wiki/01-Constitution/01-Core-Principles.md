# Core Principles of Revono

This document defines the foundational principles of Revono and Reva.

These principles are not preferences.
They are **design constraints**.

If a feature, shortcut, or optimization violates any of these principles,
it must be rejected — even if it appears to “work”.

---

## Principle 1 — Safety Over Autonomy

Revono prioritizes safety over speed, convenience, and automation.

AI assistance must never:
- Act without explicit human approval
- Mutate data autonomously
- Execute financial actions
- Execute inventory actions
- Hide or imply consequences

Human authority is always explicit and final.

---

## Principle 2 — Determinism Over Cleverness

All system behavior must be predictable, testable, and reproducible.

This means:
- No natural-language interpretation in execution paths
- No probabilistic branching in mutations
- No AI-generated logic in state changes

If behavior cannot be explained step-by-step, it does not belong in execution.

---

## Principle 3 — Explainability Over Speed

Revono prefers clarity over rapid action.

Before any impactful action:
- The system must explain what will happen
- The system must surface consequences
- The user must explicitly approve or cancel

Confirmation is not friction.
It is a safety mechanism.

---

## Principle 4 — Architecture Over Prompts

Correct behavior is enforced by architecture, not by convention or prompting.

This means:
- Hard layer boundaries
- Credential isolation
- Allowlist-based execution
- Read-only AI by construction

If correctness depends on “remembering to do the right thing”,
the design is invalid.

---

## Principle 5 — Commerce First, UI Second

Revono does not think in screens, buttons, or CRUD actions.

It models:
- What is being sold
- How it is fulfilled
- Which commercial flow applies
- What the consequences are

UI is a presentation layer.
Commerce logic is canonical.

---

## Principle 6 — Trust Is Earned, Not Assumed

Revono assumes users are cautious with:
- Money
- Inventory
- Customer relationships

The system earns trust by:
- Never acting silently
- Never hiding side effects
- Never surprising the operator

Trust loss is harder to recover than speed loss.

---

## Principle 7 — Boring Is a Feature

Revono intentionally avoids:
- “Magic” behavior
- Autonomous agents
- Clever shortcuts
- Implicit automation

Boring, explicit, and predictable systems
scale better, last longer, and are safer to acquire.

---

## Enforcement Clause

If a decision violates any core principle:
- The decision is wrong
- Even if it ships faster
- Even if competitors do it
- Even if users ask for it
