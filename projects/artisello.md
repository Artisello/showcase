# Artisello — applying operational lessons to mobile and B2B software

**Public Android listing:** https://play.google.com/store/apps/details?id=com.artisello.app

This is my current startup work. I include it here to demonstrate technical breadth, while keeping the distinction between a publicly listed mobile product and emerging B2B projects.

## Consumer product: discover real local food

The Artisello Android app helps people explore Italian foods, producers, places and events, then save and record their experiences.

The app's technical foundation includes:

- React Native / Expo mobile application and map-based discovery.
- A PostgreSQL / PostGIS data foundation with location-aware queries.
- Supabase-backed authentication and user-scoped records.
- Food, producer, territory, place and event data models.
- Personal food experiences and saved collections.

**Public evidence:** the [Google Play listing](https://play.google.com/store/apps/details?id=com.artisello.app). A store listing confirms distribution, not active users or revenue.

## Trade: a different product and stage

Italeen exposed a deeper B2B problem: product information often lives in documents and email, while buyers and producers need to discuss offers using accurate, authorized facts.

The Artisello Trade MVP explores this workflow:

1. An authorized supplier provides a product document.
2. Software extracts or proposes structured product information.
3. A human checks and approves material facts.
4. Private buyer–supplier requests and offers retain the right visibility.
5. Revisions and decisions retain provenance.

**Status:** early/pilot development. No claim here of a production marketplace, automatic legal compliance, verified traction or fully autonomous AI agents.

## Independent API foundation

A separate FastAPI / PostgreSQL project explores canonical identities, product/catalog records, channel-aware commerce events and the foundations of future contractual entitlements. It is **not** a drop-in replacement for the current Supabase Trade application and is not claimed as a live financial infrastructure.

## The common thread

Italeen taught me the operating constraints. The mobile app addresses food discovery; Trade explores repeatable commerce and trusted business information. These are related problems, but distinct products with distinct levels of readiness.

[← Back to portfolio](../README.md)
