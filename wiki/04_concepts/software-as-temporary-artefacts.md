---
title: Software as Temporary Artefacts
status: emerging
tags:
  - concept
  - operator-side
  - middle-layer
  - operating-model
  - vocabulary
last-updated: 2026-05-26
---

# Software as Temporary Artefacts

> [!abstract] One-line
> Inside an AI-native operating loop ([[ai-first-company-loop]]), the marginal cost of synthesising a small, narrowly-scoped piece of software has collapsed far enough that the firm no longer buys persistent middle-layer SaaS for every operational need — agents in the loop's *tool layer* synthesise bespoke tools on demand, use them, and discard or narrow them when the need passes. The middle of [[H2_u-curve-of-value]] is not squeezed; for AI-first firms, much of it is *abolished* — there is no buyer for off-the-shelf middle-layer products because the firm fabricates its own.

The concept is a direct consequence of the tool layer (Layer 3) of [[ai-first-company-loop]]. It is presented here as its own page because the strategic implications cut into [[H2_u-curve-of-value]], [[middle-layer-defensibility]], and the entire Weber [[ai-development-facilitator]] pattern — large enough to warrant separate citation rather than living buried inside the operating-model page.

## The mechanism

In a pre-AI firm, an operational need — *we want to manage meeting-room bookings* — is met by one of: (a) buying a SaaS product, (b) commissioning custom development at meaningful cost and timeline, or (c) leaving the need unmet because the cost of (a) or (b) exceeds the value. Categories (a) and (b) are the *seller-side* of the existing middle-layer software market. Category (c) is the suppressed demand the firm absorbs as friction or as workaround.

In an AI-first firm running the five-layer loop, the same operational need arrives at the *policy* layer (Layer 2) as a decisioning problem, and the *tool* layer (Layer 3) addresses it by synthesising the needed software in situ. The author's 2026-05-26 daily-thought example is the canonical illustration: an agent in the loop builds a small system that

- shows the room's availability via a screen at the door,
- accepts bookings through a dynamic QR code,
- starts recording and transcribing automatically when the room is in use,
- summarises the meeting at the end and routes the summary to both the relevant inboxes and the loop's own knowledge store (feeding Layer 1).

Nothing in this tool is novel as software primitives. The novel claim is that the *act of bringing these primitives together for this firm's specific room-booking need* costs almost nothing — minutes of an agent's time and a fraction of a foundation-model dollar — so it makes sense to build the artefact rather than buy a generic meeting-room SaaS or do without.

The "temporary" qualifier captures two distinct conditions:

1. **Scope-temporary.** The artefact is built for this firm's exact need; it carries no portability tax, no multi-tenant abstraction, no configuration surface beyond what this firm uses. When the firm's need changes, the artefact is modified or replaced — there is no annuity-style switching cost because there is no annual contract.
2. **Time-temporary.** Some artefacts exist only for the duration of a campaign, project, audit, or migration. They are scaffolding, not infrastructure. They appear, do their work, and are decommissioned when the work ends.

Some artefacts persist (the meeting-room manager would). Others are ephemeral by design (a one-off compliance evidence collector for a specific audit). The unifying property is not that the artefact dies quickly but that *its persistence is a function of continued usefulness*, not of a vendor contract or of organisational inertia.

## Why this is a sharpening of the U-curve, not a contradiction

[[H2_u-curve-of-value]] currently reads as: top (distribution-fortified products), middle (squeezed), bottom (compute and foundation models). [[middle-layer-defensibility]] documents which middle-layer products survive (those with distribution lock-in and rich context control — Cursor, Windsurf, LangGraph). The "software as temporary artefacts" claim does not contradict either page — it sharpens both.

- **Against [[middle-layer-defensibility]]:** the survivors of the middle remain survivors *in the seller-side market for middle-layer products*. The new question is whether that market keeps shrinking as AI-first firms route more of their tool layer through in-house synthesis. The Cursors and Windsurfs of the middle survive *not because the middle is healthy* but because their position is structurally outside the substitutable range of in-house synthesis: they sit close to the act of programming itself, with model and IDE primitives that the AI-first firm uses *to* synthesise its own middle.
- **Against [[ai-development-facilitator]] (Weber Pattern 2):** the squeezed middle of the U is squeezed harder than the original Weber 2021 framing predicted. The squeeze is not just from above (frontier-lab cannibalisation) and below (commoditised models) — it is from a third direction: *the buyer's substitute is the buyer building it themselves at near-zero cost*. Weber Pattern 2 firms that survive will be those positioned as *primitives* for in-house synthesis (frameworks, RL APIs, eval tooling, deployment infrastructure) rather than as *finished workflow products*.
- **Reinforcing the top of the U:** distribution-fortified products at the top of the U are *more* protected, not less, by this dynamic — they sit at consumer-or-developer interfaces where the act of synthesising a personal-or-team substitute is itself non-trivial (you cannot easily synthesise your own Cursor; you can easily synthesise your own meeting-room manager).
- **Reinforcing the bottom of the U:** compute and foundation-model providers gain demand from every in-house synthesis event, because every synthesised artefact consumes their API. The bottom captures the marginal inference cost of every tool the AI-first firm builds for itself.

The U-curve, post-sharpening, reads: top is fortified by interface position (hard to self-substitute), bottom is fortified by inference demand (every tool burns tokens), and the middle is split into a narrow surviving band of *primitives-for-synthesis* (Cursor, LangGraph, RL APIs, eval tooling) and a vast collapsing band of *finished workflow products* whose buyers are abandoning them for in-house substitutes.

## Strategic consequences

- **For Track B operator-builders ([[H5_ai-as-operational-not-product]]):** the cost-base advantage from running AI-native operations comes from this mechanism more than from any other. Per-seat per-firm SaaS costs scale linearly with headcount and tool surface. In-house synthesised artefacts scale with foundation-model inference costs, which are roughly per-task. For a Track B firm with bounded operational complexity, the ratio is dramatic.
- **For Track A AI-as-product firms in the middle ([[ai-development-facilitator]]):** the survivable repositioning is *toward primitives*, not toward finished products. The firms that thrive sell the synthesis-engine, the orchestration framework, the eval harness, the RL API — the components AI-first firms use to build their own middle. The firms that struggle sell complete workflows the buyer can now reproduce.
- **For the [[H6_industrial-ai-rollup-captive-suppliers]] thesis:** the per-acquired-firm SaaS budget that would otherwise scale linearly with the rollup's firm count collapses toward zero. The synthesis cost is borne once (in the centralised loop-build team); the artefacts are reused or re-synthesised per firm at near-zero marginal cost. This is the second amortisation engine in the rollup, alongside the centralised loop-operation team.
- **For investors evaluating middle-layer AI-software bets in 2026 and beyond:** the diligence question shifts from "is this product better than incumbents?" to "is this product a *primitive for in-house synthesis* or a *finished workflow product*?" The two have inverted unit economics.

## Honest caveats

- **The claim depends on synthesis cost staying low.** If frontier-lab API pricing reverts upward (loss-leader pricing ending), or if liability and audit requirements force a heavy compliance overhead onto every in-house artefact, the substitution shifts back toward SaaS purchase. The claim is currently economically true; whether it stays true depends on the future shape of [[circular-ai-economy]] pricing.
- **The boundary between "primitive" and "finished workflow" is not crisp.** Cursor is partially a primitive (model + agent + tool integration) and partially a finished workflow (the IDE itself). Empirically, the surviving middle is the set of products that *function as primitives for the buyer's synthesis* even if they appear as finished products from outside. The framing here under-specifies the boundary and treats it as discoverable empirically.
- **Many firms cannot synthesise reliably.** The claim assumes the buyer firm has the AI-first operating loop in place ([[ai-first-company-loop]]) — a non-trivial precondition that the [[scaling-gap]] and [[ai-productivity-firm-level]] J-curve literature both indicate is rare. For most firms in 2026, the substitution is still a hypothetical capacity rather than a present option. The dynamic accelerates as more firms cross the threshold and the marginal substitution cost continues to fall.
- **Tool layer artefacts are not free of governance burden.** An in-house synthesised tool that touches customer data, regulated information, or financial records carries audit, security, and compliance requirements that an enterprise SaaS vendor absorbs. Some of the SaaS premium is a compliance premium, and the synthesis substitute has to absorb that premium itself, possibly through dedicated security and audit primitives that *are* purchased as middle-layer products. This is one of the things the surviving middle (primitives) does for the AI-first firm.

## Related

- [[ai-first-company-loop]] — the five-layer operating model whose Layer 3 (tool) instantiates this concept; this page is the strategic consequence page, that page is the architectural page.
- [[H2_u-curve-of-value]] — the seller-side curve this page sharpens: middle splits into primitives (surviving) and finished workflows (collapsing).
- [[middle-layer-defensibility]] — the existing claim about which middle products survive; sharpened here to be specifically about *primitives*, not about any middle-layer product with distribution lock-in.
- [[ai-development-facilitator]] — Weber Pattern 2; the population at risk; the survivors are the subset positioned as primitives.
- [[ai-charged-product-service-provider]] — Weber Pattern 1; the top of the U; *more* defensible under this dynamic, not less.
- [[H5_ai-as-operational-not-product]] — operator-builder; this page supplies its cost-base advantage mechanism.
- [[H6_industrial-ai-rollup-captive-suppliers]] — rollup; this page supplies its second amortisation engine alongside centralised loop operation.
- [[karpathy-software-3]] — "software is changing again"; this page is one of the operational consequences of Software 3.0 at the firm level.
- [[democratization-of-programming]] — the natural-language-as-programming-language framing; the synthesis happens in NL-to-code, often through the loop's agents.
- [[circular-ai-economy]] — synthesis-driven inference demand reinforces foundation-model and hyperscaler economics; bottom-of-U mechanism.
- [[jevons-paradox-ai]] — every synthesis event is a Jevons increment; total inference demand rises with the number of AI-first firms × the number of tools each synthesises.
- [[foundation-model-layer]] — the layer that captures the marginal inference cost of every synthesised artefact.
- [[application-layer]] — the layer most exposed to the substitution; the boundary between "application" and "synthesised tool" is exactly what this dynamic blurs.
- [[vertical-ai-orchestration]] — vertical orchestrators sold as products are at risk of in-house synthesis substitutes; vertical orchestration *primitives* are not.
- [[context-control]] — Chase's framing; context-management primitives are exactly the sort of middle-layer product that survives as a primitive for in-house synthesis.

## Source

- YC Root Access — "How to Build a Self-Improving Company with AI." YouTube: <https://www.youtube.com/watch?v=t-G67yKAHBQ>. The seed concept ("software as temporary artefacts") is from this lecture. Treated as a borrowed framework; no separate source page. The strategic consequences worked through here are the wiki's contextualisation, not the lecture's claims.

## Referenced by

*Auto-generated reverse-link index — pages in the wiki that link here. Maintained by `/lint` and reverse-link sweeps.*

Pending — to be added by next `/lint` sweep:
- [[ai-first-company-loop]]
- [[H2_u-curve-of-value]]
- [[middle-layer-defensibility]]
- [[ai-development-facilitator]]
- [[H5_ai-as-operational-not-product]]
- [[H6_industrial-ai-rollup-captive-suppliers]]
- [[karpathy-software-3]]
