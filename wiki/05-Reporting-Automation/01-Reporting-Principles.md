# Reporting Principles

This document defines the principles governing reporting and analytics in Revono.

Reporting exists to inform decisions —
not to make them, automate them, or enforce them.

---

## Core Reporting Rule

Reporting in Revono is **read-only by design**.

Reports must never:
- Mutate operational data
- Trigger execution
- Apply business logic
- Cause side effects implicitly

If a report can change the system, the design is invalid.

---

## Separation of Insight and Action

Revono strictly separates:
- **Insight** (reports, analytics, forecasts)
- **Action** (execution, automation, mutation)

Reports may inform actions,
but they may never cause them.

---

## Data Access Rules

Reporting may access only:
- Read-only database views
- Pre-aggregated metrics
- Explicitly approved joins

Reporting may never access:
- Write-enabled tables
- Execution functions
- Mutable state

This prevents accidental corruption.

---

## AI and Reporting

AI may assist reporting by:
- Translating natural language into query intent
- Explaining metrics and trends
- Summarizing results

AI may never:
- Write SQL directly
- Access raw operational tables
- Infer actions from analytics
- Trigger follow-up execution

AI explains. It does not decide.

---

## Forecasting Safety

Forecasts are:
- Probabilistic
- Informational
- Non-authoritative

Forecast rules:
- Confidence bands are mandatory
- Explanations are required
- Forecasts never trigger actions
- Forecasts never auto-schedule

Forecasts inform planning — nothing more.

---

## Tenant Isolation

All reporting is:
- Tenant-scoped
- Credential-isolated
- Execution-separated

Cross-tenant reporting is structurally forbidden.

---

## Auditability

All reporting actions that produce artifacts
(e.g. exports, schedules) must be audited.

Viewing reports does not mutate state,
but export and delivery actions must be traceable.

---

## Summary

Reporting in Revono provides:
- Insight without risk
- Analytics without authority
- Forecasts without enforcement

This preserves trust while enabling clarity.
