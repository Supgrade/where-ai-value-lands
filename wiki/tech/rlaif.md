---
title: RLAIF — Reinforcement Learning from AI Feedback
status: reference
tags:
  - tech
  - reinforcement-learning
  - alignment
last-updated: 2026-05-24
---

# RLAIF — Reinforcement Learning from AI Feedback

> [!abstract] One-line
> Replace the human preference labeler with a strong AI labeler (a "judge" model), often guided by a written constitution or rubric.

## The idea

Human preference labels are expensive and slow. If a sufficiently capable model agrees with human labelers 80–95% of the time on preference judgements, you can scale preference data by 100× by replacing the human step with the judge — and recover most of the signal at a fraction of the cost.

The judge is typically instructed via a **constitution** (a short written set of principles) or a domain-specific **rubric**. The training pipeline is otherwise the same as [[rlhf]]: pairwise preferences feed a Bradley-Terry reward model (or skip straight to DPO).

## How it works (sketch)

Same pipeline as [[rlhf]] with one substitution:

- Sample two completions from the candidate model.
- Ask the judge model: "Given these principles, which completion is better?" Optionally have the judge produce a short critique.
- Use the resulting `(prompt, A, B, judge_choice)` triples exactly as you would human-labeled preferences.

**Constitutional AI** (Anthropic, Bai et al., 2022) is the canonical variant: a model critiques and revises its own outputs against a written constitution, producing self-supervised preference pairs without a second judge model at all.

## A canonical example

Anthropic's **Constitutional AI** for the Claude family. **Llama-3** post-training used heavy AI-feedback in significant parts of the pipeline. Most recent open chat models lean on a hybrid: small amounts of high-quality human preference data anchoring a much larger pool of AI-generated preference data.

## Where this fits in *Where AI Value Lands*

This is the **cost-of-labels lever** for [[H4_rl-specialization-value-pocket]]. If a startup can use a frontier model as a cheap labeler over a customer's narrow process data, the unit economics of domain RL fine-tuning change significantly — labeling stops being the bottleneck, instrumentation does.

But two costs transfer:

- The **bias and capability ceiling of the judge model** flow into the trained model. A judge that systematically misjudges a niche domain bakes that misjudgement into every preference label.
- For tasks **no model has ever solved well**, the judge has no ground to stand on. Connect to [[eval-real-world-gap]]: a judge model may be a perfectly wrong evaluator for a genuinely novel task.

## Related

- [[rlhf]]
- [[rl-from-verifiable-rewards]]
- [[rl-data-preparation]]
- [[rl-testing-validation]]
- [[eval-real-world-gap]]
- [[H4_rl-specialization-value-pocket]]

## Referenced by

*Auto-generated reverse-link index — pages in the wiki that link here. Maintained by `/lint` and reverse-link sweeps.*
