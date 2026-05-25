---
title: Weber Taxonomy — 2026 Gaps
status: working-draft (diagnostic; awaiting source-side fill from a 2024–2026 taxonomy update)
tags:
  - concept
  - taxonomy
  - business-models
  - diagnostic
last-updated: 2026-05-25
---

# Weber Taxonomy — 2026 Gaps

A diagnostic page: what the [[weber-ai-startup-business-models]] 11-dimension / 39-characteristic / 4-pattern taxonomy fails to encode about AI startups as they exist in 2026. Built from material already in the wiki — not yet anchored to a post-2023 academic update, which is the next ingest target (see [[01_source-list]] §2/§3).

> [!warning] Status
> Working draft. Every gap below names a dimension whose **2026 evidence already lives in the wiki**; what is missing is a *single empirical source* that has re-derived the Weber taxonomy on a post-ChatGPT sample. Until one is ingested, each new dimension should be treated as a candidate, not as established framework.

## Prerequisite — the unit of analysis (added 2026-05-25, [[westerveld-business-model-portfolio-2023]])

Before reading the gaps below, a scoping rule that Weber's morphological method does **not** make explicit but that this project now treats as binding:

> **The unit of analysis is a single business model, not a startup.** A startup running multiple business models — a [[business-model-portfolio]] — is classified by applying the Weber four-pattern taxonomy *separately* to each BM, not by forcing the whole firm into one pattern.

This is not a missing *dimension* in Weber's morphological box (gaps 1–7 below). It is a missing **scoping prerequisite**: Weber's 11-dimension box silently assumes one firm = one BM. In 2026 this assumption is violated routinely — an AI startup may run a self-serve B2C product *and* a consulting engagement *and* a developer API at the same time, each with its own value proposition, distribution architecture, pricing logic, and (per gap 7) commercialisation motion. Forcing such a startup into one Weber pattern destroys signal.

The strategic justification (Westerveld et al. 2023): operating multiple BMs has shifted from a defensive contingency into a *proactive strategic tool*. Three intents (Diversifying / Sensing / Complementing) and four permanent paradoxes (Horizon / Cannibalization / Digital / Dogmatic) are documented in [[business-model-portfolio]]. The operational consequence for this wiki: each AI-startup source page should declare **one Weber pattern per BM**, and the GTM sibling taxonomy planned in *Strand B* below will inherit the same per-BM granularity.

## Why this page exists

The Weber et al. paper sampled Crunchbase in October 2020 — twenty-five months **before** ChatGPT and roughly four years before the agentic-workflow turn. The four-pattern clustering and the 11-dimension morphological box remain the cleanest published seller-side classifier the project has access to (see [[ai-startup-business-archetypes-weber]] for the operational classifier the wiki uses to tag new ingests). But three structural shifts since 2021 — foundation-model commoditization, the agentic turn, and the rise of distribution-as-moat — have invalidated parts of the taxonomy *as a generative frame for new startups in 2026*:

1. **Foundation-model commoditization** ([[middle-layer-defensibility]], [[open-weight-asymmetry]]) — most of what Weber called *AI Development Facilitator* in 2021 has been eaten by the GPT-4 / Claude API surface. The dimension that picks the survivors (proprietary-model ownership vs API-on-top vs open-weight self-host) is **absent** from Weber.
2. **The agentic turn** ([[agentic-revolution]], [[autonomy-slider]], [[vertical-ai-orchestration]]) — autonomy and orchestration depth are now the most strategically loaded design choices an AI startup makes. Weber's *Core AI value* dimension captures "Autonomous robots & bots" as a single characteristic; this is **wholly inadequate** for the copilot / agent / autonomous-worker spectrum that organises 2026 product design.
3. **Distribution-as-moat** ([[distribution-moat]], [[middle-layer-defensibility]]) — Weber's *Delivery mode* dimension (software application / programmable interface / base technology / AI-produced output) conflates *form factor* with *distribution architecture*. In 2026 the same form factor can be sold through a direct channel, embedded inside a platform, or routed through a marketplace — and which one a startup picks predicts value capture better than any other single choice.

The rest of this page lists, dimension by dimension, what would have to be added to make Weber generative again in 2026 — plus the fifth archetype the existing taxonomy folds into Pattern 1 and probably shouldn't.

## Seven missing dimensions

Each row below names a dimension Weber's 11-dimension box does not encode, the evidence already in the wiki that the dimension is load-bearing in 2026, and a one-line proposed characteristic set. Characteristic sets are intentionally provisional — they should be re-derived against a 2024–2026 startup sample, not imposed top-down.

> [!info] Note on dimension 7
> Dimensions 1–6 below were derived from wiki-internal evidence (concept pages, hypothesis pages) before any post-2023 taxonomy ingest. Dimension 7 — *Commercialisation motion / GTM posture* — was added after partial ingest of [[gultekin-pinarbasi-commercialisation-ai-2025]] surfaced a *process* dimension Weber's morphological method could not encode. It is therefore the first gap-page dimension **empirically derived from an ingested source** rather than from wiki-internal triangulation, and the only one currently anchored in a peer-reviewed empirical study.

### 1. Model sourcing

| | |
|---|---|
| **What it captures** | Where the AI capability that powers the product comes from, and whether the startup owns the weights. |
| **Why pre-FM era didn't have it** | In 2020–2021, every AI startup with non-trivial capability trained its own model; the question was undifferentiating. |
| **2026 wiki evidence** | [[rl-apis]], [[open-weight-asymmetry]], [[middle-layer-defensibility]], [[ai-charged-product-service-provider]] (Cursor, Windsurf, Perplexity — *none* of which train their own base models). |
| **Provisional characteristics** | Own-trained foundation model · Proprietary fine-tune of a closed FM · Proprietary fine-tune of an open-weight FM · Pure API-on-top (no fine-tune) · Multi-model swappable (Perplexity pattern). |
| **Why it predicts value capture** | Sits orthogonal to Weber's *Primary AI technology* and to [[H1_L0-L7-ladder]]; differentiates the survivors of the AI-Development-Facilitator pattern from the casualties. |

### 2. Autonomy level

| | |
|---|---|
| **What it captures** | How much of the work the AI does on its own once invoked. |
| **Why pre-FM era didn't have it** | Pre-ChatGPT systems were either narrow predictors (no autonomy choice) or full robots (the "Autonomous robots & bots" characteristic). The copilot / partial-autonomy middle didn't exist as a design space. |
| **2026 wiki evidence** | [[autonomy-slider]], [[karpathy-software-3]] ("Iron Man suit" framing), [[agentic-revolution]], [[H1_L0-L7-ladder]] (autonomy is a candidate orthogonal axis named in [[H3_orthogonal-axes-under-priced]]). |
| **Provisional characteristics** | Predictor / classifier (no autonomy) · Suggester (UI surfaces output, human acts) · Copilot (human-in-the-loop, AI proposes, human accepts) · Agent (AI executes, human verifies after) · Autonomous worker (AI executes, no per-task verification). |
| **Why it predicts value capture** | Verification-surface design is the mechanism behind the data flywheel in [[distribution-moat]]. The autonomy level determines what kind of behavioural data the startup accumulates. |

### 3. Orchestration depth

| | |
|---|---|
| **What it captures** | How the AI is composed: a single model call, a deterministic chain, a multi-agent system, or a vertical-domain orchestrator. |
| **Why pre-FM era didn't have it** | The 2020 product surface was single-model-call. Chains and multi-agent systems were research curiosities. |
| **2026 wiki evidence** | [[vertical-ai-orchestration]], [[context-control]] (Chase: orchestration *is* context management), [[middle-layer-defensibility]] (LangGraph survives the squeezed middle because orchestration is non-trivial), [[deloitte-ai-dossier-eri]] use cases (Aker BP Yggdrasil, BMW supply-chain twin). |
| **Provisional characteristics** | Single model call · Templated chain (RAG, deterministic) · Adaptive multi-step agent · Multi-agent system · Vertical-domain orchestrator (industry-specific composition over many specialised models). |
| **Why it predicts value capture** | Determines defensibility of the middle layer; the [[vertical-ai-orchestration]] argument is essentially that orchestration depth *creates* the moat that pure form factor doesn't. |

### 4. Distribution architecture

| | |
|---|---|
| **What it captures** | The channel and counterparty geometry through which the product reaches the user. Weber bundles this into *Delivery mode*, conflating form factor with channel. |
| **Why pre-FM era didn't have it** | In 2020, "B2B SaaS" was the default and the channel question collapsed into "direct sales vs. self-serve". |
| **2026 wiki evidence** | [[distribution-moat]] (Srinivas / Truell / Mohan), [[choudary-ecosystem-teardown]] (Aggregator archetype), [[ecosystem-business-archetypes]], [[middle-layer-defensibility]] (Cursor / Windsurf — direct channels survive; thin API wrappers do not), [[oecd-sme-ai-adoption-2025]] (SMEs adopt AI primarily through pre-existing platform aggregators). |
| **Provisional characteristics** | Direct (own UI, own user) · Marketplace-listed (AWS / GCP marketplace, app stores) · Platform-embedded (Shopify, ServiceNow, Salesforce app) · Wholesale-API (sells capability to another product that owns the user) · Foundation-model-store (OpenAI GPT store, Anthropic skills, etc. — new in 2024–2026) · Open-source-distributed (Hugging Face, GitHub). |
| **Why it predicts value capture** | This is the user's stated central concern, and the [[distribution-moat]] literature argues it dominates every other choice. **A full sibling morphological box for distribution / GTM, parallel to Weber, is the next major contribution this project can make.** See the *Next move* section below. |

### 5. Data flywheel

| | |
|---|---|
| **What it captures** | Whether the product accumulates a proprietary data asset that compounds with usage — and what kind. Weber's *Continuous learning* dimension captures the technical fact of model updates but not the strategic asset. |
| **Why pre-FM era didn't have it** | Most 2020 AI startups had access only to acquired or self-generated data. Behavioural-data flywheels of the Cursor / Perplexity kind did not exist at scale. |
| **2026 wiki evidence** | [[continual-learning-paradigm]] (Sutskever's reframe), [[context-control]], [[distribution-moat]] (Cursor's automobile-vs-engine moat is the canonical behavioural flywheel), [[middle-layer-defensibility]], [[H4_rl-specialization-value-pocket]] (proprietary trajectory data as the H4 asset). |
| **Provisional characteristics** | None (no proprietary data accumulated) · Behavioural (user actions inside the product) · Preference / RLHF loop (human ratings feed reward model) · Domain corpus (proprietary text / image / sensor data) · Trajectory data (state-action-outcome traces — the H4 asset). |
| **Why it predicts value capture** | Distinguishes startups whose moat compounds from those whose moat is a one-shot product feature. Tightly coupled to *Autonomy level* (higher autonomy → richer verification trajectories → stronger flywheel). |

### 6. Ethics / safety / compliance as product

| | |
|---|---|
| **What it captures** | Whether the startup sells, or is sold against, an ethics / safety / regulatory-compliance surface as a first-class product feature. |
| **Why pre-FM era didn't have it** | Weber et al. **explicitly expected to find this dimension** and didn't — see [[weber-ai-startup-business-models]] §"Contradictions surfaced". In 2020 it was not yet a buyable thing. |
| **2026 wiki evidence** | [[brussels-effect-and-mirage]] (EU AI Act creates buyable compliance), [[sovereign-ai]] (sovereignty as a feature), the existence of dedicated alignment / red-team startups (Anthropic-adjacent ecosystem). |
| **Provisional characteristics** | Not a product surface · Compliance-bundled (SOC 2 / GDPR / AI Act / HIPAA included) · Sovereignty-positioned (data residency, on-prem option, EU-hosted weights) · Alignment / safety as the primary deliverable (red-team, evals, governance tooling). |
| **Why it predicts value capture** | Differentiates buyers' willingness-to-pay in regulated verticals; load-bearing for the EU bottom-of-U story in [[divergent-value-stack-optima]]. |

### 7. Commercialisation motion / GTM posture

| | |
|---|---|
| **What it captures** | The **process model and resource posture** by which the startup actually goes to market — independently of the channel geometry it uses (dimension 4). Whether commercialisation is dev-led-and-deferred (BAH-style), marketing-led-and-tested (Claessens-style), or emergent / fuzzy (modal in practice). Maps to the *acquisition motion* dimension in the Strand B planning notes below. |
| **Why pre-FM era didn't have it** | Weber et al. (2021) sampled *standing* startups from Crunchbase and encoded **structural** characteristics (what the firm *is*); they did not encode **process** characteristics (how the firm *acts to commercialise*). The dimension is invisible to a morphological method on operating-status snapshots — it surfaces only when researchers ask founders directly. [[gultekin-pinarbasi-commercialisation-ai-2025]] is the first such study in the wiki. |
| **2026 wiki evidence** | [[gultekin-pinarbasi-commercialisation-ai-2025]] — the explicit BAH-vs-Claessens contrast in §5 (BAH: linear, dev-first, marketing-as-last-stage; Claessens: marketing strategy and market-testing interleaved *before* full commercialisation), the internal-vs-external resource spectrum in §5.1, demo-as-primary-sales-tool, sales-cycle asymmetry (the **single B2C firm (LP1) is the only one with > 100k customers**; nine B2B firms have < 50 each, "one or two sales per year is good" — CV2). Also [[distribution-moat]] (Srinivas, Truell, Mohan all emphasise *acquisition motion* — self-serve vs sales-led — as load-bearing, not just channel); [[middle-layer-defensibility]] (Cursor's direct-self-serve motion is half the moat, the other half being product). |
| **Provisional characteristics** | Dev-led linear (BAH-style: build, then market) · Market-led iterative (Claessens-style: marketing strategy and market test interleaved with development) · Emergent / fuzzy (no deliberate model — empirically *modal* in the Turkish sample, plausibly modal more widely) · Network / contest-channelled (state programs, accelerators, awards as primary entry point; the Turkish AI-startup norm) · Demo-led enterprise sales (long cycle, high touch, "one or two per year") · Self-serve / B2C-direct (low-touch, mass-market, the Cursor / LP1 motion). |
| **Why it predicts value capture** | **The empirical signal in [[gultekin-pinarbasi-commercialisation-ai-2025]] is sharp**: of 10 firms, only one — LP1 — has self-serve / B2C-direct motion; it is also the **only** firm with mass-market reach (>100k customers vs <50 for the other nine). The remaining nine, regardless of their AI capability, are stuck in the long-cycle, demo-led, contest-channelled posture and have not scaled. In a single sample of 10 this is anecdotal — but it **directionally points the same way** as the [[distribution-moat]] thesis (Cursor's $50B / $2B ARR is built on self-serve motion as much as on product), and contradicts the "AI capability = commercial success" Weber-implicit reading. **If this pattern holds in a larger 2024–2026 sample, GTM motion may dominate channel geometry, and channel geometry may dominate core-AI capability, in predicting where value lands.** This is the user's central interest and the load-bearing input to the Strand B "acquisition motion" dimension below. |

## The fifth archetype Weber probably misses

Both [[ai-startup-business-archetypes-weber]] and [[weber-ai-startup-business-models]] already flag this as a 2026 vintage caveat. Repeated here for completeness so the gaps inventory is self-contained:

> *Agentic-workflow providers* — startups that orchestrate multiple foundation-model calls into multi-step business workflows. The 2021 taxonomy folds these into [[ai-charged-product-service-provider]], but the value-creation logic (action orchestration over [[context-control]] + [[autonomy-slider]]) is sufficiently different that they may deserve their own pattern.

Provisional sketch (to be validated against a 2024–2026 sample, not imposed):

| Pattern | Definition | Canonical 2026 example | Top-of-U / bottom-of-U |
|---|---|---|---|
| **Agentic-workflow provider** | Multi-step orchestration of foundation-model calls into a business workflow, sold either as a horizontal agent platform or a vertical-domain orchestrator. Distinct from [[ai-charged-product-service-provider]] in that the value comes from *action composition*, not from an embedded trained model. | Sierra (customer-service agents), Cognition / Devin (coding agent), LangGraph apps, [[vertical-ai-orchestration]] in ER&I | Top-of-U *when* paired with a [[distribution-moat]]; squeezed-middle when sold as a generic agent framework. |

The point of separating this archetype is that it has a **different value-capture logic**: agentic-workflow providers can price on outcome (closed tickets, drafted contracts, completed code reviews) rather than on seats or tokens, which makes them the most plausible site for the *outcome-based pricing* turn that [[distribution-moat]] practitioners (Sierra in particular) have started arguing for.

## First independent evidence — Gültekin et al. (2025)

[[gultekin-pinarbasi-commercialisation-ai-2025]] is a 2025 qualitative interview study of 10 Turkish AI-as-core-product startups, with interviews collected November 2022 (≈ one month before ChatGPT). It adopts Weber's four-pattern taxonomy as classifier without modification. Per-gap signal:

| Gap | Signal from Gültekin et al. (2025) |
|---|---|
| **1. Model sourcing** | **Weak indirect support.** Only 1 of 10 firms classifies as [[ai-development-facilitator]]; nine fall into [[ai-charged-product-service-provider]] or [[ai-data-analytics-provider]]. Consistent with the reading that facilitator is the most-squeezed slot. The paper does not ask the model-sourcing question. |
| **2. Autonomy level** | Nothing — sample and interview guide pre-date the copilot / agent / autonomous-worker distinction. |
| **3. Orchestration depth** | Nothing — pre-ChatGPT sample. |
| **4. Distribution architecture** | **Channel-geometry data is thin, but it surfaces a deeper miss.** The original gap-4 proposal framed distribution purely as *channel geometry* (Direct / Marketplace-listed / Platform-embedded / Wholesale-API / FM-store / OSS). The paper documents richer mechanics on the channel side (state-program contests / awards / international-body lobbying as primary entry points for Turkish AI startups) but, more importantly, makes visible a **process** dimension that the original gap 4 silently conflated with channel — see new gap 7. After splitting that off, gap 4 narrows to "channel geometry only" and remains under-evidenced for the FM-store / OSS characteristics on this Turkish, pre-ChatGPT sample. |
| **5. Data flywheel** | Nothing — "customer feedback" is dominant in the sample but as *human iterative conversation*, not as a behavioural/trajectory data asset. |
| **6. Ethics as product** | **Confirms the asymmetry.** Participants raise transparency, accountability, and social-benefit integration as **macro concerns for sustainability** but none of the ten firms sells ethics, safety, or compliance as a product surface. Independently corroborates Weber et al.'s 2021 "expected-but-did-not-find" observation — the gap is stable across two pre-2023 samples on different geographies. |
| **7. Commercialisation motion** (new) | **Strong empirical support — this is the paper's most decisive contribution to this page.** §5 of the paper contrasts BAH (1982) (linear, dev-first, marketing-as-last-stage) with Claessens (2015) (marketing strategy and market-testing **before** full commercialisation) and finds Turkish AI startups default to BAH despite none having a "deliberate approach or model for commercialization" — the process is described as *fuzzy* even by those who follow BAH. §5.1 surfaces the internal-vs-external resource spectrum. The single B2C self-serve firm (LP1) is the only one to escape the < 50-customers trap. This material does not fit anywhere in Weber's 11 structural dimensions and warrants a dimension of its own. Promoted to **gap 7** above. |

**Net effect:** strong support for **gap 7 (new)**; weak / narrow support for **gaps 1, 6**; **gap 4 split** into pure channel geometry (this dimension) and commercialisation motion (now gap 7); **gaps 2, 3, 5** unaddressed; retires no dimension; does **not** validate the agentic-workflow fifth archetype (sample has none, consistent with the November 2022 cutoff).

The page's `Status` and `Confidence` remain *working-draft* — but with the qualification that **gap 7 is now anchored in a peer-reviewed empirical study**, the first such anchor on this page. What this independent ingest *also* closes is the meta-question of whether Weber's classification has been **abandoned** by the research community: it has not; it remains the operational classifier of choice in 2024 BISE-adjacent venues. Strand A (a post-ChatGPT re-derivation) is still the binding source-side work.

## What this page is *not* doing

- It is **not** proposing a replacement taxonomy. Re-deriving the Weber clustering against a 2024–2026 Crunchbase sample requires more work than this wiki can host. The honest path is to ingest someone else's updated study (see *Next move*) and react to it.
- It is **not** authoritative. Each dimension above is wiki-internal evidence; none has been validated against a fresh post-2023 100-startup sample.
- It is **not** the [[distribution-moat]] / GTM sibling taxonomy the user has asked for. That is a separate, parallel contribution — sketched in *Next move* and to be built once the source-side ingest is done.

## Next move

Two strands of work fall out of this diagnosis.

### Strand A — Close the Weber gaps with a post-2023 source

Find and ingest **one** 2024–2026 academic or rigorous-practitioner taxonomy that has re-derived the AI-startup BM landscape post-ChatGPT. Candidate search vectors (the author hunts these, per the goal statement):

- **BISE / ECIS / ICIS / HICSS 2023–2026** — "generative AI business model taxonomy", "LLM-based business models", "AI agent business models". Weber's own journal (BISE) is the highest-yield first stop.
- **Nickerson taxonomy-method follow-ups** — German-school IS researchers (Schoormann, Hunter, Möller, etc.) have built post-ChatGPT taxonomies using the same methodology Weber et al. used.
- **Practitioner market maps** that are taxonomy-rigorous, not just slideware: Bessemer State of the Cloud 2025, Menlo Ventures State of AI in the Enterprise 2024 / 2025, Sapphire / Foundation Capital "Service-as-Software".

One ingested source → each of the six dimensions above gets either confirmed-as-published or stays-as-working-draft. The page should be revised, not rewritten, after ingest.

### Strand B — Build the DISTRIBUTION / GTM sibling taxonomy (the user's stated central want)

Parallel to Weber, **not** an extension of it. The proposed dimension structure is the working draft in the conversational planning notes (acquisition motion, entry point, channel, pricing logic, pricing counterparty, switching surface, data flywheel, FM relationship, buyer maturity served). To make this rigorous rather than speculative, **three sources of GTM-specific material** need ingestion before the morphological box can stop being a sketch:

- **Tomasz Tunguz** — outcome-based pricing essays 2024–2026 (theory.vc / tomtunguz.com). Highest signal per minute on AI pricing patterns.
- **Christoph Janz (Point Nine)** — the canonical "5 ways to build a $100M business" GTM taxonomy, updated for AI.
- **One of:** Bessemer State of the Cloud 2025 · a16z "service-as-software" essays · Sapphire Ventures Service-as-Software thesis · Foundation Capital outcome-pricing material. (Pick the most concrete; ingest one.)

After three GTM ingests:
- Create `wiki/04_concepts/gtm-business-archetypes.md` — the Weber-parallel morphological box for distribution / GTM.
- Create `outputs/gtm-taxonomy.html` — the sibling interactive to `outputs/weber-ai-startup-taxonomy.html`.

The two strands are independent. Strand B is the larger contribution and the user's main interest; Strand A is faster to close.

## See also

- [[ai-startup-business-archetypes-weber]] — the operational classifier this page diagnoses.
- [[weber-ai-startup-business-models]] — the source.
- [[business-model-portfolio]] — the **prerequisite scoping rule** introduced at the top of this page: BM (not firm) is the unit of analysis when applying Weber.
- [[westerveld-business-model-portfolio-2023]] — the source for the BMP prerequisite.
- [[gultekin-pinarbasi-commercialisation-ai-2025]] — first independent (Turkish, pre-ChatGPT) study to use Weber's classifier; weakly supports gaps 1, 4, 6.
- [[ai-charged-product-service-provider]] · [[ai-development-facilitator]] · [[ai-data-analytics-provider]] · [[ai-deep-tech-researcher]] — the four 2021 archetypes.
- [[H1_L0-L7-ladder]] · [[H2_u-curve-of-value]] · [[H3_orthogonal-axes-under-priced]] · [[H4_rl-specialization-value-pocket]] — the project hypotheses whose seller-side mirror Weber provides.
- [[distribution-moat]] · [[middle-layer-defensibility]] · [[choudary-ecosystem-teardown]] · [[ecosystem-business-archetypes]] — the source material for Strand B (GTM sibling taxonomy).
- [[autonomy-slider]] · [[vertical-ai-orchestration]] · [[context-control]] · [[continual-learning-paradigm]] — concept anchors for dimensions 2, 3, 5.
- [[open-weight-asymmetry]] · [[rl-apis]] · [[middle-layer-defensibility]] — concept anchors for dimension 1.
- [[brussels-effect-and-mirage]] · [[sovereign-ai]] · [[divergent-value-stack-optima]] — concept anchors for dimension 6.
- [[01_source-list]] — the project bibliography; the Strand A and Strand B candidates above should be reflected there once ingested.
- [[protschky-ml-monitoring-2025]] — surfaces a **candidate 8th gap dimension: monitoring sophistication / operational discipline**. Two vendors at the same Weber position with the same domain may differ dramatically in production survival depending on how deeply they internalise the C1–C5 / 17-practice surface ([[ml-monitoring]]). The 2021 instrument has no slot for this — it became visible as a discriminator only with the post-2023 expansion of agentic / production-deployed AI startups.
- [[ml-monitoring]] · [[ml-production-environment-characteristics]] · [[ml-monitoring-quality-cycle]] — operational vocabulary for the candidate 8th dimension.
