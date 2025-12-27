# Scheduling Safety

This document defines how scheduling operates in Revono.

Scheduling exists to **deliver information**, not to execute actions.
It is treated as execution-adjacent and is therefore tightly controlled.

---

## Scheduling Is Not Automation

Scheduling in Revono is limited to:
- Report delivery
- Information summaries
- Insight notifications

Scheduling is explicitly **not**:
- Workflow execution
- Operational automation
- Customer-facing action
- Financial or inventory mutation

If a schedule can change system state, the design is invalid.

---

## Explicit Creation Requirement

All schedules must be:
- Explicitly created by a human
- Previewed before confirmation
- Confirmed with full visibility of effects

There are no default schedules.
There is no implicit scheduling.

---

## Schedule Definition Rules

A schedule definition must explicitly declare:
- What report or summary is delivered
- Delivery frequency
- Delivery destination
- Tenant scope
- Failure behavior

Implicit assumptions are forbidden.

---

## Execution Behavior

Scheduled execution:
- Runs deterministically
- Uses tenant-scoped credentials
- Accesses read-only data only
- Cannot trigger execution logic

Scheduled jobs do not “decide” anything.
They deliver exactly what was defined.

---

## Failure Handling

If scheduled delivery fails:
- No retries occur silently
- Failures are surfaced to the tenant
- No cascading effects occur

Scheduling failures must never impact operations.

---

## Pausing and Cancellation

All schedules must be:
- Pausable
- Editable
- Cancelable

Cancellation:
- Is explicit
- Is auditable
- Does not affect historical data

---

## Audit Requirements

All scheduling actions must be audited, including:
- Creation
- Modification
- Execution
- Failure
- Cancellation

Audit logs must be tenant-scoped and immutable.

---

## Design Constraint

If a scheduling feature requires:
- Hidden retries
- Conditional execution
- Cross-tenant context
- Side effects beyond delivery

The feature must be rejected or redesigned.

---

## Summary

Scheduling in Revono delivers information on a timer —
nothing more.

This ensures insight scales
without turning into unsafe automation.
