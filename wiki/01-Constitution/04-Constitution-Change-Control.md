# Constitution Change Control

This document defines how the Revono Constitution may be changed.

The Constitution includes:
- Core Principles
- System Invariants
- Explicit Refusals

These documents define what Revono **is allowed to be**.

They are not guidelines.
They are constraints.

---

## Default Rule

The default state of the Constitution is **locked**.

Changes are **exceptional**, not routine.

---

## What Requires a Constitution Change

A Constitution change is required if a proposal:

- Alters AI authority or autonomy
- Introduces new execution paths
- Modifies confirmation requirements
- Changes inventory or financial safety rules
- Weakens audit guarantees
- Adds implicit side effects
- Reinterprets fulfillment logic
- Allows behavior previously refused

If unsure, assume a Constitution change **is required**.

---

## What Does NOT Require a Constitution Change

The following do **not** require Constitution updates:

- UI layout or visual changes
- Performance optimizations that preserve behavior
- New features that obey all invariants
- New reports that are read-only
- Additional explanations or tooling
- Internal refactors with identical outcomes

If behavior does not change, the Constitution stands.

---

## Change Requirements

Any Constitution change must:

1. Be explicit  
2. Be written before code changes  
3. State **why the change is necessary**  
4. State **which invariants are affected**  
5. Describe **new risks introduced**  
6. Describe **how those risks are mitigated**  

Silent or implied changes are forbidden.

---

## Review Discipline

A Constitution change requires:

- Deliberate review
- Cooling-off time
- Explicit acceptance of new risk

This applies even to the original author.

Speed is never justification.

---

## Forbidden Justifications

The following are **not valid reasons** to change the Constitution:

- “Users asked for it”
- “Competitors do it”
- “It’s faster”
- “It’s just this one case”
- “We’ll fix it later”
- “It’s only AI”

If a change cannot be justified structurally, it is rejected.

---

## Versioning

Each accepted Constitution change must:

- Increment a visible version
- Be recorded in Git history
- Be explainable to a third party
- Be defensible to an auditor or acquirer

If a change cannot be defended later, it should not be made now.

---

## Final Enforcement

If code behavior contradicts the Constitution:

- The code is wrong
- The feature is invalid
- The system is considered unsafe

The Constitution always wins.
