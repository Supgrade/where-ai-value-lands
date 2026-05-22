---
title: Generative Site Design
status: idea
tags:
  - idea
  - design
  - infrastructure
  - generative
  - planning
last-updated: 2026-05-22
---

# Generative Site Design

> [!abstract] What the AI does
> Generative AI **evaluates spatial variables** (solar orientation, traffic flow, accessibility, soil conditions, zoning constraints) and produces optimized infrastructure blueprints. It auto-annotates designs with specifications and materials, collapsing weeks of iterative human planning into hours.

## Domain
Industrial site planning, renewable-energy site design, warehouse layout, EV-charging network rollout.

## Pattern
- **In:** site constraints (GIS, zoning, environmental) + design objectives (throughput, capex budget, environmental compliance).
- **Reasoning:** generative model proposes layouts; physics-aware evaluator scores against objectives; iteration converges on optimum.
- **Out:** annotated CAD blueprints + bill of materials + estimated capex.
- **Human checkpoint:** civil engineer reviews; planning authority approves the human-finalized version.

## Deployments in the wild
- Generic ER&I pattern in [[deloitte-ai-dossier-eri]]; no named deployment in this synthesis.

## What's actually being measured
- Time-to-blueprint (asserted reduction; no quantified figure).
- Capex reduction vs. human baseline (asserted).
- *Not measured publicly:* rate at which AI-generated designs are rejected or substantially modified in planning review.

## Concept linkages
- [[democratization-of-programming]] — natural-language design briefs as the new input medium.
- [[agentic-revolution]] — closes the loop from brief → blueprint → spec → procurement.
- [[ai-materials-science]] — adjacent pattern: generative search over a constrained design space.
- [[autonomy-slider]] — necessarily low: civil-engineering decisions have long-lived public-safety consequences.

## Open questions
- How does liability allocate when an AI-generated layout produces a downstream safety failure?
- Do planning authorities accept generative designs as primary documents, or only as drafts a human engineer signs?
- Does this commoditize the architectural / civil-engineering function or augment it?

## Related
- [[deloitte-ai-dossier-eri]] — primary source.
- [[ai-materials-science]] — sibling generative-search pattern.
- [[grid-optimization]] — adjacent: AI-driven grid expansion planning.
