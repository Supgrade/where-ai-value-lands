---
title: Cross-Archetype Confusion
status: active
tags:
  - concepts
  - strategy
  - platforms
last-updated: 2026-05-23
---

# Cross-Archetype Confusion

The strategic failure mode — flagged explicitly by Choudary in [[choudary-ecosystem-teardown]] — of **benchmarking the wrong [[ecosystem-business-archetypes|archetype]]**.

## The failure pattern

A firm building an Integrator or Infrastructure looks at the BigTech Aggregators (Facebook, Amazon, Google) for inspiration. The Aggregator playbook — viral consumer growth, ad-monetised data, two-sided matchmaking — does not transfer.

Two concrete instances Choudary cites:

- **B2B platforms** designing for consumer-aggregator metrics (DAU, engagement loops, ad inventory). They are actually Integrators (switchboards) or Infrastructures (substrate + roadmap), and their **success criteria are different**: producer-side API breadth, distributor-side integration depth, switching costs, regulatory permission, not engagement.
- **Integrators** benchmarking growth to consumer aggregators. Aggregator growth curves are powered by network effects on the consumer side; Integrator growth is gated by enterprise procurement cycles, API certification, and bilateral commercial deals. Setting an aggregator-shaped growth target on integrator-shaped fundamentals leads to over-investment, wrong-shape teams, and eventual misalignment of strategy with archetype.

## Why this matters for AI

The AI wave concentrates the same error. Many 2023–2024 "AI startups" benchmarked themselves to consumer Aggregators (ChatGPT-scale growth, viral user acquisition) while actually building Capability providers (an API for one task) or Integrators (a switchboard between models and tools). The mismatch helped fuel the failure rate that the **[[scaling-gap]]** indirectly reflects on the supply side: products designed for the wrong archetype-shape are structurally hard to scale.

The defensibility argument in [[middle-layer-defensibility]] depends on getting the archetype right. Cursor and Perplexity succeed not because they "are AI Aggregators" but because they correctly identified an Aggregator-archetype opening (owning a direct user relationship in a domain — developers, search) and built for **Aggregator success criteria**, not Capability or Infrastructure ones.

## How to avoid the trap

Choudary's prescription is procedural rather than substantive:

1. Map the ecosystem first.
2. Identify your archetype honestly. The test: who is your buyer, what coordination problem do you solve, where does your data come from?
3. Set success metrics from the archetype's own logic — not from whatever firm is currently most visible.

For AI firms specifically, the test sharpens: **does your data flywheel close inside your product, or does it leak to whichever foundation model you wrap?** Aggregator-archetype data flywheels close; Capability-archetype ones often leak; Integrator-archetype ones close only if the bilateral relationships are exclusive.

## Related

- [[ecosystem-business-archetypes]] — the taxonomy this failure mode sits inside
- [[choudary-ecosystem-teardown]] — primary source
- [[middle-layer-defensibility]] — the defensibility argument that depends on getting the archetype right
- [[distribution-moat]] — Aggregator-archetype success criteria for AI firms
- [[scaling-gap]] — supply-side correlate: products designed for the wrong archetype-shape are structurally hard to scale
- [[07_analytical-vocabulary]] — Axis 3 (Business Archetype); cross-archetype confusion is the vocabulary failure mode
