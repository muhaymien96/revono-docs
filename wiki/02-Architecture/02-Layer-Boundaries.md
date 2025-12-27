# Layer Boundaries

This document defines the **hard boundaries** between system layers in Revono.

These boundaries are enforced by architecture, credentials, and execution design —
not by developer discipline or convention.

If logic appears in the wrong layer, it is a **defect**.

---

## Boundary Philosophy

Each layer has:
- Explicit responsibilities
- Explicit prohibitions

No layer may “help” another by overstepping its role.

Boundaries exist to prevent:
- AI autonomy
- UI-driven logic
- Implicit side effects
- Safety erosion over time

---

## Layer 1 — Interface Layer (Human Authority)

### Responsibilities

The Interface Layer is responsible for:
- Capturing human intent (chat, forms, onboarding)
- Rendering structured proposals
- Displaying Impact Summaries
- Requiring explicit confirmation
- Rendering reports and previews
- Displaying execution outcomes

### Explicitly Forbidden

The Interface Layer must **never**:
- Contain business logic
- Mutate state
- Trigger execution
- Perform calculations with financial impact
- Interpret fulfillment rules
- Decide execution paths

If the UI “knows” how something should behave,
that logic belongs elsewhere.

---

## Layer 2 — Intelligence Layer (Reva)

### Responsibilities

The Intelligence Layer is responsible for:
- Interpreting user intent
- Resolving entities explicitly
- Identifying offerings (product, service, hybrid)
- Analyzing fulfillment per line item
- Selecting commercial flows
- Detecting and explaining risk
- Generating structured proposals
- Explaining consequences in human terms

### Explicitly Forbidden

The Intelligence Layer must **never**:
- Write to the database
- Send emails or notifications
- Charge or refund money
- Deduct or adjust inventory
- Schedule jobs or workflows
- Execute actions of any kind

Reva reasons and proposes.
It never acts.

---

## Layer 3 — Execution Layer (Deterministic Authority)

### Responsibilities

The Execution Layer is responsible for:
- Validating approved proposals
- Applying predefined business logic
- Mutating state deterministically
- Triggering declared side effects
- Emitting complete audit logs

### Explicitly Forbidden

The Execution Layer must **never**:
- Accept natural language input
- Call AI models
- Infer intent or behavior
- Branch probabilistically
- Perform undeclared side effects

Execution enforces reality.
It does not interpret meaning.

---

## Cross-Layer Interaction Rules

- The Interface Layer may **request** reasoning
- The Intelligence Layer may **propose** actions
- Only the Execution Layer may **mutate** state

There is no direct path:
- From UI → Execution
- From Reva → Database
- From Reva → Side Effects

Any shortcut is a critical defect.

---

## Boundary Violations

The following are considered boundary violations:
- UI calling execution functions directly
- AI tools mutating state
- Execution logic branching on AI output
- UI conditionals deciding fulfillment behavior
- AI-generated instructions passed to execution

Boundary violations must be fixed immediately.

---

## Enforcement Rule

If a feature requires crossing a boundary,
the design is wrong.

The correct response is to redesign —
not to add exceptions.
