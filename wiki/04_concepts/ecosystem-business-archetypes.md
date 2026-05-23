---
title: Ecosystem Business Archetypes (Choudary)
status: active
tags:
  - concepts
  - vocabulary
  - platforms
  - ecosystems
last-updated: 2026-05-23
---

# Ecosystem Business Archetypes (Choudary)

Sangeet Paul Choudary's four-archetype framework for **horizontal business models** that emerge once a vertically integrated value chain unbundles into a layered ecosystem. The vocabulary predates the AI wave (the canonical statement is the 2022 teardown — see [[choudary-ecosystem-teardown]]) but it is the cleanest off-the-shelf taxonomy for naming *where in the ecosystem* a firm sits and *how that position captures value*.

The four archetypes are not stack layers (Axis 1) and not levels of autonomy (Axis 2). They are positions in a **horizontal ecosystem** — orthogonal cuts on the value chain.

## The four archetypes

| Archetype | Faces | Mechanism | Canonical examples |
|---|---|---|---|
| **Aggregator** | Consumer (B2C) | Aggregates demand; owns consumer engagement and data; gatekeeps producer market access | Facebook, Amazon, Netflix, Apple, Google |
| **Integrator** | B2B (producer ↔ distributor) | API switchboard: integrates supply-side product APIs with demand-side distribution surfaces | Amadeus, Sabre (travel); Plaid, Galileo (BaaS) |
| **Infrastructure** | Whole ecosystem | Provides core production substrate, standards, roadmap; coordinates ecosystem firms toward a shared output | iOS, AWS, Shopify, Autodesk Construction Cloud, DeepMind |
| **Capability** | Ecosystem firms (embeddable) | Specialised function licensed via APIs / modules; embedded inside aggregators, integrators, infrastructures | Stripe, identity providers, healthcare diagnostic AI |

### Aggregator
Consumer-facing. Three functions: (1) provisioning consumer services, (2) capturing and monetising consumer data, (3) matchmaking producers ↔ consumers. The strategic asset is **ownership of consumer engagement** — increasingly scarce, increasingly valuable as a gatekeeping position. Aggregation Theory's home archetype.

### Integrator
B2B switchboard between producers and distributors. Three functions: (1) production-side service integration (one-stop storefront for distributors), (2) data exchange between sides, (3) consumer analytics fed back to producers. Quietly dominant in industries that **look fragmented from the outside** (travel inventory, payment rails, banking-as-a-service).

### Infrastructure
The substrate the ecosystem runs on. Three functions: (1) **publish a future vision and roadmap** producers can align with, (2) provide knowledge services (data, ML models) to ecosystem actors, (3) attract third-party service providers (AWS Marketplace, Shopify Fulfilment Network). Captures value by being the coordination layer around which others organise.

### Capability
Specialised module licensed via APIs. Three functions: (1) provisioning a non-commoditised capability (requires IP / data advantage), (2) architecting for ease of embedding (developer experience is competitive), (3) using capability-usage data to improve the capability and provide analytics. Survives by **out-specialising** generalists; loses if commoditised.

## Mapping to this project

Choudary's archetypes sit on **Axis 3 — Business Archetype** ([[07_analytical-vocabulary]]). They give a clean four-way decomposition that complements the project's fifteen-archetype roster:

| Choudary | This project (partial mapping) |
|---|---|
| Aggregator | Consumer AI app; AI marketplace / platform |
| Integrator | System integrator; AI agency (when API-bundling); BaaS-style platforms |
| Infrastructure | Hyperscaler AI services; Foundation model lab (in part); AI developer tools (Cursor, when treated as developer platform) |
| Capability | Data services; deep tech startup (when API-licensed); identity / payments / verticalised AI APIs |

The mapping is **not bijective**. OpenAI is Foundation + Capability + (consumer) Aggregator simultaneously. The point of Choudary's framework is to force a primary-archetype choice and surface mistakes — see [[cross-archetype-confusion]].

## Why this matters for "where AI value lands"

The 2022 framework predicts the modern AI wave's value-capture pattern with little adjustment. Distribution-moat firms ([[distribution-moat]]: Cursor, Perplexity, Windsurf) are **Aggregators in B2B clothing** — consumer-of-developer engagement, data flywheel, gatekeeping the model providers below. Foundation-model labs occupy the **Infrastructure** archetype (publish a roadmap, provide knowledge services as licensed weights, attract third-party ecosystems). Most failed mid-stack AI startups attempted **Capability** positions without the IP or distribution to survive commoditisation.

This is also the cleanest answer to the [[middle-layer-defensibility]] question: there is no monolithic "middle." There is an Integrator middle (which can be defensible — Stripe-class switchboards) and an undifferentiated "thin wrapper" middle (which is not an archetype at all in Choudary's taxonomy — it is a failed Capability).

## Relationship to [[H2_u-curve-of-value]]

Choudary's "horizontal business models" thesis is a **structural precursor** to the U-curve. His claim: as vertical chains unbundle (see [[vertical-to-horizontal-unbundling]]), value concentrates in horizontal positions that span the chain. H2 is the AI-era specialisation: among Choudary's four, **Aggregators and Infrastructures capture most surplus** (top and bottom of the U), **Integrators are bimodal** (defensible if switchboard-essential, squeezed if generic), and **Capabilities concentrate or commoditise** depending on IP defensibility.

## Open questions

- Where does an Integrator's value sit on the U-curve? Plaid and Stripe both look like "top of U" by economics but sit in the middle by Choudary's position. → contradiction with H2 or refinement?
- Is the four-archetype taxonomy stable for AI-era ecosystems, or does agentic infrastructure require a fifth archetype (e.g., **Orchestrator** — the multi-agent coordination layer described in [[vertical-ai-orchestration]])?
- How do the archetypes interact with [[divergent-value-stack-optima]]? Choudary's vocabulary is US-stack-shaped; China's open-weight commoditisation strategy and the EU's compliance-layer play do not map cleanly onto Aggregator / Integrator / Infrastructure.

## Related

- [[choudary-ecosystem-teardown]] — primary source
- [[vertical-to-horizontal-unbundling]] — the structural driver behind ecosystem emergence
- [[cross-archetype-confusion]] — the strategic warning about benchmarking the wrong archetype
- [[07_analytical-vocabulary]] — Axis 3 (Business Archetype) — this framework is the cleanest off-the-shelf sub-vocabulary
- [[H2_u-curve-of-value]] — Choudary's horizontal-value thesis is the structural precursor
- [[middle-layer-defensibility]] — disambiguates which "middle" survives (Integrator-as-switchboard vs failed Capability)
- [[distribution-moat]] — Aggregator's "ownership of consumer engagement" is the canonical precursor of distribution-moat reasoning
- [[vertical-ai-orchestration]] — candidate fifth archetype (Orchestrator) for the agentic era
