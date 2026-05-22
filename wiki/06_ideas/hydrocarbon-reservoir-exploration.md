---
title: Hydrocarbon Reservoir Exploration ("Peering Below the Surface")
status: idea
tags:
  - idea
  - exploration
  - oil-and-gas
  - synthetic-data
  - simulation
last-updated: 2026-05-22
---

# Hydrocarbon Reservoir Exploration

> [!abstract] What the AI does
> AI **denoises and completes poor-quality seismic data**, fuses it with well logs and core samples, and simulates reservoir dynamics to recommend where (and whether) to drill. The economic point: each "dry" well avoided is tens of millions of dollars saved.

## Domain
Upstream oil & gas exploration.

## Pattern
- **In:** seismic surveys (noisy, incomplete), legacy well logs, core sample analyses, historical production data.
- **Reasoning:** generative model fills gaps with [[synthetic-data-generation]] respecting physical constraints; simulator forecasts reservoir behavior under candidate drilling scenarios.
- **Out:** ranked drilling locations with confidence intervals, predicted recovery rates, risk-adjusted economic recommendations.
- **Human checkpoint:** geoscientist reviews; investment committee approves capex.

## Deployments in the wild
- Generic ER&I pattern in [[deloitte-ai-dossier-eri]]; no single named deployment in this synthesis.

## What's actually being measured
- Recovery-rate improvement (asserted; magnitude not given).
- Reduction in dry-well rate (asserted).
- *Not measured publicly:* OOD failure rate on novel basins or unfamiliar lithology.

## Concept linkages
- [[synthetic-data-generation]] — the load-bearing technique; also its load-bearing risk (physics fidelity).
- [[scaling-wall]] — Deloitte explicitly flags OOD failure on "novel geological scenarios" as the deployment ceiling here.
- [[agentic-revolution]] — analytical-leaning version: the agent recommends, but the human-and-billion-dollar-capital-call still owns the decision.
- [[autonomy-slider]] — necessarily low-autonomy: irreversibility of drilling decisions caps the slider.
- [[ai-materials-science]] — adjacent pattern: virtual screening replacing physical testing.

## Open questions
- What's the actual hit-rate of AI-recommended drilling locations vs. legacy seismic-only methods?
- How transferable is a model trained on North Sea geology to a Permian or West African basin?
- Does the workflow create new lock-in to one vendor's geophysical platform?

## Related
- [[deloitte-ai-dossier-eri]] — primary source.
- [[synthetic-data-generation]] — methodology page.
- [[minerals-processing-optimization]] — same synthetic-data + OOD-risk profile, adjacent vertical.
- [[scaling-wall]] — application-layer ceiling.
