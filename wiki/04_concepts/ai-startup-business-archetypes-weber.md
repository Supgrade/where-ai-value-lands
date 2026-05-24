---
title: AI Startup Business Archetypes (Weber et al. 2021)
status: established-framework
tags:
  - concept
  - taxonomy
  - business-models
  - classification
last-updated: 2026-05-24
---

# AI Startup Business Archetypes (Weber et al. 2021)

A four-pattern taxonomy of AI-startup business models, derived empirically from a 100-startup Crunchbase sample by [[weber-ai-startup-business-models]]. Sits parallel to [[ecosystem-business-archetypes]] (Choudary's horizontal taxonomy) and [[taker-shaper-maker]] (WEF buyer-side typology) — together these form the three off-the-shelf sub-vocabularies the project uses for [[H3_orthogonal-axes-under-priced]].

## The four archetypes (one-line each)

| Pattern | Definition | Sample share | Canonical example |
|---|---|---|---|
| [[ai-charged-product-service-provider]] | Products/services with **readily trained AI models embedded** — value delivered by the trained model itself, not by analyzing the customer's data | 26 / 100 | Overjet (dental X-ray analysis); Alegion (data-labeling) |
| [[ai-development-facilitator]] | Tools that help **other firms build their own AI** — SDKs, APIs, no-code workbenches, customizable chatbot platforms | 25 / 100 | BotXO (custom conversational AI); Hugging Face (NLP APIs) |
| [[ai-data-analytics-provider]] | Integrates and analyzes **vast data** (internal + external) for decision support; classical analytics with ML inside | 30 / 100 (largest) | Kubit (retention/profitability anomaly detection); Falkonry (sensor → machine-state) |
| [[ai-deep-tech-researcher]] | Research-led; develops **frontier AI tech for niche problems** (robotics, autonomous driving, drug discovery, neurotech); not yet standardized; often pre-revenue | 19 / 100 | Cerenion (brain-activity interpretation); Syrius Robotics (warehouse robots) |

## How to classify a startup (the salient-characteristic shortcut)

Weber et al. built an 11-dimension / 39-characteristic taxonomy (value proposition, value creation, value delivery, value capture), then clustered. For practical classification, the **salient characteristics** that separate one pattern from the others are usually enough:

```
Is the AI model already trained when delivered?
├─ Yes, standardized product → AI-charged Product/Service Provider
├─ No, customer trains via tools you provide → AI Development Facilitator
└─ AI runs over customer's own data, no embedded model → Data Analytics Provider

Is the technology itself the deliverable (not productized yet)?
└─ Yes → Deep Tech Researcher
```

The full discriminating-dimension table (data type, data source, hardware provision, customization level, customer, industry scope, revenue model) is in each pattern page's "Salient characteristics" section.

## Mapping to project hypotheses

- **[[H2_u-curve-of-value]] — where each pattern sits on the U:**
  - AI-charged Product/Service Provider → **top of U** (workflow-embedded, distribution-dependent). Cursor, Windsurf, Perplexity are 2026 instances of this pattern.
  - AI Development Facilitator → **the squeezed middle.** Generic SDKs and chatbot-builders are exactly what [[middle-layer-defensibility]] argues *fails* — except when distribution survives (Hugging Face).
  - Data Analytics Provider → **shoulder of U** (mature, profitable, but not where the new AI margin sits — closer to traditional [[ai-productivity-firm-level]] BI).
  - Deep Tech Researcher → **bottom of U** when the niche is genuinely defensible (frontier weights, robotics, biology). Closely related to [[H4_rl-specialization-value-pocket]].

- **[[H1_L0-L7-ladder]] — seller-side parallel:** the Weber taxonomy is a **seller-side** sibling of the ladder, which is mostly buyer/substrate-side. An AI-charged Product/Service Provider typically *sells* at L1–L2 of the buyer's stack; a Deep Tech Researcher *sells* the L4–L6 substrate.

- **[[H3_orthogonal-axes-under-priced]] — direct evidence.** The 11 dimensions Weber et al. extracted are exactly the kind of cross-cutting axes H3 names. Two startups at the same ladder position can sit in opposite Weber patterns.

## What Weber et al. argue is genuinely new about AI startup BMs

From the paper's discussion (§5):
1. **New value propositions** — shifting IT into the domain of **knowledge and service work** (replacing humans rather than streamlining backends).
2. **Different roles of data** — in the AI-charged P/S Provider pattern especially, data is used to *train an embedded model*, not to *generate insights*. This is the qualitative break from [[wiener-traditional-it-archetypes]] (data users / data suppliers / data facilitators).
3. **Technology-centered business logic** — not all AI startups are equally data-dependent. The pattern decides.

## 2021 → 2026 vintage shift (what has happened since)

The paper is December 2021 — pre-ChatGPT. Three things have shifted:

1. **Foundation-model commoditization.** Most of what was "AI Development Facilitator" in 2021 (custom NLP stacks, build-your-own-chatbot) has been eaten by the GPT-4 / Claude API surface. The pattern now mostly survives only where distribution + infra sticks (Hugging Face) — see [[middle-layer-defensibility]].
2. **Crunchbase AI-startup count.** Sept 2021: 27,900 → 2026: ~97,000 (≈3.5×). See [[ai-startup-count-crunchbase-2021-2026]].
3. **A fifth pattern is plausibly emerging in 2026:** *agentic-workflow providers* — startups that orchestrate multiple foundation-model calls into multi-step business workflows (Cursor's task agents, LangGraph apps, the [[vertical-ai-orchestration]] pattern from ER&I). The 2021 taxonomy folds these into "AI-charged Product/Service Provider", but the value-creation logic (action orchestration over [[context-control]]) is different enough that it may deserve its own pattern.

## Why this matters for the project

The user's stated goal at ingest was to enable **future-startup classification using this taxonomy** as new startups appear in the wiki. The four-pattern table above + the salient-characteristic decision tree are the operational classifier. Use it whenever a new AI-startup source is ingested, and tag the resulting source/concept page with the Weber pattern in its frontmatter (`weber-pattern: ai-charged-product-service-provider` etc.).

## See also
- [[weber-ai-startup-business-models]] — the source.
- [[ecosystem-business-archetypes]] — Choudary's parallel four-archetype taxonomy (horizontal-ecosystem lens, not AI-tech lens). The two read together cover Axis 3 of [[07_analytical-vocabulary]].
- [[taker-shaper-maker]] — WEF's three-archetype buyer-side typology.
- [[wiener-traditional-it-archetypes]] — the *pre-AI* IT-business-model triad (data users / suppliers / facilitators) the Weber paper positions itself against.
- [[H1_L0-L7-ladder]], [[H2_u-curve-of-value]], [[H3_orthogonal-axes-under-priced]], [[H4_rl-specialization-value-pocket]].
