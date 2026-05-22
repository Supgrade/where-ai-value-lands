---
title: Context Control
status: active
tags:
  - concepts
  - orchestration
  - agentic-systems
  - engineering
last-updated: 2026-05-22
---

# Context Control

Harrison Chase's (LangChain / LangGraph) diagnosis of why LLMs fail in production — and the engineering principle that follows.

## The diagnosis

LLMs fail in production agentic systems not because they lack intelligence or reasoning capability but because they receive **incorrect, vague, or incompletely formatted context**. The intelligence is usually adequate; the surrounding infrastructure is not. Every hallucination, every wrong tool call, every broken multi-step workflow traces back to a failure of context supply, not model quality.

Implication: the hardest engineering problem in building reliable agentic systems is not prompting or model selection. It is *context control* — ensuring that the exact, appropriate data is retrieved, properly formatted, and passed to the model at the right step of a complex workflow.

## Why generic wrappers fail

Frameworks that rely on high-level "agent abstractions" — black-box wrappers that handle routing and retrieval without exposing internals — set a low ceiling for production viability. They obscure what is actually being passed to the LLM, making it impossible for engineers to inspect, debug, or control the context at each step. When something goes wrong (which it will), the developer cannot see why.

## The LangGraph response

LangGraph treats agentic systems not as autonomous black boxes but as **stateful machines** that blend deterministic code paths with non-deterministic model routing. Developers retain explicit control over context at every node in the execution graph.

This requires production-grade infrastructure:
- **State management:** short-term thread history + long-term cross-session memory
- **HITL:** human operators can intercept, review, edit, or approve high-stakes tool calls before execution
- **HOTL + time-travel:** inspect exact token inputs/outputs at any node; rewind state; replay from failure point
- **Streaming + observability:** real-time intermediate output; deep integration with observability platforms for debugging

By providing these features as first-class primitives, LangGraph embeds itself as **enterprise infrastructure** — the operating system governing how commoditized intelligence interfaces with proprietary corporate data. This is what makes it sticky: not abstraction, but control.

## Relationship to [[middle-layer-defensibility]]

Context control is the technical mechanism underlying the claim that sophisticated orchestration layers are defensible. A framework that gives developers explicit context control is not a wrapper — it is infrastructure. This distinction separates companies like LangGraph (defensible) from generic prompt-chaining tools (commoditizable).

## Broader implication for the stack

If context control is the decisive variable in production agentic reliability, then the layer that owns context — what data exists, how it is retrieved, how it is formatted — holds the real moat. This is not the foundation model. It is the orchestration framework and the knowledge infrastructure it orchestrates (proprietary corporate data, embedded schemas, behavioral memory). See [[H2_u-curve-of-value]]: what survives in the top of the U is precisely this — "who owns the user, the schema, the habits."

## Related

- [[middle-layer-defensibility]] — context control is the engineering basis for orchestration-layer moats
- [[where-value-lands-2026]] — primary source (Harrison Chase, LangChain blog)
- [[H2_u-curve-of-value]] — schema and habit ownership = context ownership
- [[autonomy-slider]] — HITL as the interface between human context and model context
- [[llm-as-operating-system]] — the OS metaphor; context control is what the OS manages for its processes
- [[agentic-scaling-law]] — test-time compute scaling works when context is correctly supplied; fails when it isn't
