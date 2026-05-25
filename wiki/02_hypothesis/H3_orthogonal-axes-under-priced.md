---
title: H3 — Orthogonal Axes Under-Priced
status: deferred-stub (premise authored, evidence not yet developed)
confidence: not-yet-assessed
tags:
  - hypothesis
  - axes
  - scaffolding
last-updated: 2026-05-25
---

# H3 — Orthogonal Axes Under-Priced

> [!abstract] Hypothesis
> The [[H1_L0-L7-ladder]] and [[H2_u-curve-of-value]] share a common blind spot: both treat substrate ownership as the primary axis along which value distributes. H3 proposes that several **orthogonal axes** — dimensions that cut across the ladder rather than running along it — may be more predictive of where defensible value lands than position on the ladder or the U alone. Candidate axes surfaced so far: **autonomy level** (the [[autonomy-slider]]: human ↔ agent control, orthogonal to substrate ownership), **deployment topology** (cloud vs. edge/on-device, which doesn't fit the ladder cleanly), **buyer maturity** (the [[enterprise-adoption-ladder]] and [[oecd-sme-adopter-taxonomy]]), and **strategic positioning** ([[taker-shaper-maker]]). The working claim is that the most defensible plays in the near term sit at specific intersections of these axes — off the simple ladder or curve — and that the axes are systematically under-priced in current analytical frames.

> [!warning] Status
> Deferred stub. The premise was authored in the kickoff conversation alongside H1 and H2 and is referenced throughout the wiki as a placeholder. No evidence has been gathered specifically to test or develop it. It is included here so that cross-references resolve and the hypothesis remains visible as a research target. H3 may be developed into a live hypothesis, retired, or merged into H1 or H2 as evidence accumulates. It is scaffolding, not a claim.

## Why this is here

The following pages currently reference this hypothesis and motivated its creation as a named placeholder:

- [[00_initial-brief]] — named as the third of the three working frames from the kickoff conversation: "the most defensible plays sit off-axis."
- [[02_purpose-and-justification]] — lists H3 alongside H1 and H2 as starting scaffolding that the research may reshape.
- [[03_structure]] — the practical half of the paper (Section 6, "who wins and how") is described as "currently scaffolded by H3."
- [[07_analytical-vocabulary]] — notes H3 as what the six-axis analytical frame may still be missing.
- [[H1_L0-L7-ladder]] — notes that edge/on-device inference doesn't fit the ladder cleanly and points here as the orthogonal-axis home; also notes the [[autonomy-slider]] as plausibly orthogonal to the ladder.
- [[H2_u-curve-of-value]] — points here as "what the U misses."
- [[autonomy-slider]] — explicitly frames the ladder × slider intersection as two orthogonal axes and cross-references this hypothesis.
- [[karpathy-software-3]] — introduces the autonomy slider as a "competing" taxonomy that is more likely orthogonal than competing.
- [[bear-case-synthesis]] — notes that the "killer app has not emerged" critique threatens any application-layer winner-take-most thesis embedded here.

## Seller-side empirical reinforcement (via [[weber-ai-startup-business-models]])

Weber et al.'s 2021 four-pattern AI-startup taxonomy ([[ai-startup-business-archetypes-weber]]) provides the **strongest piece of evidence so far** that the orthogonal-axes claim is real:

- The taxonomy is built on **11 dimensions × 39 characteristics** that span value proposition, value creation, value delivery, and value capture. These dimensions are *empirically derived* from 100 AI startups, not theoretically imposed.
- Two startups sitting at the same [[H1_L0-L7-ladder]] position (e.g., both selling at L1–L2 of the buyer stack) can land in **completely different Weber patterns** — one as [[ai-charged-product-service-provider]] (top of U), another as [[ai-development-facilitator]] (middle of U). The difference is explained by axes the ladder does not encode: data source, customization level, hardware provision, continuous-learning posture.
- Specific Weber dimensions that look most orthogonal-axis-shaped:
  - **Continuous learning** (central updates vs customer-side vs none) — orthogonal to substrate.
  - **Hardware provision** (yes / no) — orthogonal to substrate; partially overlaps with [[H1_L0-L7-ladder]]'s L4–L6 but not cleanly.
  - **Data source** (self-generated / acquired / public / customer-on-demand / customer-continuous) — orthogonal to substrate; closely related to [[distribution-moat]] economics.
  - **Industry scope** (focused vs agnostic) — orthogonal to substrate; closely related to vertical-vs-horizontal posture and to [[taker-shaper-maker]].

This is mild **activation evidence** for H3 — at least three of the Weber dimensions correlate with value-capture archetype more cleanly than ladder position does. Promotion to live-hypothesis status still requires a *quantitative* demonstration that these axes outperform the ladder in predicting where value lands; the Weber paper does the descriptive half but not the predictive half.

[[weber-taxonomy-2026-gaps]] extends this argument by naming six **additional** orthogonal-axis-shaped dimensions Weber's 2021 box does not encode (model sourcing, autonomy level, orchestration depth, distribution architecture, data flywheel, ethics-as-product). Each of those dimensions is a candidate orthogonal axis in the H3 sense — empirically motivated by 2026 wiki evidence, awaiting source-side validation against a post-ChatGPT taxonomy update.

### Structural reinforcement from the BMP frame (added 2026-05-25)

The [[business-model-portfolio]] frame (source: [[westerveld-business-model-portfolio-2023]]) is the *structural* reason orthogonal axes are load-bearing: a single firm running multiple BMs *necessarily* occupies multiple positions on every analytical axis simultaneously. If the firm were the unit of analysis, the orthogonal axes would partially collapse into "this firm is mixed." With the BMP frame applied, each BM is a clean point on each axis — and the H3 claim sharpens: *the most defensible plays sit at specific axis intersections, evaluated per business model, not per firm.* This does not yet activate H3 (it remains a scaffolding hypothesis), but it removes a structural objection to its empirical testability.

## What would activate this

H3 would be promoted from stub to live hypothesis if any of the following conditions are met:

- Evidence emerges that two or more of the candidate orthogonal axes explain variance in value capture *better* than L0–L7 position alone — e.g., a firm at L2 substrate with high autonomy and high buyer maturity outperforms a firm at L5 with low buyer maturity.
- A dominant analytical frame in the literature explicitly organizes value-capture predictions around cross-cutting axes rather than a single stack dimension.
- The paper's practical half (per [[03_structure]] Section 6) requires finer-grained positioning claims that the ladder and U cannot supply without the additional axes.
- Interview or case evidence surfaces a durable winner whose position is best described by axis-intersection coordinates rather than by ladder level or U position.
