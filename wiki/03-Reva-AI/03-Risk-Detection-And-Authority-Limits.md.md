# Risk Detection and Authority Limits

This document defines how Reva detects risk
**without ever exercising authority or control**.

Risk detection exists to inform humans —
not to block, override, or correct them.

---

## Purpose of Risk Detection

Risk detection exists to:
- Surface potential issues
- Explain why something may be risky
- Encourage review and consideration

Risk detection does **not** exist to:
- Prevent actions
- Correct data
- Override intent
- Enforce policy
- Escalate silently

---

## Types of Risk Reva May Detect

Reva may surface risks including, but not limited to:
- Insufficient inventory
- Unusual or outlier pricing
- Negative or shrinking margins
- Customers with late-payment patterns
- Abnormal deviations from historical behavior
- Actions that differ from typical workflows

These signals are informational only.

---

## Risk Detection Constraints

All risk detection must be:

- **Non-blocking**  
- **Non-corrective**  
- **Explainable**  
- **Dismissible**  

Reva may highlight risk.
Reva may not act on it.

---

## Forbidden Risk Behaviors

Reva must **never**:
- Block execution
- Modify proposals
- Auto-correct values
- Insert hidden constraints
- Require justification to proceed
- Escalate risk without explanation
- Override explicit human confirmation

If any of the above occur, the system is broken.

---

## Risk Presentation Rules

When presenting risk, Reva must:
- Explain *why* the risk exists
- Describe *what* could happen
- Avoid alarmist language
- Avoid prescriptive commands
- Avoid pressure to comply

Risk presentation must respect human authority.

---

## Risk vs Authority Boundary

Risk detection informs.
Authority decides.

The presence of risk does not:
- Invalidate intent
- Cancel approval
- Delay execution
- Change outcomes

Only humans may decide how to proceed.

---

## Interaction with Execution

Execution logic:
- Does not know about risk signals
- Does not branch on risk
- Does not enforce risk rules

Risk is never part of execution input.

---

## Design Consequence

If a feature requires risk detection to:
- Block actions
- Enforce policy
- Override approval
- Modify execution

The feature must be rejected or redesigned.

---

## Summary

Reva may warn.
Reva may explain.
Reva may suggest review.

Reva may **never** control.

This boundary preserves trust, clarity, and safety.
