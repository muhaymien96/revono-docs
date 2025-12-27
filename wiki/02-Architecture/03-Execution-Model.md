# Execution Model

This document defines how approved actions are executed in Revono.

Execution is the **only** phase where state may change.
It is deliberately isolated, deterministic, and auditable.

If execution behavior is unclear, the system is unsafe.

---

## Core Execution Principle

Execution is **authority**, not intelligence.

It does not:
- Interpret intent
- Understand language
- Make decisions
- Evaluate risk
- Optimize outcomes

Execution applies reality exactly as approved.

---

## End-to-End Execution Flow

All executions follow the same sequence:

1. A structured proposal is generated  
2. An Impact Summary is rendered  
3. A human explicitly confirms  
4. Execution validates the proposal  
5. Deterministic logic is applied  
6. Side effects are triggered  
7. An audit record is written  

If any step fails, execution does not occur.

---

## Execution Inputs

Execution functions accept **structured data only**, including:
- Approved action type
- Affected entities
- Quantities and values
- Declared side effects
- Tenant context
- Approving user identity

Natural language is never accepted as input.

---

## Validation Before Execution

Before mutating state, execution must validate:
- The proposal was approved
- The approving user is authorized
- The tenant context is correct
- The action matches the proposal
- The Impact Summary is complete

If validation fails, execution aborts.

---

## Deterministic Logic Requirement

Execution logic must be:
- Predefined
- Explicit
- Testable
- Reproducible

Forbidden:
- AI involvement
- Probabilistic branching
- Dynamic rule interpretation
- “Best effort” logic

The same input must always produce the same result.

---

## Side Effect Control

Execution may only perform side effects that were:
- Explicitly declared
- Shown in the Impact Summary
- Approved by the human

Side effects include:
- Emails
- Notifications
- Inventory movements
- Financial mutations
- Schedules
- Exports

Hidden side effects are forbidden.

---

## Failure Handling

If execution fails:
- No partial state may persist
- No partial side effects may occur
- No retries may happen silently

Failures must be surfaced immediately and clearly.

---

## Audit Trail

Every execution must produce an audit record containing:
- Tenant identifier
- Approving user
- Action type
- Affected entities
- Timestamp
- Execution outcome

Audit logs are immutable and tenant-scoped.

---

## Execution Is Final

Once execution completes successfully:
- Changes are real
- Changes are visible
- Changes are auditable

There is no rollback via inference.
Corrections require explicit new actions.

---

## Architectural Guarantee

This execution model guarantees that:
- AI never mutates data
- Humans always approve impact
- All changes are intentional
- All changes are traceable

If execution deviates from this model,
the architecture is broken.
