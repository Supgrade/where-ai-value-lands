---
title: Open Questions
status: draft
tags:
  - planning
  - decisions
last-updated: 2026-05-26
---

# Open Questions

Decisions still to make, ordered by how soon they need to land.

## Before research starts in earnest
- [ ] **Byline / brand wrapper** — Redacy, personal byline, or neutral "research collective" wrapper? Each implies a different distribution shape and credibility surface.
- [ ] **Co-author or expert reviewer** — invite a named external reviewer (academic, analyst, recognized operator) to lend credibility *before* publication, or after?
- [ ] **Final title** — current working title is provisional. Decide before first infographic is commissioned.

## Before drafting scenarios
- [ ] **Geographic frame** — three blocs (US / China / Europe), or two (US-China duopoly + Europe as variant), or geography as a cross-cutting lens rather than its own section?
  - **Sharpened by [[geopolitics-global-ai-divide]] / [[divergent-value-stack-optima]]:** the three-bloc frame is empirically the right structure, but its *role* in the paper now matters more than its presence. If each bloc engineers a structurally different value-stack optimum (top-heavy US, bottom-heavy China, regulatory-centric EU), then Section 5 cannot be a standalone "geography" sidebar — it must function as a **cross-cut of Section 3 (Where the margin lands)**. Realistic choices: (a) keep Section 5 as a standalone but reframe Section 3 around the bloc-specific shapes from the start; (b) dissolve Section 5 into Section 3, with each shape getting its own treatment; (c) keep both but make explicit that Sections 3 and 5 are two views of the same object.
- [ ] **Bear-case anchor** — pick one recognized skeptic voice (Marcus, Zitron, Acemoglu, etc.) to engage with seriously in-text. Decide who.
  - **Sharpened by [[bear-case-synthesis]]:** the four candidate skeptics attack different pillars — Marcus (cognitive ceiling), Acemoglu (labor/macro), GS/Covello (capex/infrastructure ROI), Zitron (product-layer circularity). They are complementary, not redundant. Realistic choices: (a) pick **Acemoglu** as the academic anchor and braid the other three around him as supporting evidence; (b) pick **Zitron** as the most direct threat to the U-curve and cite the other three as boundary conditions. Avoid forcing one "anchor" if the four pillars together are the actual frame.

## Before publishing
- [ ] **GitHub repo license** — MIT vs. CC-BY vs. CC-BY-NC. Affects forking and commercial reuse.
- [ ] **Embargo / private circulation list** — finalize the ~20–30 recipients for pre-launch.
- [ ] **Italian-language manifesto** — translate for Italian press, or English-only?

## Possibly out of scope (decide and document)
- [ ] **Embodied AI / robotics** — full chapter, paragraph, or excluded?
- [ ] **Consumer AI / chat assistants** — the paper is operator-facing, but consumer dynamics drive frontier-lab economics. How much to include?

## Labor-side incidence (added 2026-05-23 via [[massenkoff-mccrory-labor-market-impacts-2026]])
- [ ] **Acemoglu vs Anthropic on labor incidence.** Acemoglu (2024) predicted exposed workers would be low-education clerical women; Anthropic (2026) finds they are more educated, higher-paid, more white/Asian. The reconciliation depends on whether the [[theoretical-vs-observed-capability-gap]] (capability outruns deployment by ~3×) is structural or transitional. Either pick a primary frame for the paper or treat the disagreement explicitly as an open research front.
- [ ] **Is "unemployment" the wrong indicator?** [[unemployment-did-exposed-workers]] shows no detectable AI displacement in unemployment through mid-2025, but [[ai-young-worker-hiring-slowdown]] shows a ~14% drop in 22–25-year-old hiring rates in exposed occupations. If labor-side AI displacement appears as suppressed hiring rather than rising unemployment, the paper's labor-side framing needs to use the right dashboard. Decide whether to highlight entry-level hiring as the leading indicator.
- [ ] **Labor-side U vs value-stack U.** Both U-shapes exist in the wiki but on different axes. The paper needs to either present them together as a coherent two-curve story (recommended) or separate them cleanly. Decide before Section 3 is drafted.
- [ ] **Anthropic publishing labor-market research about its own deployment.** The conflict-of-interest dimension is unstated in [[massenkoff-mccrory-labor-market-impacts-2026]] but is itself an open question. Does the paper engage this directly, treat the Anthropic measure as one of several (alongside Brynjolfsson, Hampole), or ignore it?

## Collaboration model (added 2026-05-22, partially resolved 2026-05-23)
Decisions promoted from [[06_collaboration]]:
- [x] **`/contribute` skill scope** — **resolved 2026-05-23: full at v1** (all four kinds — source, daily thought, concept note, open question). Implemented in `.claude/skills/contribute/SKILL.md`.
- [ ] **Newsletter platform** — Buttondown vs. Substack vs. self-hosted Mailgun. Decision driven by *list* vs. *publication* framing.
- [x] **Contributor charter** — **resolved 2026-05-23: see [[08_contributor-charter]].** Terse + filtering posture, CONTRIBUTORS.md + per-page footer credit model.
- [ ] **Community channel choice** (T3) — LinkedIn page, X account, or Discord — pick one, defer the others. See [[06_collaboration]] for tradeoffs.
- [x] **Static site domain** — **resolved 2026-05-23: GitHub Pages default** (`supgrade.github.io/where-AI-value-lands`). Custom domain deferred until T0 produces signal.
- [x] **Quartz vs. alternatives** — **resolved 2026-05-23: Quartz.** Recommended generator for Obsidian-flavored wikis; native wikilink support; deployed via GitHub Action to GitHub Pages.
- [x] **Repo license** — **resolved 2026-05-23: MIT (code) + CC-BY-4.0 (content).** See [`LICENSE`](../../LICENSE) and [`LICENSE-content`](../../LICENSE-content).
- [x] **Repo owner + name** — **resolved 2026-05-23: `github.com/Supgrade/where-AI-value-lands`** (personal account, name includes "AI" to surface the subject at URL level).

## Analytical vocabulary (added 2026-05-22)
Decisions promoted from [[07_analytical-vocabulary]]:
- [ ] **"Archetype" as canonical term** — the project uses "business archetype" to name the 15 organizational types (agency, vertical SaaS, micro-SaaS, etc.). Is this the right term, or should the paper use "value-capture pattern," "firm type," or "go-to-market form"? Needs to be locked before the paper's glossary (Section 8) is drafted.
- [ ] **Interface layer vs. application layer** — the top two stack layers blur in practice (Cursor is both application and interface). Does the paper need a clean distinction, or is the overlap acceptable? If we collapse them, the stack has four layers, not five.
- [ ] **Multi-archetype organizations** — OpenAI is simultaneously a foundation model lab, an AI developer tool (API), and a consumer app. The paper needs a rule: do we assign a primary archetype, or treat them as multi-archetype? Answer affects how we use the archetype list in Section 6.
- [ ] **Axis 6 (Taker/Shaper/Maker) scope** — this posture typology was designed for enterprise AI buyers (WEF/Accenture). Does it apply cleanly to AI-native suppliers (e.g., Cursor is a Shaper building for developers who are Makers)? Or should Axis 6 be buyer-side only?
- [ ] **Which axes appear in the paper explicitly** — all six axes currently live in [[07_analytical-vocabulary]]. The paper probably cannot introduce all six in Section 2 without losing the reader. Candidate collapses: Axis 5 (adopter maturity) appears only in Section 5 and 6; Axis 6 (posture) is footnoted in Section 6. Decide which axes are load-bearing for the main argument vs. which are supporting evidence.

## RL-driven specialization as value pocket (added 2026-05-24 via [[H4_rl-specialization-value-pocket]])
- [ ] **Break-even contract size.** At what customer contract value (€/year, multi-year) does dedicated RL fine-tuning + harness build break even against an equivalently good base-model + retrieval + tools play? Unit economics of the boutique vendor archetype are unproven.
- [ ] **Verifiable-reward feasibility across verticals.** Which industrial domains actually admit a constructible verifiable reward in the [[rl-from-verifiable-rewards]] sense? Software is easy (tests). Energy retrofitting / industrial implant intervention proposals — the author's worked example — have month-long noisy feedback loops and contestable attribution. Open question whether [[value-functions-as-algorithmic-emotion]]-class intermediate signals close the gap.
- [ ] **Open-weight vs closed-frontier base model choice.** The single most consequential vendor decision in this hypothesis ([[rl-open-vs-closed-source]], [[rl-apis]]): owning the weights enables [[continual-learning-paradigm]]-style compounding moat inside one customer; renting them via OpenAI RFT / Anthropic custom models gives better base capability but disposable IP. Both paths exist; the economics under each are not yet legible.
- [ ] **Boutique vendor vs frontier-lab tuning API.** Does a startup that does domain RL fine-tuning as a service survive the moment frontier labs ship verticalised fine-tuning at scale? Closest precedent: vertical AI orchestrators in industrials ([[vertical-ai-orchestration]], [[deloitte-ai-dossier-eri]]) — but the model layer was rarely the moat there.
- [ ] **Customer data exclusivity.** Will industrial / SME customers — especially the Italian family-business archetype — agree to let proprietary process know-how flow into a vendor's training data? If not, the cross-customer amortisation that the vendor's unit economics need is contractually forbidden.
- [ ] **Where on the ladder does H4 sit.** Tentatively L3–L5 substrate (agent + harness + RL-tuned model on rented or owned compute), Phase 3+ buyer maturity ([[enterprise-adoption-ladder]]), [[taker-shaper-maker]] Maker posture at vertical scale, [[oecd-sme-adopter-taxonomy]] Champion-adjacent customer. Confirm or revise as evidence accumulates.

## Operator-side hypothesis and P2 paper-portfolio (added 2026-05-26 via [[H5_ai-as-operational-not-product]] and [[09_paper-portfolio]])

The operator-side reframe of 2026-05-26 has spawned a sibling paper (P2 — *What to Start Now*) and a new working hypothesis (H5). See [[09_paper-portfolio]] for the portfolio decision. Open questions:

- **[P2] What is the operator-builder's capital threshold for Track B?** H5 claims two tracks (VC-megafund race-in vs operator). The boundary needs a load-bearing variable: capital threshold ($X Series A), revenue threshold ($Y ARR), or distribution-prior threshold (audience of size Z). The three correlate but are not identical.
- **[P2] Does the "Cursor for local SEO" archetype exist in 2026?** Bear case for H5: small-vertical AI-orchestration products at sub-Series-B scale could constitute a viable third track between A and B. Empirical search across 3–4 verticals (local SEO, dental marketing, restaurant ops, real-estate listings) needed before H5 hardens.
- **[P2] What is the right Weber-classifier home for the operator-builder?** None of the four 2021 Weber patterns fits — operator-builders are *not AI startups* in Weber's seller-side sense. This becomes the next gap dimension on [[weber-taxonomy-2026-gaps]].
- **[P2] How does H5 interact with [[H4_rl-specialization-value-pocket]]?** H4 (seller-side) and H5 (operator-side) — are H4 vendors *suppliers* to H5 operator-builders, or are they competitors for the same surplus? Decide which framing the paper uses.
- **[P2] Italian-market or G7?** [[sme-ai-adoption-gap]] / [[g7-sme-ai-policy-pluralism]] suggest the operator-track is structurally harder in Italy than in the US or UK. Is H5 a global hypothesis or specifically guidance for the author's home market?
- **[P2] Where does P2 live commercially?** P1 is free PDF + GitHub-Pages wiki. P2 might want a different distribution surface (Substack, cohort-based course, Italian-language landing page). Decide before P1 ships so the P2 surface can be staged.
- **[P2] Italian-language P2 vs English-only?** The operator-builder reader the author has most empathy for is Italian. Is the natural primary language for P2 Italian (with English secondary), or the same English-primary stance as P1?

## Industrial-AI rollup of captive suppliers (added 2026-05-26 via [[H6_industrial-ai-rollup-captive-suppliers]])

H6 is the rollup variant of H5 — a holding company acquiring captive-supplier SMEs in a single industrial customer's supply chain and installing the [[ai-first-company-loop]] in each, replacing the management layer while preserving production. The thesis is speculative; the four sub-questions below are the ones the author flagged in the 2026-05-26 daily-thought reflection.

- **[P2] Why are manufacturers not AI-first — newness or structural barrier?** The wiki's read ([[ai-productivity-firm-level]], [[ai-skill-shortage-as-diffusion-bottleneck]], [[sme-connectivity-divide]], [[sme-ai-finance-gap]], [[oecd-sme-enabler-quartet]]) is **structural**, not newness — AI is a multiplier of pre-existing complementary capital, and most SMEs do not have the complementary capital to multiply. Confirm with primary Italian-district data (ISTAT, Cerved) and decide whether the paper presents this as a settled finding or as a live debate.
- **[P2] Will it be a natural transformation with time, or will the gap widen?** [[sme-ai-adoption-gap]] (40% large / 11.9% small OECD-wide 2024) is *widening* between 2020 and 2024, not closing. [[sme-broadband-firm-size-gap]] has been flat at ~25–28 pp for five years. McElheran's J-curve says even adopters take years to capture the surplus. The empirical bet behind H6 is *not* a bet on time alone — it is a bet that targeted acquisition + deliberate rebuild beats organic diffusion.
- **[P2] Can acquisition accelerate it, and at what unit economics?** This is the question the wiki has *almost no material on*. The H6 thesis depends on (a) the management layer being a 8–20% addressable cost share, (b) the dominant-customer relationship surviving ownership change, (c) the loop-build cost amortising across 5+ acquired suppliers in similar positions, (d) Italian regulatory and labour-relations exposure not making the management-layer reorganisation prohibitive at scale. Each is an empirical sub-question.
- **[P2] Are AI-first manufacturers actually more competitive?** [[ai-productivity-firm-level]] reports labor-productivity premia of >4% (sometimes >15%) for AI users within cohort across G7 — but most of the premium is *not* AI-caused: it reflects pre-existing competitiveness. The AI-attributable share for SMEs specifically is smaller. The H6 bet is that a *deliberate* rebuild (not organic adoption) captures the surplus organic adoption cannot, by installing the complementary capital across all five layers of the [[ai-first-company-loop]] simultaneously.
- **[P2] Is H6 structurally distinct from H5, or H5 with leverage?** H5 is one operator-builder running an AI-native firm; H6 is N operator-builder firms acquired and rolled up. Mechanically H6 is a multi-firm H5; strategically the questions are different (M&A pipeline, post-acquisition integration, loop portability, relational risk at ownership change). Decide whether the paper treats them as separate hypotheses or as a single hypothesis with single-firm and rollup variants.

## AI-first-company operating model and software-as-temporary-artefacts (added 2026-05-26 via [[ai-first-company-loop]] and [[software-as-temporary-artefacts]])

- **[P1+P2] Does "software as temporary artefacts" tighten H2 into an L?** The mechanism predicts that the buyer-side market for finished middle-layer workflow products shrinks as AI-first firms route tool needs through in-house synthesis. The surviving middle is *primitives for synthesis* (LangGraph, RL APIs, eval tooling, frameworks). If empirically true at scale, [[H2_u-curve-of-value]]'s middle is sharper than the existing wiki frames it — not just squeezed, partly abolished. Decide whether the paper presents this as a sharpening of H2 or as a separate sub-hypothesis.
- **[P2] Is gate design (Layer 4 of the [[ai-first-company-loop]]) a defensibility surface for operator-builder firms?** The page argues yes — gate-calibration data is accumulated, transferable, and durably valuable; firms that learn to gate well make fewer reputation-damaging mistakes than firms that don't. Empirical work needed: can we point to any firm in 2026 whose operational edge is plausibly gate-design quality rather than model or distribution quality?

## Business archetype taxonomy (added 2026-05-22)
The taxonomy emerged from the daily thought of 2026-05-22. Decisions needed:
- [ ] **Completeness** — are there archetypes missing from the current 15? Candidates: AI research lab (non-commercial, e.g., DeepMind inside Google), government / public-sector AI deployer, AI-enabled hardware company (e.g., Humane, Rabbit), embodied AI / robotics startup.
- [ ] **North Italian / SME archetype gap** — the taxonomy is currently US-stack-centric. The author's home market (North Italy, traditional SME industry) is an AI adopter, not an AI supplier. A 16th archetype may be needed: "traditional-industry AI integrator" — the type of firm the author is, and the type of firm reading the paper.
- [ ] **Archetype-to-U-curve mapping** — should the mapping of archetypes to H2 positions (top / squeezed middle / bottom) become a standalone wiki page or live inside [[H2_u-curve-of-value]]? It is currently a table in the annotated daily thought only.
