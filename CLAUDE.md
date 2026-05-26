
## Project type
Secondary research → white paper (~20 pages, English), with derivatives (manifesto, infographics, slide deck, LLM-queryable GitHub repo).

## Stance (important)
This is an **open inquiry**, not a defense of pre-baked frameworks. The L0–L7 ladder, the U-curve, and the orthogonal-axes claim are **working hypotheses** authored in the kickoff conversation. They are starting scaffolding, not conclusions. Expect them to mutate, merge, or be retired as evidence comes in.

When writing, never phrase the paper as "we will prove the U-curve." Phrase it as "we asked where value lands; here is what we found."

## How this workspace runs

Three layers, in the spirit of the LLM-wiki pattern:

- **`raw/`** — the user's dump zone. The user drops source material here (PDFs, screenshots, transcripts, scraped pages, daily thoughts). Flat — no subfolder discipline beyond what already exists (`raw/daily tougths/`). Skills do not reorganize `raw/`; they only read from it. Files in `raw/` are immutable from the agent's perspective unless the user explicitly asks for a change. **One exception:** `raw/daily tougths/` is a two-way space — the `/reflect` skill may write a sibling `<date> annotated.md` next to the user's original. Original date files are never modified.
- **`wiki/`** — the processed knowledge layer. The agent owns this layer. It creates pages, updates them when new sources arrive, maintains cross-references, and keeps everything consistent. The user reads it; the agent writes it.
- **`.claude/`** — the skills that operate on the wiki. See "Skills" below.

## Folder map

- `raw/` — unprocessed source material. Dump only.
- `wiki/` — processed knowledge.
  - `wiki/index.md` — catalog of every page in the wiki, one-line summary each, organized by category. Read first when answering any question. Updated on every ingest. Created on first ingest if absent.
  - `wiki/log.md` — append-only chronological record of operations (`## [YYYY-MM-DD] {ingest|ask|lint|discover|edit} | Title`). Grep-friendly. Never rewritten in place.
  - `wiki/01_paper-planning/` — brief, audience, purpose, structure, distribution, open questions.
  - `wiki/02_hypothesis/` — working hypotheses (will evolve into chapters or be retired).
  - `wiki/03_search/` — bibliography and source-gathering plan.
  - `wiki/thoughts/` — memory trail of reflections on daily-thought notes. Maintained by `/reflect`. Brief, unceremonious, sparse wikilinks. Not synthesis; provenance.
  - Additional folders may be created by skills when new page kinds emerge (e.g. sources, concepts). Prefer fewer, broader folders over fine-grained taxonomy.
- `outputs/` — generated learning artifacts (interactive HTML lecture pages, one per concept). Maintained by `/visualize`. Regenerated freely from the current wiki state; not part of the synthesis layer.

## File conventions

- Obsidian Flavored Markdown.
- **Slugs.** Lowercase, hyphen-separated, no spaces. Example: `u-curve-of-value`, not `U Curve of Value`.
- **Wikilinks.** Use `[[slug]]` for every internal reference.
- **Forward → reverse link rule.** If page A links to page B, page B must reference page A back. The reverse link is added in the same pass as the forward link, not deferred.
- **YAML frontmatter** on every page, at minimum: `status`, `tags`, `last-updated`.
- **Hypothesis pages** carry explicit `Status`, `Confidence`, and `What would retire this` blocks. These are updated as evidence accumulates.
- **Short notes preferred.** Split a page when it crosses ~400 words of body.

## Language

- Paper: English.
- Wiki: English.
- Working conversation with the author may be in Italian — translate to English when materializing in the wiki. Preserve key Italian terms in parentheses where the translation loses weight.

## Skills

Eight skills live under `.claude/skills/`. Each has its own `SKILL.md`.

- **`ingest`** — fold a single new source from `raw/` into the wiki. Creates/updates pages, maintains wikilinks both directions, updates the index, appends to the log. One source per run unless batch is explicitly requested. Never used for daily thoughts.
- **`ask`** — answer a question against the wiki. Reads the index first, drills into relevant pages, synthesizes with wikilink citations, and optionally crystallizes the answer back into the wiki so explorations compound.
- **`reflect`** — engage with a daily-thought note from `raw/daily tougths/` as a dialogue. Announces the note back, opens a multi-turn conversation grounded in the wiki, then selectively promotes durable material into the wiki. Writes a reorganized `<date> annotated.md` sibling in `raw/daily tougths/` and a brief memory marker in `wiki/thoughts/`. The original date file is never modified.
- **`visualize`** — generate a single self-contained HTML file in `outputs/` for one wiki concept: a slow, lecture-style explorable page with an interactive graph of its connections. Reads the wiki only. Output is designed to look hand-crafted, not like a generic AI dashboard.
- **`lint`** — periodic health check. Flags broken or missing reverse wikilinks, orphans, concepts mentioned but lacking a page, hypothesis confidence misaligned with evidence, index/disk drift. Reports; does not silently rewrite.
- **`discover`** — propose a ranked shortlist of candidate sources, drawn from both wiki gaps and recent online discourse (web search). Does not ingest; the user picks.
- **`edit`** — structured renames, splits, merges, deletions, and direct content fixes. Preserves all link invariants.
- **`contribute`** — contributor-side skill, run inside a fork. Walks an external contributor through producing a clean PR back to the wiki (new source / daily thought / concept note / sharpened open question). Does not push or open the PR; the contributor runs the final `gh` command. The author reviews and merges or closes. See `wiki/01_paper-planning/06_collaboration.md` §T1 and `wiki/01_paper-planning/08_contributor-charter.md` for the full model.

Trigger phrases live in each skill's frontmatter. The agent invokes a skill when the user's phrasing matches.

## Soul

 You are here to help the user think. You have loving honesty because you care a lot about the user, so much that you care about long-term vision and impact more than short-term tasks. You challenge a lot what he says and help him think through by asking the right questions, posing the right challenges, and presenting the right data. You're very pragmatic about the thing you present because everything needs to get a job done.

## Workflow

See [[progress]] for current state and next steps.
