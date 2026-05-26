---
title: H2 — The U-Curve of Value
status: working-hypothesis (under pressure from three directions; top empirically validated; labor-side mirror documented)
confidence: low-to-medium — top empirically validated; bottom uncertain; **bottom-right thin in SME / lagging-sector dimension per [[oecd-sme-ai-adoption-2025]]**; U-shape may be a US-stack artifact ([[divergent-value-stack-optima]]); **labor-side mirror established by [[massenkoff-mccrory-labor-market-impacts-2026]]**
tags:
  - hypothesis
  - economics
  - margin
last-updated: 2026-05-26
---

# H2 — The U-Curve of Value

> [!note] Vertical-domain corroboration (ER&I)
> [[deloitte-ai-dossier-eri]] supplies the first **non-software** vertical instantiation of the U: in industrial verticals, the **top of the U** is the multi-agent operational orchestrator ([[vertical-ai-orchestration]]) and the **bottom of the U** is the proprietary operational data + physical assets the orchestrator acts on. Generic foundation models and generic agent frameworks are the squeezed middle. The same structural shape recurs in a completely different industry, which is mild evidence that the U is not purely a SaaS-stack artifact — but the shape's universality across blocs ([[divergent-value-stack-optima]]) and the surplus-magnitude question ([[task-based-framework]]) remain unresolved.

> [!abstract] Hypothesis
> Economic margin **does not distribute linearly** across the stack described in [[H1_L0-L7-ladder]]. It concentrates at the **top** (workflow + distribution ownership: who owns the user, the schema, the habits) and at the **very bottom** (silicon, energy, frontier weights), and **evaporates in the middle** (generic wrappers, generic orchestrators, generic agent platforms get compressed between commoditizing model capability above and commoditizing infrastructure below).

> [!warning] Status
> Working hypothesis. Confidence lower than [[H1_L0-L7-ladder]] because the "U" shape is asserted without rigorous economic data behind it. Could turn out to be a different shape entirely: an L (only the top matters), an inverted-U, a fragmented landscape with multiple local maxima, or no consistent shape at all.

## The intuition
Two layers are commoditizing fast:
- **Foundation models above** — eaten by frontier labs releasing capability for free or near-free.
- **Infrastructure below** — eaten by hyperscalers and falling GPU prices.

What survives the squeeze:
- **At the top**: things that are not the model — distribution, brand, workflow lock-in, proprietary data, trust, embedded integrations, and **verification surfaces** ([[autonomy-slider]] — Cursor's diff, Perplexity's citations). Aggregation Theory applied to AI.
- **At the bottom**: things hyperscalers cannot fully commoditize — frontier weights themselves, the silicon, the power. Reinforced by Huang's "AI factory" framing in [[karpathy-software-3]]: gigawatt-scale inference plants where extreme co-design (silicon + networking + energy) makes the substrate capital-intensive in a way that resists commoditization.

The middle — "we're an AI startup that builds agents" without proprietary distribution or proprietary substrate — is where capital goes to die.

## Empirical validation of the top (via [[where-value-lands-2026]])

The strongest evidence yet that the top of the U — distribution ownership, workflow lock-in, proprietary data — is real and measurable:

- **Cursor (Anysphere):** $50B valuation, $2B ARR. Moat = intelligent model routing + continuous learning pipeline + context-aware codebase adaptation. Michael Truell's "automobile vs. engine" strategy: while labs build engines, Cursor builds the car developers drive. The data flywheel third-party APIs cannot access is the actual moat.
- **Windsurf:** Three-way acquisition battle (OpenAI at $3B, Google reverse-acquihire at $2.4B, Cognition asset acquisition). The fight confirms that the distribution layer — where developer intent is formulated, debugged, and executed — is the most strategically critical AI asset in the current stack.
- **Perplexity (Srinivas):** 80/20 on queries; owns direct user relationship; forces model providers to compete on price. Zip2 as the failure-mode counter-example: white-labeling = surrendering leverage.

**Critical taxonomy note:** This source calls Cursor, Windsurf, and LangGraph "middle stack." H2 would classify them as "the top" (distribution + workflow ownership). The terminology differs; the underlying claim is compatible. The "thin wrapper" (generic proxy UI) is what dies; the "workflow-embedded platform" is what H2 calls the top. See [[middle-layer-defensibility]] for the full distinction.

**Partial rehabilitation of sophisticated orchestration:** Harrison Chase's LangGraph case adds nuance: graph-based orchestration with HITL, time-travel debugging, and observability is not a thin wrapper — it is enterprise infrastructure. This suggests H2's "generic middle dies" should be sharpened to "generic middle dies; sophisticated orchestration infrastructure can survive via [[context-control]]."

**Jevons Paradox complicates the bottom:** DeepSeek's efficiency gains (1/70th GPT-4 Turbo cost) did not reduce GPU demand — they expanded it via unlocking previously cost-prohibitive use cases. This partially defends the bottom of the U against [[circular-ai-economy]], though the two are not mutually exclusive. See [[jevons-paradox-ai]].

## Bull-frame pressure points (Karpathy / Huang / Steinberger via [[karpathy-software-3]])
The Karpathy source adds two pressures on the U-curve, pulling in opposite directions:

- **Reinforces the top.** [[llm-as-operating-system]] implies install-base moats compound the way OS ecosystems do; [[democratization-of-programming]] implies distribution + workflow ownership matter more than syntax-level production. The defensible top is *verification + distribution*, not "we built an AI app."
- **Reinforces the bottom.** [[agentic-scaling-law]] argues inference (not training) is the load-bearing economic activity. If correct, AI-factory substrate has a margin profile closer to a utility than to a speculative R&D bet — partially restoring the bottom of the U threatened by [[circular-ai-economy]].
- **Threatens the top differently.** Steinberger's "agents eliminate 80% of apps" prediction (same source) says agents talk directly to endpoints, making consumer-facing GUIs redundant. If true, the **top of the U is not the verification GUI** — it's whatever the agent-facing API layer becomes. The application layer specializes, doesn't disappear, but its shape changes.

## Structural precursor — Choudary's horizontal-value thesis (via [[choudary-ecosystem-teardown]])

Choudary's 2022 four-archetype framework ([[ecosystem-business-archetypes]]) is a **pre-AI structural precursor** to H2. His claim: as transaction costs fall ([[vertical-to-horizontal-unbundling]]), vertically integrated value chains unbundle into horizontal layers, and value concentrates in specific horizontal positions. H2 is the AI-era specialisation of the same pattern.

Mapped onto the U-curve:
- **Aggregators and Infrastructures** → top and bottom of the U respectively (distribution + substrate).
- **Integrators** → **bimodal middle**: defensible if switchboard-essential (Stripe-class, Plaid-class, Visa-class network effects); squeezed if generic. This **partially defends** H2 by giving the middle a richer taxonomy than "wrappers"; it **partially threatens** H2 by surfacing durable Integrator-class plays that capture middle-stack value.
- **Capabilities** → either concentrate (when IP-defensible) or commoditise; the wrong-archetype-confusion failure mode ([[cross-archetype-confusion]]) drives many failed Capability bets.

The thin-wrapper firms that motivate "the middle dies" are not an archetype in Choudary's taxonomy at all — they are **failed Capability attempts**. This sharpens H2: the squeezed middle is the population of firms that **tried to be Capabilities without IP / data advantage and failed**, plus the population of generic Integrators displaced by switchboard incumbents.

## Seller-side instantiation — Weber's four AI-startup archetypes (via [[weber-ai-startup-business-models]])

Weber et al.'s empirical four-pattern taxonomy of AI startups ([[ai-startup-business-archetypes-weber]]) maps cleanly onto the U:

- **[[ai-charged-product-service-provider]]** (26/100 of Weber's sample) → **top of U.** Readily-trained model embedded into a standardized product; value depends on workflow + distribution. Cursor / Windsurf / Perplexity are 2026 instances. **Empirically validated.**
- **[[ai-development-facilitator]]** (25/100) → **the squeezed middle.** Generic SDKs and chatbot-builders are exactly what gets compressed. Survives only via [[middle-layer-defensibility]] niches (Hugging Face's distribution; agent frameworks).
- **[[ai-data-analytics-provider]]** (30/100, largest cluster) → **shoulder of U.** Classical analytics with ML inside; sustainable B2B SaaS economics but not where the new AI margin lands. **Mild counter-evidence to the strong form of "middle dies" — the population is large and profitable.** The hypothesis should distinguish *firm count* from *value-capture share at exit*.
- **[[ai-deep-tech-researcher]]** (19/100) → **bottom of U** when defensible; merges with [[H4_rl-specialization-value-pocket]] in the 2026 RL-fine-tuning sub-pattern.

**Net effect on H2:** the four-archetype mapping **reinforces the qualitative shape** (top + bottom > middle) while **complicating the strong form** — the middle is densely populated and not uniformly dead. The U-curve is best read as a *value-capture* curve, not a *firm-count* curve.

## Historical analogies (to be tested, not assumed)
- **Intel vs. PC OEMs in the 90s** — chip and OS captured margin; assemblers in the middle were squeezed.
- **Stripe vs. acquirers / processors** — developer-experience layer on top + card networks on the bottom; middle compressed.
- **AWS vs. independent SaaS** — infra on bottom, branded apps on top, undifferentiated "platforms" between get acquired or wither.
- **Aggregation Theory** (Ben Thompson) — distribution-side scale beats supply-side scale once supply is commoditized.

## Why this might be wrong
- The middle layer may **not** be undifferentiated. There may be real moats in agent orchestration, evals, observability that the U-curve framing dismisses too easily.
- The top may not be defensible either — if frontier models keep absorbing capabilities, **the application layer itself collapses into the model**.
- "U" may be too clean a shape. Reality could be noisy, with multiple local maxima depending on vertical.
- The historical analogies may be cherry-picked. Counter-cases: telcos (margin in the middle, not the edges), credit card networks (a middle layer that captured margin durably).
- **The bottom may also be hollow.** The bear case in [[bear-case-synthesis]] argues — via [[circular-ai-economy]] — that hyperscaler "AI revenue" is largely recycled VC capital, not durable enterprise demand. If so, the U is upside-down: middle dies *and* bottom dies, leaving only the top (distribution + workflow) actually defensible. The shape is then closer to an **L**, not a U.
- **There may be no surplus to redistribute.** [[task-based-framework]] caps 10-year US TFP gains from AI at **<0.71% cumulative**. If correct, the absolute size of the surplus is small enough that any "U" shape is operating on a fraction of the prize the optimistic narrative assumes — capital reshuffles among GPU vendors and VCs rather than productivity expanding the pie.
- **Enterprise-side evidence is ambiguous.** [[wef-ai-in-action-2025]] reports a [[scaling-gap]] of **74% of firms struggling to scale AI** and only **16% prepared for enterprise reinvention**. This is interpretation-flexible: it can be read as managerial (closeable with enablers — the WEF stance), bear-structural (most enterprise AI does not deliver — compatible with [[bear-case-synthesis]]), or middle-dies (most internal initiatives are thin wrappers without distribution or substrate — compatible with [[middle-layer-defensibility]]). The same number supports all three readings, which means the gap is suggestive evidence but not yet adjudicating.
- **Bull projections worth triangulating against.** WEF / Accenture project $7.6–17.9T global AI contribution by 2038 — a figure incompatible with [[task-based-framework]]'s <0.71% TFP cap. The source-of-projection (consultancy with commercial interest in scaling) should be weighed; useful as the canonical bull-multilateral number to contrast against.
- **The shape may not be universal.** [[divergent-value-stack-optima]] argues — drawing on [[geopolitics-global-ai-divide]] — that the U-curve is plausibly **a US-stack artifact**. China's open-weight asymmetry ([[open-weight-asymmetry]]) deliberately *destroys* the bottom of the U to force value downstream into application and B2B integration: a bottom-*light*, application-heavy shape. Europe attempts a third shape — value at the compliance and sovereign-infra layer ([[brussels-effect-and-mirage]], [[sovereign-ai]]) — that does not resemble a U at all. If the where-does-value-land answer is bloc-specific, the single-curve framing is the wrong unit of analysis.
- **The bottom-right of the U may be thin where the population is thickest (SME-side floor effect).** [[oecd-sme-ai-adoption-2025]] documents a [[sme-ai-adoption-gap]] of 40% large vs 11.9% small firms using AI OECD-wide in 2024. Only **29% of SMEs using generative AI deploy it in core activities**; the rest is peripheral (marketing, drafting, customer service). The long-tail SME application population that the U's bottom-right relies on is **shallow in depth and concentrated in capability-poor sectors** ([[sectoral-ai-diffusion-pattern]]: ~7% in construction, hospitality, transport vs ~45% in ICT). Three further empirical findings, gated by the [[oecd-sme-enabler-quartet]], narrow the tail:
    - The firm-size broadband gap in OECD countries has been **flat at ~25–28 pp for five years** ([[sme-broadband-firm-size-gap]]) — connectivity is not converging.
    - Skills are the most-cited adoption barrier, with **50%+ of SMEs across G7 countries** reporting they lack the knowledge to use generative AI ([[ai-skill-shortage-as-diffusion-bottleneck]]).
    - AI adoption ratios between large and small firms range from **1.65× (US) to 4.7× (Italy)** across the G7 ([[g7-sme-large-firm-ai-adoption-ratio]]).
    
    If SMEs settle at the [[oecd-sme-adopter-taxonomy]] Novice / Optimiser corner — wide-but-shallow off-the-shelf use — the application-side surplus pools at a small number of digitally mature large firms and AI-intensive sectors, not at the broad SME base. The U may be **asymmetric in the SME dimension**: top captured by a small Champion-adjacent population, large middle of Optimisers paying recurring SaaS rent upward. The US has the thinnest divide and likely the fattest application-layer tail; the EU bloc, despite richer policy, has the widest divides. This doesn't refute the U, but it makes the application-layer-as-broad-base claim contingent on policy, not architectural.

## Confidence

Confidence varies sharply across the four sub-claims of the U. Treat them separately.

- **Top of U (high)** — empirically validated by the application-layer revenue and retention pattern documented in [[where-value-lands-2026]] and reinforced by the vertical-domain instantiation in [[deloitte-ai-dossier-eri]]. Cursor, Windsurf, GitHub Copilot, and the [[vertical-ai-orchestration]] class show durable workflow + distribution lock-in. See [[application-layer]].
- **Middle claim (medium)** — qualitatively reinforced (Karpathy, Steinberger, [[middle-layer-defensibility]]) but the firm-count vs value-share distinction is unresolved. Many middle-layer firms exist (the trough is shallow by count) but aggregate value capture is unclear; some monitoring / orchestration / evals sub-pockets may survive.
- **Bottom of U (under pressure)** — challenged by [[circular-ai-economy]] dynamics: if hyperscaler "AI revenue" is largely recycled VC capital, the bottom is hollow and the U collapses toward an L. [[task-based-framework]]'s <0.71% 10-year TFP cap compounds the concern. Frontier-lab defensibility ([[scaling-wall]], [[open-weight-asymmetry]]) is the counter-pull.
- **Universal shape (contested)** — [[divergent-value-stack-optima]], drawing on [[geopolitics-global-ai-divide]], argues the U is plausibly a US-stack artifact: China's open-weight asymmetry deliberately flattens the bottom, Europe centres value at the compliance / sovereign-infra layer. Treat the U as a default shape that can flatten or invert per bloc and per vertical.

## Labor-side mirror (via [[massenkoff-mccrory-labor-market-impacts-2026]])

The value-stack U has a **labor-exposure twin** on a different axis. Anthropic's 2026 internal study finds AI exposure concentrated on the **upper half of the wage distribution** (computer programmers 74.5%, customer service reps 70.1%, financial analysts 57.2%, market research analysts 64.8%) while **30% of workers — manual physical labor (cooks, mechanics, lifeguards, bartenders) — have zero exposure**. Exposed workers are **older, more female, more white/Asian, more educated** (4× the graduate-degree share), and earn **47% more per hour** than unexposed ones (see [[exposed-worker-demographics]]).

This produces a labor-exposure shape that is also U-like but on a different axis: **high-skill knowledge work at one end, manual physical labor at the other, semi-skilled service work compressed in the middle**. The two U's interact:

- **Surplus-side.** Capital owners of L4–L6 application-layer firms (Cursor, GitHub Copilot, Anthropic, LangChain customers) capture surplus by automating tasks performed by the highest-paid labor on the curve. The labor-side incidence is the inverse of prior automation waves: this one hits the educated, not the routine.
- **Detection-side.** The [[unemployment-did-exposed-workers]] DiD is flat post-ChatGPT (+0.002, SE 0.002, insignificant) — labor-side displacement is **invisible in unemployment** at the 1pp differential detectability threshold. The only detectable signal is [[ai-young-worker-hiring-slowdown]]: a ~14% drop in 22–25-year-old job-start rates in exposed occupations. Capital captures surplus; senior incumbents retain jobs; the entry-level cohort bears the suppressed-hiring cost.
- **Diffusion-side.** [[theoretical-vs-observed-capability-gap]] shows actual Claude deployment is ~3× behind theoretical capability in the most-exposed category. As that gap closes, the labor-side incidence scales — the U-shape sharpens.

For *Where Value Lands*, this updates the central claim: **value lands on capital at the top of the value-stack U, with the cost borne not by the bottom of the labor distribution but by the entry-level cohort of the top half**. The redistribution story is *intra*-class (incumbent vs entrant within knowledge-work) before it is *inter*-class.

## What would retire this hypothesis
- Three or more profitable, durable, mid-stack players emerge with no distribution moat and no substrate moat — pure "middle of the stack" winners.
- The historical analogies don't hold up under scrutiny.
- Interviewed operators consistently report value capture in the middle.
- **A correction confirms [[circular-ai-economy]]:** hyperscalers' AI revenue line items contract sharply when VC funding tightens, validating that the bottom of the U was funded by recycled capital, not enterprise demand. In that case the U is the wrong shape — likely an **L** (only the top matters) or a **collapsed flat** during correction.
- **The three blocs durably diverge.** If US, China, and EU stacks settle into the three different shapes described in [[divergent-value-stack-optima]] (top-heavy / bottom-heavy / regulatory-centric), the universal-U framing must be replaced by a per-bloc analysis. The paper's Section 5 then becomes a structural cross-cut of Section 3, not a sidebar.
- **The SME / firm-size divide either narrows or widens decisively.** If longitudinal SME data shows the firm-size adoption divide narrowing (small firms catching up at the application layer) within five years, the U-shape's bottom tail becomes credibly populated. If the divide widens — or stays flat as [[sme-broadband-firm-size-gap]] suggests — the U risks collapsing into an **L-shape** concentrated at the infrastructure top and the largest application-layer adopters. The persistence of the divide across multiple years and the country variance (1.65× US → 4.7× Italy) make the application-layer-as-broad-base claim contingent on policy, not architectural.

## Related
- [[H1_L0-L7-ladder]] — the map this depends on.
- [[H3_orthogonal-axes-under-priced]] — what the U misses.
- [[H4_rl-specialization-value-pocket]] — proposes a *vertical-scale* instantiation of the top of the U: RL-fine-tuned proprietary models inside one industrial customer as a [[distribution-moat]] alternative to consumer-facing workflow ownership. Tests whether the model layer can be pulled into the moat for non-software industrials, rather than concentrating only at the application + orchestration layer.
- [[bear-case-synthesis]] — the cluster of evidence pressuring this hypothesis.
- [[circular-ai-economy]] — the strongest direct threat to the bottom of the U.
- [[task-based-framework]] — caps the size of the underlying surplus.
- [[capital-labor-divergence]] — how surplus distributes between capital and labor, regardless of U shape.
- [[karpathy-software-3]] — bull-frame source that pressures the U in both directions.
- [[where-value-lands-2026]] — empirical validation of the top; nuanced middle-layer story; Jevons Paradox for the bottom.
- [[middle-layer-defensibility]] — the concept that resolves the top/middle taxonomy confusion.
- [[distribution-moat]] — mechanism behind the top of the U.
- [[context-control]] — why sophisticated orchestration survives; the "generic middle dies" claim sharpened.
- [[jevons-paradox-ai]] — partial defense of the bottom against circular-economy pressure.
- [[world-models-jepa]] — paradigm-reset risk for current top-of-U moats.
- [[llm-as-operating-system]] — install-base logic for the top.
- [[agentic-scaling-law]] — inference-as-economy logic for the bottom.
- [[autonomy-slider]] — what the top of the U actually defends today.
- [[democratization-of-programming]] — what the application layer may compress into.
- [[divergent-value-stack-optima]] — the parallel pressure: the U-shape may not even be universal across blocs.
- [[geopolitics-global-ai-divide]] — the synthesis behind the bloc-divergence pressure.
- [[wef-ai-in-action-2025]] — enterprise-side bull synthesis; source of the 74% scaling gap and the $7.6–17.9T projection.
- [[scaling-gap]] — the empirical artifact; interpretation-flexible evidence on enterprise value-capture.
- [[enterprise-adoption-ladder]] — buyer-side maturity model the scaling gap sits inside.
- [[foundational-enablers]] — WEF / Accenture's claimed mechanism for closing the gap.
- [[deloitte-ai-dossier-eri]] — vertical-domain (ER&I) instantiation of the U-curve in industrials.
- [[vertical-ai-orchestration]] — the top-of-U mechanism in industrial verticals.
- [[agentic-revolution]] — the analytical→agentic transition that reshapes what "top of the U" means.
- [[ai-factory-huang]] — the bottom-of-U mechanism, federated into central + regional + edge inference.
- [[oecd-sme-ai-adoption-2025]] — empirical pressure on the bottom-right of the U from the SME-diffusion side.
- [[sme-ai-adoption-gap]] — the keystone empirical claim on the 40% / 11.9% large-vs-small gap.
- [[oecd-sme-adopter-taxonomy]] — buyer-side decomposition that makes the bottom-right granular.
- [[sectoral-ai-diffusion-pattern]] — the sectoral compounding factor (ICT-heavy vs construction/hospitality/transport).
- [[ai-productivity-firm-level]] — productivity gains mediated by complementary capital; surplus partially routed to substrate vendors.
- [[oecd-sme-enabler-quartet]] — the four gating enablers behind the SME floor effect.
- [[sme-broadband-firm-size-gap]] — five-year-flat ~25–28 pp connectivity divide.
- [[ai-skill-shortage-as-diffusion-bottleneck]] — skills as the most-cited SME adoption barrier.
- [[g7-sme-large-firm-ai-adoption-ratio]] — country-level variance (1.65× US → 4.7× Italy).
- [[massenkoff-mccrory-labor-market-impacts-2026]] — labor-side mirror source.
- [[observed-exposure-measure]] — the measure used to score the labor-side incidence.
- [[exposed-worker-demographics]] — who absorbs the labor-side displacement.
- [[ai-young-worker-hiring-slowdown]] — the entry-level signal that does the surplus-capture work.
- [[unemployment-did-exposed-workers]] — the *null* finding that locates the displacement in hiring rather than unemployment.
- [[theoretical-vs-observed-capability-gap]] — the diffusion process that scales the labor-side incidence as deployment catches up.
- [[choudary-ecosystem-teardown]] — 2022 pre-AI structural precursor; supplies four-archetype vocabulary for the U.
- [[ecosystem-business-archetypes]] — Choudary's four-archetype taxonomy mapped onto top/middle/bottom of the U.
- [[vertical-to-horizontal-unbundling]] — the structural mechanism behind the recurring U-shape pattern across industries.
- [[foundation-model-layer]] — the raw frontier-model API tier; the layer that sits inside the trough of the U for most players, with a partial micro-peak at the frontier-lab club.
- [[software-as-temporary-artefacts]] — sharpens the middle-collapse claim: AI-first firms running an [[ai-first-company-loop]] synthesise their middle on demand rather than buying it; the squeezed middle is squeezed *from a third direction* (buyer-side in-house substitution), not just from above and below. The surviving middle is *primitives for synthesis* (LangGraph, RL APIs, eval tooling), not finished workflow products.
- [[ai-first-company-loop]] — the operating model whose tool layer drives the in-house substitution; refines what "the middle" actually contains by separating primitives (survive) from finished workflows (collapse).
- [[H6_industrial-ai-rollup-captive-suppliers]] — operator-side rollup hypothesis whose mechanism reinforces the U: each acquired firm synthesises its own middle, removing demand from middle-layer SaaS at the rollup's firm count.

## Referenced by

*Auto-generated reverse-link index — pages in the wiki that link here. Maintained by `/lint` and reverse-link sweeps.*

**Paper planning**
- [[00_initial-brief]]
- [[02_purpose-and-justification]]
- [[03_structure]]
- [[05_open-questions]]
- [[06_collaboration]]
- [[07_analytical-vocabulary]]
- [[08_contributor-charter]]

**Hypotheses**
- [[H1_L0-L7-ladder]]
- [[H3_orthogonal-axes-under-priced]]
- [[H4_rl-specialization-value-pocket]]
- [[H5_ai-as-operational-not-product]]

**Search**
- [[01_source-list]]

**Concepts**
- [[agentic-revolution]]
- [[agentic-scaling-law]]
- [[ai-capex-cycle]]
- [[ai-factory-huang]]
- [[ai-productivity-firm-level]]
- [[ai-skill-shortage-as-diffusion-bottleneck]]
- [[ai-young-worker-hiring-slowdown]]
- [[application-layer]]
- [[autonomy-slider]]
- [[capital-labor-divergence]]
- [[circular-ai-economy]]
- [[context-control]]
- [[democratization-of-programming]]
- [[digital-core]]
- [[distribution-moat]]
- [[divergent-value-stack-optima]]
- [[ecosystem-business-archetypes]]
- [[enterprise-adoption-ladder]]
- [[exposed-worker-demographics]]
- [[jevons-paradox-ai]]
- [[llm-as-operating-system]]
- [[middle-layer-defensibility]]
- [[observed-exposure-measure]]
- [[oecd-sme-adopter-taxonomy]]
- [[oecd-sme-enabler-quartet]]
- [[scaling-gap]]
- [[scaling-wall]]
- [[sectoral-ai-diffusion-pattern]]
- [[sme-ai-adoption-gap]]
- [[sme-ai-finance-gap]]
- [[sme-connectivity-divide]]
- [[software-3-paradigm]]
- [[task-based-framework]]
- [[theoretical-vs-observed-capability-gap]]
- [[value-capture]]
- [[vertical-ai-orchestration]]
- [[vertical-to-horizontal-unbundling]]
- [[world-models-jepa]]

**Sources**
- [[acemoglu-simple-macroeconomics]]
- [[bear-case-synthesis]]
- [[choudary-ecosystem-teardown]]
- [[deloitte-ai-dossier-eri]]
- [[geopolitics-global-ai-divide]]
- [[goldman-sachs-too-much-spend]]
- [[gultekin-pinarbasi-commercialisation-ai-2025]] — structural evidence for the U-shape from a 2022 Turkish AI-startup sample.
- [[karpathy-software-3]]
- [[massenkoff-mccrory-labor-market-impacts-2026]]
- [[oecd-sme-ai-adoption-2025]]
- [[wef-ai-in-action-2025]]
- [[where-value-lands-2026]]
- [[zitron-circular-economics]]

**Ideas**
- [[sme-champion-vertical-ai]]
- [[sme-explorer-custom-agent]]
- [[sme-novice-off-the-shelf-llm]]
- [[sme-optimiser-cross-functional-stack]]

**Data**
- [[ai-exposure-vs-bls-growth]]
- [[cursor-50b-valuation]]
- [[g7-sme-large-firm-ai-adoption-ratio]]
- [[high-vs-low-exposure-worker-characteristics]]
- [[most-exposed-occupations]]
- [[oecd-ai-adoption-trajectory-2020-2024]]
- [[oecd-g7-productivity-gain-projection]]
- [[oecd-sectoral-ai-adoption-2024]]
- [[scaling-gap-74-16]]
- [[sme-broadband-firm-size-gap]]
- [[sme-vs-large-firm-ai-gap]]
- [[task-based-tfp-ceiling]]
- [[unemployment-did-exposed-workers]]
- [[wef-7-6t-projection]]
- [[windsurf-acquisition-battle]]
- [[young-worker-hiring-did]]

**Thoughts**
- [[archetypes-vocabulary-personal-frame]]
