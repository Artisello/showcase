# Supplier Portal — reducing manual work with producers

**Context:** Italeen → Artisello Trade.

**Stage:** active MVP / pilot candidate. Code and tests exist in private repositories; the full production integration and real multi-buyer adoption have not been verified.

## Problem observed at Italeen

A multi-producer checkout creates work after payment: a supplier needs to understand an order, confirm whether it can fulfill it, prepare the goods and respond to exceptions. Repeated calls, messages and document exchanges do not scale.

## Product approach

Focus on **one repeated operational job** rather than building an ERP:

1. Producer receives a narrowly scoped, signed, single-order interaction.
2. Producer can confirm or decline and communicate an exception.
3. Store operator can see unresolved cases and decide what to do next.
4. Events are attributed and recorded so an issue can be reviewed later.

The broader codebase also explores versioned food technical sheets, evidence-driven review and private supplier workspaces. These capabilities are **not** all represented as released to production.

## Architectural principles

- Supplier/customer data is not made public by default.
- Short, explicit actions are preferable to elaborate dashboards.
- Keep WooCommerce authoritative for orders and payments.
- Preserve provenance and human verification for sensitive business documents.
- Integrations (for example shipping providers or Artisello) must be activated and verified independently.

## Why I built it

The original insight came from running Italeen: a producer usually does not need another complex application; they need the simplest reliable way to answer the next important question.

[← Back to portfolio](../README.md)
