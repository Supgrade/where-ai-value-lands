---
title: Software 3.0 — The Three Paradigms of Computing
status: emerging
tags:
  - concept
  - paradigm
  - bull-frame
last-updated: 2026-05-21
---

# Software 3.0 — The Three Paradigms

> [!abstract] One-line
> Karpathy's framing that computing has moved through **three paradigms**: 1.0 (explicit code), 2.0 (neural-network weights), 3.0 (LLMs steered by natural-language prompts). 3.0 is currently absorbing parts of both 1.0 and 2.0.

## The three paradigms

- **Software 1.0.** Explicit, deterministic instructions written in languages like C++ or Python. The programmer encodes the rules.
- **Software 2.0.** Code is implicitly written by **optimizing weights** over a dataset. Fixed-function neural networks (image classifiers, perception stacks, etc.). The dataset and architecture together encode the rules.
- **Software 3.0.** LLMs as a new kind of programmable computer where **natural language (English) is the programming language**. The user steers behavior by writing prompts.

## The "eating" dynamic
Karpathy's empirical example is from Tesla Autopilot: as the neural network (2.0) improved, it cannibalized the C++ image-stitching logic (1.0). His claim is that 3.0 is now eating both — generic LLMs absorbing tasks previously handled by hand-tuned classifiers *and* by hand-written deterministic code.

## Where the claim comes from
[[karpathy-software-3]]. Corroborated within the same source by Jensen Huang's parallel framing — computing moving from "retrieval-based" (fetching stored files) to "generative-based" (generating tokens in real time) — and by Peter Steinberger's operational case ("agentic engineering") where natural-language voice prompts build self-modifying architectures.

## Why this matters for *Where Value Lands*
- Reframes the substrate of [[H1_L0-L7-ladder]]. The ladder talks about who owns the substrate (chat → IDE → orchestrator → sandbox → fleet → model → datacenter). The 1.0/2.0/3.0 frame asks **what kind of code runs on that substrate**. Both are needed: substrate ownership × paradigm = the actual stack.
- If 3.0 absorbs both lower paradigms, the **scope of "AI-eaten" surplus is much wider** than the bear case in [[bear-case-synthesis]] / [[task-based-framework]] accounts for — the Acemoglu task-share estimate (~19.9% exposure) was calibrated on classifier-era automation, not natural-language-programmable systems.
- But the absorption is **uneven and unverified**: 3.0 has not actually eaten safety-critical 1.0 (avionics, payments clearing, kernel code), and may not. The "eating" metaphor needs to be tested against domains, not asserted.

## Why this might be wrong
- The 1.0/2.0/3.0 sequence is a **clean story imposed retrospectively**. In practice, modern systems are hybrids (LLM + tool calls + deterministic guards + classifiers). Calling the hybrid "3.0" obscures more than it reveals.
- The "natural language as programming language" claim **understates the prompt-engineering / context-window discipline** actually required. Saying English is the language is like saying machine code is "just on-and-off switches."
- Periodization is **rhetorical**, not analytical — it builds momentum for a paradigm without specifying the falsifiable boundary between paradigms.

## Open questions
- Which production systems have actually had 1.0 code deleted in favor of 3.0 (not 2.0)? Karpathy's Tesla example is a 1.0 → 2.0 transition, not 1.0 → 3.0.
- Is the "paradigm" lens the right one, or is this better described as a tooling shift inside one continuous probabilistic-programming paradigm?
- What's the half-life of each paradigm? 1.0 has lasted 70 years and is still load-bearing.

## Related
- [[karpathy-software-3]]
- [[llm-as-operating-system]]
- [[autonomy-slider]]
- [[democratization-of-programming]]
- [[H1_L0-L7-ladder]]
- [[H2_u-curve-of-value]]
