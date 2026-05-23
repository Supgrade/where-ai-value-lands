---
title: "Choudary — Ecosystem Business Models: A Teardown"
status: draft
tags:
  - source
  - platforms
  - ecosystems
  - business-archetypes
last-updated: 2026-05-23
---

# Choudary — Ecosystem Business Models: A Teardown

## Citation

- **Author:** Sangeet Paul Choudary (Platform Thinking Labs)
- **Title:** *Ecosystem business models: A teardown*
- **Venue:** Platforms (Substack newsletter)
- **Published:** 2022-06-15
- **URL:** https://platforms.substack.com/p/ecosystem-business-models-a-teardown
- **Type:** Practitioner / advisory essay (consultancy-newsletter format)

## Central claim

When transaction costs fall and vertically integrated value chains unbundle into modular, layered ecosystems, value concentrates in **horizontal business models** at specific layers. There are four such archetypes — **Aggregators, Integrators, Infrastructures, Capabilities** — each with distinct functions, success criteria, and strategic logic. A firm that misidentifies its archetype (typically by benchmarking BigTech aggregators when it is actually an Integrator or Infrastructure) makes poor design choices that prevent it from realising its archetype's natural value-capture mechanism.

## Key arguments

### 1. The unbundling thesis ([[vertical-to-horizontal-unbundling]])

> "As transaction costs fall with the emergence of new digital infrastructures and new mechanisms to organise the market, the vertically integrated value chain starts to unbundle."

This is Choudary's structural premise. Falling transaction costs make multi-firm coordination cheaper, undermining the coordination-cost advantage that justified vertical integration. The result is a **modular, layered ecosystem** where firms at each layer specialise.

### 2. The four archetypes ([[ecosystem-business-archetypes]])

Horizontal business models in an ecosystem differentiate by **position in the value chain** and **side of the market** they face:

- **Aggregators** — consumer-facing (B2C). Aggregate demand, capture engagement + data, gatekeep producer access. Three functions: provision consumer services, manage consumer data insights, matchmake producers ↔ consumers. Canonical: Facebook, Amazon, Netflix, Apple, Google. (Aggregation Theory's home archetype.)
- **Integrators** — B2B switchboards. Integrate product APIs on the supply side with distribution surfaces on the demand side. Three functions: production-side integration (one-stop storefront), data exchange, consumer analytics. Canonical: Amadeus / Sabre (travel), Plaid / Galileo (banking-as-a-service).
- **Infrastructures** — substrate + standards + roadmap. Coordinate ecosystem firms toward a shared production output. Three functions: publish ecosystem roadmap, provide knowledge services (data, ML models), attract third-party providers (AWS Marketplace, Shopify Fulfilment). Canonical: iOS, AWS, Shopify, Autodesk Construction Cloud, DeepMind.
- **Capabilities** — specialised licensable functions, embedded into the other three archetypes. Three functions: provision a non-commoditised capability (requires IP / data advantage), architect for ease of embedding (developer experience), use capability-usage data for improvement + analytics. Canonical: Stripe (payments), identity providers, healthcare diagnostic AI.

### 3. The cross-archetype confusion warning ([[cross-archetype-confusion]])

> "Many B2B platforms tend to be infrastructures or integrators but they often look at the BigTech aggregators for inspiration and end up making poor design choices."

The strategic failure mode: benchmarking the wrong archetype. Each archetype has its own logic (success metrics, growth shape, data flywheel topology). Importing aggregator playbooks into integrator or infrastructure builds is a structural error.

## Key data points

This is a **conceptual** source — no empirical statistics, no measured outcomes. Its value is **vocabulary and taxonomy**, not evidence. The named examples (Facebook, Amazon, Stripe, Plaid, Amadeus, Shopify, AWS, etc.) function as illustrations of the four archetypes, not as data points.

## Figures interpreted

The source uses five illustrative diagrams (substackcdn.com URLs) showing each archetype's position in a generic value-chain schematic. Each diagram positions the archetype between producers and consumers and labels its mediating function. They are pedagogical, not analytical.

## Hypothesis touches

- **[[H1_L0-L7-ladder]]**: Neutral. Choudary's framework is about ecosystem position and value-capture archetype; it does not map directly onto an autonomy ladder. It supplies orthogonal vocabulary.
- **[[H2_u-curve-of-value]]**: **Supporting (structural precursor).** Choudary's horizontal-value thesis is a 2022 pre-AI formulation of the same structural pattern H2 describes for the AI wave. His Aggregator and Infrastructure archetypes correspond to the top and bottom of the U respectively. Integrators occupy a **bimodal middle**: defensible if switchboard-essential (Stripe, Plaid), squeezed if generic. This **partially defends** H2 against the "U is too clean" critique by supplying a richer taxonomy of what the "middle" actually contains, and it **partially threatens** H2 by suggesting durable Integrator-class middle plays exist (Stripe, Visa-style networks, BaaS providers) — see also [[middle-layer-defensibility]].

## Open questions surfaced

1. **Integrator-class value capture vs U-curve.** Stripe is a Capability by Choudary's taxonomy (specialised, embeddable) but exhibits Aggregator-like economics. Plaid is an Integrator with top-of-U margin profile. Are these counterexamples to H2 or refinements to the middle?
2. **A fifth archetype for the agentic era?** Choudary's 2022 framework predates multi-agent orchestration. [[vertical-ai-orchestration]] looks like a candidate fifth archetype — an **Orchestrator** that sits above Capability and below Aggregator. Worth testing against the four-way taxonomy.
3. **Geopolitical fit.** The archetypes are implicitly US-stack-shaped. They do not cleanly accommodate China's open-weight commoditisation strategy ([[open-weight-asymmetry]]) or the EU's compliance-as-archetype play ([[brussels-effect-and-mirage]]). [[divergent-value-stack-optima]] should be re-examined with Choudary's vocabulary as a checklist.
4. **Where does the [[H1_L0-L7-ladder]] sit relative to Choudary's archetypes?** The ladder is an autonomy axis; the archetypes are a position axis. They are orthogonal — but the paper's Axis 3 (Business Archetype) currently uses a 15-archetype roster that overlaps Choudary's four. Should the paper adopt Choudary's four as the **primary** sub-vocabulary inside Axis 3, with the 15-archetype roster as elaboration?

## See also

- [[ecosystem-business-archetypes]] — the master concept page extracted from this source
- [[vertical-to-horizontal-unbundling]] — the structural thesis behind ecosystem emergence
- [[cross-archetype-confusion]] — the strategic warning about benchmarking the wrong archetype
- [[07_analytical-vocabulary]] — Axis 3 (Business Archetype); Choudary's framework as canonical sub-vocabulary
- [[H2_u-curve-of-value]] — Choudary's horizontal-value thesis is a structural precursor
- [[middle-layer-defensibility]] — Choudary's vocabulary disambiguates which "middle" survives
- [[distribution-moat]] — Aggregator's "ownership of consumer engagement" is the canonical precursor
- [[vertical-ai-orchestration]] — candidate fifth archetype (Orchestrator) for the agentic era
- [[divergent-value-stack-optima]] — the geopolitical extension Choudary does not directly address
