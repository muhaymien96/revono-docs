# Integrations and External Systems

This document defines how Revono integrates with external systems
while preserving safety, determinism, and authority boundaries.

Integrations are **execution-adjacent** and therefore tightly constrained.

---

## Integration Philosophy

Integrations exist to:
- Exchange data
- Synchronize state
- Deliver information

Integrations do **not** exist to:
- Transfer authority
- Delegate execution
- Introduce hidden automation
- Bypass confirmation

If an integration can act autonomously, the design is invalid.

---

## Integration Classification

All integrations fall into one of the following categories:

1. **Inbound Data Sources**  
2. **Outbound Delivery Targets**  
3. **Read-Only Sync Providers**

Each category has different constraints.

---

## Inbound Data Sources

Inbound integrations may:
- Import data explicitly
- Map external entities to internal models
- Require human review before persistence

Inbound integrations may not:
- Mutate state automatically
- Trigger execution
- Create financial or inventory records without confirmation

Imported data is treated as **untrusted until reviewed**.

---

## Outbound Delivery Targets

Outbound integrations may:
- Deliver approved reports or exports
- Send notifications explicitly declared
- Sync confirmed state

Outbound integrations may not:
- Execute workflows
- Trigger financial actions
- Modify external systems autonomously

Outbound delivery follows the same preview and confirmation rules.

---

## Read-Only Sync Providers

Read-only integrations may:
- Pull reference data
- Refresh metadata
- Provide context for reporting

Read-only integrations may never:
- Write data
- Trigger execution
- Influence execution logic

Read-only means read-only.

---

## Authentication and Credentials

Integration credentials:
- Are tenant-scoped
- Are least-privilege
- Are revocable
- Are never shared across tenants

Credential misuse is a critical defect.

---

## Integration and Reva

Reva may:
- Reason about integration data
- Explain integration status
- Propose integration-driven actions

Reva may never:
- Execute integration calls
- Retry failed integration actions
- Mask integration failures

Reva explains. Execution decides.

---

## Failure Handling

If an integration fails:
- No retries occur silently
- Failures are surfaced explicitly
- No partial state persists

Failures do not cascade.

---

## Audit Requirements

All integration-related actions must be audited, including:
- Credential changes
- Sync operations
- Data imports
- Data deliveries
- Failures

Audit logs are tenant-scoped and immutable.

---

## Design Constraint

If an integration requires:
- Autonomous execution
- Hidden retries
- Cross-tenant access
- Undeclared side effects

The integration must be rejected or redesigned.

---

## Summary

Integrations in Revono exchange information —
they never exchange authority.

This preserves determinism, trust, and control.
