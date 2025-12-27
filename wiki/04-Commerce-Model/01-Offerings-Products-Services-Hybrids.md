# Offerings: Products, Services, and Hybrids

This document defines how Revono models what a business sells.

Everything Revono reasons about is modeled as an **offering**.

This abstraction is foundational.
If offerings are modeled incorrectly, the entire system becomes unsafe.

---

## What Is an Offering

An offering represents something a business sells to a customer.

An offering may be:
- A **product**
- A **service**
- A **hybrid**

Offerings are not UI concepts.
They are commercial truth.

---

## Why Offerings Exist

Most systems fail by:
- Treating everything as a product
- Bolting services on later
- Applying inventory globally
- Inferring fulfillment behavior

Revono avoids these failures by:
- Making fulfillment explicit
- Evaluating behavior per offering
- Never guessing what something is

---

## Product Offerings

A product offering represents a tangible good.

Characteristics:
- Inventory applies
- Quantity matters
- Fulfillment deducts stock
- Cost of goods sold is tracked

Product offerings may:
- Be batched
- Have expiry
- Use FIFO or similar allocation

Product offerings **always** interact with inventory.

---

## Service Offerings

A service offering represents non-tangible work or value.

Characteristics:
- No inventory applies
- Time-based or outcome-based
- Fulfillment does not deduct stock
- Cost may be labor or overhead

Service offerings **never** interact with inventory.

If inventory is touched, the model is incorrect.

---

## Hybrid Offerings

A hybrid transaction contains both products and services.

Important clarification:
- There is no single “hybrid offering”
- Hybridity exists at the **transaction level**

Each line item is evaluated independently:
- Product lines follow product rules
- Service lines follow service rules

This separation guarantees safety.

---

## Offering Classification Rules

Offering type must be:
- Explicit
- Declared
- Stored

Offering type must **never** be:
- Inferred
- Guessed
- Derived from price or quantity
- Determined by UI behavior

If classification is unclear, the system must ask.

---

## Design Consequence

All downstream logic depends on offering type:
- Fulfillment behavior
- Inventory interaction
- Commercial flow selection
- Reporting and analytics

If offering classification is wrong, everything else is wrong.

---

## Summary

Revono treats offerings as first-class commercial entities.

By modeling products, services, and hybrids explicitly:
- Inventory safety is guaranteed
- Hybrid transactions are safe by construction
- Commercial correctness is preserved

This is not a feature.
It is a foundation.
