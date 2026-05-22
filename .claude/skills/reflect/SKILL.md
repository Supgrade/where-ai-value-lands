---
name: reflect
description: This skill should be used when the user asks to "reflect", "let's reflect on today", "reflect on my daily thought", "go through my notes from today", "read my thought from 21-05", "what do you make of what I wrote", drops a date matching a file in `raw/daily tougths/`, or otherwise wants the agent to engage with a daily-thought note as a dialogue rather than ingest it as a source. Reads the named note, restates it back, opens a multi-turn conversation that uses the current wiki to deepen the thought, then selectively promotes durable material into the wiki and leaves a memory marker in `wiki/thoughts/`. Daily thoughts are the author's internal monologue and are never folded into the wiki via `/ingest`.
---

# Reflect

Engages with a daily-thought note from `raw/daily tougths/`. Daily thoughts are the user's stream-of-consciousness reasoning *about* the inquiry, not external evidence. They deserve dialogue, not ingestion. Most of what the user writes in a daily thought should stay as conversation; only a fraction earns a place in the wiki.

This skill is the third operating mode of the wiki, alongside `/ingest` (external evidence → wiki) and `/ask` (wiki → answer):

- **reflect** — the author's thinking is examined, challenged using what the wiki already knows, and selectively promoted into wiki structure.

## Important contract

`raw/daily tougths/` is the **one** part of `raw/` the agent may write into. The agent may create a companion file next to the original (see "Annotated companion" below). Everything else in `raw/` remains user-owned and read-only.

`wiki/thoughts/` is the agent-maintained memory trail of reflections. The agent is free to create subfolders or files there as it sees fit. Notes there are brief and unceremonious — markers of "we discussed this", not claims of importance.

## Workflow

### 1. Identify the note

If the user names a date (e.g. "reflect on 21-05" or "reflect on 21-05-2026"), open the matching file in `raw/daily tougths/`. If unspecified, default to the most recent file in that folder and confirm with the user.

### 2. Announce it back

Read the note in full. Restate its main threads back to the user in a few short bullets, in English (translate from Italian if needed). Keep the restatement faithful — do not interpret yet. Ask the user whether the framing is correct before going deeper. This single beat matters: it confirms the agent read the note and gives the user a chance to correct the frame before the dialogue runs in the wrong direction.

### 3. Pull the wiki into context

Read `wiki/index.md`. Identify pages whose topics overlap with the threads in the daily note — hypotheses, concept pages, open questions, paper-planning pages, prior reflections in `wiki/thoughts/`. Read the most relevant 3–6 pages.

### 4. Engage

Open a dialogue. Anchor questions in what the wiki already contains so the reflection compounds with prior work. Useful question shapes:

- "[[h1-l0-l7-ladder]] currently says X with `Confidence: medium`. Today you wrote Y, which cuts against that. Want to revise the confidence, or is Y a different scope?"
- "You wrote that builder fever wastes resources. The open question in [[05_open-questions]] about 'who is the paper for' is unresolved — do these two connect?"
- "Karpathy has argued [external touchstone] — does that sharpen or complicate what you just wrote?"
- Steelman the opposite position when the user states a confident claim. Push back when a claim is stated as fact but the wiki does not support it.

This is a real conversation, not a checklist. Listen. Follow the thread the user finds interesting. Do not rush to promote anything into the wiki yet.

### 5. Promote selectively

When the dialogue reaches a point where the user signals readiness to commit something ("yes, that's a real shift", "okay write that up", "we should keep that"), switch into promotion mode. Propose specific wiki changes as a numbered list. Common kinds:

- New hypothesis page in `wiki/02_hypothesis/` — initial `Status: draft`, `Confidence: very low`.
- Update to an existing hypothesis page (revised confidence, new evidence-against, refined "What would retire this").
- Update to `wiki/01_paper-planning/` — audience refinement, purpose adjustment, structural change.
- New entry in `wiki/01_paper-planning/05_open-questions.md`.
- New concept page if a recurring term has earned one.

The user accepts or rejects each proposed change one by one. Do not auto-promote. Daily thoughts are speculative by definition; the user is the gate.

For every accepted change, apply the same invariants as the other skills: slug convention, wikilinks both directions, update `wiki/index.md`.

### 6. Write the annotated companion

Create a sibling file next to the original in `raw/daily tougths/`. Naming convention: append ` annotated` before the extension.

```
raw/daily tougths/21-05-2026.md            ← user's original (untouched)
raw/daily tougths/21-05-2026 annotated.md  ← agent's reorganized rewrite
```

The annotated file is a clean, English, theme-organized rewrite of the original thought, with the dialogue's clarifications and decisions folded in. Structure it however reads best — typically by the threads identified in step 2, with subheadings. Mark in brackets where the user later changed their mind during the conversation, e.g. `[Revised during reflection: actually the bubble argument is stronger than originally stated.]`.

This file is *for the user* — a clean record of how the thought evolved. It is not consulted by the wiki and not cited from wiki pages.

The original date file is never modified.

### 7. Leave a memory marker in `wiki/thoughts/`

Create a brief markdown in `wiki/thoughts/` recording that this reflection happened. Keep it loose. Suggested:

- Filename: free-form, readable, slug-conventional (e.g. `bubble-and-builder-fever.md`, `audience-narrowing-may.md`). Do not date-prefix or enumerate.
- Body: 3–10 bullets max. What was discussed. What landed in the wiki (if anything). What stayed as conversation. Sparse wikilinks to the 1–3 most central pages touched — apply the forward → reverse rule by adding a short `## Discussed in` section on those pages, listing the thought as `[[thought-slug]]`.
- Tone: not "this is important", not "we decided X". Just "we thought about this". The thoughts folder is provenance, not synthesis.

Create `wiki/thoughts/` lazily if it does not yet exist. The agent is free to add subfolders inside `wiki/thoughts/` as the volume grows (by month, by theme — agent's call).

### 8. Append to the log

```markdown
## [YYYY-MM-DD] reflect | brief topic
- Daily note: 21-05-2026
- Annotated: 21-05-2026 annotated
- Memory marker: [[thought-slug]]
- Wiki changes: [[page-a]] (updated), [[page-b]] (created), or "none — kept as conversation"
```

### 9. Report

Brief summary: what was discussed, what was promoted, what was kept as conversation, where the annotated file and the memory marker live.

## What not to do

- Do not ingest a daily thought via `/ingest`. Daily thoughts are not external sources.
- Do not modify the original daily-thought file. The annotated copy is a separate sibling.
- Do not auto-promote claims into the wiki. The user gates each promotion.
- Do not heavily wikilink the memory markers in `wiki/thoughts/`. Sparse links only — these notes are provenance, not claims.
- Do not announce the workflow's structure to the user ("we are now in phase 2"). The dialogue should feel like a conversation, not a script.
- Do not skip the announce-back step in (2). Reading the note silently and jumping into questions loses the user's confirmation that the framing is right.
- Do not extend writes anywhere else in `raw/` — only the `raw/daily tougths/` sibling-file exception applies.
