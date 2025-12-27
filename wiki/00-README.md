# Revono Canonical Wiki

This repository contains the **canonical system documentation** for Revono and Reva.

These documents define:
- Architectural boundaries
- System invariants
- AI authority limits
- Commercial correctness rules

If there is a conflict between:
- Code
- UI behavior
- Verbal explanation
- These documents

👉 **These documents win.**

---

## Structure

- `01-Constitution` — System law (non-negotiable)
- `02-Architecture` — Structural boundaries
- `03-Reva-AI` — AI reasoning model and limits
- `04-Commerce-Model` — Product/service correctness
- `05-Reporting-Automation` — Read-only analytics & schedules
- `06-Platform` — Multi-tenancy & gating
- `07-Onboarding` — Trust establishment
- `08-Developer-Guide` — How to change the system safely
- `09-Glossary` — Shared definitions

---

## Change Discipline

Any change that affects system behavior **must** update the relevant document.

If code behavior contradicts this wiki, the code is wrong.
