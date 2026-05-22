---
title: Analytical Vocabulary
status: draft
tags:
  - planning
  - vocabulary
  - framework
last-updated: 2026-05-22
---

# Analytical Vocabulary

This page is the project's glossary of analytical terms. Before writing anything — a wiki page, a section of the paper, a PR description — consult this page to use the right word. Vocabulary drift is the fastest way to make the research incoherent.

> [!note] Why this page exists
> The research uses at least six independent analytical frameworks simultaneously. Each framework has its own vocabulary. "Layer," "level," "tier," "dimension," "archetype," and "axis" are not interchangeable. This page locks down what each word means in this project.

---

## The six analytical axes

A given organization or product has a coordinate on all six axes simultaneously. The paper's analytical work is, in large part, plotting coordinates and comparing them.

---

### Axis 1 — Stack Layer
**Question it answers:** *Where in the technical system does this sit?*

The AI stack has five horizontal layers, from bottom to top:

| Layer name | What it contains | Examples |
|---|---|---|
| **Infrastructure layer** | Silicon, energy, datacenter, networking | NVIDIA GPUs, Azure data centers, nuclear PPAs, custom ASICs |
| **Foundation model layer** | Weights, training runs, inference APIs | GPT-4o, Claude 3, Mistral, Llama 3 |
| **Orchestration layer** | Agents, workflows, multi-agent systems, memory, tool-calling | LangGraph, LlamaIndex, custom agent frameworks, n8n |
| **Application layer** | SaaS products, vertical tools, integrations, domain-specific deployments | Harvey, Glean, Cursor, Otter.ai, custom enterprise apps |
| **Interface / distribution layer** | UX, brand, direct user relationship, workflow lock-in | Cursor's IDE, Perplexity's search box, ChatGPT's consumer app |

**Correct usage:**
- "The infrastructure layer" ✓
- "The application layer" ✓
- "Moving up the stack" ✓
- "Infrastructure layer" = the bottom, not "Level 0" ✗

**Do not call stack layers "levels."** Levels belong to Axis 2.

Note: The interface/distribution layer and the application layer often overlap. The distinction is: the application layer is where the *function* lives; the interface/distribution layer is where the *user relationship* lives. Cursor is an application; Cursor's IDE integration is its interface/distribution asset.

---

### Axis 2 — Autonomy Level
**Question it answers:** *How much of the work does the AI do without a human in the loop?*

Described by [[H1_L0-L7-ladder]]. Eight positions, L0 to L7:

| Level | Name | What it means |
|---|---|---|
| L0 | Human as API | Copy-paste from chat; user moves data between model and world |
| L1 | AI inside existing tools | Inline assistance; still synchronous, HITL |
| L2 | Deterministic workflows with AI nodes | Hand-designed graph; AI is a function inside |
| L3 | Agent decides for itself | Non-deterministic loop; human gives goal, agent picks steps |
| L4 | Agent in dedicated sandbox, always on | Agent has its own runtime; works while user is away |
| L5 | Fleet of collaborating agents | Orchestrator + N workers; bottleneck is review, not execution |
| L6 | Vertical: model + compute owned | Inference is an asset, not a bill |
| L7 | Intelligence as commodity, energy included | Full vertical — produce energy, run model, sell output |

**Correct usage:**
- "Operating at L3" ✓
- "An L4-level deployment" ✓
- "The ladder" (referring to L0–L7) ✓
- "The L3 layer" ✗ — it is a level, not a layer

**Relationship to Axis 1:** A product's stack layer and its autonomy level are independent. Cursor sits in the application layer (Axis 1) and enables L1–L3 work (Axis 2). An L5 fleet can be built entirely on the application layer using rented APIs.

---

### Axis 3 — Business Archetype
**Question it answers:** *What type of organization is this? How does it capture margin?*

Fifteen archetypes identified so far. Each archetype combines: what the organization does, where it primarily sits in the stack, and its characteristic margin-capture mechanism.

| Archetype | Primary stack layer | Margin mechanism | Solopreneur-accessible? |
|---|---|---|---|
| Foundation model lab | Foundation model | API + subscription | No |
| Hyperscaler AI services | Infrastructure | Compute consumption | No |
| AI developer tools | Interface/distribution | Subscription; editor lock-in | Possible at small scale |
| Vertical SaaS | Application | Subscription on deep workflow | Yes, with domain expertise |
| Consumer AI app | Interface/distribution | Freemium / B2C subscription | Yes; high competition |
| Deep tech startup | Orchestration–Application | IP + recurring SaaS or licensing | Hard; requires R&D runway |
| Forward-deployed / embedded engineering | Application–Orchestration | High-value retainer; embeds in one client | Yes; small team model |
| AI agency | Application | Services margin on AI-assisted delivery | Yes; scale ceiling is people + automation |
| Boutique AI consulting | Interface | Pure advisory at C-suite | Yes; low leverage, high margin |
| Solo builder / micro-SaaS | Application | Subscription in a narrow niche | Primary path |
| Open source + enterprise | Foundation model–Application | Free core + enterprise tier | Yes; requires community |
| Data services | Foundation model | Labeling, cleaning, synthetic data | Yes at the top; labor-intensive at base |
| System integrator | Application | Project + managed services | Yes (small boutique form) |
| AI marketplace / platform | Interface/distribution | Hosting + marketplace cut | Hard; network-effect dependent |
| AI-augmented creator | Interface/distribution | Subscription + sponsorships + products | Yes; this research project is an example |

**Correct usage:**
- "The AI agency archetype" ✓
- "A micro-SaaS archetype" ✓
- "Which archetype best describes..." ✓
- "Business model" — acceptable in casual speech, but imprecise. "Business model" typically refers only to the *revenue mechanism* (subscription, API fees, etc.). "Archetype" names the full organizational form.

**Open question:** → [[05_open-questions]] — is "archetype" the right term, or should it be "value-capture pattern" or "firm type"?

---

### Axis 4 — Value Capture Position
**Question it answers:** *How much economic surplus does this position actually retain?*

Described by [[H2_u-curve-of-value]]. Three positions on the U:

| Position | What it means | Empirical examples |
|---|---|---|
| **Top of curve** | Distribution/workflow ownership; interface moat; user relationship | Cursor ($50B), Windsurf ($3B), vertical SaaS with data flywheel |
| **Squeezed middle** | Generic wrappers, undifferentiated orchestration, thin API proxies | Most "AI startups" from 2023–2024; agencies without proprietary workflow |
| **Bottom of curve** | Silicon, energy, frontier weights; capital-intensive, hard to replicate | NVIDIA, hyperscalers, OpenAI/Anthropic weights |

**Correct usage:**
- "A top-of-curve position" ✓
- "The squeezed middle" ✓
- "Bottom-of-curve economics" ✓

**Important:** H2 is a working hypothesis, not a confirmed law. See [[H2_u-curve-of-value]] for the full critique. The U may be an L (only the top matters) if the bottom is funded by recycled VC capital rather than durable enterprise demand.

**Relationship to Axis 3:** Each archetype *tends* toward a U-curve position, but the relationship is not deterministic. An AI agency can escape the squeezed middle if it builds genuine distribution moat; a vertical SaaS can fall into the middle if it becomes a thin wrapper.

---

### Axis 5 — Adopter Maturity
**Question it answers:** *How mature is the organization deploying AI?*

Two parallel taxonomies — one for enterprises, one for SMEs:

**Enterprise (Axis 5a):** [[enterprise-adoption-ladder]]
- Phase 1: Initial (isolated GenAI experiments)
- Phase 2: Thousand-flowers-bloom (multiple pilots, no integration)
- Phase 3: End-to-end (connected across a function)
- Phase 4: Enterprise-level (cross-functional transformation)
- Phase 5: Value-chain reinvention (ecosystem-level change)

**SME (Axis 5b):** [[oecd-sme-adopter-taxonomy]]
- Novice: Off-the-shelf LLMs for peripheral tasks
- Optimiser: Multiple off-the-shelf tools, cross-functional
- Explorer: Custom/frontier model in a narrow scope
- Champion: Custom/frontier across the organization

**Correct usage:**
- "A Phase 3 enterprise" ✓
- "A Champion-tier SME" ✓
- "The Optimiser segment" ✓
- "Tier" is correct here for the SME taxonomy; "Phase" for the enterprise ladder

---

### Axis 6 — Strategic Posture
**Question it answers:** *How does this organization relate to the AI ecosystem?*

Described by [[taker-shaper-maker]]:

| Posture | What it means | Relationship to AI |
|---|---|---|
| **Taker** | Rents the model; deploys off-the-shelf | Buys API access or SaaS |
| **Shaper** | Customizes the model; fine-tunes or orchestrates | Uses open weights or API + prompt engineering |
| **Maker** | Trains the model; builds from scratch | Foundation model labs, deep tech with custom training |

**Correct usage:**
- "A Shaper posture" ✓
- "Operating as a Taker" ✓
- "Maker-level commitment" ✓

---

## Vocabulary quick-reference

| Word | What it refers to | Never use it for |
|---|---|---|
| **Layer** | Horizontal slice of the technical stack (Axis 1) | Autonomy levels; maturity tiers |
| **Level** | Position on L0–L7 (Axis 2) | Stack layers; business types |
| **Archetype** | Type of business organization (Axis 3) | Revenue mechanism alone |
| **Business model** | Revenue mechanism (how money is charged) | Full organizational form (use "archetype") |
| **Curve position** | Location on the U-curve (Axis 4) | Stack position or business type |
| **Phase** | Enterprise adoption maturity stage 1–5 (Axis 5a) | SME maturity (use "tier") |
| **Tier** | SME adopter rank (Axis 5b) OR collaboration tier (T0–T4) | Enterprise maturity stages |
| **Posture** | Strategic orientation toward AI ecosystem (Axis 6) | Stack position |
| **Stack** | The full technical AI system | Any single axis |
| **Axis** | Any of the six analytical dimensions | A single concrete position |
| **Dimension** | Same as axis, preferred in formal writing | — |
| **Bloc** | Geopolitical cluster (US / China / EU) | Technical layer or business type |

---

## Sample coordinates

To make this concrete, here are two organizations fully plotted:

**Cursor:**
- Stack layer: Application layer + Interface/distribution layer
- Autonomy level: Enables L1–L3 in the developer's hands
- Business archetype: AI developer tools
- Curve position: Top of curve (distribution + workflow lock-in + data flywheel)
- Adopter maturity: N/A (Cursor is a supplier, not a buyer)
- Strategic posture: Shaper (builds on top of foundation models)

**A North Italian manufacturing SME deploying Copilot for drafting emails:**
- Stack layer: Interface layer (consuming a product built there)
- Autonomy level: L1 (AI inside an existing tool)
- Business archetype: N/A (not an AI business; it's an AI adopter)
- Curve position: N/A (as an adopter, not in the supply-side U)
- Adopter maturity: Novice (Axis 5b — off-the-shelf, peripheral)
- Strategic posture: Taker

---

## Open questions

See also [[05_open-questions]].

- [ ] Is "archetype" the final term, or should the paper use "firm type," "value-capture pattern," or something else? Decision needed before the glossary in Section 8.
- [ ] The interface/distribution layer and the application layer blur in practice. Does the paper need a cleaner distinction, or is the overlap acceptable?
- [ ] Axis 6 (Taker/Shaper/Maker) is used in WEF/Accenture material for enterprise buyers. Does it apply equally to AI-native suppliers (e.g., Cursor is a Shaper building for Makers)?
- [ ] Do all six axes appear explicitly in the paper, or are some collapsed? Candidate collapse: Axis 5 (adopter maturity) may only appear in Section 5 (Geographic split) and Section 6 (practical half).
- [ ] How do we handle organizations that span multiple archetypes (OpenAI = foundation model lab + developer tools + consumer app simultaneously)?

---

## Discussed in
- [[archetypes-vocabulary-personal-frame]]

## Related

- [[H1_L0-L7-ladder]] — the authoritative source for Axis 2.
- [[H2_u-curve-of-value]] — the authoritative source for Axis 4.
- [[H3_orthogonal-axes-under-priced]] — what the six-axis frame may still be missing.
- [[taker-shaper-maker]] — source for Axis 6.
- [[enterprise-adoption-ladder]] — source for Axis 5a.
- [[oecd-sme-adopter-taxonomy]] — source for Axis 5b.
- [[middle-layer-defensibility]] — sharpens the Axis 4 "squeezed middle" claim.
- [[distribution-moat]] — the mechanism behind top-of-curve positions.
- [[03_structure]] — where each axis appears in the paper.
