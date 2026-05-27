---
title: Specialist subagent for orchestrators
status: speculative
confidence: low (architectural premise sound; defensibility unvalidated; GTM open)
tags:
  - business-idea
  - h4-application
  - mcp
  - agent-composition
  - rl-specialization
last-updated: 2026-05-27
---

# Specialist subagent for orchestrators

> [!abstract] One-line pitch
> Build and sell a **narrow-vertical specialist agent** — a model trained to do *one* job exceptionally well — exposed as an **MCP tool** that other people's general-purpose orchestrators (Opus, GPT, Gemini, in-house) can call as a node in their agent graph. The buyer keeps their orchestrator; they swap one underperforming node for your specialist.

> [!warning] Status
> Speculative — authored 2026-05-27 from the operator's seat. The architectural premise (specialists composed into general orchestrators via MCP) follows directly from Layer 3 of [[ai-first-company-loop]] and from [[software-as-temporary-artefacts]]. The defensibility premise (proprietary industrial data as the moat) is a restatement of [[H4_rl-specialization-value-pocket]] and inherits its open question: whether boutique RL-specialization vendors can hold margin against frontier-lab horizontal expansion. **Confidence is low.** The page exists to be sharp enough to refute.

## The mechanism — why the buyer pays

Agent builders (companies, agencies, in-house teams, software vendors) are already shipping AI products whose internal architecture is one orchestrator (Opus 4.7, GPT, etc.) coordinating multiple tool calls. For most tasks, the orchestrator alone is good enough. For one or two specific nodes in the graph, it isn't — the accuracy gap matters, the cost of an error is high, and the buyer has neither the proprietary data nor the RL stack to close the gap themselves.

The wedge: **the buyer would pay for a drop-in specialist callable via MCP for that specific node**, rather than (a) accepting the orchestrator's accuracy on the underperforming node, (b) building their own specialist (no data, no expertise, high opportunity cost), or (c) waiting for the next foundation-model release to maybe close the gap horizontally.

The architectural fit is clean:

- The orchestrator stays the orchestrator. The customer keeps their existing harness, prompts, agent loop. No re-platforming.
- The specialist is a tool. MCP is a tool-calling protocol; the specialist is a callable function with a typed surface. The orchestrator already knows how to call tools.
- The economics of the call are bounded. The buyer pays per call, only on the node where the specialist beats the orchestrator. No flat platform fee.

This composition pattern — a generalist orchestrator calling vertical specialists as MCP tools — is what Layer 3 of [[ai-first-company-loop]] predicts as the steady-state shape of agent systems, and is the buyer-side mirror of [[software-as-temporary-artefacts]]: the buyer synthesises bespoke tooling on demand for most jobs, but rents specialists for the jobs the synthesis can't reach.

## Required conditions — what must be true

This business does not work without **all three** of the following.

### 1. Proprietary data behind the specialist

Without proprietary data, the next foundation-model release eats the specialist. Generic capability ("write LinkedIn posts well", "summarise legal documents", "transcribe meetings") trains on scraped public data; any competitor scrapes the same data, and the frontier labs already have it at scale. The economics are a treadmill the specialist loses.

The specialist only holds if the training data is one of:

- **Industrial process data** — a customer's manufacturing telemetry, defect imagery, sensor traces, operator decisions. See [[predictive-maintenance]], [[minerals-processing-optimization]], [[autonomous-drone-inspection]] for the texture.
- **Contractually exclusive industry corpora** — see [[exclusive-industry-data-partnerships]]. Regulated verticals, healthcare networks, payments rails, insurance claim histories.
- **Captured operational trajectories** — preference labels and verifiable rewards (per [[rl-from-verifiable-rewards]] and [[rl-data-preparation]]) collected over time inside one customer or one vertical, accumulating into a flywheel the frontier labs structurally cannot enter.

The 2026-05-27 daily note named "LinkedIn post writer" as a candidate example — it fails this condition and is therefore not a candidate for this business. It belongs to the [[ai-development-facilitator]] vintage problem: the squeezed middle of [[H2_u-curve-of-value]], absorbed by [[software-as-temporary-artefacts]] on the customer side.

### 2. Vertical narrow enough that frontier labs structurally do not enter

[[H4_rl-specialization-value-pocket]] names this as its load-bearing assumption: the value pocket exists only where a frontier lab cannot or will not horizontally absorb the specialist's domain. The narrowness criterion is best stated as the inverse — *can OpenAI / Anthropic / Google make a quarterly OKR out of beating you on this vertical?* If yes, the pocket evaporates the next training cycle. If no — because the data is contractually locked, the regulatory surface is too costly to navigate, or the addressable market is too small to be worth a frontier lab's attention — the pocket can hold.

This same criterion is why this business sits more naturally inside [[H6_industrial-ai-rollup-captive-suppliers]] geography (industrial districts, captive industrial verticals) than inside generic horizontal software.

### 3. A composable, low-friction integration surface

MCP is currently the cleanest such surface; that may shift, but a tool-calling protocol of some kind is the integration spine. The specialist must be callable with predictable latency, a typed input/output schema, observable failures, and per-call pricing the buyer's orchestrator can budget against. If integration friction is high, the buyer's path of least resistance is to wait for the foundation lab to close the gap, not to wire in a third-party specialist.

This is operationally hard. The bill of materials is not just the model — it is the full [[ml-monitoring]] surface ([[ml-monitoring-quality-cycle]]'s 17 practices, especially Practices 8–11 for silent rot detection), the API hosting, the MCP-side schema, the auth, the billing, the SLA, the on-call. Underpricing the operations side is the canonical way this kind of vendor dies.

## GTM options

These are not mutually exclusive; the right answer is probably *sequenced*.

### Option A — Single industrial customer partnership (H4-canonical)

Match [[H4_rl-specialization-value-pocket]]'s native shape. Land one industrial customer whose process data is the training substrate. Build the specialist inside their walls. Charge a license + ops fee. The customer gets a proprietary operational asset; you get the data flywheel and the proof.

- **Strength:** the only path that solves the data-moat condition from a cold start. The customer pays you to *acquire the moat* you would otherwise have no way to build.
- **Weakness:** indistinguishable from a high-end industrial AI consultancy in year one. Margin is bounded by services revenue until the artifact generalises across customers. The leap from "trained for Customer A" to "sold to Customer B" is the unvalidated step.
- **Reference business model:** closest to [[ai-deep-tech-researcher]] (Pattern 4 from Weber's taxonomy) at a tighter scope.

### Option B — Closed-source API access (Anthropic-style)

Host the specialist; sell metered API access. Buyers integrate via MCP. This is the framing the 2026-05-27 daily note proposed.

- **Strength:** scales horizontally across many small buyers. Standard SaaS unit economics. MCP makes integration cheap.
- **Weakness:** capital-heavy. GPU inventory, ops, on-call, billing, SLA. **More fundamentally — this is Track A of [[H5_ai-as-operational-not-product]], the capital-locked race-in track that the operator-builder paper (P2) explicitly says capital-light builders should *not* pick.** And the hosting layer alone is not defensible: [[rl-apis]] documents that Modal, Together, Fireworks, Predibase already provide this hosting surface. The defensibility has to be the *model artifact*, which means the data moat from condition 1 has to be real.
- **Honest framing:** Option B is only viable *after* Option A produces an artifact the data moat has paid for. It is the harvesting motion, not the founding motion.

### Option C — Data aggregator first, model second

The deeper move: instead of training a model from a single customer's data, **become the aggregator** that pools data across multiple customers in a vertical and trains a shared specialist on the union. The artifact is sold back to participants (and to non-participants at a premium).

- **Strength:** the data moat scales with the number of participants and compounds. Structurally similar to credit bureaus, claims-data utilities, industry-wide telematics consortia. If the wedge is real, this is the long-game defensibility.
- **Weakness:** requires a *governance* play, not just a technical one. Data-sharing legal architecture, anti-competitive scrutiny, participant onboarding cost. Probably impossible without first proving the artifact's value via Option A on one or two customers.
- **Reference business model:** closest to [[exclusive-industry-data-partnerships]] reified as a company.

A plausible sequence: **A → B for additional buyers within the same vertical → C when the participant set is large enough to negotiate around**.

## What would kill it — concrete bear cases

- **The frontier lab horizontally absorbs the specialist.** GPT-X.Y ships and now does the specialist's job within a margin of error. The wiki names this as the structural risk under [[ai-development-facilitator]] and [[software-as-temporary-artefacts]]. The data-moat condition (1 above) is the only defence.
- **The single industrial customer claws back the surplus.** Common pattern when one customer is >40% of revenue (the [[H6_industrial-ai-rollup-captive-suppliers]] dynamic in reverse). Once the artifact works, the customer pressures for cost-plus pricing or insources the specialist. Mitigation: explicit IP-retention terms, Option-A → Option-B transition built into the contract from day one.
- **MCP commodifies, integration friction goes to zero, and the buyer's path of least resistance becomes "self-train on the foundation lab's RL API + their own data."** [[rl-apis]] is already this surface. The defensibility collapses to "the buyer doesn't have the data or the expertise," which is true today and may not be true in 2028.
- **Operations cost dominates margin.** Per-call pricing of a hosted specialist looks great until the [[ml-monitoring]] / drift-detection / on-call / SLA overhead is properly counted. [[ml-monitoring-quality-cycle]]'s 17 practices are the floor, not a wishlist.
- **The buyer's orchestrator vendor (Anthropic, OpenAI) ships a first-party "specialist marketplace" with revenue share.** The specialist is now sold through the orchestrator vendor's distribution, which means [[distribution-moat]] re-asserts itself and the specialist vendor loses both pricing power and customer relationship. This is the most likely 2026–2028 disruption vector.

## Open questions

1. **Is there a single vertical where the data moat is closeable by a capital-light operator?** Industrial districts in the [[H6_industrial-ai-rollup-captive-suppliers]] geography are the strongest candidate. Need to identify two or three.
2. **What is the minimum viable specialist surface?** Is it one model + one MCP tool, or does the buyer also need observability, eval pipes, version pinning, rollback? The full surface looks more like a hosted product than a model.
3. **Is the buyer "the agent builder who already has an orchestrator" or "the industrial firm itself, who hires an agency to build their orchestrator"?** These two buyers want very different things. The first wants API + MCP; the second wants a deliverable workflow with the specialist embedded.
4. **What does the customer-acquisition motion look like for Option A?** [[gultekin-pinarbasi-commercialisation-ai-2025]] documents that the BAH-vs-Claessens-vs-fuzzy GTM debate is empirically alive in this space (gap 7 on [[weber-taxonomy-2026-gaps]]); this business needs an explicit hypothesis about which motion it runs.
5. **Does the existence of frontier-lab "specialist routing" inside their own products (rumoured for 2026–2027) eliminate the wedge before it can be filled?** This is the single largest external risk.

## Relation to the wiki

This page is the buyer-side composition framing of [[H4_rl-specialization-value-pocket]] — H4 today describes the vendor offering and the technical premise; this page describes *how the artifact enters the buyer's stack*. The two should be read together.

It sits inside Track A of [[H5_ai-as-operational-not-product]] as proposed (Option B GTM), and inside Track B if pursued via Option A first (the specialist is built as operational input to one industrial customer, with the artifact-as-product play emerging only later). The choice of GTM is also a choice of which H5 track the operator is on.

It is architecturally enabled by Layer 3 of [[ai-first-company-loop]] (tools the loop synthesises and calls) and by [[software-as-temporary-artefacts]] (the surviving middle re-classified as *primitives for synthesis* — the specialist is one such primitive when synthesis can't reach the required accuracy).

## Related

- [[H4_rl-specialization-value-pocket]] — vendor-side and technical premise; this page is its buyer-side composition mirror.
- [[H5_ai-as-operational-not-product]] — Track A vs Track B framing constrains GTM choice.
- [[H6_industrial-ai-rollup-captive-suppliers]] — natural geography for the proprietary-data condition.
- [[ai-first-company-loop]] — Layer 3 (tool) is the architectural slot the specialist occupies inside the buyer.
- [[software-as-temporary-artefacts]] — the buyer-side rationale for renting specialists rather than synthesising them.
- [[middle-layer-defensibility]] — the empirical case the specialist competes with; the specialist is itself a middle-layer bet.
- [[exclusive-industry-data-partnerships]] — Option C's structural template.
- [[rl-apis]] — the commercial surface this business competes against on the hosting side.
- [[ml-monitoring]] — the operational bill of materials the specialist deliverable has to include past the model itself.
- [[distribution-moat]] — the orchestrator vendor's marketplace risk.
- [[ai-charged-product-service-provider]] — Weber Pattern 1 sibling; the specialist as an embedded model artifact.
- [[ai-development-facilitator]] — the anti-example; what this business looks like when the data-moat condition fails.

## Referenced by

*Auto-generated reverse-link index — pages in the wiki that link here. Maintained by `/lint` and reverse-link sweeps.*
