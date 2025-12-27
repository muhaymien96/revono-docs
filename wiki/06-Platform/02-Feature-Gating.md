# Feature Gating and Entitlements

This document defines how Revono controls feature availability
across plans, pricing tiers, and tenant entitlements.

Feature gating must never affect correctness, safety, or execution behavior.

---

## Core Gating Principle

Feature gating controls **access**, not **behavior**.

If enabling or disabling a feature changes:
- Execution safety
- Financial correctness
- Inventory behavior
- Audit guarantees

The gating model is invalid.

---

## What Feature Gating May Control

Feature gating may control:
- UI visibility
- Access to reports
- Access to analytics depth
- Access to integrations
- Access to automation setup
- Usage limits

Feature gating may not control:
- Core execution rules
- Confirmation requirements
- Invariant enforcement
- Audit logging
- Tenant isolation

---

## Enforcement Layer

Feature gating is enforced:
- At request entry
- Before proposal generation
- Before execution authorization

Execution logic does not branch based on plan tier.

---

## Gating and Reva

Reva may:
- Be aware of feature availability
- Explain why a feature is unavailable

Reva may never:
- Propose gated actions as if available
- Alter proposals to bypass gating
- Infer plan upgrades

Reva informs. It does not negotiate.

---

## Feature Availability and Safety

If a tenant lacks access to a feature:
- The feature is unavailable
- No partial behavior is allowed
- No degraded execution path exists

“Lite” execution paths are forbidden.

---

## Entitlement Changes

When entitlements change:
- New access is granted explicitly
- No historical behavior is reinterpreted
- No backfilled execution occurs

Upgrades unlock access going forward only.

---

## Audit Requirements

All entitlement changes must be audited, including:
- Plan upgrades
- Plan downgrades
- Feature enablement
- Feature removal

Entitlement audits are tenant-scoped and immutable.

---

## Design Constraint

If a feature requires:
- Different execution behavior per plan
- Weakened safety guarantees for lower tiers
- Conditional audit behavior

The feature must be redesigned or rejected.

---

## Summary

Feature gating in Revono controls access,
not correctness.

This ensures monetization never compromises safety.
