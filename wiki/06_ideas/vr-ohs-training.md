---
title: Personalized OHS Training (AI + VR)
status: idea
tags:
  - idea
  - safety
  - training
  - vr
  - human-capital
last-updated: 2026-05-22
---

# Personalized Occupational Health & Safety Training

> [!abstract] What the AI does
> AI generates **personalized hazard simulations in VR**, drawn from real incident reports and local compliance standards. Workers safely rehearse dangerous scenarios — gas leak, structural collapse, electrical fault — building real-world response reflexes without real-world exposure.

## Domain
Heavy industry: oil & gas, mining, construction, utilities, manufacturing.

## Pattern
- **In:** real incident reports + site-specific hazard inventory + local compliance standards + worker skill profile.
- **Reasoning:** LLM generates scenario script; simulation engine renders it in VR; performance model assesses worker response and tailors the next scenario.
- **Out:** personalized training sequence + competency record + regulatory documentation.
- **Human checkpoint:** safety officer signs off on training completion; not autonomously certifying.

## Deployments in the wild
- Generic ER&I pattern in [[deloitte-ai-dossier-eri]]; no named deployment in this synthesis.

## What's actually being measured
- Training completion rate.
- Incident-rate reduction (the load-bearing claim, hard to attribute cleanly).
- *Not measured publicly:* whether scenario realism translates to behavioral change under real adrenaline conditions.

## Concept linkages
- [[fusion-skills]] — labor-side: AI-augmented worker capability is the framing this pattern operationalizes.
- [[capital-labor-divergence]] — sits adjacent: the AI tool is the moat, but the worker is the beneficiary of the safer rehearsal.
- [[synthetic-data-generation]] — the rare catastrophic scenarios that have no natural training corpus.
- [[autonomy-slider]] — low autonomy: the AI proposes scenarios, the human safety officer governs.

## Open questions
- Does VR-based rehearsal produce durable behavioral change at the worksite, or only short-term test-passing?
- How is "personalized" calibrated without crossing into intrusive worker-surveillance territory?
- Does training-content liability shift from the safety officer to the AI vendor when scenarios are AI-generated?

## Related
- [[deloitte-ai-dossier-eri]] — primary source.
- [[fusion-skills]] — the labor-capability framing this pattern instantiates.
- [[synthetic-data-generation]] — rare-event scenario generation.
