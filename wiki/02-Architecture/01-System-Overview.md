# System Overview

This document describes the high-level structure of Revono.

It explains how the system is partitioned to enforce:
- Safety over autonomy
- Determinism over cleverness
- Explicit human authority
- Auditability of all actions

This document describes **structure**, not features.

---

## Core Structural Insight

Revono is built on a strict separation between:

- **Human Authority**
- **AI Reasoning**
- **Deterministic Execution**

These concerns are intentionally isolated to prevent
AI autonomy, implicit behavior, and unsafe mutations.

---

## High-Level System Flow

1. A human expresses intent  
2. AI reasons about intent and consequences  
3. The system proposes an action  
4. The human explicitly confirms or rejects  
5. Deterministic execution applies changes  
6. The system records an audit trail  

At no point may AI act autonomously.

---

## Primary System Components

Revono consists of three primary layers:

### 1. Interface Layer (Human Authority)

Responsibilities:
- Capture human intent
- Display proposals
- Render impact summaries
- Require explicit confirmation
- Display results and reports

Restrictions:
- No business logic
- No state mutation
- No side effects

---

### 2. Intelligence Layer (Reva)

Responsibilities:
- Interpret intent
- Resolve entities
- Analyze data
- Select commercial flows
- Detect risk
- Generate proposals
- Explain consequences

Restrictions:
- Read-only access only
- No mutation capability
- No execution authority
- No side effects

---

### 3. Execution Layer (Deterministic Authority)

Responsibilities:
- Validate approved proposals
- Apply predefined logic
- Mutate state
- Trigger declared side effects
- Emit audit logs

Restrictions:
- No AI involvement
- No natural language input
- No probabilistic behavior

---

## Architectural Goal

This separation ensures that:

- AI can reason but never act
- Humans can approve but never bypass safeguards
- Execution is predictable and auditable

If any responsibility crosses layers,
the architecture is considered broken.
