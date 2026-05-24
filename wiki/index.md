---
title: Wiki Index
status: living
tags:
  - index
last-updated: 2026-05-24
---

# Wiki Index
<!-- Last edit: 2026-05-24 — added H4 hypothesis (RL-driven specialization as value pocket) + new `tech/` reference subfolder with 7 RL explainer pages (rlhf, rlaif, rl-from-verifiable-rewards, rl-data-preparation, rl-testing-validation, rl-open-vs-closed-source, rl-apis). Patched H1, H2, post-scaling-research-pivot, value-functions-as-algorithmic-emotion, agentic-scaling-law, continual-learning-paradigm, scaling-wall with H4 forward references.

Previous: 2026-05-24 — ingested Sutskever "Age of Research" interview synthesis. Added 4 new concept pages (post-scaling-research-pivot, continual-learning-paradigm, eval-real-world-gap, value-functions-as-algorithmic-emotion) + 1 source (sutskever-age-of-research). Patched scaling-wall, agentic-scaling-law, karpathy-software-3, world-models-jepa, autonomy-slider with cross-source synthesis. -->


Catalog of every page in the wiki, one-line summary each. Read first when answering any question. Updated on every ingest.

## Paper planning — `01_paper-planning/`
- [[00_initial-brief]] — one-line frame: a secondary-research white paper on where AI value lands, for capital-rich operators.
- [[01_audience]] — who reads it, what they should be able to do after.
- [[02_purpose-and-justification]] — why this paper, why secondary research is the right vehicle.
- [[03_structure]] — proposed ~20-page structure, theoretical + practical halves.
- [[04_distribution]] — channels, derivatives, timing.
- [[05_open-questions]] — decisions still to make before research, drafting, publishing.
- [[06_collaboration]] — how others contribute to the wiki while it's in flight; tiered surfaces from PRs to a chat-with-the-wiki app. Updated 2026-05-22: repo structure, Quartz static site spec, full `/contribute` skill specification. T0 + T1 shipped 2026-05-23.
- [[07_analytical-vocabulary]] — canonical glossary of all analytical axes (stack layer, autonomy level, business archetype, curve position, adopter maturity, strategic posture); vocabulary quick-reference table; sample coordinates.
- [[08_contributor-charter]] — high-bar standard for what counts as a good contribution; terse + filtering posture; out-of-scope list; evidentiary standards; per-page credit format. Operationalises [[06_collaboration]] §T1.

## Hypotheses — `02_hypothesis/`
- [[H1_L0-L7-ladder]] — agentic AI stack as a ladder of substrate ownership and autonomy.
- [[H2_u-curve-of-value]] — value concentrates at the top and bottom of the stack, evaporates in the middle. **Top now empirically validated (Cursor, Windsurf). Bottom uncertain. U-shape may be US-stack artifact.**
- [[H3_orthogonal-axes-under-priced]] — *deferred stub.* Claims axes that cut across L0–L7 (autonomy, deployment topology, buyer maturity) are more predictive of where value lands than ladder position alone. Premise authored in kickoff; evidence not yet developed.
- [[H4_rl-specialization-value-pocket]] — **new 2026-05-24.** RL-driven domain-specific fine-tuning of base models — sold to a single industrial customer or a narrow vertical as a *proprietary operational asset* — may be a real value pocket as pre-training saturates. Technical premise grounded in [[post-scaling-research-pivot]] + [[agentic-scaling-law]]; business case unvalidated. The thing sold is closer to AlphaFold-class domain specialization than to generic image/text-to-3D fine-tuning.

## Search — `03_search/`
- [[01_source-list]] — prioritized bibliography organized by paper section.
- [[02_deep-research-prompts]] — agent-ready research briefs.
- [[03_keyword-search-strings]] — boolean search strings.
- [[suggested-sources]] — candidate sources proposed by `/discover` for author review.

## Concepts — `04_concepts/`
- [[scaling-wall]] — the architectural ceiling on next-token-prediction reasoning.
- [[task-based-framework]] — Hulten's theorem applied to AI; the <0.71% TFP ceiling.
- [[circular-ai-economy]] — the financial ouroboros from VC → apps → models → hyperscalers.
- [[ai-capex-cycle]] — boom-then-bust pattern in hyperscaler training capex → inference demand → potential overcapacity; bear-case mechanism.
- [[capital-labor-divergence]] — how AI directs surplus toward capital and away from labor.
- [[displacement]] — the substitution side of AI's labor effect, distinct from augmentation; measurement debate (theoretical vs observed exposure) and the unemployment-invisibility / hiring-suppression evidence.
- [[value-capture]] — the share of generated surplus that a firm or stack position actually retains; the value-creation-vs-capture wedge.
- [[application-layer]] — L0–L2 territory where end-user AI products live; the layer the top-of-U thesis depends on and the circular-economy thesis threatens.
- [[software-3-paradigm]] — Karpathy's 1.0/2.0/3.0 framing of computing.
- [[autonomy-slider]] — continuous human↔agent control spectrum; "Iron Man suit" partial-autonomy default.
- [[llm-as-operating-system]] — LLM as CPU, context window as RAM; 1960s-time-sharing analogy.
- [[agentic-scaling-law]] — Huang's test-time-compute axis; the strongest counter to [[scaling-wall]].
- [[democratization-of-programming]] — natural language as programming language; "vibe coding".
- [[divergent-value-stack-optima]] — the U-curve is not universal; each geopolitical bloc engineers a different optimum (top-heavy / bottom-heavy / regulatory-centric).
- [[digital-empires-tripartite]] — Bradford's three governance models (US market / China state / EU rights), each exporting a different form of power.
- [[diffusion-vs-innovation]] — Ding's GPT-marathon thesis: economic power transitions are decided by diffusion capacity, not invention.
- [[open-weight-asymmetry]] — China's strategic commoditization of the foundation-model layer; the "Android of the AI era" play.
- [[brussels-effect-and-mirage]] — EU regulatory imperialism and its structural limits in high-risk state-controlled domains.
- [[sovereign-ai]] — the European hardware play; AI factories, sovereignty traps.
- [[middle-layer-defensibility]] — the empirical case that distribution-embedded platforms (Cursor, Windsurf, LangGraph) survive the "middle dies" thesis.
- [[distribution-moat]] — owning the direct user relationship as the decisive AI competitive variable (Srinivas, Truell, Mohan).
- [[context-control]] — Chase's insight: LLMs fail due to poor context supply, not poor intelligence; orchestration = context management infrastructure.
- [[world-models-jepa]] — LeCun's JEPA architecture; proposed successor to autoregressive LLMs; next paradigm moat.
- [[jevons-paradox-ai]] — efficiency gains in AI inference expand total compute demand rather than contracting it.
- [[scaling-gap]] — the 74% / 16% empirical artifact (BCG / Accenture): most firms cannot scale AI past pilots; interpretation-flexible evidence for managerial / bear / middle-dies readings.
- [[enterprise-adoption-ladder]] — WEF / Accenture five-phase organizational maturity ladder; buyer-side parallel to L0–L7.
- [[foundational-enablers]] — WEF / Accenture's six-factor framework (ecosystem, trust, self-governance, talent, cybersecurity, digital core) claimed to close the scaling gap.
- [[agentic-revolution]] — analytical→agentic transition; action-orchestration replaces prediction as the value-capture unit.
- [[vertical-ai-orchestration]] — multi-agent industrial-domain orchestrators as the durable AI moat in asset-heavy verticals (non-software instantiation of [[middle-layer-defensibility]]).
- [[synthetic-data-generation]] — generative methodology for dark-data verticals; partially relocates the operational-data moat but inherits a version of [[scaling-wall]].
- [[ai-factory-huang]] — Huang's framing of the AI-era datacenter as a tokens-per-second-per-watt manufacturing unit; bottom-of-U mechanism, federated across central / regional / edge.
- [[digital-core]] — buyer-perspective 3-layer enterprise stack (apps / data backbone / infra); architectural precondition the bull-managerial frame treats as load-bearing.
- [[taker-shaper-maker]] — WEF strategic-adoption typology (rent / customize / train the model); third orthogonal axis to substrate ladder and maturity ladder.
- [[fusion-skills]] — workforce-capability frame; humans + AI as unit of analysis; labor-side counterpart of the autonomy slider.
- [[sme-ai-adoption-gap]] — the structural firm-size AI adoption gap (40% large / 11.9% small OECD-wide 2024); holds across G7 / applications / sectors / controls.
- [[oecd-sme-adopter-taxonomy]] — OECD four-quadrant SME adopter taxonomy (Novices / Optimisers / Explorers / Champions); two axes (complexity × scope) + digital-maturity diagonal.
- [[sectoral-ai-diffusion-pattern]] — ICT-led, traditional-sector lagging diffusion pattern; ICT ~45% vs Construction 7.2% OECD-wide 2024.
- [[ai-productivity-firm-level]] — firm-level AI productivity premium evidence and methodological caveats; premium shrinks once complementary digital capital is controlled.
- [[oecd-sme-enabler-quartet]] — OECD four-enabler frame (connectivity, AI-enabling inputs, skills, finance); SME-specific cousin of [[foundational-enablers]].
- [[ai-skill-shortage-as-diffusion-bottleneck]] — skills as the most consistently cited SME AI-adoption barrier; 50%+ of SMEs in four G7 countries.
- [[sme-ai-finance-gap]] — credit-condition mismatch for multi-year AI integration; short-term lending shift 2022–2024.
- [[sme-connectivity-divide]] — persistent ~27 pp small-vs-large broadband gap; widening urban-rural mobile gap (5 → 45 Mbps, 2019–2024).
- [[sme-policy-pathway-novice-to-champion]] — stage-conditional policy matrix mapping OECD adopter stages to enabler interventions.
- [[g7-sme-ai-policy-pluralism]] — four operationally distinct G7 SME-AI policy optima (market-led / state-coordinated industrial / state-coordinated soft-law / federal-regional); convergence on instruments alongside divergent framing.
- [[observed-exposure-measure]] — Massenkoff–McCrory usage-weighted occupation-level AI displacement-risk measure; theoretical capability + realized Claude work-context usage.
- [[theoretical-vs-observed-capability-gap]] — Claude work-context usage covers ~33% of Computer & Math tasks vs ~94% theoretical; "the red area will grow to cover the blue" diffusion lag at occupation granularity.
- [[exposed-worker-demographics]] — AI-exposed workers are older, female, more white/Asian, more educated (4× graduate-degree share), 47% higher-paid; partial contradiction of the Acemoglu wage-incidence prediction.
- [[ai-young-worker-hiring-slowdown]] — the only detectable AI labor-side signal: ~14% drop in 22–25-year-old job-start rate in exposed occupations post-ChatGPT; "canary in the coal mine."
- [[eloundou-beta-exposure]] — theoretical LLM task-exposure scoring (β=0/0.5/1) used as input to most modern exposure measures; 97% of Claude work-context usage falls on β≥0.5 tasks.
- [[ecosystem-business-archetypes]] — Choudary's four-archetype taxonomy (Aggregator / Integrator / Infrastructure / Capability) for horizontal business models; the cleanest off-the-shelf sub-vocabulary for Axis 3.
- [[vertical-to-horizontal-unbundling]] — structural thesis: falling transaction costs unbundle vertical chains into modular horizontal ecosystems where value concentrates in archetype positions.
- [[cross-archetype-confusion]] — strategic failure mode of benchmarking the wrong ecosystem archetype (B2B firms aping BigTech aggregators).
- [[post-scaling-research-pivot]] — Sutskever's "Age of Research" reframe; pre-training data exhausted, algorithmic research replaces brute-force scaling as the binding leap.
- [[continual-learning-paradigm]] — sample-efficient on-the-job learning as the proposed successor to static pre-trained models; the algorithmic answer to anterograde amnesia.
- [[eval-real-world-gap]] — superhuman benchmarks coexisting with brittle real-world performance; "human reward hacking" by researchers optimising for evals.
- [[value-functions-as-algorithmic-emotion]] — Sutskever's RL proposal: biological emotions as the proof-of-concept for cheap robust intermediate trajectory signals during long-horizon learning.

## Sources — `05_sources/`
- [[bear-case-synthesis]] — internal synthesis of the four-pillar bear case.
- [[acemoglu-simple-macroeconomics]] — NBER WP 32487 (stub via synthesis).
- [[goldman-sachs-too-much-spend]] — *Top of Mind* #129, June 2024 (stub via synthesis).
- [[marcus-world-models-failure]] — Marcus on AI, June 2025 (stub via synthesis).
- [[zitron-circular-economics]] — *Better Offline* / wheresyoured.at (stub via synthesis).
- [[karpathy-software-3]] — Karpathy's *Software Is Changing (Again)* lecture (with Huang + Steinberger synthesis); bull-frame paradigm document.
- [[geopolitics-global-ai-divide]] — internal synthesis of the tripartite AI governance architecture (US / China / EU) and the divergent value-stack optima each engineers.
- [[bradford-digital-empires]] — *Digital Empires* (2023) and the tripartite governance frame (stub via synthesis).
- [[ding-diffusion-marathon]] — Ding's RAND + FPRI work on GPT diffusion and China's diffusion deficit (stub via synthesis).
- [[lee-01ai-pivot]] — Kai-Fu Lee on 01.AI's B2B pivot and open-source-for-Global-South thesis (stub via synthesis).
- [[where-value-lands-2026]] — 2026 synthesis of the technical frontier; empirical validation of distribution moats (Cursor, Windsurf, Perplexity, LangGraph); LeCun JEPA; DeepSeek commoditization; Jevons Paradox.
- [[wef-ai-in-action-2025]] — WEF / Accenture flagship white paper (Jan 2025); canonical bull-multilateral synthesis of enterprise AI adoption, foundational enablers, and the $7.6–17.9T projection; surfaces the 74% [[scaling-gap]].
- [[deloitte-ai-dossier-eri]] — vertical-industrial deep-dive on Energy, Resources & Industrials; 12 ER&I AI use cases; introduces the [[agentic-revolution]], [[vertical-ai-orchestration]], [[synthetic-data-generation]], and [[ai-factory-huang]] concepts (stub-via-synthesis of the Deloitte AI Dossier integrated with WEF and Karpathy/Huang material).
- [[non-tech-digital-core-synthesis]] — secondary LLM-generated executive digest condensing WEF + Karpathy + Huang into a non-tech-enterprise prescription; elevates [[digital-core]], [[taker-shaper-maker]], [[fusion-skills]] to dedicated concept pages.
- [[oecd-sme-ai-adoption-2025]] — OECD discussion paper for the G7 (2025); canonical official-multilateral document on SME-specific AI diffusion; four-enabler quartet, four-stage adopter taxonomy, G7 country policy profiles; load-bearing for [[diffusion-vs-innovation]] and the bottom-right of [[H2_u-curve-of-value]].
- [[massenkoff-mccrory-labor-market-impacts-2026]] — Anthropic internal study (March 2026); introduces [[observed-exposure-measure]]; finds no detectable AI unemployment effect through 2025 but tentative entry-level hiring slowdown for 22–25-year-olds; partial contradiction of Acemoglu's incidence prediction; bull-frame internal datapoint.
- [[choudary-ecosystem-teardown]] — Sangeet Paul Choudary 2022 newsletter teardown; pre-AI canonical statement of the four-archetype ecosystem-business-model taxonomy; structural precursor to [[H2_u-curve-of-value]] and to [[distribution-moat]].
- [[sutskever-age-of-research]] — Sutskever (2026) declares the Age of Scaling over and the Age of Research begun; primary-architect concession of the empirical scaling wall; proposes continual learning + value functions + a "straight-shot" deployment posture.

## Ideas — `06_ideas/`
Concrete use-case patterns: how AI is *actually being used* on the ground. Pattern-level pages (not theoretical frameworks) — what the AI does, who's deploying it, what's been measured, what concepts it connects to.

### ER&I (Energy, Resources & Industrials) — via [[deloitte-ai-dossier-eri]]
- [[predictive-maintenance]] — multimodal sensors → failure prediction + auto-generated work orders. **SBB: 60% faster inspections.**
- [[autonomous-drone-inspection]] — drone-in-a-box + BVLOS + thermal/visual/LiDAR fusion for linear infrastructure. **>50% cycle-time reduction.**
- [[drone-footage-smart-summaries]] — NLP layer on top of drone video; queryable methane-leak detection.
- [[autonomous-field-operations]] — multi-agent orchestrator for offshore/remote ops. **Aker BP "Yggdrasil" — periodically unmanned platforms.**
- [[hydrocarbon-reservoir-exploration]] — AI denoises seismic + synthetic reservoir simulation → fewer dry wells.
- [[minerals-processing-optimization]] — ore characterization + chemical-process simulation; the canonical OOD-failure example.
- [[ai-materials-science]] — virtual screening of chemical compositions. **Merck: €100k+ saved per testing campaign.**
- [[grid-optimization]] — dispatch + market trading + consumer demand-response on stressed renewable grids.
- [[supply-chain-digital-twin]] — what-if simulation + tier-n risk + NL query. **BMW: 30–40% productivity gain.**
- [[intelligent-commercial-operations]] — forecasting + pricing + bid-drafting + margin-monitoring agents replace spreadsheet ops.
- [[generative-site-design]] — generative AI proposes annotated industrial site blueprints from constraints.
- [[vr-ohs-training]] — personalized AI+VR hazard simulations from real incident reports.

### SME adoption patterns — via [[oecd-sme-ai-adoption-2025]]
- [[sme-novice-off-the-shelf-llm]] — embedded LLMs for peripheral tasks (SEO, copywriting). **SF coffee roaster, Hamburg photographer.**
- [[sme-optimiser-cross-functional-stack]] — multiple off-the-shelf tools, cross-functional. **Sèvres bakery, Brescia bag manufacturer.**
- [[sme-explorer-custom-agent]] — custom/frontier model in narrow scope. **Tokyo B2B with multilingual sales-mediation agents.**
- [[sme-champion-vertical-ai]] — custom/frontier across functions. **Calgary healthcare-tech, Cambridge biotech.**

## Tech — `tech/`
Reference layer: short technical explainer pages grounding the analytical concepts and hypotheses in real algorithmic detail. New 2026-05-24 to support [[H4_rl-specialization-value-pocket]]. See [[README]] for the catalog.

- [[rlhf]] — Reinforcement Learning from Human Feedback. SFT → reward model → PPO/DPO. The production recipe behind aligned chat models.
- [[rlaif]] — Reinforcement Learning from AI Feedback. Replace the human labeler with a strong model labeler (Constitutional AI).
- [[rl-from-verifiable-rewards]] — RLVR. Deterministic checker as reward (unit tests, theorem provers, simulators). The mechanism behind reasoning-tuned models (o1, R1).
- [[rl-data-preparation]] — trajectory collection, preference labeling, deduplication, contamination filtering, reward shaping.
- [[rl-testing-validation]] — held-out evals, reward-hacking probes, distribution-shift checks, real-world A/B; closes (or fails to close) [[eval-real-world-gap]].
- [[rl-open-vs-closed-source]] — open algorithms (PPO, DPO, GRPO) and frameworks (TRL, OpenRLHF, verl) vs closed recipes inside frontier labs; strategic implications for moat location.
- [[rl-apis]] — the commercial fine-tuning surface: OpenAI RFT, Anthropic custom models, Google Vertex tuning, Together, Fireworks, Predibase, Modal-hosted TRL.

## Data — `data/`
Citable units of evidence: statistics, tables, figures, images. Each numeric claim in a concept page should resolve to one of these. See [[README]] for conventions.

### Infrastructure evolution
- [[evolution-of-it-infrastructure]] — McKinsey-framed H2M→M2M shift from CLI/bare-metal (2000) through IaC/NLP (2020s) to intent-based autonomous infrastructure (2030 vision).

### Bear-case ceilings
- [[task-based-tfp-ceiling]] — Acemoglu's <0.71% 10-year US TFP ceiling.
- [[ai-task-exposure-decomposition]] — the 19.9% / 23% / 4.6% / 15.4% decomposition behind the ceiling.

### Capex and unit economics
- [[hyperscaler-capex-trajectory]] — ~$800B booked + ~$1.7T planned 2026–2027.
- [[hyperscaler-customer-concentration]] — 70–80% of MSFT/AWS AI capacity → OpenAI + Anthropic.
- [[perplexity-burn-ratio]] — ~164% of revenue to compute (2024).

### Adoption and bull projections
- [[scaling-gap-74-16]] — the BCG / Accenture 74% / 16% scaling gap.
- [[wef-7-6t-projection]] — Accenture's $7.6–17.9T by 2038.
- [[global-ai-spend-632b]] — IDC's $632B by 2028 (29% CAGR).
- [[ai-leader-productivity-delta]] — leaders' 4.5% / 2.4× / 15% outperformance.

### Distribution-moat empirical anchors
- [[cursor-50b-valuation]] — $50B valuation, $2B ARR.
- [[windsurf-acquisition-battle]] — $3B OpenAI bid / $2.4B Google reverse-acquihire.

### Vertical-industrial deltas
- [[eri-use-case-deltas]] — SBB 60% / BMW 30–40% / Merck €100k / drone >50%.

### Labor-side AI exposure (Massenkoff–McCrory, 2026)
- [[most-exposed-occupations]] — Top-10 list: computer programmers (74.5%), customer service reps (70.1%), data entry keyers (67.1%), medical record specialists, market research analysts.
- [[ai-exposure-vs-bls-growth]] — Slope −6.07 (SE 1.32), R² 0.027 — 10pp more coverage → 0.6pp less BLS projected growth; theoretical β alone does *not* correlate.
- [[high-vs-low-exposure-worker-characteristics]] — CPS Aug–Oct 2022: top-quartile-exposed vs zero-exposure demographic/wage/education table.
- [[unemployment-did-exposed-workers]] — DiD pooled post-ChatGPT +0.0020 (SE 0.0019) — no detectable unemployment effect.
- [[young-worker-hiring-did]] — DiD pooled post-ChatGPT −14.3% (SE 7.2) — tentative entry-level hiring suppression for 22–25-year-olds.

### SME diffusion (OECD G7, 2025)
- [[sme-vs-large-firm-ai-gap]] — 40% large / 20.4% medium / 11.9% small OECD-wide 2024.
- [[oecd-ai-adoption-trajectory-2020-2024]] — 5.6% → 14% OECD-wide AI adoption.
- [[oecd-sectoral-ai-adoption-2024]] — ICT 45% / Professional services 26% / Construction 7.2%.
- [[oecd-g7-productivity-gain-projection]] — 0.2–1.3 pp annual labour-productivity gain across G7 over next decade.
- [[sme-broadband-firm-size-gap]] — persistent ~27.5 pp small-vs-large high-speed broadband gap.
- [[ai-skill-shortage-sme-share]] — skill-shortage shares and skill-importance shift across G7.
- [[g7-sme-large-firm-ai-adoption-ratio]] — Italy 4.7× (widest) to US 1.65× (narrowest).

## Glossary — `Glossary/`
- [[inference]] — glossary stub.

## Thoughts — `wiki/thoughts/`
- [[archetypes-vocabulary-personal-frame]] — reflection on 2026-05-22: business archetype taxonomy, analytical vocabulary, personal research frame.
