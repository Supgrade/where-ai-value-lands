---
title: Taker / Shaper / Maker (WEF Adoption Archetypes)
status: concept
tags:
  - adoption
  - strategy
  - framework
  - consultancy
last-updated: 2026-05-22
---

# Taker / Shaper / Maker

A strategic-adoption typology from [[wef-ai-in-action-2025]] (echoed in [[non-tech-digital-core-synthesis]]). Names three positions a non-tech enterprise can take relative to foundation models.

## The three archetypes

- **Taker** — integrate commercial off-the-shelf AI into existing workflows. Minimal customization. The model is rented as a service; the firm's job is to wire it into business processes.
- **Shaper** — augment an existing foundation model with proprietary data, fine-tunes, RAG over internal knowledge, or domain-specific evaluation. The base model is rented; the differentiation is in the *layer above it*.
- **Maker** — train bespoke foundation models from scratch. Full vertical ownership of model weights, training data, training compute. Only a small fraction of non-tech firms have the capital or talent to do this.

## How it relates to the other ladders

The taker/shaper/maker axis is a **strategic-positioning** axis, distinct from but interacting with:

| Axis | What it answers |
|------|-----------------|
| [[taker-shaper-maker]] | *How much of the model do we own / customize?* |
| [[H1_L0-L7-ladder]] | *How much of the substrate stack do we own?* |
| [[enterprise-adoption-ladder]] | *How deeply has AI penetrated our operations?* |
| [[digital-core]] | *Have we built the architectural preconditions?* |

A firm can sit anywhere on the taker/shaper/maker spectrum at any phase of the adoption ladder. The interesting empirical fact is that **most non-tech firms are takers**, and the bull-managerial frame implicitly assumes this — its case studies (Accenture / SAP / Databricks customers) are nearly all takers and shapers, almost never makers.

## What the typology reveals

- **The strategic question is not "should we use AI?" but "what is our position relative to the foundation model?"** This is more useful than the binary "AI vs. no AI" framing common in earlier consultancy material.
- **Most differentiation lives at the shaper layer.** Taker has no moat (everyone rents the same API). Maker is gated by capex. Shaper is where domain knowledge, proprietary data, and workflow integration compound — and is plausibly where the largest population of non-tech firms can build defensible positions.
- **Shaper-vs-taker is the consultancy upsell axis.** Accenture's commercial interest is precisely to move clients from taker (cheap, commoditized) to shaper (custom integration work, ongoing engagement). Read the typology with this in mind.

### Mapping to the OECD SME taxonomy

[[oecd-sme-ai-adoption-2025]] proposes a buyer-side SME four-stage taxonomy ([[oecd-sme-adopter-taxonomy]]) — Novices, Optimisers, Explorers, Champions — that maps approximately onto Taker / Shaper / Maker (see also [[sme-policy-pathway-novice-to-champion]]):

- **AI Novices** → **Takers.** Renting turnkey gen-AI via cloud APIs; no internal AI capability. The Novice rents narrowly.
- **AI Optimisers** → **Takers transitioning to Shapers.** Embedding off-the-shelf AI widely across functions; co-funding training; beginning to restructure operations around it.
- **AI Explorers** → **Shapers.** Developing bespoke tools, custom agents, fine-tunes on proprietary data in narrow scope; consuming sovereign compute and curated datasets; investing in long-term R&D. The model is rented; the layer above it is proprietary.
- **AI Champions** → deep **Shapers**, occasionally small-scale **Makers** (e.g. SMEs operating near the frontier — such as those training proprietary ML stacks for rare-disease drug discovery, where the data + model architecture is genuinely the business). Integrated into innovation ecosystems; minimal direct subsidy needs.

Two implications follow:

- **The OECD case-study evidence supports the commercial-interest reading.** Most SMEs are pure Takers (Novices + Optimisers); the consultancy / policy upsell is precisely to move them into the Shaper layer (Explorers / Champions).
- **Empirical support for "most differentiation lives at the shaper layer."** Calvino & Fontanelli (2024) show firms developing AI internally capture significantly larger productivity premia than firms sourcing externally ([[ai-productivity-firm-level]]).

Policy instruments differ at each stage: Novices need awareness; Optimisers need skills and pre-approved tools; Explorers need compute and data; Champions need stable ecosystem and frontier infrastructure. This is the buyer-side policy analogue of the supplier-side rent/customize/train framing.

## What it hides

- **Renting the maker layer.** A "shaper" who builds on top of OpenAI is still paying surplus to OpenAI. Taker/shaper/maker says nothing about whether the firm captures or transfers value at the underlying layer. See [[H1_L0-L7-ladder]].
- **Distribution.** A Maker that nobody uses captures no value. A Taker with a dominant user relationship may capture more than a Maker without one. See [[distribution-moat]].
- **The middle dies.** The Shaper position assumes the middle of the stack is defensible. [[middle-layer-defensibility]] argues this is true *only* for distribution-embedded platforms (Cursor, Windsurf) — a generic shaper without distribution is a thin wrapper.
- **Bloc divergence.** In China, the Maker layer is partially commoditized via [[open-weight-asymmetry]], collapsing the cost gap between Shaper and Maker. In the EU, [[sovereign-ai]] is an attempt to push national champions toward Maker status via subsidy, which is structurally different from US private-capital Maker plays.

## Why the framing persists

It is **legible to executive buyers**: three boxes, one per strategic appetite for risk and capital. It is also **flattering to non-tech firms**: it presents Shaper as a credible position rather than admitting that most firms will remain pure Takers. And it is **commercially aligned with consultancies**: every transition between archetypes is a multi-year engagement.

## Use in the paper

Likely useful as a *foil*: introduce the typology as the consensus consultancy framing, then show what it leaves out — substrate ownership ([[H1_L0-L7-ladder]]), distribution ([[distribution-moat]]), surplus capture ([[capital-labor-divergence]]), and bloc structure ([[divergent-value-stack-optima]]). The paper's value is to surface the dimensions the typology collapses.

## Related

- [[wef-ai-in-action-2025]] — primary source.
- [[non-tech-digital-core-synthesis]] — restatement.
- [[digital-core]] — architectural precondition the typology assumes.
- [[foundational-enablers]] — the enabler frame the typology sits inside.
- [[H1_L0-L7-ladder]] — substrate-ownership axis the typology collapses.
- [[enterprise-adoption-ladder]] — buyer-side maturity ladder; orthogonal axis.
- [[distribution-moat]] — strategic asset the typology ignores.
- [[middle-layer-defensibility]] — the load-bearing question for Shapers.
- [[ai-startup-business-archetypes-weber]] — seller-side companion taxonomy; together Taker/Shaper/Maker (buyer-side) + Weber's four patterns (seller-side) + [[ecosystem-business-archetypes]] (ecosystem-position) form the three-lens Axis 3.
- [[open-weight-asymmetry]] — what happens to the Maker layer in China.
- [[sovereign-ai]] — EU push toward national-champion Makers.
- [[oecd-sme-ai-adoption-2025]] — SME-side mapping.
- [[oecd-sme-adopter-taxonomy]] — the buyer-side decomposition that maps onto Taker/Shaper/Maker.
- [[sme-policy-pathway-novice-to-champion]] — staged policy instruments along the same axis.
- [[sme-ai-adoption-gap]] — empirical context for the Taker-population size.
- [[ai-productivity-firm-level]] — evidence for the Shaper premium.
- [[H5_ai-as-operational-not-product]] — applies the Taker/Shaper/Maker decomposition at firm level: the operator-builder is a Taker of AI capability, a Shaper of harness, and a Maker of a non-AI deliverable.
