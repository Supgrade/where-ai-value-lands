---
title: OECD SME Adopter Taxonomy (Novices / Optimisers / Explorers / Champions)
status: concept
target_folder: wiki/04_concepts/
tags:
  - adoption
  - sme
  - framework
  - taxonomy
last-updated: 2026-05-22
---

# OECD SME Adopter Taxonomy

A four-quadrant typology of SME AI adopters proposed by [[oecd-sme-ai-adoption-2025]]. Crossed on **two axes** — *complexity of AI use* and *scope of AI application* — and shaded by a **third dimension**, *digital maturity*, that runs diagonally across both. It is the SME-specific analogue of the large-firm [[enterprise-adoption-ladder]].

## The two axes

**Complexity of AI use** (x-axis, five steps from low to high):

| Level | Marker | Example |
|-------|--------|---------|
| None | No AI in any capacity | Family logistics firm on paper-based systems |
| Embedded | Built-in AI features in everyday digital tools, often unnoticed | Word grammar correction; email spam filter |
| Off-the-shelf | Public AI tools (ChatGPT, Gemini, Midjourney) used directly | Tourism SME drafting multilingual marketing copy with Llama |
| Customised | Models trained on proprietary data or fine-tuned for sector | B2B retrieval / generative stack on Cohere; clinical-triage fine-tune |
| Frontier | State-of-the-art systems in business-critical workflows; multimodal / agentic | Consulting firm with multimodal pipelines; agents autonomously managing ad campaigns |

**Scope of AI application** (y-axis, five steps from narrow to broad):

| Level | Marker | Example |
|-------|--------|---------|
| None | No strategic or operational use | Pharmacy on paper records |
| Isolated | Single use case by one team; PoC | Chatbot for FAQs, no integration |
| Functional | Multiple discrete tasks in a small number of functions | Marketing agency drafting content + visuals, no co-ordinated workflow |
| Cross-functional | Multiple tools across most departments, with shared data + governance | Online retailer running Claude, Midjourney, Shopify-integrated analytics |
| Enterprise-wide | AI embedded in virtually all functions, driving strategy + operations | Insurer with AI across underwriting, claims, retention, pricing |

**Digital maturity** is the diagonal shading. It is both a *precondition* for moving up either axis and a *consequence* of doing so — successful AI adoption raises a firm's digital maturity, which in turn enables the next step.

## The four quadrants

| Quadrant | Complexity | Scope | What it looks like |
|----------|------------|-------|--------------------|
| **AI Novices** | Embedded / Off-the-shelf | Isolated / Functional | Off-the-shelf LLMs in single workflows; experimental. Built on prior digital-tool experience. |
| **AI Optimisers** | Off-the-shelf | Cross-functional | Wide variety of off-the-shelf tools across departments; growing co-ordination but no custom models. |
| **AI Explorers** | Customised / Frontier | Isolated / Functional | Bespoke models or agentic workflows in *narrow* niches; data-intensive sectors (manufacturing, ICT) dominate. |
| **AI Champions** | Customised / Frontier | Cross-functional / Enterprise-wide | AI embedded across operations and strategy; advanced LLMs, NLP, computer vision underpinning both product and internal processes. |

Two implicit corners sit outside the taxonomy:
- **Non-users** — bottom-left, no AI at all. Need awareness-and-information policy, not adoption policy.
- **AI-first firms** — top-right, AI is the product. Drive innovation, not the policy focus of the SME blueprint.

The policy-relevant population sits in the **broad middle** of the matrix.

## How it relates to the other axes in this wiki

| Axis | What it measures | What it answers |
|------|------------------|-----------------|
| [[H1_L0-L7-ladder]] | Substrate ownership | Who owns the stack? |
| [[autonomy-slider]] | Human↔agent control | How much does the agent decide? |
| [[enterprise-adoption-ladder]] | Org maturity (large firms) | How deeply has the firm absorbed AI? |
| [[oecd-sme-adopter-taxonomy]] | **Complexity × Scope** (SME-specific) | What is the firm doing with AI, and how broadly? |
| [[taker-shaper-maker]] | Position relative to the model | Renting / customizing / training? |

The OECD SME taxonomy is **not** a fourth orthogonal axis — it is closer to a **two-axis decomposition** of the same maturity dimension that the WEF/Accenture five-phase ladder collapses into one number. It is structurally richer for the SME population because it distinguishes "wide-but-shallow" (Optimisers) from "deep-but-narrow" (Explorers) — a distinction the linear ladder cannot make.

## Mapping to taker-shaper-maker

The mapping is approximate but instructive:

- **Novices and Optimisers** → **Takers.** They rent off-the-shelf models; no proprietary customization.
- **Explorers** → **Shapers.** They customize models on proprietary data; the model itself is still rented.
- **Champions** → **Shapers or (rarely) Makers.** Most stay in the Shaper layer; only a small fraction (often deeply technical, often AI-first) cross into Maker.

Read with [[taker-shaper-maker]]: the OECD taxonomy *names the population* that the WEF typology *strategizes for*. Most SMEs are Novices/Optimisers — i.e., Takers — and the bull-managerial frame's pathway is to lift them into Shapers / Optimisers-with-customization. That pathway is exactly the consultancy commercial interest [[taker-shaper-maker]] flags.

## What this taxonomy adds that L0-L7 misses

- **The SME-specific failure mode of "wide but shallow"** (Optimisers): comfortable with many off-the-shelf tools across departments, but never crossing into custom or core-business use. Most generative-AI-using SMEs sit here; only 29% report core-activity use.
- **The barrier between Functional and Cross-functional scope** — likely the SME analogue of the [[scaling-gap]] (74% stuck between Phase 2 and Phase 3 on the enterprise ladder). Pre-Cross-functional, AI is decoration; post-Cross-functional, it is operational.
- **The Explorer corner** as a distinct strategic position: deep customization in narrow niches. Often missing from the WEF/Accenture framing, which assumes maturity = breadth.

## What it hides

- **No vendor / substrate axis.** A Champion running everything on Anthropic's API and a Champion running its own fine-tuned weights both appear in the same quadrant. The [[H1_L0-L7-ladder]] is the complement.
- **No surplus-capture axis.** The taxonomy describes *adoption posture*, not *who captures value*. A Champion paying $1M/month to OpenAI is a different economic actor from a Champion that has built proprietary data assets it monetizes. [[H2_u-curve-of-value]] is the complement.
- **No distribution / market axis.** A B2C Optimiser with millions of users and a B2B Champion with five clients look comparable in the matrix and incomparable in cash flow.

## Use in the paper

The taxonomy is the **buyer-side substrate** of the white paper's argument. Section 4 of the OECD source ties each quadrant to its dominant barrier (Novices need awareness + skills; Optimisers need data integration; Explorers need compute + talent; Champions need finance + scale). For our paper, the taxonomy is the natural decomposition of the SME population that the U-curve must address — it forces the paper to be specific about *which* SME population it is talking about when it asks where value lands.

## Related

- [[oecd-sme-ai-adoption-2025]] — primary source.
- [[sme-ai-adoption-gap]] — the empirical gap this taxonomy structures.
- [[enterprise-adoption-ladder]] — large-firm 5-phase parallel.
- [[H1_L0-L7-ladder]] — substrate-ownership axis the taxonomy is silent on.
- [[taker-shaper-maker]] — strategic-positioning axis the taxonomy decomposes for SMEs.
- [[H2_u-curve-of-value]] — surplus-capture question the taxonomy cannot answer alone.
- [[scaling-gap]] — the intra-firm pilot-to-scale gap; the OECD taxonomy makes visible an SME analogue.
- [[foundational-enablers]] — the four enablers tied to each quadrant.
- [[diffusion-vs-innovation]] — the SME taxonomy charts the literal substrate of the diffusion S-curve.
- [[autonomy-slider]] — orthogonal axis on human↔agent control.
- [[digital-core]] — the architectural precondition implicit in "digital maturity".
- [[sme-novice-off-the-shelf-llm]], [[sme-optimiser-cross-functional-stack]], [[sme-explorer-custom-agent]], [[sme-champion-vertical-ai]] — illustrative case-pattern pages drawn from the OECD case studies.
