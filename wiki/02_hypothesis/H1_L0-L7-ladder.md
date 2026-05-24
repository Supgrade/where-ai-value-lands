---
title: H1 — The L0–L7 Ladder
status: working-hypothesis
confidence: medium (lower at L4+ in light of [[scaling-wall]]; partially restored by [[agentic-scaling-law]] for tasks with verifiable intermediate steps)
tags:
  - hypothesis
  - stack
  - framework
last-updated: 2026-05-23
---

# H1 — The L0–L7 Ladder

> [!abstract] Hypothesis
> The agentic AI stack can be mapped as a **ladder of substrate ownership and human-in-the-loop autonomy**, from L0 (human-as-API, copy-pasting from chat) to L7 (vertically integrated datacenter + green energy + proprietary model — intelligence as commodity). Each step downward trades capital for autonomy and reduces dependence on the supply chain above.

> [!warning] Status
> Working hypothesis. Authored as a starting frame in the kickoff conversation. Likely to mutate. The number of levels, their boundaries, and the ordering itself are all open to revision.

## The ladder as currently sketched

- **L0 — Human as API.** Copy-paste from chat. The user moves data between model and world.
  - A: web chat (ChatGPT, Claude.ai). B: mobile app. C: desktop with screen share / vision.
- **L1 — AI inside existing tools.** Inline assistance, no copy-paste. Still 100% sync, human-in-the-loop.
  - A: IDE (Cursor tab, Copilot). B: SaaS inline (Notion AI, Linear, Granola). C: browser extensions.
- **L2 — Deterministic workflows with AI nodes.** The graph is hand-designed; AI is a pure function in the middle.
  - A: n8n / Zapier / Make. B: custom scripts with API calls. C: prompt chains (LangChain, BAML).
- **L3 — Agent decides for itself.** Non-deterministic loop: prompt → tool → observe → repeat. Human gives the goal; agent picks the steps.
  - A: computer use on user's machine. B: coding agents in IDE. C: agents with custom tools via MCP / function calling.
- **L4 — Agent in dedicated sandbox, always on.** The agent has its own runtime, filesystem, browser. The user closes the laptop and the agent works.
  - A: ephemeral cloud sandbox per task (Vercel Sandbox, E2B, Daytona). B: persistent VM/container with memory + scheduled triggers. C: isolated worktrees + merge (Cowork pattern).
- **L5 — Fleet of collaborating agents.** Orchestrator + N workers, exchange via MCP / A2A, shared task queues. Bottleneck shifts to review, not execution.
  - A: multi-agent on someone else's cloud. B: self-hosted swarm. C: cross-org agent-to-agent economy.
- **L6 — Vertical: model + compute owned.** Inference stops being a bill, becomes an asset. Own the weights (open or proprietary) and the GPUs running them.
  - A: open weights on rented GPU. B: GPU on-prem. C: own datacenter + own model.
- **L7 — Intelligence as commodity, energy included.** Datacenter + power generation (solar / wind / nuclear). Intelligence becomes a marginal output like tap water.
  - A: datacenter + green PPA. B: datacenter co-located with generation. C: full vertical — produce energy, run model, sell output downstream.

## Why this might be wrong
- The "ladder" framing implies linear progress. Reality may be more like a **graph** — many parallel paths, not one ordered descent.
- Levels may not be discrete. The boundary between L3 and L4, or L4 and L5, is mushy.
- Edge / on-device inference doesn't fit the ladder cleanly — it's an orthogonal axis (see [[H3_orthogonal-axes-under-priced]]).
- "Substrate ownership" may not be the right backbone. Alternatives worth testing: degree of autonomy, capital intensity, distance-to-end-user.
- **A competing single-axis taxonomy exists.** Karpathy's [[autonomy-slider]] (cited via [[karpathy-software-3]]) describes the same territory as one continuous human↔agent control axis, not a substrate-ownership ladder. The two are not incompatible — the slider is plausibly orthogonal to the ladder (a product can be high-on-ladder, low-on-slider, or vice versa) — but the field may converge on the simpler frame.
- **A buyer-side parallel ladder exists.** [[wef-ai-in-action-2025]] proposes a five-phase [[enterprise-adoption-ladder]] (Initial / Thousand-flowers-bloom / End-to-end / Enterprise-level / Value-chain reinvention). It runs along the *adopter / organizational maturity* axis, not the *substrate ownership* axis L0–L7 charts. The two are complementary — a firm can sit high on one and low on the other — and the interesting position is high on both. The adoption ladder surfaces the [[scaling-gap]] (74% of firms stuck below Phase 3) that L0–L7 has no native vocabulary for.
- **A third orthogonal axis: [[taker-shaper-maker]].** WEF also names a *strategic-positioning* typology (rent the model / customize the model / train the model) distinct from both the substrate ladder and the maturity ladder. A firm's coordinates are roughly (L0–L7 substrate, Phase 1–5 maturity, Taker/Shaper/Maker positioning). Most non-tech enterprises in 2026 sit at L0–L2 substrate, Phase 2–3 maturity, Taker–Shaper positioning — and the consultancy frame's commercial interest is precisely in moving them rightward on the latter two while leaving substrate position (and surplus capture) untouched.
- **The autonomy plateau may be capped by architecture, not by engineering.** The [[scaling-wall]] argument from [[marcus-world-models-failure]] says L4–L5 (long-running autonomous agents, fleets) cannot reach production reliability on hard-to-learn enterprise tasks without a paradigm shift beyond next-token prediction. If true, the "ladder" stops being a glide path past L3 for most enterprise use cases — it becomes a wall, not a staircase.
- **But the scaling-wall argument has a direct counter.** Huang's [[agentic-scaling-law]] (also via [[karpathy-software-3]]) claims test-time compute is a second scaling axis that operates on top of base models. If correct, L4–L5 become reachable not through better base models but through sub-agent reasoning and search — reshaping the wall rather than removing it. The honest position is unsettled: both axes are partially real.
- **L7 is a bet on a paradigm shift, not a glide path.** "Intelligence as commodity, energy included" requires inference that is cheap *and* reliable on hard tasks. The bear case argues the second condition is the unsolved one — see [[bear-case-synthesis]]. The bull case ([[llm-as-operating-system]] + [[agentic-scaling-law]]) argues L7 is exactly the structural destination if inference is the load-bearing economic activity and the LLM becomes the new OS-with-install-base.
- **An OECD buyer-side taxonomy mirrors the ladder from the demand side.** [[oecd-sme-ai-adoption-2025]] proposes [[oecd-sme-adopter-taxonomy]] — Novices / Optimisers / Explorers / Champions — crossed on *complexity of AI use* (Embedded → Off-the-shelf → Customised → Frontier) and *scope of AI application* (Isolated → Functional → Cross-functional → Enterprise-wide), with *digital maturity* as a diagonal third dimension. Unlike the linear [[enterprise-adoption-ladder]], it distinguishes "wide-but-shallow" Optimisers from "deep-but-narrow" Explorers — a distinction L0–L7 has no native vocabulary for. The taxonomy is the **buyer-side mirror** of the supply-side ladder: where L0–L7 describes who in the stack captures value as it flows downstream, the OECD frame describes which firms can reach upstream to extract it. The mapping to substrate ownership is loose — most Champion SMEs in the case studies still sit at L0–L2 substrate (rented APIs, embedded features). Useful pairing for the white paper: a country's economic capture of AI-generated value is a product of (a) where its firms sit in the stack as suppliers, and (b) where its firms sit in the adopter taxonomy as buyers. A country can win the stack but lose diffusion, or vice versa. The taxonomy also aligns with [[taker-shaper-maker]]: Novices/Optimisers behave as takers, Explorers as shapers, Champions as (small-scale) makers — see [[sme-policy-pathway-novice-to-champion]]. A firm's full coordinates are now closer to (substrate L0–L7, maturity Phase 1–5, positioning Taker/Shaper/Maker, **SME-adopter Novice/Optimiser/Explorer/Champion**) — i.e., the SME taxonomy is a *fourth independent decomposition*, primarily useful in the long-tail population the other three frames under-resolve.

## Confidence

Confidence varies substantially by layer and is not uniform across the ladder.

**High (L0–L3).** These levels are directly observable today. Users actively move between them — from web chat (L0) to IDE assistance (L1) to workflow automation (L2) to single-agent loops (L3). The tooling is well-documented, products are shipping at scale, and the substrate-ownership distinction between levels is empirically legible. The ladder's descriptive validity here is not seriously contested.

**Medium (L4–L5).** Sustained autonomous execution and multi-agent fleets exist in production, but reliability under real-world enterprise conditions is uneven. Confidence here depends partly on how the [[scaling-wall]] argument resolves: if long-horizon tasks on hard-to-learn enterprise problems require a paradigm shift beyond next-token prediction, L4–L5 becomes a wall rather than a staircase for most buyers. Confidence is partially restored by the [[agentic-scaling-law]] (test-time compute as a second scaling axis), which suggests that sub-agent reasoning and search can route around the wall for tasks with verifiable intermediate steps — but the honest position is that both the wall and the counter-axis are partially real and unsettled.

**Low / speculative (L6–L7).** Vertical integration at this scale — own weights, own GPUs, own datacenter, own energy — is currently hyperscaler-centric. Evidence for broad enterprise adoption of L6 economics is sparse; L7 (intelligence as commodity, energy included) is a structural bet on a paradigm shift in inference cost and reliability that has not yet generalized beyond a handful of firms. Confidence here depends on energy and silicon economics that remain deeply uncertain. Useful as a visionary horizon, not a near-term operational claim.

## What would retire this hypothesis
- The field converges on a different canonical taxonomy (e.g., an Anthropic or DeepMind "levels of autonomy" frame becomes dominant) and ours adds nothing.
- In interviews, no operator finds the L4 / L5 distinction useful for their own positioning.
- Counterexamples to the linear ordering pile up to the point the ladder loses explanatory power.

## Related
- [[H2_u-curve-of-value]] — the economic claim that depends on this map.
- [[H3_orthogonal-axes-under-priced]] — what the ladder leaves out.
- [[H4_rl-specialization-value-pocket]] — sits at L3–L5 substrate (agent + harness + RL-tuned model) and proposes a Maker posture at vertical scale; tests whether the ladder's middle rungs admit durable third-party value capture via RL specialization.
- [[scaling-wall]] — the architectural ceiling that may cap the ladder above L3.
- [[agentic-scaling-law]] — the counter-axis (test-time compute) that may route around the wall.
- [[autonomy-slider]] — competing/orthogonal single-axis taxonomy.
- [[llm-as-operating-system]] — sharpens the substrate-ownership argument at L6–L7.
- [[karpathy-software-3]] — bull-frame source that introduces the slider, OS, and agentic scaling.
- [[bear-case-synthesis]] — broader skeptic frame this hypothesis must survive.
- [[enterprise-adoption-ladder]] — buyer-side parallel ladder; orthogonal axis to substrate ownership.
- [[wef-ai-in-action-2025]] — source of the adoption ladder and the WEF / Accenture consultancy frame.
- [[deloitte-ai-dossier-eri]] — vertical-industrial instantiation; the 12 ER&I use cases sit at L3–L5 (agent decides → fleet of agents) inside asset-heavy operations.
- [[vertical-ai-orchestration]] — what the L3–L5 layer looks like when specialized to one industrial domain.
- [[agentic-revolution]] — the paradigm shift that makes L3+ economically load-bearing.
- [[taker-shaper-maker]] — strategic-positioning axis orthogonal to substrate ownership.
- [[digital-core]] — the buyer-perspective 3-layer stack that maps roughly onto L0–L2 (apps) / mid (data) / L6–L7 (infra) but collapses substrate ownership into procurement.
- [[non-tech-digital-core-synthesis]] — secondary source that crystallizes the taker/shaper/maker + digital-core frame for non-tech firms.
- [[oecd-sme-ai-adoption-2025]] — primary source for the SME-specific buyer-side taxonomy.
- [[oecd-sme-adopter-taxonomy]] — the four-quadrant decomposition (Novices / Optimisers / Explorers / Champions) that mirrors L0–L7 from the demand side.
- [[sme-policy-pathway-novice-to-champion]] — the policy-pathway framing that links the adopter quadrants to [[taker-shaper-maker]] positioning.
- [[sme-ai-adoption-gap]] — empirical evidence that most SMEs sit at L0–L2 regardless of taxonomy quadrant.
- [[ai-productivity-firm-level]] — the productivity premium that the ladder's strategic claim implicitly depends on.

## Referenced by

*Auto-generated reverse-link index — pages in the wiki that link here. Maintained by `/lint` and reverse-link sweeps.*

**Paper planning**
- [[00_initial-brief]]
- [[02_purpose-and-justification]]
- [[03_structure]]
- [[06_collaboration]]
- [[07_analytical-vocabulary]]

**Hypotheses**
- [[H2_u-curve-of-value]]
- [[H3_orthogonal-axes-under-priced]]

**Concepts**
- [[agentic-scaling-law]]
- [[ai-factory-huang]]
- [[application-layer]]
- [[autonomy-slider]]
- [[circular-ai-economy]]
- [[digital-core]]
- [[enterprise-adoption-ladder]]
- [[foundational-enablers]]
- [[g7-sme-ai-policy-pluralism]]
- [[llm-as-operating-system]]
- [[oecd-sme-adopter-taxonomy]]
- [[oecd-sme-enabler-quartet]]
- [[scaling-gap]]
- [[scaling-wall]]
- [[software-3-paradigm]]
- [[taker-shaper-maker]]
- [[vertical-ai-orchestration]]
- [[world-models-jepa]]

**Sources**
- [[bear-case-synthesis]]
- [[choudary-ecosystem-teardown]]
- [[deloitte-ai-dossier-eri]]
- [[geopolitics-global-ai-divide]]
- [[karpathy-software-3]]
- [[marcus-world-models-failure]]
- [[massenkoff-mccrory-labor-market-impacts-2026]]
- [[non-tech-digital-core-synthesis]]
- [[oecd-sme-ai-adoption-2025]]
- [[wef-ai-in-action-2025]]

**Ideas**
- [[sme-champion-vertical-ai]]
- [[sme-explorer-custom-agent]]
- [[sme-novice-off-the-shelf-llm]]
- [[sme-optimiser-cross-functional-stack]]
