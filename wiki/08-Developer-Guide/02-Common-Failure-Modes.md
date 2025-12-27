# Common Failure Modes

This document catalogs common ways systems like Revono fail over time.

These failures rarely happen all at once.
They accumulate slowly through “small exceptions” and “temporary fixes”.

Recognizing these patterns early prevents long-term damage.

---

## Failure Mode 1 — Autonomy Creep

Symptoms:
- AI begins executing actions “just this once”
- Confirmation is skipped for convenience
- Background retries are added quietly

Why it happens:
- Pressure to reduce friction
- Misplaced trust in automation

Why it is dangerous:
- Silent errors multiply
- Accountability becomes unclear
- Trust is lost quickly

Correct response:
- Reassert proposal → confirmation → execution
- Remove execution authority from AI
- Redesign the flow

---

## Failure Mode 2 — UI-Driven Business Logic

Symptoms:
- Frontend conditionals decide behavior
- UI controls fulfillment or pricing logic
- Backend assumes UI correctness

Why it happens:
- Faster iteration
- Lack of clear boundaries

Why it is dangerous:
- Logic becomes fragmented
- Changes become unpredictable
- Bugs bypass safeguards

Correct response:
- Move logic into execution
- Reduce UI to rendering only
- Restore boundary discipline

---

## Failure Mode 3 — “Temporary” Safety Bypasses

Symptoms:
- Auto-confirm paths for demos
- Hard-coded overrides
- Flags that disable checks

Why it happens:
- Time pressure
- Stakeholder demos
- “We’ll fix it later” thinking

Why it is dangerous:
- Temporary paths become permanent
- Safety guarantees erode invisibly

Correct response:
- Remove bypasses immediately
- Rebuild demos using safe flows
- Update documentation

---

## Failure Mode 4 — Plan-Based Logic Forks

Symptoms:
- Different execution behavior per plan
- Safety reduced for lower tiers
- Conditional audit behavior

Why it happens:
- Monetization pressure
- Feature differentiation mistakes

Why it is dangerous:
- Correctness depends on pricing
- Hard-to-test edge cases
- Compliance risk

Correct response:
- Restrict gating to access only
- Keep execution identical
- Redesign monetization

---

## Failure Mode 5 — Integration Authority Leakage

Symptoms:
- External systems triggering execution
- Webhooks mutating state
- Silent retries or reconciliation

Why it happens:
- Over-trusting third parties
- Convenience over control

Why it is dangerous:
- Loss of determinism
- Difficult debugging
- Audit gaps

Correct response:
- Treat integrations as untrusted
- Require explicit confirmation
- Audit all interactions

---

## Failure Mode 6 — Reporting-Induced Actions

Symptoms:
- Reports triggering workflows
- Forecasts auto-scheduling tasks
- Analytics causing side effects

Why it happens:
- Desire for “smart” systems
- Confusion between insight and action

Why it is dangerous:
- Hidden automation
- Unintended consequences

Correct response:
- Enforce read-only reporting
- Separate insight from execution
- Require explicit action

---

## Failure Mode 7 — Documentation Drift

Symptoms:
- Code behavior diverges from docs
- Docs are not updated with changes
- “Everyone knows how it works”

Why it happens:
- Time pressure
- Overconfidence
- Lack of ownership

Why it is dangerous:
- Invariants erode
- New contributors make unsafe changes

Correct response:
- Treat docs as canonical
- Block merges without doc updates
- Revisit Constitution regularly

---

## Summary

Most system failures are not technical.
They are **discipline failures**.

Revono avoids these by:
- Enforcing boundaries
- Requiring confirmation
- Preferring clarity over cleverness
- Treating safety as non-negotiable
