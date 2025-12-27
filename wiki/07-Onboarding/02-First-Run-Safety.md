# First-Run Safety Guarantees

This document defines the safety guarantees that apply
from the very first use of Revono.

First-run behavior must be **strictly safer**, never looser,
than normal operation.

---

## No Silent Side Effects

During first use, Revono must never:
- Send emails automatically
- Notify customers or suppliers
- Schedule reports or summaries
- Trigger integrations
- Export data
- Modify inventory
- Create financial records

Nothing leaves the system without explicit confirmation.

---

## No Implicit Execution

First-run flows must never:
- Auto-confirm proposals
- Execute “example” actions
- Apply demo data to real records
- Perform irreversible steps silently

All execution requires conscious intent.

---

## Demo and Sample Data Rules

If demo or sample data is used:
- It must be clearly labeled
- It must be isolated from real data
- It must be removable
- It must never affect accounting or inventory

Demo data must never masquerade as real data.

---

## Confirmation Is Mandatory

During first use:
- Impact Summaries must be shown
- Confirmation must be explicit
- Cancellation must always be possible

Onboarding does not reduce confirmation requirements.

---

## Conservative Defaults

First-run defaults must:
- Avoid automation
- Avoid scheduling
- Avoid integrations
- Avoid outbound communication

Defaults favor safety over convenience.

---

## Audit from Day One

All first-run actions that do occur must:
- Be audited
- Be tenant-scoped
- Be attributable to a user

There is no unaudited “getting started” behavior.

---

## Error Handling on First Run

If something fails during onboarding:
- No retries occur silently
- No fallback execution happens
- Errors are explained clearly

Failure must not create hidden state.

---

## Design Constraint

If a first-run experience requires:
- Hidden execution
- Reduced confirmation
- Skipped audit logging
- Silent side effects

The experience must be redesigned.

---

## Summary

Revono earns trust on day one by:
- Doing less
- Showing more
- Asking before acting
- Leaving nothing hidden

First impressions are permanent.
