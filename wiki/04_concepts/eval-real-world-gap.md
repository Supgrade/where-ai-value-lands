---
title: The Eval / Real-World Gap
status: emerging
tags:
  - concept
  - evaluation
  - reward-hacking
  - generalization
  - sutskever
last-updated: 2026-05-24
---

# The Eval / Real-World Gap

> [!abstract] One-line
> The paradox that modern LLMs **achieve superhuman scores on complex benchmarks** while **failing at basic iterative real-world tasks** — diagnosed by Sutskever ([[sutskever-age-of-research]]) as a structural consequence of "human reward hacking" by researchers over-optimising RL environments to pass the evals.

## The phenomenon

The canonical Sutskever example: an LLM identifies a bug in a codebase, introduces a second bug while fixing the first, and reverts to the original bug when corrected — entering an infinite loop of locally-logical-but-globally-incoherent edits ("vibe coding" failure mode). The model has near-saturated competitive-programming benchmarks but cannot execute the iterative debugging loop a junior engineer handles routinely.

The same pattern repeats across domains: high SWE-bench scores, brittle multi-turn behaviour; high math-olympiad scores, hallucinated arithmetic in spreadsheets; high agent-benchmark scores, costly real-world detours.

## Sutskever's diagnosis: reward hacking by researchers

Not by the model — by the humans optimising the model. RL training environments are constructed specifically to push benchmark scores. Researchers iterate on the environment, the reward shape, and the data mix until the eval climbs. The result is **narrow, fragile capability** indistinguishable from genuine generalisation *on the eval*, but exposed the moment the model meets a distribution the environment didn't anticipate.

This is the "two students" analogy Sutskever uses: a 10,000-hour competitive-programming memoriser vs a 100-hour deep-reasoning generaliser — both can ace the exam; only one survives the open-ended task.

## Cross-source corroboration

- **Karpathy's "jagged intelligence"** ([[karpathy-software-3]]) is the same observation at a different granularity: superhuman in narrow domains, sub-toddler nearby. The jaggedness is what eval scores hide.
- **Karpathy's "anterograde amnesia"** is one mechanism behind the gap — the model cannot accumulate context across the iterative loop the way a human can.
- **Steinberger's "agentic trap"** is the deployment-side manifestation: monolithic prompts and autonomous loops fail because the agent lacks deep system understanding that benchmarks cannot test.
- **[[scaling-wall]]'s compositionality failure** is a sub-case: the eval covers atomic skills; real tasks require composing them; composition is where it breaks.

## Why this matters for *Where Value Lands*

- **Caps the autonomy slider.** [[autonomy-slider]] argues humans must verify because the model is unreliable. The eval/real-world gap is the *empirical mechanism* of that unreliability — and it doesn't go away with more parameters, because it's a training-objective problem, not a capacity problem.
- **Reinforces the top of [[H2_u-curve-of-value]].** Products that succeed (Cursor, Perplexity, Windsurf) win not by having "better intelligence" but by **engineering verification surfaces around an unreliable engine**. The gap is the moat. See [[middle-layer-defensibility]].
- **Pressures the agent-economy thesis.** Multi-agent systems that score well on coordination benchmarks may still compound errors in real deployments. Pricing agentic infrastructure on benchmark performance is exactly the failure mode Sutskever describes.

## Why this might be wrong or overstated

- **Evals will improve.** The current generation of benchmarks (HumanEval, MMLU, SWE-bench) is a known-weak signal; the field is actively building more realistic, longer-horizon, adversarial evals. The gap may narrow as evaluation methodology improves rather than because models improve.
- **"Reward hacking by researchers" is a strong claim.** The same data is consistent with simpler explanations — long-tail distribution coverage, lack of iterative training signal, weak intermediate-step rewards. Sutskever's framing assigns blame; the mechanism may be more banal.
- **Some apparent failures are prompt-fragility, not capability gaps.** A model that loops in "vibe coding" with a naive harness may execute cleanly with proper scaffolding (test-time check loops, memory primitives). The gap is partly engineered, not intrinsic.

## Related

- [[sutskever-age-of-research]]
- [[continual-learning-paradigm]]
- [[value-functions-as-algorithmic-emotion]]
- [[scaling-wall]]
- [[karpathy-software-3]]
- [[autonomy-slider]]
- [[agentic-scaling-law]]
- [[middle-layer-defensibility]]
- [[H1_L0-L7-ladder]]
- [[H2_u-curve-of-value]]
- [[business-model-portfolio]] — Sutskever's "human reward hacking" is the AI-research instance of Westerveld's Dogmatic paradox.
- [[protschky-ml-monitoring-2025]] — operational decomposition of the gap: C2 (Metrics proxy) names the eval-real-world divergence as a structural property of every deployed ML application; Practices 8–11 (data-quality checks, drift detection, cause-effect, adaptation) are the production-time mitigations.
- [[ml-monitoring]] — the discipline whose entire premise is that the representation layer ≠ the real-world layer.
- [[ml-production-environment-characteristics]] — C1–C5 vocabulary; C2 is the operational instance of this concept.
