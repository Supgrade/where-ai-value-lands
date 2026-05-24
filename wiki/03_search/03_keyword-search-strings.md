---
title: Keyword Search Strings — arXiv & EBSCO
status: draft
tags:
  - search
  - keywords
  - boolean
  - arxiv
  - ebsco
last-updated: 2026-05-21
---

# Keyword Search Strings — arXiv & EBSCO

Ready-to-paste boolean strings for the five thematic areas in [[01_source-list]]. Each area has: a concept-block table, two strings (narrow + broad), and database-specific notes for arXiv and EBSCO Business Source Complete.

> [!tip] How to use
> Run **String B (broad)** first. If results > 300, switch to **String A (narrow)**. If results < 20, expand OR blocks or remove one AND condition. Log every run in `04_search-log.md` (to be created after first pilot).

> [!note] Syntax reminder
> - **arXiv:** field codes `ti:` (title), `abs:` (abstract), `AND / OR / ANDNOT`. Wrap phrases in double quotes. No truncation wildcard — spell out variants.
> - **EBSCO:** field codes `TI` (title), `AB` (abstract), `SU` (subject heading). Truncation with `*`. Wrap phrases in double quotes. Combine with `AND / OR / NOT`.

---

## Area 1 — Vision & AI Trajectory

*Target: understand how the AI stack is conceptualized and what the long-run trajectory claims are.*

### Concept Blocks

| Block | Core Terms | Synonyms / Alternatives |
|---|---|---|
| AI system framing | artificial general intelligence, large language model, foundation model | LLM, AGI, AI stack, AI architecture |
| Trajectory / capability | AI capabilities, AI progress, AI scaling, emergent behavior | scaling laws, capability frontier, intelligence explosion |
| Economic / social implication | AI transformation, AI disruption, future of software | software 3.0, AI-driven economy, technology transition |

### String A — Narrow (high precision)

**arXiv:**
```
ti:("foundation model" OR "large language model") AND abs:("AI stack" OR "AI architecture" OR "software transformation") AND abs:("economic impact" OR "technology transition")
```

**EBSCO:**
```
TI("foundation model" OR "large language model") AND AB("AI stack" OR "AI capabilities" OR "software disruption") AND AB("economic impact" OR "technology transition" OR "digital transformation")
```

### String B — Broad (high recall)

**arXiv:**
```
abs:("large language model" OR "foundation model" OR "AGI" OR "artificial general intelligence") AND abs:("AI trajectory" OR "AI capabilities" OR "scaling" OR "AI transformation")
```

**EBSCO:**
```
AB("large language model" OR "foundation model" OR "artificial general intelligence") AND AB("AI capabilities" OR "technology transition" OR "AI transformation" OR "future of AI")
```

### Database Notes
- **arXiv sections:** `cs.AI`, `cs.LG`, `cs.CL` — most relevant; check `econ.GN` for socioeconomic framing papers
- **EBSCO subject filters:** add Subject Heading `Artificial intelligence — Economic aspects` or `Technology and civilization`
- **Date range:** 2022–2025 preferred; pre-2022 useful for historical analogy framing only

---

## Area 2 — Economics, Strategy & Value Distribution

*Target: peer-reviewed work on AI industry structure, margin distribution, platform economics, and the U-curve / commoditization dynamic.*

### Concept Blocks

| Block | Core Terms | Synonyms / Alternatives |
|---|---|---|
| Value / margin | value distribution, economic surplus, profit margin, rent capture | value capture, economic rent, margin compression |
| AI industry structure | AI platform, AI market structure, AI industry, AI ecosystem | AI supply chain, AI stack economics, AI vertical integration |
| Platform / aggregation | platform economics, aggregation theory, network effects, market concentration | two-sided market, digital platform, winner-take-all |
| Commoditization | commoditization, price competition, open-source disruption | margin erosion, competitive pressure, undifferentiated |

### String A — Narrow

**arXiv:**
```
ti:("AI platform" OR "AI market" OR "AI industry") AND abs:("value distribution" OR "profit margin" OR "market concentration" OR "platform economics")
```

**EBSCO:**
```
TI("artificial intelligence" OR "AI platform" OR "AI ecosystem") AND AB("value distribution" OR "economic surplus" OR "market concentration" OR "platform economics") AND AB("commoditization" OR "margin" OR "competitive advantage")
```

### String B — Broad

**arXiv:**
```
abs:("AI market" OR "AI platform" OR "AI industry structure") AND abs:("value capture" OR "economic rent" OR "margin" OR "commoditization" OR "network effect")
```

**EBSCO:**
```
AB("artificial intelligence" OR "machine learning" OR "generative AI") AND AB("platform economics" OR "value capture" OR "market structure" OR "competitive advantage" OR "commoditization") AND AB("industry" OR "firm" OR "market")
```

### Database Notes
- **arXiv sections:** `econ.GN`, `cs.GT` (game theory), `econ.IO` (industrial organization) — IO papers most relevant for market structure
- **EBSCO subject filters:** Business Source Complete — filter by Business / Economics journals; add `Strategic Management Journal`, `Management Science`, `Information Systems Research` to journal list
- **Extra string for platform economics specifically (EBSCO):**
  ```
  AB("platform" OR "two-sided market" OR "aggregation") AND AB("artificial intelligence" OR "digital economy") AND AB("value" OR "margin" OR "rent")
  ```

---

## Area 3 — Technical Frontier: Agents, Models & Open Source

*Target: empirical and technical work on AI agents, orchestration layers, open-weight model economics, and edge/on-device AI.*

### Concept Blocks

| Block | Core Terms | Synonyms / Alternatives |
|---|---|---|
| Agents | AI agent, autonomous agent, coding agent, AI assistant | agentic AI, multi-agent system, LLM agent |
| Orchestration | AI orchestration, agent framework, workflow automation | task planning, tool use, chain-of-thought, ReAct |
| Open source / open weight | open-source LLM, open-weight model, model democratization | Llama, Mistral, open model, model commoditization |
| Edge / deployment | edge AI, on-device AI, model compression, inference efficiency | federated learning, local inference, small language model, SLM |

### String A — Narrow

**arXiv:**
```
ti:("AI agent" OR "autonomous agent" OR "LLM agent") AND abs:("orchestration" OR "tool use" OR "workflow") AND abs:("open-source" OR "open-weight" OR "deployment")
```

**EBSCO:**
```
TI("AI agent" OR "autonomous agent" OR "intelligent agent") AND AB("orchestration" OR "workflow automation" OR "task planning") AND AB("open-source" OR "model deployment" OR "edge computing")
```

### String B — Broad

**arXiv:**
```
abs:("AI agent" OR "agentic AI" OR "multi-agent" OR "LLM agent") AND abs:("open-source" OR "open-weight" OR "orchestration" OR "edge AI" OR "on-device")
```

**EBSCO:**
```
AB("AI agent" OR "autonomous agent" OR "intelligent agent" OR "agentic") AND AB("open-source" OR "open-weight" OR "edge computing" OR "model deployment" OR "small language model")
```

### Database Notes
- **arXiv sections:** `cs.AI`, `cs.MA` (multi-agent systems), `cs.CL` — run all three; `cs.NI` (networks) for edge
- **EBSCO coverage note:** arXiv is the primary source here — most cutting-edge agent work is preprint-first. EBSCO/conference proceedings (AAAI, NeurIPS, ICML) are the peer-reviewed complement
- **Additional arXiv string for open-weight economics:**
  ```
  abs:("open-source model" OR "open-weight" OR "model democratization") AND abs:("economic" OR "cost" OR "commoditization" OR "competition")
  ```

---

## Area 4 — Skeptics & Bear Case

*Target: empirical work on AI productivity effects, ROI evidence, labor displacement, and structural critiques of AI transformation claims.*

### Concept Blocks

| Block | Core Terms | Synonyms / Alternatives |
|---|---|---|
| Productivity / ROI | AI productivity, AI return on investment, AI adoption, AI value | AI business value, AI implementation, technology ROI |
| Labor / employment | labor displacement, automation and employment, AI and jobs | task automation, worker substitution, skill-biased technology change |
| Critique / limitations | AI limitations, AI failure, AI overhype, AI risks | AI hype, AI disappointment, AI capability gap |
| Macroeconomic | AI and GDP, AI and growth, AI and inequality | technology and productivity, innovation and growth, digital divide |

### String A — Narrow

**arXiv:**
```
ti:("AI productivity" OR "AI return on investment" OR "AI adoption") AND abs:("empirical" OR "evidence" OR "measurement") AND abs:("limitation" OR "failure" OR "gap" OR "inequality")
```

**EBSCO:**
```
TI("artificial intelligence" OR "automation") AND AB("productivity" OR "return on investment" OR "economic impact") AND AB("empirical" OR "evidence" OR "labor" OR "employment" OR "inequality")
```

### String B — Broad

**arXiv:**
```
abs:("AI productivity" OR "AI adoption" OR "AI impact") AND abs:("labor" OR "employment" OR "GDP" OR "economic growth" OR "return on investment" OR "ROI")
```

**EBSCO:**
```
AB("artificial intelligence" OR "automation" OR "machine learning") AND AB("productivity" OR "labor market" OR "employment" OR "GDP" OR "economic growth" OR "skill") AND AB("empirical" OR "evidence" OR "study" OR "analysis")
```

### Database Notes
- **EBSCO:** Business Source Complete + EconLit combination recommended; EconLit is strongest for labor economics papers (Acemoglu-type work)
- **arXiv sections:** `econ.GN`, `econ.LB` (labour economics) — add `cs.CY` (computers and society) for critique pieces
- **Suggested journal filter for EBSCO:** `Quarterly Journal of Economics`, `American Economic Review`, `Journal of Economic Perspectives`, `Management Science`

---

## Area 5 — Geopolitics & Governance

*Target: work on AI policy, US-China AI competition, EU regulation, and the geopolitics of AI infrastructure and sovereignty.*

### Concept Blocks

| Block | Core Terms | Synonyms / Alternatives |
|---|---|---|
| Geopolitics / competition | AI geopolitics, US China AI, AI competition, technology race | AI arms race, semiconductor rivalry, AI nationalism |
| Regulation / governance | AI governance, AI regulation, AI policy, AI Act | AI ethics regulation, algorithmic accountability, AI safety law |
| Sovereignty / blocs | AI sovereignty, digital sovereignty, AI fragmentation | technological sovereignty, AI blocs, AI de-coupling |
| Infrastructure | AI infrastructure, semiconductor supply chain, AI compute | chip supply chain, GPU export controls, data center geopolitics |

### String A — Narrow

**arXiv:**
```
ti:("AI governance" OR "AI regulation" OR "AI policy") AND abs:("geopolitics" OR "US China" OR "sovereignty" OR "European Union") AND abs:("competition" OR "fragmentation" OR "regulatory")
```

**EBSCO:**
```
TI("artificial intelligence" AND ("governance" OR "regulation" OR "policy")) AND AB("geopolitics" OR "US China" OR "digital sovereignty" OR "European Union") AND AB("competition" OR "market" OR "regulation")
```

### String B — Broad

**arXiv:**
```
abs:("AI governance" OR "AI regulation" OR "AI policy" OR "AI geopolitics") AND abs:("China" OR "European Union" OR "sovereignty" OR "semiconductor" OR "export control")
```

**EBSCO:**
```
AB("artificial intelligence" OR "AI") AND AB("governance" OR "regulation" OR "policy" OR "geopolitics") AND AB("China" OR "United States" OR "European Union" OR "sovereignty" OR "competition")
```

### Database Notes
- **EBSCO:** add Political Science database or PAIS Index for policy/governance papers
- **arXiv sections:** `cs.CY` (computers and society) is the primary section for AI governance preprints; also check `econ.GN`
- **Complementary databases:** SSRN is strong for AI policy working papers (especially law + economics intersection); worth a separate search run
- **Suggested journals (EBSCO):** `Regulation & Governance`, `Global Policy`, `Telecommunications Policy`, `Journal of Information Technology & Politics`

---

## Calibration Thresholds

| Result count | Action |
|---|---|
| > 300 results | Switch from String B to String A; restrict to `TI` / `ti:` fields only; add date filter |
| 50–300 results | Proceed to title/abstract screening |
| 20–50 results | Acceptable but check if a block is too restrictive; consider expanding one OR list |
| < 20 results | Switch to String B; widen date range; remove one AND block |

---

## Related
- [[01_source-list]] — source map these strings are built from
- [[02_deep-research-prompts]] — agent prompts for grey literature and podcast/interview sources
