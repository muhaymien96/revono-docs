# Exports and Previews

This document defines how Revono generates previews and exports.

Previews and exports produce **artifacts**.
Artifacts must never introduce ambiguity, mutation, or silent behavior.

---

## Preview-First Principle

All exports must be:
- Previewed before generation
- Explicitly confirmed
- Deterministically generated

Nothing is generated “in the background”.

---

## What Previews Are

Previews are:
- Read-only representations
- Deterministic snapshots
- Derived from approved queries
- Visually rendered for inspection

Previews never:
- Mutate data
- Trigger execution
- Schedule delivery

If a preview causes side effects, the system is broken.

---

## Export Rules

Exports must:
- Be initiated explicitly
- Match the preview exactly
- Use deterministic formatting
- Be tenant-scoped
- Be auditable

Exports may include:
- CSV
- PDF
- Spreadsheet formats
- Structured data outputs

Exports must never:
- Trigger execution
- Modify source data
- Combine multiple tenants
- Include undeclared fields

---

## Export Confirmation

Before export generation, the system must show:
- What data will be included
- Time range
- Format
- Destination
- Size implications

The user must explicitly confirm.

---

## Export Execution

Export generation:
- Uses read-only data access
- Executes deterministically
- Produces a single artifact
- Emits an audit record

If export generation fails:
- No partial artifact persists
- Failure is surfaced clearly

---

## Scheduled Exports

Scheduled exports follow all scheduling rules:
- Explicit creation
- Preview before scheduling
- Deterministic execution
- No hidden retries

Scheduled exports never:
- Trigger execution
- Modify operational state

---

## Artifact Handling

Generated artifacts:
- Are immutable
- Are tenant-scoped
- May expire by policy
- Are never silently replaced

Regeneration requires explicit action.

---

## Audit Requirements

All export actions must be audited, including:
- Preview generation
- Export confirmation
- Export execution
- Delivery
- Failure

Artifacts without audit records are invalid.

---

## Summary

Exports and previews in Revono are:
- Explicit
- Deterministic
- Previewed
- Auditable
- Safe

This ensures insight can be shared
without turning reporting into execution.
