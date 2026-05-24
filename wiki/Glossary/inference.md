---
title: Inference
status: stable
tags:
  - glossary
  - technical
last-updated: 2026-05-24
---

# Inference

The computational act of running a trained model forward to produce outputs — generating text, embeddings, or decisions from an input. Distinct from **training** (adjusting model weights on data from scratch) and **fine-tuning** (adapting weights on a smaller supervised or RL dataset).

## Why it matters here

Inference is the economic transaction at the center of the AI stack. Every API call, every Cursor suggestion, every agentic loop iteration is an inference event. Its cost, latency, and throughput shape the project's core arguments.

- **Bottom-of-U economics.** Inference infrastructure — GPUs, data centers, energy — is the capital-intensive substrate that [[ai-factory-huang]] frames as a tokens-per-second-per-watt manufacturing unit. It anchors the bottom of [[H2_u-curve-of-value]] and the lowest rungs of [[H1_L0-L7-ladder]].
- **Jevons dynamics.** Cheaper inference per token historically expands total inference volume rather than contracting it. See [[jevons-paradox-ai]].
- **Test-time compute.** [[agentic-scaling-law]] argues that more inference per query — chain-of-thought, multi-agent loops, verifiable-reward checks — substitutes for pre-training scale. This is the primary counter-argument to [[scaling-wall]].
- **Sovereign tension.** Running inference locally versus in a foreign cloud is the operational axis behind [[sovereign-ai]] policy.

## Variants

| Type | Description |
|---|---|
| **Cloud inference** | API call to a hosted model (OpenAI, Anthropic, Google). Billed per token. |
| **On-premise / edge inference** | Model runs on local hardware. Higher fixed cost; no per-token bill; latency and data-sovereignty advantages. |
| **Test-time compute** | Deliberately extended inference — more tokens, multiple reasoning steps, tool calls — to trade compute for accuracy at query time. The mechanism behind o1-class and R1-class reasoning models. |
| **Batch inference** | Asynchronous processing of many inputs; cheaper per token, higher latency. Standard for bulk data pipelines. |

## In the analytical vocabulary

In [[07_analytical-vocabulary]], inference infrastructure sits at the **Infrastructure layer** (Axis 1) and is consumed by operators at every autonomy level (L0–L7, Axis 2). As inference commoditizes, margin pressure increases at the Foundation model layer — the mechanism compressing the middle of [[H2_u-curve-of-value]].

## Related

- [[ai-factory-huang]] — Huang's framing of inference infrastructure as a manufacturing system
- [[jevons-paradox-ai]] — cheaper inference → more inference, not less
- [[agentic-scaling-law]] — test-time compute as a scaling axis
- [[scaling-wall]] — pre-training ceiling; inference efficiency becomes the next battleground
- [[sovereign-ai]] — on-premise / sovereign inference as a policy objective
- [[rl-apis]] — commercial fine-tuning surface built on top of the inference layer
- [[H2_u-curve-of-value]] — inference infrastructure as bottom-of-U anchor
- [[H1_L0-L7-ladder]] — every rung above L0 is mediated by inference events
