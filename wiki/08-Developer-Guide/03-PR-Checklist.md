# Pull Request Checklist

This checklist must be completed for **every change** to Revono.

It exists to enforce the Constitution in daily development.

Skipping this checklist is equivalent to skipping safety review.

---

## Constitutional Compliance

- [ ] No Core Principle is violated
- [ ] No System Invariant is weakened
- [ ] No Explicit Refusal is bypassed
- [ ] No Constitution change is required  
      (If one is required, it has been written and approved first)

---

## Layer Discipline

- [ ] The change clearly belongs to one layer
- [ ] UI contains no business logic
- [ ] Reva remains read-only
- [ ] Execution remains deterministic
- [ ] No boundary crossings exist

---

## Authority & Safety

- [ ] All mutations require explicit confirmation
- [ ] No silent side effects are introduced
- [ ] AI does not gain execution authority
- [ ] Inventory and financial logic remain explicit
- [ ] Audit logging is preserved

---

## Reporting & Automation

- [ ] Reporting remains read-only
- [ ] Scheduling delivers information only
- [ ] No report triggers execution
- [ ] Exports are previewed and auditable

---

## Integrations & Platform

- [ ] Tenant isolation is preserved
- [ ] Feature gating affects access only
- [ ] Integrations do not gain authority
- [ ] No cross-tenant behavior exists

---

## Documentation

- [ ] Relevant wiki documents are updated
- [ ] Documentation matches code behavior
- [ ] Changes are explainable to a third party

---

## Final Sanity Check

- [ ] If this change failed in production, damage would be limited
- [ ] If an auditor reviewed this, it would be defensible
- [ ] If future-me reviewed this tired, it would still be safe

---

## Declaration

By merging this change, I confirm that:
- I understand its impact
- I accept its risks
- It does not compromise Revono’s safety or trust guarantees
