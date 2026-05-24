# Log

Append-only chronological record of wiki operations. Entry format: `## [YYYY-MM-DD] {ingest|ask|lint|discover|edit} | Title`.

## [2026-05-24] edit | Site welcome callout + graph excludes index/log

- `wiki/index.md` — added `> [!abstract]` callout (research one-liner + author: student/operator, Veneto).
- `quartz-config/quartz.layout.ts` — new; `excludeSlugs: ["index", "log"]` on local + global graph; breadcrumbs hidden on home; footer → repo.
- `quartz-config/components/scripts/graph.inline.ts` — patched upstream graph script to honour `excludeSlugs`.
- `.github/workflows/deploy.yml` — copies layout + graph script on build.

## [2026-05-24] edit | Glossary — inference and taxonomy entries

- Populated `wiki/Glossary/inference.md` (previously an empty stub): definition, four inference variants (cloud, on-premise, test-time, batch), role in bottom-of-U economics and Jevons dynamics, links to [[ai-factory-huang]], [[jevons-paradox-ai]], [[agentic-scaling-law]], [[scaling-wall]], [[sovereign-ai]], [[rl-apis]], [[H2_u-curve-of-value]], [[H1_L0-L7-ladder]].
- Created `wiki/Glossary/taxonomy.md`: MECE-type definition, distinction table (taxonomy vs. ladder vs. axis vs. framework vs. curve), inventory of all six project taxonomies, capitalization rule for named types. Links to [[07_analytical-vocabulary]], [[ecosystem-business-archetypes]], [[oecd-sme-adopter-taxonomy]], [[taker-shaper-maker]], [[digital-empires-tripartite]], [[g7-sme-ai-policy-pluralism]].
- Updated `wiki/index.md` Glossary section with descriptive one-liners for both entries.

## [2026-05-24] edit | New hypothesis H4 + tech/ reference subfolder (RL-driven specialization)

- **Trigger:** author-proposed working hypothesis — pre-training has saturated, RL (especially [[rl-from-verifiable-rewards]]) is the still-scaling axis, and the entrepreneurial opportunity is domain-specific RL fine-tuning of base models sold as a *proprietary operational asset* to a single industrial customer or narrow vertical. Worked example: industrial-implant intervention-proposal model trained on a company's own (state, proposal, outcome) history. Technical premise grounded; business case explicitly under-validated.
- **New hypothesis page:** `wiki/02_hypothesis/H4_rl-specialization-value-pocket.md` — status `working-hypothesis`, confidence `low-to-medium (technically grounded above; business case unvalidated)`. Sections cover claim, technical premise, business premise, the worked industrial-implant example, six bear arguments, four falsifiability conditions, six open research questions.
- **New subfolder `wiki/tech/`** introduced as a NEW page kind: short didactic technical-reference pages (200–500 words each) grounding the analytical layer in algorithmic detail. Seven content pages + a README:
  - `tech/README.md` — catalog + framing.
  - `tech/rlhf.md` — Reinforcement Learning from Human Feedback (InstructGPT recipe; SFT → RM → PPO/DPO).
  - `tech/rlaif.md` — Reinforcement Learning from AI Feedback (Constitutional AI; judge-model labelers).
  - `tech/rl-from-verifiable-rewards.md` — RLVR (o1/R1/AlphaProof recipe; the technical engine under H4).
  - `tech/rl-data-preparation.md` — trajectory collection, dedup, contamination filtering, reward shaping.
  - `tech/rl-testing-validation.md` — held-out evals, reward-hacking probes, real-world A/B; closes (or fails to close) [[eval-real-world-gap]].
  - `tech/rl-open-vs-closed-source.md` — algorithms commoditised, recipes + data + value-function research stay closed; mirrors [[open-weight-asymmetry]] one floor down.
  - `tech/rl-apis.md` — frontier-lab tuning (OpenAI RFT, Anthropic custom, Vertex) vs open-weight tuning (Together, Fireworks, Predibase, Modal/Replicate/RunPod, Lamini, Anyscale); the most consequential vendor unit-economics choice in H4.
- **Patches to existing pages** (forward + reverse link integrity):
  - `wiki/index.md` — H4 added to Hypotheses catalog; new `## Tech` section listing the 7 pages.
  - `wiki/01_paper-planning/05_open-questions.md` — new "RL-driven specialization as value pocket" section with six open questions (break-even contract size, verifiable-reward feasibility across verticals, open-weight vs closed-frontier base choice, boutique vendor vs frontier-lab fine-tuning API, customer data exclusivity, position on H1 ladder).
  - `wiki/02_hypothesis/H1_L0-L7-ladder.md` — H4 added to Related (L3–L5 substrate, Maker posture at vertical scale).
  - `wiki/02_hypothesis/H2_u-curve-of-value.md` — H4 added to Related (vertical-scale top-of-U via RL specialization).
  - `wiki/04_concepts/post-scaling-research-pivot.md` — H4 added to Related (load-bearing premise).
  - `wiki/04_concepts/value-functions-as-algorithmic-emotion.md` — H4 + four tech pages added (value-function tractability is the gating constraint).
  - `wiki/04_concepts/agentic-scaling-law.md` — H4 + [[rl-from-verifiable-rewards]] added.
  - `wiki/04_concepts/continual-learning-paradigm.md` — H4 + three tech pages added (continual learning is the single-customer compounding moat).
  - `wiki/04_concepts/scaling-wall.md` — H4 added (entrepreneurial wager on the wall + bear pressure if wall generalises to RL).
- **Status note.** H4 is the first hypothesis page with explicit technical-layer scaffolding underneath it. Confidence is asymmetric: higher that RL specialization will matter more in the next 18 months, much lower that boutique RL-fine-tuning vendors capture the surplus (vs frontier-lab tuning APIs or the customers themselves). The `tech/` subfolder is intentionally light — sufficient depth for an operator to weigh the hypothesis above, not encyclopaedic. Future `/lint` sweep will populate the `Referenced by` blocks across the new pages.

## [2026-05-23] edit | Quartz publish filter + baseUrl fix

- **Problem:** Live site at `https://supgrade.github.io/where-ai-value-lands/` showed only empty RSS XML — no HTML home page.
- **Cause:** `ExplicitPublish` filtered all 111 wiki files (none had `publish: true`); deploy artifact had `index.xml` but no `index.html`.
- **Fix:** Removed `ExplicitPublish`; use `RemoveDrafts` only. Corrected `baseUrl` to `supgrade.github.io/where-ai-value-lands` (matches GitHub repo slug). Local build now emits 303 files including `index.html`.
- **Files:** `quartz-config/quartz.config.ts`, `quartz-config/README.md`, `README.md`

## [2026-05-23] edit | Collaboration infrastructure (T0 + T1) shipped — repo go-public-ready
- Decisions resolved (six of the open questions promoted from [[06_collaboration]]):
  - **License:** MIT (code) + CC-BY-4.0 (content). Two separate files at repo root: `LICENSE`, `LICENSE-content`. Maximally compatible with T1–T4.
  - **Repo:** `github.com/Supgrade/where-AI-value-lands` — personal account, repo name includes "AI" to surface the subject at URL level.
  - **Domain:** GitHub Pages default (`supgrade.github.io/where-AI-value-lands`); custom domain deferred until T0 produces signal.
  - **Static-site tool:** Quartz v4, default theme. Cloned fresh by CI on every build (kept out of repo via `.gitignore`); our customizations live in `quartz-config/`.
  - **`/contribute` skill scope at v1:** all four contribution kinds (source, daily thought, concept note, open question). Implemented in `.claude/skills/contribute/SKILL.md`.
  - **Contributor charter:** terse + filtering posture; CONTRIBUTORS.md + per-page footer credit model. Lives at [[08_contributor-charter]].
- Files created at repo root (public-facing entry surface):
  - `README.md` — rewritten for public consumption; project frame, audience, repo layout, skill table, license, contributing pointer
  - `CONTRIBUTING.md` — short pointer doc into the charter and the `/contribute` skill; out-of-scope list; license-acceptance clause
  - `CONTRIBUTORS.md` — seed roll with author listed; one-line entry format documented
  - `LICENSE` — MIT, copyright Gabriele Dalla Costa 2026, with scope clarification at the bottom
  - `LICENSE-content` — CC-BY-4.0 short-header form, with recommended attribution string
  - `.gitignore` — excludes `quartz/`, `node_modules/`, `public/`, `.quartz-cache/`, OS/IDE noise; preserves `.obsidian/`
- Files created in `.github/`:
  - `.github/workflows/deploy.yml` — Node 22, clones Quartz v4, copies `quartz-config/quartz.config.ts` over the install, builds with `-d ../wiki`, uploads `public/` artifact, deploys via `actions/deploy-pages@v4`; pinned modern Pages-via-Actions pattern (not deploy-from-branch)
- Files created in `quartz-config/`:
  - `quartz.config.ts` — Quartz v4 config: pageTitle "Where AI Value Lands", baseUrl `supgrade.github.io/where-AI-value-lands`, default plugin set, Source Serif 4 / Source Sans 3 / JetBrains Mono typography (matches `/visualize` register), analytics off, `ignorePatterns: [private, templates, .obsidian, _staging]`
  - `README.md` — explains the Quartz-as-build-tool pattern (clone-on-build, not committed), local-preview steps, required GitHub repo settings (Settings → Pages → Source = GitHub Actions), customisation notes
- Files created in `.claude/skills/contribute/`:
  - `SKILL.md` — full v1 skill spec implementing [[06_collaboration]] §T1: pre-flight check (verify fork, branch, `gh` auth), Step 1 scope check (reads [[05_open-questions]] + index head), Step 2 contribution-kind menu (4 kinds), Step 3 per-kind workflows with file paths and frontmatter shapes, Step 4 branch + PR description template (dual `Pages affected` Obsidian wikilinks / `Page links` GitHub relative links), Step 5 forward → reverse link audit (no silent edits to existing pages; choice surfaced to contributor), Step 6 print-the-`gh`-command (skill does not push), explicit out-of-scope list, what-not-to-do
- Files created in `wiki/01_paper-planning/`:
  - `08_contributor-charter.md` — high-bar standard; terse + filtering; explicit out-of-scope (consumer AI, robotics, ML research, general AI safety, surface summaries); evidentiary standards (every claim sourced, quantitative claims have data pages, secondary syntheses flagged, bear and bull frames engaged); voice calibration; per-page contributor credit format; "friction is the feature" stance
- Files updated:
  - [[06_collaboration]] — Related section now links [[08_contributor-charter]]
  - [[05_open-questions]] — six collaboration-model decisions marked resolved with date and link
  - `CLAUDE.md` — bumped "Seven skills" to "Eight"; added /contribute description
- Key takeaway: T0 (public repo + static site infrastructure) and T1 (`/contribute` skill) are now mechanically complete. The repo is ready to push to GitHub once the author runs `git init` + `gh repo create`. Quartz deploys on first push to `main` via Actions. The charter is `status: draft` and will mutate as real contributions accumulate — by design.
- Recommended next:
  1. Author: `git init`, then `gh repo create Supgrade/where-AI-value-lands --public --source=. --remote=origin`, then push to `main`.
  2. Configure repo on GitHub: Settings → Pages → Source = GitHub Actions; verify the workflow run completes; check the live site at `https://supgrade.github.io/where-AI-value-lands/`.
  3. Optional T2 (auto-digest newsletter) and T3 (LinkedIn) remain deferred per [[06_collaboration]] sequence.
  4. /lint to verify reverse-link integrity of the new [[08_contributor-charter]] page against [[06_collaboration]] and [[05_open-questions]].

## [2026-05-22] edit | Create `wiki/data/` — citable-evidence layer
- New folder `wiki/data/` for citable units of evidence (statistics, tables, figures, images). Each numeric claim in a concept page should resolve to a data page here. README documents conventions: one-data-point-per-file, required frontmatter (`type`, `source-primary`, `source-via`, `year`, `related`), images-must-have-sibling-markdown rule, forward→reverse link rule preserved.
- 10 initial data pages populated (the most prominent quantitative claims already scattered across concepts and sources):
  - Bear ceilings: [[task-based-tfp-ceiling]], [[ai-task-exposure-decomposition]].
  - Capex / unit economics: [[hyperscaler-capex-trajectory]], [[hyperscaler-customer-concentration]], [[perplexity-burn-ratio]].
  - Adoption / bull projections: [[scaling-gap-74-16]], [[wef-7-6t-projection]], [[global-ai-spend-632b]], [[ai-leader-productivity-delta]].
  - Distribution-moat anchors: [[cursor-50b-valuation]], [[windsurf-acquisition-battle]].
  - Vertical-industrial deltas: [[eri-use-case-deltas]].
- Reverse links added on the concept and source pages that previously hosted these numbers inline: [[scaling-gap]], [[task-based-framework]], [[circular-ai-economy]], [[middle-layer-defensibility]], [[capital-labor-divergence]], [[distribution-moat]], [[enterprise-adoption-ladder]], [[vertical-ai-orchestration]], [[wef-ai-in-action-2025]], [[zitron-circular-economics]], [[acemoglu-simple-macroeconomics]], [[where-value-lands-2026]], [[deloitte-ai-dossier-eri]]. Each got a new `## Data` block referencing the relevant data pages.
- Index updated: new "Data — `data/`" section with the 10 entries grouped by theme.
- No images included in this first pass — markdown stats and tables only. The README documents the image convention so future ingest passes (e.g. a U-curve chart, a hyperscaler-capex bar chart) can drop a JPEG + sibling markdown into the folder.
- Suggested next: lint pass to catch any quantitative claims still living only in concept text that should also have data pages (genai trust gap, McKinsey 65%, Anthropic vs OpenAI revenue splits, etc.).

## [2026-05-22] edit | Add `06_collaboration` to paper-planning
- New page: [[06_collaboration]] — brainstorms how others contribute to the wiki while it is in flight. Distinct from [[04_distribution]] (which is about the finished paper).
- Source for the page: today's daily thought (`raw/daily tougths/2026-05-22.md`), which articulated the PR-via-`/contribute`-skill contribution model, the operator-only friction tolerance, and the long-term "tool for founders to share by prompting" framing.
- Structure: five additive tiers (T0 read-only repo → T1 PRs + `/contribute` skill → T2 auto-digest newsletter → T3 community channel (LinkedIn / X / Discord, pick one) → T4 chat-with-the-wiki web app), plus a recommended ship sequence, a risks section, and a how-it-fits-with-existing-skills table.
- Stance taken (user-directed): contributions are technical-by-default (CLI + PR), author is the single merge gatekeeper, voice coherence beats contribution volume — *"reject more than you accept, especially early."*
- Reverse links added: [[04_distribution]] (Related section), [[05_open-questions]] (new "Collaboration model" block listing four decisions promoted up: `/contribute` skill scope, newsletter platform, contributor charter, community channel choice), [[00_initial-brief]] (added to the plan map).
- Index updated: new entry under "Paper planning".
- Suggested next: `/edit` to author the contributor charter referenced in [[05_open-questions]]; spec out the `/contribute` skill before publishing the repo (currently a placeholder, not a real skill); decide repo license — T1/T2 work in MIT or CC-BY, T4 is complicated by CC-BY-NC.

## [2026-05-22] reflect | Business archetypes, analytical vocabulary, personal research frame
- Daily note: 2026-05-22
- Annotated: 2026-05-22 annotated
- Memory marker: [[archetypes-vocabulary-personal-frame]]
- Wiki changes:
  - [[07_analytical-vocabulary]] (created) — six analytical axes, vocabulary quick-reference table, sample coordinates for Cursor and a North Italian SME; canonical source for "layer" vs "level" vs "archetype" vs "tier"
  - [[06_collaboration]] (updated) — T0 expanded with repo structure (full folder tree) and static site spec (Quartz recommended, GitHub Action deployment); T1 expanded with full `/contribute` skill specification (scope check, 4 contribution kinds, branch + PR description template, forward→reverse link check)
  - [[05_open-questions]] (updated) — three new sections: collaboration model additions (static site domain, Quartz vs. alternatives), analytical vocabulary decisions (5 open Qs on terminology and axis scope), business archetype taxonomy decisions (completeness, SME/Italian archetype gap, archetype-to-U-curve mapping)
  - [[index.md]] (updated) — [[07_analytical-vocabulary]] entry added; [[thoughts/]] section initialized
- Kept as conversation: personal life-design framing (what to start, where, what kind of life) — live material for Section 6 drafting; U-curve mapping of archetypes (open question, not yet a wiki page)

## [2026-05-22] discover | SME & mid-cap ER&I AI adoption
- Mode: both (wiki-driven + news-driven)
- Candidates surfaced: 8
- Gaps targeted: [[enterprise-adoption-ladder]] (no SME phase anchors), [[scaling-gap]] (SME shape unknown), [[H2_u-curve-of-value]] (tested against large firms only), [[divergent-value-stack-optima]] (EU firm-level data absent), [[foundational-enablers]] (universalist claim untested for SMEs)
- Top picks: IEA Energy and AI 2025 (energy-sector primary source), OECD AI Adoption by SMEs Dec 2025 (76% are "AI novices"), Eurostat 2025 sector×size breakdown (EU energy AI = ICT security, not operations), PIIE 2026 industrial sectors (manufacturing AI outside production), Fed monitoring note April 2026 (14:1 investment gap), St. Louis Fed EU/US gap Mar 2026 (employer encouragement drives 95% of gap), TwinLadder Mittelstand (94% not ready), McKinsey State of AI Nov 2025 (6% high performers)

## [2026-05-22] visualize | enterprise-adoption-ladder (ER&I reading)
- Output: `outputs/enterprise-adoption-ladder.html`
- Concept resolved: [[enterprise-adoption-ladder]], read through the ER&I lens (user asked for "timeline of AI adoption + value creation for an ER&I company, plus small/medium vs big differences").
- User scope choice: visualize the existing concept ER&I-flavored, not invent a new page. The small-vs-big-firm dimension is flagged as a wiki gap in the output's closing tension — every current ER&I case study (BMW, Aker BP, SBB, Merck, Siemens, Chevron) is a large firm; SME industrial AI adoption is not represented in the wiki yet.
- Nodes: 25 (1 center + 5 phase markers + 8 concepts + 2 hypotheses + 6 ER&I use cases + 3 sources).
- Edges: 42 (33 wikilinks + 9 citations).
- Anchors: P1 generic-utility-pilot (no concrete case in wiki); P2 disconnected-pilots (most ER&I firms here); P3 BMW supply-chain digital twin (30–40% productivity claim); P4 Aker BP Yggdrasil (periodically unmanned offshore); P5 no public exemplar.
- Design: Tufte-style two-column layout, Source Serif 4 body, JetBrains Mono for marginalia and chrome, ink-blue accent (#1f3a5f) on off-white (#f4f1ea), d3-force graph clustered along the phase axis (left→right), scroll-triggered reveals, no emoji / no cards / no gradients.
- Size: ~40KB, self-contained except for Google Fonts + d3 CDN.
- Suggested next: `/discover` on SME and mid-cap ER&I AI adoption surveys (EU SME digital-maturity, IEA small-utility AI) before re-running `/visualize` with a firm-size dimension folded in.

## [2026-05-22] edit | Materialize ER&I use cases into `06_ideas/` folder
- New folder: `wiki/06_ideas/` — concrete use-case pattern pages, browsable on their own as "how AI is actually being used."
- Pages created (12, all from [[deloitte-ai-dossier-eri]]): [[predictive-maintenance]], [[autonomous-drone-inspection]], [[drone-footage-smart-summaries]], [[autonomous-field-operations]], [[hydrocarbon-reservoir-exploration]], [[minerals-processing-optimization]], [[ai-materials-science]], [[grid-optimization]], [[supply-chain-digital-twin]], [[intelligent-commercial-operations]], [[generative-site-design]], [[vr-ohs-training]].
- Pages updated: [[deloitte-ai-dossier-eri]] (the 12 numbered items now wikilink out to the dedicated pattern pages), [[index]] (new "Ideas" section with ER&I sub-section + 12 entries).
- Cut style chosen (user-directed): one page per **generic use-case pattern** (not per company implementation). Each page lists named deployments (SBB, Aker BP, BMW, Merck) underneath the pattern description, with measured outcomes where available.
- Page template: pattern description → domain → in/reasoning/out + human checkpoint → named deployments → what's actually being measured (and what's not) → concept linkages → open questions → related.
- Key takeaway: this is structural-edit work, not new evidence. The intent is to make the wiki browsable along a different axis — by *what AI does* rather than *who said it* — so the paper's practical half has a clean inventory of operational patterns to draw from. Concept pages ([[agentic-revolution]], [[vertical-ai-orchestration]], [[autonomy-slider]], [[scaling-wall]], [[synthetic-data-generation]]) each show up multiple times across the 12 pages, surfacing which patterns load which concepts most heavily.
- Suggested next: extend the same cut to the WEF case studies (the 18 cases inside [[wef-ai-in-action-2025]]) once the user wants the full corpus; `/lint` to verify reverse-link integrity across the 12 new pages and the heavy index update; `/ask` to query "which use cases load [[agentic-revolution]] hardest?" to surface the strongest evidence for the paper's practical half.

## [2026-05-22] ingest | "Digital Core" and the Structural Requirements for Non-Tech Enterprises (synthesis note)
- Pages created: [[non-tech-digital-core-synthesis]] (source), [[digital-core]], [[taker-shaper-maker]], [[fusion-skills]]
- Pages updated: [[foundational-enablers]] (digital-core now a wikilink + Related expanded), [[wef-ai-in-action-2025]] (Frameworks section: digital-core / taker-shaper-maker / fusion-skills now wikilinks + Related expanded), [[enterprise-adoption-ladder]] (Related expanded), [[autonomy-slider]] (Related expanded: fusion-skills as labor-side counterpart), [[democratization-of-programming]] (Related expanded), [[karpathy-software-3]] (Related expanded), [[H1_L0-L7-ladder]] (Tensions: third orthogonal axis taker-shaper-maker added; Related expanded), [[index]] (4 new entries)
- Key takeaway: this source is a **secondary LLM-generated synthesis** of material already in the wiki ([[wef-ai-in-action-2025]] + [[karpathy-software-3]] + Huang). Its real contribution is *naming*: it elevates three handles that were latent bullet items in the primary sources — [[digital-core]] (3-layer enterprise stack), [[taker-shaper-maker]] (strategic-adoption typology), and [[fusion-skills]] (workforce capability) — into addressable concepts. With these, the wiki now has the full three-axis coordinate system for non-tech firms: (substrate L0–L7, maturity Phase 1–5, positioning Taker/Shaper/Maker).
- Contradictions surfaced:
  - **Methodologically thin.** The source claims "PhD-level analysis" but provides no anchored citations. The "GANs for synthetic data" claim is two cycles behind the 2026 frontier (LLM-distilled / diffusion-generated synthetic data). Flagged on the source page.
  - **No bear-case engagement.** The source repeats the bull-managerial frame ([[scaling-gap]] is a readiness problem) without acknowledging [[zitron-circular-economics]], [[task-based-framework]], or [[marcus-world-models-failure]] exist.
  - **The "digital core" frame silently locks the enterprise into the L0–L2 / renter position.** By treating L3 infrastructure as "procurement," it collapses substrate-ownership into a non-question — exactly the move [[H1_L0-L7-ladder]] is meant to make visible. Documented on [[digital-core]].
  - **Fusion-skills is a managerial answer to capital-labor divergence, not a refutation.** The framing implies the AI-augmented worker captures surplus; the structural critique ([[capital-labor-divergence]]) argues the vendor of the AI tool does. Flagged on [[fusion-skills]].
- Suggested next: this source is meta-evidence of how the bull-managerial frame propagates into non-tech firms via LLM-generated executive digests — worth treating as a *discourse artifact* in the paper, not just a content source. Possible follow-ups: `/lint` to verify reverse-link integrity across the four new pages; `/ask` to materialize the three-axis (substrate / maturity / positioning) coordinate map as a draft section; `/discover` to find the **primary Huang GTC keynote** material the source quotes but does not cite.

## [2026-05-22] ingest | Deloitte AI Dossier — AI Use Cases in Energy, Resources & Industrials
- Pages created: [[deloitte-ai-dossier-eri]], [[agentic-revolution]], [[vertical-ai-orchestration]], [[synthetic-data-generation]], [[ai-factory-huang]]
- Pages updated: [[H2_u-curve-of-value]] (vertical-domain corroboration block + 4 new Related links), [[H1_L0-L7-ladder]] (Related: ER&I use cases sit at L3–L5 in industrial verticals), [[autonomy-slider]] (vertical-industrial restatement of the Iron Man Suit imperative; liability allocation as the constraint), [[middle-layer-defensibility]] (Non-software instantiation block; 3 new Related links), [[scaling-wall]] (Vertical-application manifestation block: OOD generalization failure in ER&I; 3 new Related), [[karpathy-software-3]] (4 new Related links), [[wef-ai-in-action-2025]] (4 new Related links), [[index]] (5 new entries)
- Key takeaway: this is the first ingested source with a **deep vertical-domain decomposition**. Deloitte's central strategic claim — "the competitive moat in ER&I will no longer be determined solely by physical assets, but by the maturity of an organization's digital core, its data ecosystems, and its ability to securely manage hybrid human-AI workforces" — places the moat at orchestration + data + workforce coordination, *not* at the AI model. This is a clean non-software instantiation of [[middle-layer-defensibility]] and supplies the first vertical-domain corroboration of [[H2_u-curve-of-value]] in industrials: top = multi-agent operational orchestrator, bottom = proprietary operational data + physical assets, squeezed middle = generic foundation models + generic agent frameworks. The source also introduces [[agentic-revolution]] (analytical → agentic transition) as the load-bearing paradigm shift the paper must address.
- Contradictions surfaced: (1) **OOD failure is self-aware bear evidence inside a bull source** — Deloitte's candid admission that models fail on "novel ores" / unfamiliar geology lands closer to [[scaling-wall]] than its own conclusion does. (2) **Magnitude is unquantified** — unlike WEF ($7.6–17.9T) and [[task-based-framework]] (<0.71% TFP cap), Deloitte does not commit to a sector-wide number. Harder to test, harder to falsify. (3) **Agentic full-stack vs. static task-set** — the agentic-revolution narrative implicitly argues the automatable task-set *expands* as orchestration improves, directly rebutting Acemoglu's static-task framing; the source does not draw the contradiction out. (4) **Bear cluster absent** — Deloitte does not engage with [[circular-ai-economy]] or [[task-based-framework]] at all. (5) **Federated AI-factory topology** opens room for vertical-incumbent or sovereign substrate strategies that bypass hyperscaler rental — consistent with [[sovereign-ai]] but pulls a different lever than [[divergent-value-stack-optima]].
- Suggested next: ingest the **primary Deloitte AI Dossier PDF** directly to verify the synthesis (this file is LLM-authored); ingest a **Huang GTC keynote** for the AI-factory framing as a primary source; `/lint` to check reverse-link integrity across the 5 new pages and the heavy update fan-out; `/ask` to draft a per-layer value-capture summary that integrates the vertical-industrial frame with the horizontal-SaaS frame ([[where-value-lands-2026]]) — the wiki now has both and they should be reconciled.

## [2026-05-22] ingest | WEF — AI in Action: Beyond Experimentation to Transform Industry (2025)
- Pages created: [[wef-ai-in-action-2025]], [[scaling-gap]], [[enterprise-adoption-ladder]], [[foundational-enablers]]
- Pages updated: [[H1_L0-L7-ladder]] (added buyer-side parallel ladder reference; Related expanded), [[H2_u-curve-of-value]] (added enterprise-side ambiguity evidence and bull-projection triangulation; Related expanded), [[bear-case-synthesis]], [[acemoglu-simple-macroeconomics]], [[karpathy-software-3]], [[zitron-circular-economics]], [[goldman-sachs-too-much-spend]], [[marcus-world-models-failure]], [[bradford-digital-empires]], [[task-based-framework]], [[distribution-moat]], [[middle-layer-defensibility]], [[circular-ai-economy]], [[capital-labor-divergence]], [[agentic-scaling-law]], [[divergent-value-stack-optima]], [[diffusion-vs-innovation]] (reverse links to the new source/concept pages), [[index]] (4 new entries)
- Key takeaway: the canonical consultancy / multilateral bull synthesis enters the wiki. Most useful single artifact: the **[[scaling-gap]]** (74% of firms cannot scale AI, only 16% are reinvention-ready) — interpretation-flexible evidence that supports managerial, bear-structural, and middle-dies readings simultaneously. The paper also contributes an *enterprise adoption ladder* (Phase 1–5) orthogonal to the substrate-side [[H1_L0-L7-ladder]] — useful as a buyer-vs-vendor cross-cut.
- Contradictions surfaced:
  - **WEF $7.6–17.9T projection vs. Acemoglu <0.71% TFP cap.** Direct quantitative contradiction. Both have credibility issues; flagged on both hypothesis and concept pages.
  - **Managerial framing of the scaling problem vs. structural framing.** WEF treats the 84% gap as solvable with foundational enablers ([[foundational-enablers]]); [[zitron-circular-economics]], [[task-based-framework]], and [[marcus-world-models-failure]] argue the constraint is somewhere else entirely (demand circularity, surplus ceiling, architectural ceiling).
  - **Universalist framing vs. bloc divergence.** WEF treats AI as globally homogeneous; [[divergent-value-stack-optima]] and [[bradford-digital-empires]] argue the question must be answered per bloc. WEF has *zero* engagement with this dimension.
  - **Silence on surplus capture.** The paper's "responsible AI" frame procedurally addresses ethics but sidesteps the [[capital-labor-divergence]] question entirely.
- Suggested next: `/lint` to verify the new pages' link integrity; or `/ask` to materialize a per-layer comparison between WEF's "digital core" 3-layer model and the L0–L7 ladder; or `/discover` for primary sources behind WEF's headline figures (IDC AI spending forecast, BCG October 2024 scaling survey, Accenture 2024 reinvention research).

## [2026-05-22] ingest | Where Value Lands: AI Redistribution of Economic Surplus (2026)
- Pages created: [[where-value-lands-2026]], [[middle-layer-defensibility]], [[distribution-moat]], [[context-control]], [[world-models-jepa]], [[jevons-paradox-ai]]
- Pages updated: [[H2_u-curve-of-value]] (status lifted to low-to-medium; empirical validation section added for the top of the U; Jevons Paradox nuance added for the bottom; Related section expanded), [[index]] (6 new entries)
- Key takeaway: the strongest empirical validation yet for H2's top — Cursor ($50B, $2B ARR) and Windsurf ($2.4B acquisition battle) prove distribution moats are real and measurable. But the taxonomy matters: what the source calls "middle stack" is what H2 calls "the top" (distribution + workflow ownership). The generic thin wrapper still dies; the sophisticated workflow-embedded platform survives. LeCun's JEPA adds a long-horizon paradigm-reset risk for current LLM-based moats. Jevons Paradox partially defends the bottom of the U against the circular-economy critique.
- Contradictions surfaced: (1) Jevons Paradox vs. [[circular-ai-economy]] — efficiency unlocks new demand, but is that demand real or VC-subsidized? (2) LeCun's JEPA threat is largely absent from the bull-frame practitioners' worldview; neither Truell nor Srinivas addresses the architectural ceiling risk their moats face in a post-LLM paradigm. (3) EU and China stacks absent from this source — bull frame is implicitly US-centric.
- Suggested next: `/ask` to draft a consolidated per-layer value-capture summary that integrates bull and bear frames across this source, [[bear-case-synthesis]], and [[karpathy-software-3]]; or `/discover` to find primary sources for Cursor/Windsurf (Lenny's Podcast transcripts) and LeCun (Davos talk / JEPA papers) to verify synthesis claims.

## [2026-05-21] ingest | The Geopolitics and Governance of the Global AI Divide
- Pages created: [[geopolitics-global-ai-divide]], [[divergent-value-stack-optima]], [[digital-empires-tripartite]], [[diffusion-vs-innovation]], [[open-weight-asymmetry]], [[brussels-effect-and-mirage]], [[sovereign-ai]], [[bradford-digital-empires]], [[ding-diffusion-marathon]], [[lee-01ai-pivot]]
- Pages updated: [[H2_u-curve-of-value]] (added second pressure: shape may be bloc-specific, not universal), [[05_open-questions]] (geographic-frame question sharpened — Section 5 may need to function as cross-cut of Section 3), [[03_structure]] (Section 5 scaffolding fleshed out with the three optima), [[01_source-list]] (Section 5 sources marked stub-via-synthesis with explicit links), [[index]] (10 new entries)
- Key takeaway: the AI value stack does not have a single global shape. The U-curve of [[H2_u-curve-of-value]] is plausibly a **US-stack artifact**; China engineers a bottom-heavy optimum via [[open-weight-asymmetry]], and the EU attempts a regulatory-centric optimum via [[brussels-effect-and-mirage]] + [[sovereign-ai]]. The where-does-value-land question must be answered per bloc.
- Contradictions surfaced: H2's universal-U framing now under pressure from two directions — the bear case ([[bear-case-synthesis]]) from the demand-circularity side, and bloc divergence ([[divergent-value-stack-optima]]) from the geopolitical side. These are complementary, not redundant. The EU "Brussels Effect" thesis as a global moat is itself contradicted internally by the LSE *Brussels Mirage* analysis — compliance form travels but rights substance does not.
- Suggested next: ingest the primary sources directly (Bradford *Digital Empires*, Ding RAND + FPRI pieces, the LSE *Brussels Mirage* paper); then `/ask` to materialize the per-bloc value-capture story as a draft Section 5; possibly `/lint` to verify reverse-link integrity across the new pages.

## [2026-05-21] ingest | AI Redistribution of Economic Surplus — The Skeptics and Bear Case
- Pages created: [[bear-case-synthesis]], [[acemoglu-simple-macroeconomics]], [[goldman-sachs-too-much-spend]], [[marcus-world-models-failure]], [[zitron-circular-economics]], [[scaling-wall]], [[task-based-framework]], [[circular-ai-economy]], [[capital-labor-divergence]]
- Pages updated: [[H1_L0-L7-ladder]] (added scaling-wall caveat at L4+), [[H2_u-curve-of-value]] (confidence lowered; bottom-of-U threatened), [[01_source-list]] (skeptic table marked as stub-via-synthesis), [[05_open-questions]] (bear-case-anchor question sharpened)
- Bootstrap: created [[index]] and `log.md` (first ingest).
- Key takeaway: the four-pillar bear case (cognitive ceiling, labor/macro ceiling, ROI shortfall, circular product-layer economics) puts substantial pressure on both working hypotheses. [[H2_u-curve-of-value]] is the most exposed: if the bottom of the U is currently propped up by VC-recycled cash via [[circular-ai-economy]], the U is the wrong shape.
- Contradictions surfaced: the U-curve assumes the bottom is durably profitable; Zitron's circular-economy thesis contradicts that. The paper's "redistribution of economic surplus" framing assumes a surplus to redistribute; [[task-based-framework]] caps it at <0.71% cumulative TFP over 10 years — meaningfully smaller than the optimistic narrative assumes.
- Suggested next: ingest the four primary sources directly (Acemoglu PDF, GS report, Marcus essay, Zitron pieces) to verify the synthesis; then run `/discover` for the strongest *bull* counter-synthesis so the wiki doesn't tilt one-sided.

## [2026-05-21] ingest | Karpathy — Software Is Changing (Again)
- Pages created: [[karpathy-software-3]], [[software-3-paradigm]], [[autonomy-slider]], [[llm-as-operating-system]], [[agentic-scaling-law]], [[democratization-of-programming]]
- Pages updated: [[H1_L0-L7-ladder]] (competing-taxonomy + agentic-scaling counter to scaling-wall added; confidence note refined), [[H2_u-curve-of-value]] (bull-frame pressure points added — install-base reinforces top, AI-factory reinforces bottom, agent-eliminates-apps threatens GUI top), [[scaling-wall]] (added direct counter via [[agentic-scaling-law]]), [[index]] (5 new concept pages + 1 new source).
- Key takeaway: this is the first strong **bull-frame paradigm document** in the wiki. It introduces a competing single-axis taxonomy ([[autonomy-slider]]) to [[H1_L0-L7-ladder]], partially restores the bottom of [[H2_u-curve-of-value]] via inference-as-economy, and offers the strongest direct counter to [[scaling-wall]] via [[agentic-scaling-law]] (test-time compute as second scaling axis).
- Contradictions surfaced:
  - **Scaling wall vs. agentic scaling law** — base-model reasoning plateau (Marcus) vs. test-time compute as second axis (Huang). Both can be partially right; the synthesis is task-distributional.
  - **GUI verification vs. GUI elimination** — Karpathy's "Iron Man suit" assumes verification GUIs are the durable design pattern; Steinberger predicts agents eliminate 80% of apps. Unresolved within the source.
  - **Bull paradigm vs. circular economy** — Karpathy treats LLMs as a utility ("intelligence on tap") and is silent on whether the substrate paying for it is solvent (cf. [[circular-ai-economy]]).
  - **OS metaphor vs. security reality** — Steinberger's OpenClaw experience suggests prompt injection is the new buffer overflow but the LLM-OS lacks the syscall ABI / permissions model that production OSes spent 40 years building.
- Suggested next: ingest the **original Karpathy talk** and a **Huang GTC keynote** directly (this file is a secondary synthesis); ingest primary **Steinberger / OpenClaw** material to verify security claims; run `/lint` to verify reverse-link integrity across the five new concept pages; revisit [[05_open-questions]] re: bear-case anchor in light of a now-present bull anchor.

## [2026-05-22] ingest | OECD — AI Adoption by SMEs (G7 Discussion Paper 2025)
- Pages created (22):
  - Concepts (10): [[sme-ai-adoption-gap]], [[oecd-sme-adopter-taxonomy]], [[sectoral-ai-diffusion-pattern]], [[ai-productivity-firm-level]], [[oecd-sme-enabler-quartet]], [[ai-skill-shortage-as-diffusion-bottleneck]], [[sme-ai-finance-gap]], [[sme-connectivity-divide]], [[sme-policy-pathway-novice-to-champion]], [[g7-sme-ai-policy-pluralism]]
  - Source (1): [[oecd-sme-ai-adoption-2025]]
  - Ideas / case patterns (4): [[sme-novice-off-the-shelf-llm]], [[sme-optimiser-cross-functional-stack]], [[sme-explorer-custom-agent]], [[sme-champion-vertical-ai]]
  - Data (7): [[sme-vs-large-firm-ai-gap]], [[oecd-ai-adoption-trajectory-2020-2024]], [[oecd-sectoral-ai-adoption-2024]], [[oecd-g7-productivity-gain-projection]], [[sme-broadband-firm-size-gap]], [[ai-skill-shortage-sme-share]], [[g7-sme-large-firm-ai-adoption-ratio]]
- Pages updated (12):
  - Hypothesis: [[H1_L0-L7-ladder]] (OECD taxonomy added as fourth orthogonal axis), [[H2_u-curve-of-value]] (bottom-right pressure: SME tail of the application layer is shallow; confidence note refined)
  - Concept: [[scaling-gap]] (SME-specific mechanism evidence: skills/finance/connectivity; different denominator that compounds with BCG 74%), [[diffusion-vs-innovation]] (OECD as measurement layer operationalising Ding's thesis at the SME tail; binding constraints sharpened), [[enterprise-adoption-ladder]] (OECD taxonomy as SME-specific parallel; two-axial vs linear), [[taker-shaper-maker]] (OECD four-stage mapped onto rent/customize/train), [[foundational-enablers]] (OECD quartet as narrower SME-specific cousin; mapping table added), [[divergent-value-stack-optima]] (four G7 optima documented, not three), [[digital-empires-tripartite]] (partial confirmation + Japan/UK complications; confidence downgrade to medium-low), [[sovereign-ai]] (G7 compute-instrument inventory across all seven countries + EuroHPC), [[fusion-skills]] (direct empirical anchor — symmetric importance shift across technical and judgement skills)
  - Search: [[01_source-list]] (new SME Diffusion & Policy section added)
  - Reverse-link backlinks added to: [[capital-labor-divergence]], [[autonomy-slider]], [[vertical-ai-orchestration]], [[middle-layer-defensibility]], [[distribution-moat]], [[digital-core]], [[task-based-framework]], [[acemoglu-simple-macroeconomics]], [[deloitte-ai-dossier-eri]], [[bradford-digital-empires]], [[brussels-effect-and-mirage]]
- Key takeaway: the OECD G7 paper is the empirical anchor for the diffusion question. It operationalises [[diffusion-vs-innovation]] at the SME tail, supplies a buyer-side taxonomy ([[oecd-sme-adopter-taxonomy]]) that is the SME analogue of [[enterprise-adoption-ladder]], and adds a third axis of doubt to [[H2_u-curve-of-value]]: the long-tail SME application surplus is thin where the population is thickest (29% of gen-AI-using SMEs in core activities; 11.9% small-firm adoption). G7 country profiles complicate [[digital-empires-tripartite]] — operational instruments converge across "empires" even where rhetoric diverges (Japan/UK as a fourth model, Canada bridging).
- Contradictions / open questions surfaced:
  - Macro projection 0.2–1.3 pp/yr (OECD/Filippucci) sits unreconciled against [[task-based-framework]]'s <0.71% cumulative TFP cap.
  - Where does SME AI surplus actually land — at the SME, the SaaS/model vendor, or the bundling platform (Shopify, Microsoft, Google Workspace)? OECD is silent.
  - Italy has the widest large-vs-small adoption divide (4.7×) despite ambitious Transition 5.0 / Competence Centre policy. Policy reach failure, structural firm-size distribution, or lag effect?
  - Convergent G7 operational instruments alongside divergent rhetoric weakens [[digital-empires-tripartite]] as a predictor of real capital flows.
  - Will most SMEs settle at Optimiser (wide-but-shallow off-the-shelf use) and never reach core-business integration? The 29% core-activity share is the diagnostic test.
- Agents used: 2 extraction (parallel), 5 patch-merge (parallel), 1 summary assembly (hit session limit; orchestrator completed inline with author-name correction)
- Suggested next: `/lint` to verify reverse-link integrity across the 22 new pages; ingest the underlying OECD micro-data papers (Calvino & Fontanelli 2023, Filippucci et al. 2025) referenced repeatedly; `/discover` for parallel diffusion-side sources from non-G7 economies (China, Korea, India, Brazil) to test whether the four-enabler quartet generalises.

## [2026-05-23] ingest | Choudary — Ecosystem Business Models: A Teardown
- Pages created (4): [[choudary-ecosystem-teardown]] (source), [[ecosystem-business-archetypes]] (master concept), [[vertical-to-horizontal-unbundling]] (structural thesis), [[cross-archetype-confusion]] (strategic failure mode).
- Pages updated (4): [[07_analytical-vocabulary]] (Axis 3 sub-vocabulary table added — Choudary's four archetypes as canonical decomposition of ecosystem position; Related expanded), [[H2_u-curve-of-value]] (Structural precursor section added — pre-AI horizontal-value thesis mapped onto top/middle/bottom of the U; Related expanded), [[middle-layer-defensibility]] (Disambiguating-the-middle section added — Integrator-as-switchboard vs failed-Capability; Related expanded), [[distribution-moat]] (Precursor section added — Aggregator archetype as canonical antecedent of distribution-moat reasoning; Related expanded).
- Key takeaway: Choudary's 2022 framework supplies the **cleanest off-the-shelf sub-vocabulary for Axis 3 (Business Archetype)** and a pre-AI structural precursor to [[H2_u-curve-of-value]]. The four archetypes (Aggregator / Integrator / Infrastructure / Capability) disambiguate what "middle" actually contains — the distinction between defensible Integrators (Stripe, Plaid) and failed Capabilities is the lens H2's "squeezed middle" was missing. The distribution-moat AI firms (Cursor, Perplexity, Windsurf) are best read as **Aggregators in B2B clothing**, not as novel AI-era inventions. Choudary's [[vertical-to-horizontal-unbundling]] mechanism locates H2 inside a recurring transaction-cost pattern across industries.
- Contradictions / open questions surfaced:
  - **Integrator-class value capture vs U-curve.** Plaid (Integrator) and Stripe (Capability with Aggregator-like economics) exhibit top-of-U margins from middle-stack positions. Counterexamples to H2 or refinements?
  - **Fifth archetype for the agentic era?** [[vertical-ai-orchestration]] looks like a candidate Orchestrator archetype not covered by Choudary's 2022 four-way taxonomy.
  - **US-stack bias.** Choudary's framework does not cleanly accommodate [[open-weight-asymmetry]] or [[brussels-effect-and-mirage]]; needs cross-checking against [[divergent-value-stack-optima]].
  - **Should the paper adopt Choudary's four as primary Axis-3 sub-vocabulary** with the fifteen-archetype roster as elaboration? Promoted to [[05_open-questions]] candidate.
- Suggested next: `/lint` to verify reverse-link integrity across the 4 new pages and 4 updates; `/edit` to fold "Should Choudary's four be the primary Axis-3 sub-vocabulary?" into [[05_open-questions]]; `/discover` for a primary Stripe / Plaid case-study source to stress-test the bimodal-Integrator hypothesis; `/ask` to draft the per-archetype value-capture map (Aggregator → top of U; Infrastructure → bottom of U; Integrator → bimodal middle; Capability → IP-defended or failed).

## [2026-05-23] ingest | Labor Market Impacts of AI — A New Measure and Early Evidence (Massenkoff & McCrory, Anthropic 2026)
- Pages created (11):
  - Source (1): [[massenkoff-mccrory-labor-market-impacts-2026]]
  - Concepts (5): [[observed-exposure-measure]], [[theoretical-vs-observed-capability-gap]], [[exposed-worker-demographics]], [[ai-young-worker-hiring-slowdown]], [[eloundou-beta-exposure]]
  - Data (5): [[most-exposed-occupations]], [[ai-exposure-vs-bls-growth]], [[high-vs-low-exposure-worker-characteristics]], [[unemployment-did-exposed-workers]], [[young-worker-hiring-did]]
- Pages updated (15):
  - Hypothesis: [[H2_u-curve-of-value]] (labor-side mirror documented; status updated; new section on labor-exposure U; +7 backlinks)
  - Concepts: [[capital-labor-divergence]] (Acemoglu-vs-Anthropic incidence disagreement made explicit; entry-level channel added), [[diffusion-vs-innovation]] (worker-level diffusion lag added as load-bearing evidence), [[scaling-gap]] (worker-level twin documented), [[task-based-framework]] (labor-side empirical anchor connected), [[ai-productivity-firm-level]] (worker-level companion linked), [[autonomy-slider]] (operationalisation in observed-exposure weighting noted), [[fusion-skills]] (half-weight discounting flagged), [[sme-ai-adoption-gap]] (entry-level cascade question), [[ai-skill-shortage-as-diffusion-bottleneck]] (worker-level twin), [[middle-layer-defensibility]] (user-base empirical confirmation), [[jevons-paradox-ai]] (software-developer outlier), [[world-models-jepa]] (capability frontier shifting), [[oecd-sme-enabler-quartet]] (worker-level mirror)
  - Source: [[acemoglu-simple-macroeconomics]] (partial-contradiction note + see-also), [[bear-case-synthesis]] (labor-side update integrated)
  - Data: [[ai-task-exposure-decomposition]] (eloundou-β backlink)
  - Planning: [[05_open-questions]] (4 new labor-side questions added; Acemoglu-vs-Anthropic disagreement, unemployment-vs-hiring leading indicator, two-curve story, conflict-of-interest)
  - Index: 6 new concept entries, 5 new data entries, 1 new source entry; header timestamp updated
- Key takeaway: this is the first wiki source that closes the loop between **theoretical AI capability** and **realized labor-market deployment**. Massenkoff–McCrory's [[observed-exposure-measure]] adds usage-weighting on top of Eloundou's β, producing the first labor-side measure that **predicts independent BLS occupational growth projections** (slope −6.07, R² 0.027) where theoretical β alone does not. The headline finding — [[theoretical-vs-observed-capability-gap]], with deployment running ~3× behind capability in the most-exposed category — operationalises [[diffusion-vs-innovation]] at occupation granularity and provides a parallel to the firm-level [[scaling-gap]]. Labor-side displacement is not detectable in unemployment data through mid-2025 ([[unemployment-did-exposed-workers]]) but the entry-level cohort (22–25) faces a ~14% hiring-rate suppression ([[ai-young-worker-hiring-slowdown]]) — the only detectable AI labor signal in the wiki to date.
- Contradictions surfaced:
  - **Acemoglu (2024) vs Anthropic (2026) on labor incidence.** Acemoglu predicted low-education clerical women bear the cost; Anthropic finds exposed workers are *more* educated, *higher*-paid, more white/Asian. Live empirical disagreement; reconciliation depends on whether [[theoretical-vs-observed-capability-gap]] is structural or transitional. Documented in [[exposed-worker-demographics]] and as a new [[05_open-questions]] item.
  - **Unemployment as the wrong dashboard.** Labor-side AI displacement is **invisible** in unemployment data but **visible** in 22–25-year-old hiring rates. Conventional labor-market dashboards may systematically miss the disruption.
  - **Bull-frame internal source.** Anthropic publishes labor-market research about its own deployment surface. The conflict-of-interest dimension is unstated in the source but added as an [[05_open-questions]] item.
- Open questions sharpened (added to [[05_open-questions]]):
  - Acemoglu vs Anthropic on labor incidence
  - Unemployment vs hiring as the leading indicator
  - Labor-side U vs value-stack U presentation in the paper
  - Anthropic as both measurer and deployer (conflict of interest)
- Suggested next: ingest the **Brynjolfsson, Chandar & Chen (2025) "Canaries in the coal mine"** paper and the **Hampole et al. (2025) NBER paper** to triangulate the labor-side findings with independent measures (different data sources, different identification strategies); run `/lint` to verify the 11 new pages have clean reverse-link integrity; revisit [[03_structure]] to decide whether the labor-side U gets its own section or sits inside Section 3.

## [2026-05-23] lint | Full wiki health check (124 content pages)
- T1 findings: 30 broken wikilinks (9× to never-created `[[H3_orthogonal-axes-under-priced]]`; case bug on `[[OECD-sme-enabler-quartet]]`; stub demo links in `[[06_collaboration]]` and `wiki/data/README`; skill-name links in `[[08_contributor-charter]]`; missing `[[ai-capex-cycle]]`); 459 missing reverse links (forward→reverse invariant decayed broadly — top hubs `[[H2_u-curve-of-value]]` (77 in), `[[H1_L0-L7-ladder]]` (37), `[[wef-ai-in-action-2025]]` (40) all under-linked back); 3 pages missing from `wiki/index.md` (`[[inference]]`, `[[suggested-sources]]`, `[[The evolution of IT infrastructure]]`); 2 genuine slug violations (`README`, `The evolution of IT infrastructure` in `wiki/data/`).
- T2 findings: `[[H1_L0-L7-ladder]]` lacks explicit body `Confidence` block (only in frontmatter); 4 widely-used terms lack pages (`value capture` ×14, `application layer` ×23, `displacement` ×14, `model layer` ×6); 7 pages over 1500 words ripe for splitting, led by `[[H2_u-curve-of-value]]` at 2852 words.
- T3 findings: 4 orphans (mostly legitimate planning/discover output); 31 hubs ≥15 incoming (healthy distribution); all pages carry `last-updated` 2026-05-21 to 2026-05-23 (no staleness); log chronological order intact.
- Suggested next: `/edit` to resolve H3 ghost references and add reverse-links to top hubs; split `[[H2_u-curve-of-value]]`; create concept pages for `value-capture`, `application-layer`, `displacement`, `ai-capex-cycle`; ingest queued sources in `raw/Clippings/` and the Massenkoff/McCrory-companion Anthropic PDF.

## [2026-05-23] edit | Lint Tier 1 cleanup + hypothesis health + 4 concept pages + top-5 hub reverse-link sweep
- Orchestrated three waves: parallel Sonnet pair → Opus → Sonnet sweep.
- **Wave 1A (Sonnet, planning/data/index):** `[[06_collaboration]]` cleaned of demo `[[index.md]]` refs (→ `[[index]]` or backticks); `[[08_contributor-charter]]` skill wikilinks (`[[ingest]]`, `[[lint]]`, `[[edit]]`, `[[contribute]]`, `[[reflect]]`, `[[log]]`) converted to slash-commands or backticked filenames; `[[CLAUDE]]`/`[[CONTRIBUTORS]]` → backticked filenames; `wiki/data/README.md` template placeholders wrapped in backticks; `wiki/data/The evolution of IT infrastructure.md` renamed via `git mv` to `wiki/data/evolution-of-it-infrastructure.md` (substantive McKinsey-derived analysis, kept); `wiki/index.md` gained Glossary section + `[[inference]]`, `[[suggested-sources]]` under Search, `[[evolution-of-it-infrastructure]]` under Data.
- **Wave 1B (Sonnet, hypothesis files):** CREATED `[[H3_orthogonal-axes-under-priced]]` stub (~270 words; status `deferred-stub`; reconstructs premise from how 9 linking pages use it — that axes cutting across L0–L7, e.g. autonomy, deployment topology, buyer maturity, are more predictive of value-landing than ladder position alone; resolves all 9 ghost references). Added `## Confidence` body section to `[[H1_L0-L7-ladder]]` (3 bands: high L0–L3, medium L4–L5 conditional on [[agentic-scaling-law]] vs [[scaling-wall]], speculative L6–L7). Fixed `[[OECD-sme-enabler-quartet]]` casing in `[[H2_u-curve-of-value]]` (×2) and `[[sme-policy-pathway-novice-to-champion]]` (×1). Converted `[[04_search-log]]` in `[[03_keyword-search-strings]]` to backticked filename.
- **Wave 2 (Opus, concept pages):** CREATED 4 concept pages with proper forward + non-hub reverse links:
  - `[[value-capture]]` — share of generated surplus a stack-position keeps vs. creates; bear-case wedge; reverse links from `[[lee-01ai-pivot]]`, `[[agentic-revolution]]`, `[[digital-empires-tripartite]]`, `[[sovereign-ai]]`, `[[world-models-jepa]]`.
  - `[[application-layer]]` — L0–L2 territory; top-of-U as a claim about workflow-embedded app-layer firms; reverse links from `[[circular-ai-economy]]`, `[[middle-layer-defensibility]]`, `[[distribution-moat]]`, `[[zitron-circular-economics]]`, `[[karpathy-software-3]]`.
  - `[[displacement]]` — substitution side of labor effect (vs augmentation); names theoretical-vs-observed measurement debate; reverse links from `[[capital-labor-divergence]]`, `[[task-based-framework]]`, `[[observed-exposure-measure]]`, `[[ai-young-worker-hiring-slowdown]]`, `[[exposed-worker-demographics]]`.
  - `[[ai-capex-cycle]]` — hyperscaler boom-then-bust mechanism (training capex → uncertain inference demand → overcapacity → write-downs on short-half-life GPUs and stranded power); reverse links from `[[circular-ai-economy]]`, `[[hyperscaler-capex-trajectory]]`, `[[ai-factory-huang]]`; previously-broken `[[ai-capex-cycle]]` refs in `[[bear-case-synthesis]]` and `[[goldman-sachs-too-much-spend]]` now resolve.
  - `wiki/index.md` updated with all 4 entries under concepts.
- **Wave 3 (Sonnet, reverse-link sweep):** appended `## Referenced by` sections to the top 5 hubs listing all inbound pages grouped by directory. Counts: `[[H2_u-curve-of-value]]` 79, `[[H1_L0-L7-ladder]]` 39, `[[wef-ai-in-action-2025]]` 41, `[[oecd-sme-ai-adoption-2025]]` 33, `[[diffusion-vs-innovation]]` 32. New concept pages picked up automatically. Frontmatter `last-updated` refreshed to 2026-05-23.
- **Orchestrator follow-up:** added `[[H3_orthogonal-axes-under-priced]]` to `wiki/index.md` under Hypotheses.
- **Net change vs pre-edit lint:** content pages 124 → 129 (+5: H3, value-capture, application-layer, displacement, ai-capex-cycle). Broken wikilinks 30 → 7 (remaining 7 are false positives — wikilinks intentionally inside backticks or image-embed syntax for `evolution-of-it-infrastructure.png`). Index gaps 3 → 0. Missing reverse links 459 → 424 (full remediation still requires sweeping non-hub pages; deferred).
- **Suggested next:** `/lint` re-run to confirm; consider splitting `[[H2_u-curve-of-value]]` (2852 words, now even larger with Referenced-by section); `/ingest` the queued sources in `raw/Clippings/`; future reverse-link sweep on the next tier of hubs (`[[capital-labor-divergence]]`, `[[autonomy-slider]]`, `[[middle-layer-defensibility]]`, `[[bear-case-synthesis]]`, `[[task-based-framework]]`, `[[circular-ai-economy]]`) to recover most of the remaining 424.

## [2026-05-24] ingest | Sutskever — From the Age of Scaling to the Age of Research
- **Source:** secondary analysis of a Sutskever interview/talk (Main thesis / Evidence / Critique / Methodology structure). LLM-generated structural digest, not verbatim transcript — claims are Sutskever's; scaffolding is the analyst's. Promoted to [[sutskever-age-of-research]].
- **Routing:** inline path (53 lines, no subsections — single orchestrator pass, no extraction agents).
- **New pages (5):**
  - [[sutskever-age-of-research]] — source summary.
  - [[post-scaling-research-pivot]] — central reframe: Age of Scaling (2020–2025) exhausted, Age of Research begins.
  - [[continual-learning-paradigm]] — sample-efficient on-the-job learning vs static pre-trained AGI.
  - [[eval-real-world-gap]] — superhuman benchmarks + brittle iterative real performance; researcher-side reward hacking diagnosis.
  - [[value-functions-as-algorithmic-emotion]] — biological emotions as cheap robust intermediate RL signals; Sutskever's load-bearing speculative claim.
- **Patches (5):**
  - [[scaling-wall]] — added Sutskever inside-operator concession of the empirical wall (not the architectural form).
  - [[agentic-scaling-law]] — added demand-side validation; Sutskever and Huang agree on the axis (test-time compute + RL), diverge on methodology (aesthetic top-down vs first-principles physics).
  - [[karpathy-software-3]] — cross-linked Karpathy's "anterograde amnesia" with Sutskever's continual-learning gap (same diagnosis, different label).
  - [[world-models-jepa]] — added Sutskever as a third convergent diagnosis of the autoregressive-pretrain bottleneck (algorithmic successor, complementary to LeCun's architectural answer).
  - [[autonomy-slider]] — added Iron Man vs straight-shot tension; Karpathy's partial-autonomy default vs Sutskever's silo-and-release posture; eval-real-world gap anchors the slider on the left.
- **Hypothesis touches:** [[scaling-wall]] gains a high-credibility inside-operator endorsement. [[agentic-scaling-law]] gains cross-source agreement on direction. [[H2_u-curve-of-value]] is reshaped without being adjudicated — the bottom-of-U mechanism partially shifts from "owns the GPUs" to "owns the algorithmic insight." [[H3_orthogonal-axes-under-priced]] modestly reinforced — Sutskever's aesthetic-vs-physics methodological axis is exactly the kind of cross-cutting variable H3 names.
- **Contradictions surfaced:**
  - Sutskever's straight-shot deployment posture directly contradicts Karpathy's Iron Man partial autonomy.
  - Value-functions claim is explicitly unfalsifiable in public ("safety + competitive reasons") — scientifically unverifiable.
  - "Neuralink plus plus" alignment equilibrium falls outside the WEF/Deloitte regulatory frame; pushes alignment from policy to transhumanist biology.
- **Open questions surfaced:** Does the research pivot favour incumbents or small algorithmic teams? Is the "Age of Research" a phase (months) or a paradigm reset (years/decades)? What signal drives next-gen training if natural data is exhausted?
- **Source moved** to `raw/ingested/`.

## [2026-05-24] ingest | Weber et al. — AI Startup Business Models (BISE 2021)
- **Source:** Weber, Beutter, Weking, Böhm, Krcmar (2021), *AI Startup Business Models: Key Characteristics and Directions for Entrepreneurship Research*, Business & Information Systems Engineering 64(1), 91–109. doi:10.1007/s12599-021-00732-w. 19-page research paper; promoted to [[weber-ai-startup-business-models]].
- **Routing:** inline path (19-page PDF read directly; no marker needed; single orchestrator pass).
- **New pages (8):**
  - [[weber-ai-startup-business-models]] — source summary.
  - [[ai-startup-business-archetypes-weber]] — operational classifier (parent overview of the four-pattern taxonomy + decision-tree shortcut). **This is the page the user will tag future AI-startup ingests against.**
  - [[ai-charged-product-service-provider]] — Pattern 1 (top of U).
  - [[ai-development-facilitator]] — Pattern 2 (squeezed middle).
  - [[ai-data-analytics-provider]] — Pattern 3 (shoulder; largest cluster).
  - [[ai-deep-tech-researcher]] — Pattern 4 (bottom of U; structural lineage to H4).
  - [[wiener-traditional-it-archetypes]] — the pre-AI baseline triad Weber positions against.
  - [[ai-startup-count-crunchbase-2021-2026]] — 27.9k → 97k datapoint.
- **Patches (8):**
  - [[H1_L0-L7-ladder]] — added "Seller-side mirror" section pointing to Weber's four patterns.
  - [[H2_u-curve-of-value]] — added "Seller-side instantiation" section mapping all four Weber patterns onto the U; documents the mild counter-evidence to the strong "middle dies" form (the 30-startup Data Analytics Provider cluster).
  - [[H3_orthogonal-axes-under-priced]] — added "Seller-side empirical reinforcement"; Weber's 11 dimensions are the strongest activation evidence yet for H3.
  - [[H4_rl-specialization-value-pocket]] — added "Seller-side archetype lineage" paragraph; H4 sits inside the Deep Tech Researcher pattern with a 2026 substitution (does not train own base model).
  - [[ecosystem-business-archetypes]] — added "Companion taxonomy" section explaining how Choudary (horizontal) and Weber (BM) complement each other inside Axis 3.
  - [[middle-layer-defensibility]] — added "Seller-side population evidence" sharpening generic-middle-dies / workflow-embedded-middle-survives with Weber's cluster sizes.
  - [[distribution-moat]] — appended Weber-archetype framing to the "what doesn't qualify" section.
  - [[ai-skill-shortage-as-diffusion-bottleneck]] — added "Seller-side mirror" pointing at Deep Tech Researcher demand.
  - [[taker-shaper-maker]] · [[vertical-ai-orchestration]] · [[rl-apis]] — added one-line reverse references.
- **Hypothesis touches:** H1 modestly reinforced (gains its seller-side sibling). H2 qualitatively reinforced + empirically complicated (large viable middle cluster). H3 modestly activated (strongest evidence so far that orthogonal axes outperform ladder position). H4 lineage clarified (Deep Tech Researcher with 2026 base-model substitution).
- **Contradictions surfaced:**
  - The 30-startup [[ai-data-analytics-provider]] cluster is mild counter-evidence to the strong form of "middle dies." Resolution: H2 needs to distinguish *firm count* from *value-capture share*.
  - Weber et al. expected ethics as a salient dimension; taxonomy contains none. Worth a future-paper note.
- **Open questions surfaced (from Weber Table 4 / discussion §5):**
  - When is data not essential to value creation for AI startups?
  - How can AI startups create competitive advantage via AI model leadership?
  - What type of AI technology is easier to replicate than others?
  - At least the first three intersect with active project questions on [[value-capture]] and [[distribution-moat]]; should be folded into [[05_open-questions]] on next pass.
- **2021 → 2026 vintage caveat documented:** Foundation-model commoditization has reshaped AI Development Facilitator pattern; a plausible fifth pattern (agentic-workflow providers) may need adding on next refresh.
- **Source moved** to `raw/ingested/`.
- **Next:** `/lint` to verify reverse-link integrity; consider promoting the four Weber open questions into [[05_open-questions]] entries.

## [2026-05-24] visualize | weber-ai-startup-taxonomy
- Output: outputs/weber-ai-startup-taxonomy.html
- Two synced views of the Weber et al. (2021) 4-category / 11-dimension / 39-characteristic taxonomy:
  - (01) Morphological box — chips, multi-select per dimension, sticky "your model" recipe bar, hover tooltips.
  - (02) Radial mind map — all 39 characteristics around the perimeter; selected leaves and the radial path back through their dimension/category/root highlight in accent.
- 4 archetype quick-loads (ACPS / ADF / ADAP / ADTR) preload canonical patterns.
