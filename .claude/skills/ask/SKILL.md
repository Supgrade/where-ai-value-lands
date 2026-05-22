---
name: ask
description: This skill should be used when the user asks to "ask the wiki", "query the wiki", "what does the wiki say about X", "synthesize what we know about X", "pull together everything on X", or poses a substantive research question that should be answered from accumulated wiki content rather than from generic knowledge or the raw sources directly. Reads `wiki/index.md` first, drills into relevant pages, synthesizes an answer with wikilink citations, and optionally crystallizes the answer back into the wiki as a new page so explorations compound.
---

# Ask

Answers a question by reading the wiki, not by re-deriving from raw sources or from generic model knowledge. The wiki is the accumulated synthesis; this skill consults it.

## Why this matters

Most LLM + document workflows are stateless: every question re-reads raw documents and re-derives an answer. This wiki is built precisely so that synthesis accumulates. `ask` must consult the wiki first. Falling back to raw sources or to model priors defeats the point.

## Workflow

### 1. Read the index

Read `wiki/index.md` in full. It is the catalog. If `index.md` does not exist, tell the user the wiki has not been ingested yet and stop — there is nothing to ask.

### 2. Identify relevant pages

From the index, pick the pages that bear on the question. Be generous on the first pass; it is cheaper to read an extra page than to miss the relevant one. Follow wikilinks between pages as the picture clarifies.

### 3. Read the pages

Read each relevant page fully. Pay attention to:
- Hypothesis pages' `Status`, `Confidence`, and `What would retire this` blocks — these tell the agent how settled a claim is.
- Source summary pages — for the citation behind a claim.
- Contradictions flagged in earlier ingests — surface these, do not paper over them.

### 4. Synthesize

Compose the answer. Required properties:

- **Cite via wikilinks.** Every non-trivial claim references the wiki page it comes from: `as shown in [[h1-l0-l7-ladder]]`, `per [[source-bourdieu-1986]]`. Citations point to wiki pages, not raw files.
- **Honor uncertainty.** If hypothesis pages say `Confidence: low`, the answer says so. Do not promote a hypothesis to fact.
- **Surface contradictions.** If two pages disagree, say so and cite both. Do not silently pick one.
- **Stay scoped.** Answer the question that was asked. Do not summarize the whole wiki unless the user asked for that.

If the wiki genuinely does not cover the question, say so plainly and suggest one of:
- ingesting a relevant source the user already has in `raw/`,
- running `/discover` to find sources,
- writing a new hypothesis page if this is a question worth tracking.

Do not silently fall back to generic knowledge.

### 5. Offer to crystallize

After delivering the answer, ask the user: "Should I file this answer back into the wiki?"

If yes:
- Write a new page with a clear slug (lowercase, hyphen-separated). Common kinds: comparison, analysis, synthesis-note, derived-question.
- Add YAML frontmatter (`status`, `tags`, `last-updated`).
- Add wikilinks both directions to every page the answer drew from.
- Update `wiki/index.md` with the new page.
- Append to `wiki/log.md`:
  ```markdown
  ## [YYYY-MM-DD] ask | Question phrased briefly
  - New page: [[slug]]
  - Pages consulted: [[a]], [[b]], [[c]]
  ```

This is the mechanism by which explorations compound rather than disappearing into chat history.

## What not to do

- Do not skip reading the index. The index exists precisely so the agent does not waste tokens reading every page.
- Do not cite raw files (`raw/foo.pdf`) — cite the wiki page that summarizes that source.
- Do not invent confidence. If the wiki says low confidence, the answer says low confidence.
- Do not over-crystallize. A throwaway clarifying question does not need a new wiki page. A genuine new connection or analysis does.
- Do not file an `ask` page that just repeats an existing page. Crystallize only when new structure is created.
