---
title: Jevons Paradox in AI
status: active
tags:
  - concepts
  - economics
  - compute
  - hardware
last-updated: 2026-05-22
---

# Jevons Paradox in AI

Named after the 19th-century economist William Stanley Jevons, who observed that improvements in coal-engine efficiency *increased* total coal consumption rather than reducing it, because cheaper coal enabled vast new applications.

## The AI instantiation

DeepSeek's algorithmic efficiency (frontier reasoning at 1/70th the cost of GPT-4 Turbo) did not reduce global GPU demand — it dramatically increased it. By collapsing the cost barrier for enterprise AI deployment, open-weight models unlocked entire categories of use cases that were previously cost-prohibitive. NVIDIA H200 demand intensified to the point of severe shortages across major cloud providers.

The mechanism: cheaper intelligence → more deployments → more inference load → more hardware demand. Each efficiency gain expands the total addressable workload rather than shrinking the infrastructure requirement.

## Implications for [[H2_u-curve-of-value]]

The bear case ([[circular-ai-economy]]) argues that the bottom of the U (silicon, energy, frontier weights) is propped up by recycled VC capital, not durable enterprise demand. The Jevons Paradox provides a partial counter-argument: if efficiency gains genuinely unlock *net new* enterprise workloads (not merely cheaper versions of existing ones), then hardware demand is a leading indicator of expanding real use — not a Ponzi loop.

**The tension:** Jevons Paradox and [[circular-ai-economy]] are not mutually exclusive. Some of the "new" enterprise use cases unlocked by cheaper models may themselves be financed by VC capital chasing AI narratives. Distinguishing genuine demand expansion from subsidized adoption requires watching what happens to GPU demand when VC funding tightens — exactly the signal [[circular-ai-economy]] says will arrive and collapse the U's bottom.

## Scope

The paradox operates at the hardware layer (silicon, energy) — the bottom of the U in [[H2_u-curve-of-value]]. It does not directly affect the middle or top of the stack. It suggests the infrastructure layer may be more durable than a pure bear-case reading implies, but it does not resolve the question of whether the surplus being captured there is real (enterprise) or recycled (VC).

## Related

- [[H2_u-curve-of-value]] — the bottom of the U; Jevons Paradox partially defends it
- [[circular-ai-economy]] — the competing hypothesis; together these define the core uncertainty about the bottom of the stack
- [[open-weight-asymmetry]] — DeepSeek's efficiency gains are what triggered the paradox
- [[where-value-lands-2026]] — source where the Jevons Paradox is documented
- [[capital-labor-divergence]] — even if the hardware layer is durable, the surplus flows to capital (GPU owners, hyperscalers), not labor
- [[ai-exposure-vs-bls-growth]] — software developers as the high-exposure / high-growth outlier; a Jevons-Paradox-style demand expansion at the labor-market level
- [[foundation-model-layer]] — the layer where falling per-token costs are eroding rent extraction the fastest.
