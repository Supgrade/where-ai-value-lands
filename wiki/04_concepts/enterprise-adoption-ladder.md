---
title: Enterprise Adoption Ladder (WEF 5-Phase)
status: concept
tags:
  - adoption
  - framework
  - consultancy
last-updated: 2026-05-22
---

# Enterprise Adoption Ladder

A buyer-side organizational maturity model proposed by [[wef-ai-in-action-2025]] (Accenture, in collaboration with the WEF AI Transformation of Industries community). Distinct from — and complementary to — the substrate-side [[H1_L0-L7-ladder]].

## The five phases

| Phase | Name | Marker | Stuck signs |
|-------|------|--------|-------------|
| 1 | Initial / ad hoc | AI sandbox experiments; basic data infra; no strategy | Regulatory paralysis, risk aversion, lack of awareness |
| 2 | "Thousand flowers bloom" | Multiple disconnected pilots; tech-savvy leaders driving MVPs | Use cases disconnected from core business |
| 3 | End-to-end reinvention | Formal AI strategy in one business domain; measurable ROI | Functional silos still intact |
| 4 | Enterprise-level reinvention | Ethical AI board; data products consumable across functions; "enterprise cognitive brain" | Inter-firm collaboration not yet structured |
| 5 | Value-chain reinvention (future vision) | AI extends across partners, suppliers, competitors; "AI as core business enabler" | (no current exemplars) |

## How it differs from L0-L7

The two ladders look superficially similar but operate on different axes:

- [[H1_L0-L7-ladder]] is a **vendor / substrate ownership** ladder. It asks: *who owns the stack?* L0 = human as API; L7 = vertically integrated datacenter + energy + model. The actor is a *builder*.
- The WEF adoption ladder is a **buyer / organizational maturity** ladder. It asks: *how deeply has this enterprise integrated AI?* Phase 1 = experiments; Phase 5 = AI is the operating model. The actor is an *adopter*.

A firm can sit high on one and low on the other. A traditional bank in Phase 4 of adoption may still operate entirely at L0–L2 of the substrate ladder (rented APIs, no model ownership). A small startup at L6 (open weights on own GPU) may still be in Phase 2 of adoption (one product, no enterprise-wide deployment).

**The SME-specific parallel.** [[oecd-sme-ai-adoption-2025]] proposes [[oecd-sme-adopter-taxonomy]] (Novices / Optimisers / Explorers / Champions) as the SME-specific analogue of the WEF / Accenture 5-phase ladder. Two structural differences:

- The WEF ladder is **linear** (one phase per firm). The OECD taxonomy is **two-axial** (complexity × scope), so a firm can be "wide-but-shallow" (Optimiser: many tools across departments, no customization) or "deep-but-narrow" (Explorer: bespoke AI in one niche). This decomposition is richer for the SME population where these two paths diverge — both are real strategies, and the WEF ladder collapses them.
- The WEF ladder is calibrated for **large enterprises**. Phase 4 ("enterprise cognitive brain", ethical AI board) describes organisational maturity at scales most SMEs cannot reach. The OECD Champion case studies (Calgary healthcare-tech, Cambridge biotech) are the SME analogue of WEF's Phase 4–5 but operate at materially different scale, with materially different substrate and finance positions.

## What this ladder reveals that L0-L7 hides

- The **[[scaling-gap]]** — most enterprises stall between Phase 2 and Phase 3. L0-L7 has no analogue for this transition; it assumes a stack actor can climb freely if capital is available. The adoption ladder makes visible that *capital alone does not move you up*; foundational enablers ([[foundational-enablers]]) do.
- The **organizational** vs. **technical** distinction. Many bear-case arguments ([[scaling-wall]], [[task-based-framework]]) operate on the technical side. The 74% gap suggests the bottleneck may also be organizational, which is a different lever set.
- Where the **[[capital-labor-divergence]]** plays out concretely. Phase 4 reorganizations are where roles change, where the chief AI officer appears, where teams reshape.

## What this ladder hides that L0-L7 surfaces

- It treats AI as something you *adopt*, not something you *own*. The question of who captures surplus is invisible.
- It collapses very different kinds of integration (renting Claude vs. running your own model) into the same maturity step.
- It has no concept of [[distribution-moat]]. A Phase 4 firm that runs everything on someone else's API is not strategically equivalent to a Phase 4 firm that owns the model.
- It is silent on geopolitics ([[divergent-value-stack-optima]]) — the same phase looks different in the US / China / EU stacks.

## Use in the paper

The two ladders are likely complementary axes in the paper's framing:
- The substrate-side ladder ([[H1_L0-L7-ladder]]) explains *where margin pools structurally*.
- The adoption ladder explains *which enterprises capture how much of that margin*.

A firm at L0–L2 (renting capability) in Phase 4 (deeply integrated) is paying surplus upward to its L6–L7 vendors. A firm at L6 (owns model) in Phase 2 (no real deployment) has built a substrate it cannot monetize. The interesting position — and likely the durable one — is high on both ladders.

## Data

- [[scaling-gap-74-16]] — the 74% / 16% artifact that motivates the ladder.
- [[ai-leader-productivity-delta]] — leader-cohort outperformance numbers.

## Related

- [[wef-ai-in-action-2025]] — source.
- [[H1_L0-L7-ladder]] — substrate-side parallel.
- [[scaling-gap]] — the empirical artifact this ladder visualizes.
- [[foundational-enablers]] — what WEF claims moves a firm up phases.
- [[H2_u-curve-of-value]] — value-capture question this ladder cannot answer alone.
- [[distribution-moat]] — the strategic asset this ladder is blind to.
- [[capital-labor-divergence]] — what changes inside the firm at Phase 3–4.
- [[divergent-value-stack-optima]] — the bloc-level pressure this ladder ignores.
- [[taker-shaper-maker]] — strategic-positioning axis orthogonal to this maturity ladder.
- [[digital-core]] — the architectural precondition assumed at each phase.
- [[fusion-skills]] — the workforce capability assumed to move firms up phases.
- [[non-tech-digital-core-synthesis]] — secondary restatement of this ladder for non-tech firms.
- [[oecd-sme-ai-adoption-2025]] — SME-specific parallel source.
- [[oecd-sme-adopter-taxonomy]] — the buyer-side decomposition for SMEs.
- [[sme-ai-adoption-gap]] — the data context that motivates an SME-specific taxonomy.
