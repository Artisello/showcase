# The multi-producer WooCommerce commerce engine

**Context:** Italeen · WordPress / WooCommerce · PHP · JavaScript · CSS · WooCommerce Store API.

**My contribution:** product definition, custom plugins, integration design, storefront engineering and ongoing operational ownership.

## The hard part

A food order may include cheese from producer A and preserves from producer B. One checkout creates two distinct dispatches, potentially with different shipping tariffs, preparation times and VAT mixes. A fix in one part of a WooCommerce stack can silently break another.

I separated the problem into explicit responsibilities rather than modifying shipping totals in several places.

## Four focused components

### 1. Italeen Multi-Artisan Shipping (MAS)

- Groups an order into producer-associated shipping packages, built on WooCommerce shipping classes.
- Preserves package identity and exposes producer-level fulfillment context.
- Integrates with WooCommerce Table Rate Shipping and supports Classic and Block checkout paths in the codebase.
- Keeps the selected shipping method—not MAS—responsible for the commercial shipping amount.

### 2. Italeen Proportional Shipping Tax (PST)

- Works **after** packages have been split.
- Allocates each final package's shipping VAT across the product tax rates relevant to that package.
- Preserves the selected gross shipping amount rather than adding a new shipping fee.
- Records accounting-relevant allocation snapshots in the order.

### 3. Italian Product Compliance

- Calculates comparison prices per kilogram, litre or piece.
- Handles product variations and quantity semantics including drained weight.
- Keeps historical order snapshots separate from changes to the catalog.

### 4. Bottega Futura — GeneratePress child theme

- Owns presentation, accessibility and responsive storefront composition.
- Uses public WooCommerce and plugin contracts rather than duplicating tax or shipping calculations in JavaScript.
- Has explicit integration boundaries for SearchIQ, caching and optimization layers.

## Responsibility map

~~~text
Customer / Cart / Checkout
          |
          v
WooCommerce products, prices and order lifecycle
          |
          +---- MAS: producer packages and fulfillment context
          |                |
          |                v
          |      Table Rate Shipping: commercial rates
          |                |
          |                v
          +---- PST: package-level shipping VAT allocation
          |
          +---- Product Compliance: unit price / food quantity facts
          |
          v
WooCommerce order and fiscal snapshots
          |
          v
Bottega Futura: presentation through public interfaces
~~~

## Design decisions

- **Keep money authoritative in WooCommerce.** Display features never recompute commercial totals.
- **One owner per concern.** MAS does package identity; PST does proportional VAT; Product Compliance does unit pricing; the theme renders.
- **Support old and new checkout paths intentionally.** Classic templates and Blocks / Store API have different integration points.
- **Treat producer workflows as operations, not merely UI.** Accurate packages and dates matter to the actual fulfillment process.

## What is public evidence?

[Italeen.com](https://italeen.com) provides an accessible storefront, producer-specific shipping policy and visible unit prices. Architectural details are summarized from maintained private repository documentation. **These source capabilities should not be interpreted as independently verified deployment status or compliance certification.**

[← Back to portfolio](../README.md)
