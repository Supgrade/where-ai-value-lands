---
name: ingest
description: This skill should be used when the user asks to "ingest", "ingest this", "add this source", "process this PDF", "fold this into the wiki", "this is a new source", drops a source file path, or refers to a new file in `raw/` that needs to enter the wiki. Reads a single source, integrates its content into the existing wiki by creating or updating pages, maintains wikilinks both directions, and appends an entry to `wiki/log.md`.
---

# Ingest

Folds a new source from `raw/` into the wiki. This is the core operation of the wiki — without it the wiki does not compound.

Sources may be PDFs, web clippings, screenshots, interview transcripts, scraped articles, or the user's own notes. Conversations with the author may be in Italian; translate to English when materializing in the wiki.

---

## Stance

This is an open inquiry, not a defense of pre-baked frameworks. When a source contradicts an existing hypothesis page ([[H1_L0-L7-ladder]], [[H2_u-curve-of-value]]), flag the contradiction explicitly rather than smoothing it away. Update the hypothesis page's `Status`, `Confidence`, and `What would retire this` fields. Hypotheses are scaffolding, not conclusions.

---

## Phase 0 — Survey (orchestrator only, context-light)

The orchestrator never reads the full source. It gathers just enough signal to route, then delegates all content work. This is deliberate: the orchestrator's context window is reserved for coordination, not content.

### 0a. Identify and prepare the source

1. Confirm the file exists in `raw/`.
2. Determine file type: PDF, markdown, HTML clip, image, etc.
3. **If PDF:** check whether a marker folder exists alongside it (a folder with the same name as the PDF, minus `.pdf`, containing a `.md` file and figure JPEGs).
   - Marker folder exists → use the `.md` inside it as the source file going forward.
   - No marker folder, PDF ≤ 20 pages → use the PDF directly in the inline path.
   - No marker folder, PDF > 20 pages → run marker first, then use the `.md`:
     ```
     marker_single "<pdf-path>" --output_dir "<raw-folder>" --output_format markdown
     ```
     Wait for completion before proceeding.

### 0b. Measure the content

```bash
wc -l "<source-file>"
grep -n "^## \|^# " "<source-file>"
```

Record `LINE_COUNT` and the list of headings with their line numbers. Do not read any body content yet.

### 0c. Read the structural skeleton

Read only:
1. First 40 lines of the source (title, abstract, citation info).
2. The heading list from 0b (already retrieved).
3. `wiki/index.md` in full.
4. Last 15 lines of `wiki/log.md`.

This is everything the orchestrator needs. Stop here.

### 0d. Routing decision

| LINE_COUNT | Route | Extraction agents |
|---|---|---|
| < 500 | **Inline** | 0 (orchestrator does it all) |
| 500–1000 | **Multi-agent** | 2 |
| 1001–2000 | **Multi-agent** | 3–4 |
| 2001–4000 | **Multi-agent** | 5–7 |
| > 4000 | **Multi-agent** | 8–10 |

Formula: `N = min(ceil(LINE_COUNT / 500), 10)`. If the heading count is less than N, reduce N to match (never split mid-section).

Announce the decision to the user: _"Source is X lines with Y sections. Routing to [inline / multi-agent with N agents]."_

---

## Phase 1A — Inline path (LINE_COUNT < 500)

Process entirely in the current context. No agents needed.

1. **Read the source** fully. For marker output, also view referenced figure JPEGs when they contain charts or tables. Note title, author(s), publication venue, year, central claim.
2. **Survey the wiki.** `wiki/index.md` is already in context. Skim any existing pages clearly relevant to this source before writing.
3. **Decide what pages this source touches** (typically 3–10):
   - **Source summary page** — always. Full citation, central claim, key arguments, key data points, hypothesis touches, notable quotes.
   - **Concept pages** — for every non-trivial concept introduced, advanced, or challenged. Check `index.md` first. Prefer updating over creating.
   - **Hypothesis pages** — update if the source bears on any hypothesis. Add evidence, flag contradictions, revise Status/Confidence/What-would-retire-this.
   - **Open question pages** — update if the source answers, sharpens, or generates a question in [[05_open-questions]].
4. **Write pages.** YAML frontmatter (`status`, `tags`, `last-updated`). `[[wikilink]]` for all internal refs. Slugs: lowercase, hyphen-separated. Enforce the **forward → reverse link rule** in the same pass: if A links to B, add B → A immediately.
5. **Update index and log.** Add new pages to `wiki/index.md`. Append to `wiki/log.md`:
   ```
   ## [YYYY-MM-DD] ingest | Source Title
   - Pages touched: [[slug1]], [[slug2]], ...
   - Key takeaway in one sentence.
   - Contradictions or open questions surfaced, if any.
   ```
6. **Report and move.** Tell the user what was created, updated, and flagged. Move the source to `raw/ingested/`.

---

## Phase 1B — Multi-agent staging path (LINE_COUNT ≥ 500)

### Overview

Each extraction agent works in an isolated staging subfolder and writes real wiki pages there — full pages, full content, with proper frontmatter and wikilinks. They do not touch the live wiki. When they finish, the orchestrator inspects their manifests, moves non-conflicting pages straight to the live wiki, and spawns merge agents only for the cases where two agents wrote the same slug. The orchestrator is the sole writer for shared files (index.md, log.md) and for reverse link patches.

### Step 1: Create the staging area

```bash
mkdir -p wiki/_staging/source-slug-A-{1..N}
```

This creates isolated folders, one per agent (called A). The staging area is ephemeral and is deleted at the end.

### Step 2: Divide into chunks

From the heading list in Phase 0, divide headings into N groups of roughly equal size. For each chunk record:
- `START_LINE` — line number of the first heading in this group (or line 1 for chunk 1)
- `END_LINE` — line before the first heading of the next group (or EOF for the last)
- `SECTIONS` — list of section titles in this chunk

Find figure files in each chunk's line range:
```bash
awk -v start=START -v end=END 'NR>=start && NR<=end && /!\[\]/' "<source.md>"
```
Include the matching JPEG paths when briefing each agent.

### Step 3: Dispatch extraction agents in parallel

Spin up all N agents simultaneously. Each is fully self-contained — it receives everything it needs in its prompt. Use this template:

---

**EXTRACTION AGENT PROMPT**

```
You are an extraction agent for a research wiki. Your job is to read your assigned section of a source document, understand it deeply, and write wiki pages to your staging folder. You write real, complete pages — not summaries or reports.

## Project context

Wiki root: <absolute path to wiki/>
Today: <YYYY-MM-DD>

[additional context]

find the current content in wiki/index.md

## Wiki conventions

- Obsidian Flavored Markdown
- YAML frontmatter on every page: status, tags, last-updated (at minimum)
- Wikilinks: [[slug]] for all internal references. Slugs: lowercase, hyphen-separated, no spaces
- Forward → reverse link rule: if you link page A to page B, you must also add a backlink from B to A — do this in the same pass
- Page length: aim for under 400 words of body text; split if a concept grows larger
- Do not create a slug that already appears in the index — update the existing page instead

## Your assignment

Source file: <absolute path to .md file>
Your section: lines <START_LINE> to <END_LINE>
Sections in your chunk: <list of section titles>
Your staging folder: wiki/_staging/agent-<N>/

Figure files in your line range (read each one to interpret charts and data):
<list of absolute paths to .jpeg files>

## Instructions

1. Read your chunk using the Read tool with offset=<START_LINE> and limit=<END_LINE - START_LINE>.
2. Read each figure file listed above. Understand what it shows (axes, trend, key values, what claim it supports).
3. Decide which wiki pages your chunk should create or update:
   - New concept pages for ideas this chunk introduces or develops
   - Updates to existing hypothesis pages if your chunk has relevant evidence (check the index)
   - A source-summary fragment (see below)
   Do not create a page for a slug already in the index unless you are updating it.
4. Write new pages to your staging folder (wiki/_staging/agent-<N>/<slug>.md). Full frontmatter, full body, all wikilinks.
5. For existing pages you want to update (hypothesis pages, open-question pages): write a patch file to wiki/_staging/agent-<N>/patches/<slug>.patch.md — see patch format below.
6. Write your source-summary fragment to wiki/_staging/agent-<N>/source-summary-fragment.md — see format below.
7. Return your manifest as your final message — see format below.

## Patch file format

A patch file describes what to add or change in an existing live wiki page. Do not reproduce the full page — only the delta.

---
PATCH FOR: <slug>
TARGET: wiki/<folder>/<slug>.md

ADD TO SECTION: <section heading to append under, e.g. "## Evidence">
<the new content to add — markdown, with wikilinks as needed>

UPDATE FIELD: Confidence
NEW VALUE: Medium-High
REASON: <why this evidence shifts confidence>
---

## Source-summary fragment format

This fragment covers only your chunk's contribution to the overall source summary page.

---
SECTIONS COVERED: <list>
KEY CLAIMS:
- <bullet>
DATA POINTS:
- <exact stat with figure reference>
FIGURES:
- <filename>: <what the chart shows>
HYPOTHESIS TOUCHES:
- H1: <supporting/contradicting/neutral — one sentence>
- H2: <supporting/contradicting/neutral — one sentence>
OPEN QUESTIONS:
- <any>
---

## Manifest format (return this as your final message)

AGENT <N> MANIFEST

NEW PAGES:
- slug: <slug>, file: wiki/_staging/agent-<N>/<slug>.md, target_folder: wiki/<folder>/, links_to: [<slug-a>, <slug-b>]
(repeat for each new page)

PATCHES:
- existing_slug: <slug>, patch_file: wiki/_staging/agent-<N>/patches/<slug>.patch.md, nature: <one-line description>
(repeat for each patch)

SOURCE FRAGMENT: wiki/_staging/agent-<N>/source-summary-fragment.md
```

---

### Step 4: Collect manifests

Wait for all N agents to complete. Read each agent's manifest (the final message from each Agent tool call). Do not read the staged page files themselves — the orchestrator works only from manifests at this stage.

Build two maps:
- **Slug map:** `slug → [list of agents that wrote it]`
- **Patch map:** `existing_slug → [list of agents that patched it]`

### Step 5: Resolve and promote (parallel where possible)

The orchestrator now moves staged work into the live wiki. Most of this can happen in parallel.

**5a. Non-colliding new pages** (slug appears in exactly one agent's manifest):
Move directly from staging to the target wiki folder. This is a file move, no content analysis needed:
```bash
mv wiki/_staging/agent-N/<slug>.md wiki/<target_folder>/<slug>.md
```
All non-colliding pages can be moved in parallel.

**5b. Colliding new pages** (same slug in two or more agents' manifests):
For each collision, spawn a merge agent. Multiple different collisions can be merged in parallel.

Merge agent prompt:
```
Merge these staged wiki pages for slug "<slug>" into one coherent page and write it to wiki/<target_folder>/<slug>.md.

Files to merge:
- wiki/_staging/agent-A/<slug>.md
- wiki/_staging/agent-B/<slug>.md
(etc.)

Wiki conventions: Obsidian Flavored Markdown, YAML frontmatter (status/tags/last-updated), [[wikilinks]], slugs lowercase-hyphenated, body under 400 words (split if needed). Preserve all distinct content from both files. Do not duplicate. If the files contradict, keep both perspectives and mark the tension explicitly.

Write the merged result to: wiki/<target_folder>/<slug>.md
Return: confirmation that the file is written.
```

**5c. Patches to existing pages**:
For each existing page in the patch map:
- If only one agent patched it: apply the patch inline. Read the patch file, then use the Edit tool to append the new evidence block to the correct section and update any changed fields.
- If multiple agents patched the same existing page: spawn a patch-merge agent:

Patch-merge agent prompt:
```
Apply these patch files to the existing wiki page wiki/<folder>/<slug>.md.

Patch files:
- wiki/_staging/agent-A/patches/<slug>.patch.md
- wiki/_staging/agent-B/patches/<slug>.patch.md

Read the existing page and each patch file. Apply all patches: add content to the indicated sections, update fields where specified. If patches conflict, keep both and note the tension. Write the updated page back to its original path.

Return: a one-line summary of what changed.
```

### Step 6: Assemble the source summary page

After all pages are promoted to the live wiki, assemble the source summary page. Spawn one summary assembly agent:

```
Assemble the source summary page for "<source title>" from these fragment files:
- wiki/_staging/agent-1/source-summary-fragment.md
- wiki/_staging/agent-2/source-summary-fragment.md
(etc.)

Also read: wiki/index.md (to find all slugs created during this ingest, which appeared in the index as of this run)

Write the complete source summary page to: wiki/05_sources/<source-slug>.md

The page must include:
- YAML frontmatter: status: draft, tags, last-updated
- Full citation block (title, authors, year, venue, URL if available)
- Central claim (one paragraph)
- Key arguments and findings (organized by section, drawn from all fragments)
- Key data points and statistics
- Figures interpreted (from all fragments)
- Hypothesis touches: H1, H2 — supporting/contradicting/neutral with evidence
- Open questions surfaced
- See also: [[wikilinks]] to every concept page created or updated during this ingest

Return: confirmation the page is written.
```

### Step 7: Reverse link pass (orchestrator)

From the manifests, the orchestrator has a complete picture of every new slug and what it links to. Now enforce the forward → reverse link rule across the full set.

For each entry `slug X links_to slug Y`:
- If Y is a newly created page (in the slug map): its file was written by an extraction agent or merge agent and should already include a backlink to X — check the file and add the backlink if missing.
- If Y is an existing live page: use the Edit tool to append `[[X]]` to its "See also" or "Linked from" section (or add that section if absent).

The orchestrator can do this with direct Edit calls — it just needs the slug list, not the content.

### Step 8: Update index and log (orchestrator)

The orchestrator writes these two shared files once, after all pages are in place.

**`wiki/index.md`:** For each new page (from the slug map + source summary), add one line under the appropriate category:
```
- [[slug]] — one-line summary (pulled from the page's YAML or first sentence)
```

**`wiki/log.md`:** Append one entry:
```
## [YYYY-MM-DD] ingest | Source Title
- Pages touched: [[slug1]], [[slug2]], ...
- Key takeaway in one sentence.
- Contradictions or open questions surfaced, if any.
- Agents used: N extraction, M merge/patch (if any), 1 summary assembly
```

### Step 9: Cleanup and report

```bash
rm -rf wiki/_staging/
```

Move the source (and marker folder if present) to `raw/ingested/`.

Report to the user:
- Pages created (list of slugs)
- Pages updated (list of slugs)
- Collisions resolved (if any)
- Hypothesis pages shifted
- Open questions surfaced
- Suggested next actions (`/lint` to check link integrity, `/discover` to find related sources)

---

## First-ingest bootstrap

If `wiki/index.md` or `wiki/log.md` do not exist yet, create them before dispatching any agents.

**`wiki/index.md`** — catalog organized by category. Start with the categories already on disk and add new categories as they arise.

**`wiki/log.md`:**
```markdown
# Log

Append-only chronological record of wiki operations. Entry format: `## [YYYY-MM-DD] {ingest|ask|lint|discover|edit} | Title`.
```

---

## Italian → English

Translate when materializing in the wiki. The wiki is English-only. Preserve key Italian terms in parentheses where the translation loses weight.

---

## What not to do

- Do not read the full source in the orchestrator. Survey only; delegate content work.
- Do not let extraction agents write to the live wiki — staging only.
- Do not skip the reverse-link pass. Broken back-links compound over time.
- Do not auto-ingest multiple sources in one run unless the user asks for batch mode.
- Do not force evidence to fit existing hypotheses. Flag contradictions plainly.
- Do not create a duplicate slug — check `index.md` (passed to all agents) first.
- Do not rewrite `log.md` in place. Append only.
- Do not leave `wiki/_staging/` behind. Always clean up.
