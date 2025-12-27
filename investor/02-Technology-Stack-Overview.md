# Revono — Technology Stack Overview

This document provides a high-level overview of the technology stack
used to implement Revono’s architecture.

The stack is intentionally modern, boring, and replaceable.

No architectural guarantees depend on a specific vendor or framework.

---

## Frontend

- React (TypeScript)
- Component-driven UI
- No business logic in the frontend
- Mobile-first, PWA-compatible

The frontend is responsible for rendering intent, proposals,
impact summaries, and confirmations only.

---

## Backend & Data

- Supabase (PostgreSQL)
- Row-Level Security (RLS) for tenant isolation
- Explicit audit tables
- Strong typing via generated schema definitions

All data access is tenant-scoped by construction.

---

## Execution Layer

- Server-side functions (Edge Functions)
- Deterministic execution only
- No AI involvement
- No natural language inputs

This layer is the only authority that mutates state.

---

## AI & Reasoning

- OpenAI APIs (reasoning only)
- LangChain for orchestration
- LangGraph for structured reasoning graphs

AI is strictly read-only and is never part of the execution path.

AI assists with:
- Intent interpretation
- Risk analysis
- Proposal generation
- Explanation

---

## Automation & Scheduling

- Rule-based execution
- Explicit user-delegated automation only
- Deterministic schedulers
- No autonomous workflows

All automation is auditable, scoped, and revocable.

---

## Integrations

- Webhook-based integrations
- Explicit inbound and outbound mapping
- No external system holds execution authority

Integrations are treated as untrusted by default.

---

## Observability & Audit

- Immutable audit logs
- Execution tracing
- Tenant-scoped logs

All impactful actions are traceable.

---

## Scalability & Replaceability

The architecture allows:
- Swapping AI providers
- Replacing frontend frameworks
- Migrating backend infrastructure
- Adding execution capacity independently

No vendor lock-in exists at the architectural level.

---

## Summary

Revono’s stack is chosen to:
- Support strict authority boundaries
- Enable deterministic execution
- Scale safely with tenant growth
- Remain understandable to future teams and acquirers

The architecture defines the system.
The stack implements it.
