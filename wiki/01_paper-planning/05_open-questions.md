---
title: Open Questions
status: draft
tags:
  - planning
  - decisions
last-updated: 2026-05-21
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

## Business archetype taxonomy (added 2026-05-22)
The taxonomy emerged from the daily thought of 2026-05-22. Decisions needed:
- [ ] **Completeness** — are there archetypes missing from the current 15? Candidates: AI research lab (non-commercial, e.g., DeepMind inside Google), government / public-sector AI deployer, AI-enabled hardware company (e.g., Humane, Rabbit), embodied AI / robotics startup.
- [ ] **North Italian / SME archetype gap** — the taxonomy is currently US-stack-centric. The author's home market (North Italy, traditional SME industry) is an AI adopter, not an AI supplier. A 16th archetype may be needed: "traditional-industry AI integrator" — the type of firm the author is, and the type of firm reading the paper.
- [ ] **Archetype-to-U-curve mapping** — should the mapping of archetypes to H2 positions (top / squeezed middle / bottom) become a standalone wiki page or live inside [[H2_u-curve-of-value]]? It is currently a table in the annotated daily thought only.
