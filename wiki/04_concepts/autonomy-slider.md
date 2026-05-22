---
title: The Autonomy Slider
status: emerging
tags:
  - concept
  - autonomy
  - agentic
  - design-pattern
last-updated: 2026-05-21
---

# The Autonomy Slider

> [!abstract] One-line
> Karpathy's framing of human-AI interaction as a **continuous spectrum** — from tap-completion (human writes, AI suggests) to full agentic autonomy (AI rewrites entire repositories with no human approval) — with the design choice being **where to fix the slider** for a given product or task.

## The spectrum (as Karpathy sketches it)

Anchored at the two ends:

- **Manual / tap-completion** — human writes code, AI completes the next token or line. Human approves every keystroke.
- **Inline assistant** — human in the IDE, AI proposes diffs, human accepts/rejects.
- **Goal-directed agent** — human gives a goal, AI loops on prompt → tool → observe → repeat with intermittent checkpoints.
- **Fully autonomous** — AI plans, executes, modifies its own code, and ships, with human reviewing only after the fact (or never).

The slider is **not destiny**: it's a product-design knob set differently per use case.

## The "Iron Man suit" — partial autonomy as default

Karpathy's prescriptive claim: today's LLMs are too **fallible, gullible, and prone to hallucinations** to be trusted across the full slider. The right default is **partial autonomy** — build products like an Iron Man suit, not an autonomous robot:

- AI generates output fast.
- Specialized **GUIs designed to exploit the human visual cortex** (e.g. side-by-side diffs in Cursor, source-cited answers in Perplexity) let humans verify rapidly.
- The bottleneck is no longer AI generation; it's **human verification speed**, so the UI is optimized for that.

Cursor, Perplexity, and similar tools succeed because they do *not* expose the raw LLM "OS" — they orchestrate multiple LLM calls and present a custom verification surface.

## Where the claim comes from
[[karpathy-software-3]]. Corroborated by Peter Steinberger inside the same source: Steinberger frames the "agentic trap" as novice developers trying to skip the slider entirely and automate everything with monolithic prompts.

**Vertical-industrial corroboration.** [[deloitte-ai-dossier-eri]] restates the Iron Man Suit imperative in physical-infrastructure terms: "AI models simulating reservoir drilling or field safety must have escalation paths… for manual review." In ER&I, the slider cannot reach full autonomy not because the AI cannot act, but because **someone must be on the hook** when the AI acts wrongly on a pipeline, a grid, or a drilling decision. The constraint is liability allocation, not just engineering reliability.

## Relationship to [[H1_L0-L7-ladder]]
The autonomy slider and the L0–L7 ladder are **distinct but correlated axes**:

- **L0–L7** = who owns the substrate (chat → IDE → orchestrator → sandbox → fleet → model → datacenter).
- **Autonomy slider** = how much human-in-the-loop oversight there is at each step.

A product can be **high on the ladder, low on the slider** (own your own GPUs but require human review on every action) or **low on the ladder, high on the slider** (run autonomous agents on someone else's cloud). The two should likely be treated as orthogonal axes — cf. [[H3_orthogonal-axes-under-priced]].

## Tensions inside the framing
- **Karpathy vs. Steinberger inside the same source.** Karpathy says the optimal product is the verification GUI (Iron Man suit). Steinberger predicts agents will **eliminate 80% of apps** by talking directly to endpoints, making human-facing GUIs redundant. These two are not reconciled.
- **The slider is asymmetric over time.** Where the slider lands is an engineering choice today, but Huang's [[agentic-scaling-law]] argues test-time compute will *push the slider rightward* automatically as reasoning improves. Karpathy's "Iron Man" phase may be a transitional design pattern, not a permanent equilibrium.
- **The slider treats reliability as a smooth knob, but reliability is bimodal in safety-critical domains.** A 99% autonomous agent is not 99% of a 100% autonomous one — it's catastrophic. The slider framing under-weights threshold effects.

## Why this matters for *Where Value Lands*
- Suggests that the **defensibility of "top of the U"** depends on whether verification GUIs remain valuable. If Steinberger is right, the application layer collapses; if Karpathy is right, the application layer is exactly where moats live.
- Reframes "agents" not as a single category but as a slider position. A lot of confused capital flows ([[circular-ai-economy]]) come from treating "agents" as one thing instead of as a design choice.

## Open questions
- Empirically, which slider positions have **shipped durably profitable products** as of 2026? Mostly toward the manual end (Cursor, Copilot) — does this validate Karpathy's claim or just say we're early?
- Are there domains where the slider naturally lives at full autonomy (well-bounded data pipelines, log triage, code formatting) vs. domains where it must stay low (legal, medical, finance)?

## Related
- [[karpathy-software-3]]
- [[software-3-paradigm]]
- [[llm-as-operating-system]]
- [[agentic-scaling-law]]
- [[H1_L0-L7-ladder]]
- [[H2_u-curve-of-value]]
- [[scaling-wall]]
- [[deloitte-ai-dossier-eri]] — vertical-industrial restatement of the Iron Man Suit imperative.
- [[agentic-revolution]] — the slider gates the deployment of agentic systems in high-stakes verticals.
- [[vertical-ai-orchestration]] — where slider position interacts with liability allocation in industrials.
- [[fusion-skills]] — workforce-capability counterpart of the slider; what humans need to actually be the verification bottleneck.
- [[non-tech-digital-core-synthesis]] — secondary restatement of the Iron Man Suit framing for non-tech enterprises.
- [[oecd-sme-adopter-taxonomy]] — the SME buyer-side taxonomy distinguishes off-the-shelf use from custom/frontier; the latter typically requires advancing further along the autonomy slider.
- [[sme-novice-off-the-shelf-llm]] · [[sme-explorer-custom-agent]] · [[sme-champion-vertical-ai]] — case patterns at progressively higher autonomy positions.
