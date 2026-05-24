---
title: Data folder — README
status: living
tags:
  - data
  - conventions
last-updated: 2026-05-22
---

# `wiki/data/` — the citable-evidence layer

This folder holds the **small, citable units of evidence** referenced across the wiki: statistics, figures, tables, charts, images.

Concept pages argue. Source pages summarize whole documents. **Data pages hold the individual numbers, charts, and images that the arguments rest on** — each one self-contained, sourced, and back-linked to the concepts that use it.

## What lives here

Each data point gets its own short markdown file:

- **Statistics** — a single number or ratio with source, year, and method (e.g. `scaling-gap-74-16.md`, `task-based-tfp-ceiling.md`).
- **Tables** — small decomposition tables (e.g. `ai-task-exposure-decomposition.md`).
- **Images / figures** — a markdown file that embeds an image and describes it. The image file (`.jpg`, `.png`, `.svg`) lives in this same folder, next to the markdown that describes it. The markdown is the citable unit; the image alone is not.

> **Rule:** every image in `data/` must have a sibling markdown that describes it, sources it, and links it into the wiki. An orphan image file is a `/lint` violation.

## File conventions

- **Slug:** lowercase, hyphen-separated, descriptive. Prefer `cursor-50b-valuation.md` over `cursor1.md`.
- **One data point per file.** Three related numbers from the same source go in three files (with cross-links) unless they form an irreducible table.
- **Frontmatter (required):**
  ```yaml
  ---
  title: Short human title
  type: statistic | table | figure | image
  source-primary: Who actually measured / published it
  source-via: Which wiki source page surfaces it (a [[source-page]] slug)
  year: 2024
  related: [concept-slug, concept-slug]
  last-updated: YYYY-MM-DD
  ---
  ```
- **Body sections (in this order):**
  1. **The data** — the number, chart, table, or `![[image.png]]` embed, with one-line caption.
  2. **Source** — full citation, primary attribution, and the wiki source page it was ingested through.
  3. **What it shows** — 1–3 sentences of plain-language interpretation.
  4. **How to cite** — a one-line format the author can paste into the paper.
  5. **Connections** — `` `[[wikilinks]]` `` to concept/hypothesis pages, each annotated with *how* the data is used there.

## The forward → reverse rule still applies

If `data/X.md` links to `04_concepts/Y.md`, then `Y.md` must reference `[[X]]` back. Same as everywhere else in the wiki.

## How data pages are used

- **In the paper.** Drop a footnote pointing to the data page; the data page is the canonical entry that owns the citation.
- **In `/ask`.** When a question touches a number, the answer cites the data page (not the source page), so the chain stays grindable.
- **In `/visualize`.** Lecture pages can pull figures/tables directly from `data/`.
- **In `/lint`.** Checks that every quantitative claim in a concept page resolves to a data page.

## What does *not* live here

- Long argumentative summaries → those are `05_sources/`.
- Theoretical framings or hypotheses → `02_hypothesis/` and `04_concepts/`.
- Raw, unprocessed source files (PDFs, screenshots) → those stay in `raw/`.

## Naming nudges

Use a noun-first slug that survives renaming the underlying source:
- ✅ `scaling-gap-74-16.md`, `hyperscaler-capex-trajectory.md`
- ❌ `wef-figure-3.md`, `acemoglu-table-2.md`

Numbers and labels survive; document page references rot.
