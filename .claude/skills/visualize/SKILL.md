---
name: visualize
description: This skill should be used when the user asks to "visualize", "visualize the concept of X", "make me a visual for X", "build a lecture page for X", "generate an explainer for X", "make an infographic for X", "show me X interactively", "build a learning page for X", or names a wiki concept and asks for a generated interactive artifact. Generates a single self-contained HTML file in `outputs/` that visualizes one concept from the wiki as a slow, lecture-style explorable explanation, including its text content and an interactive graph of its connections to neighboring concepts and sources. Output is designed to look hand-crafted, not like a generic AI dashboard.
---

# Visualize

Generates a one-page **visual-first** artifact for a single concept from the wiki. The output is an HTML file the user opens in a browser. The page leads with a bespoke diagram of the concept itself, supports it with secondary visuals, and uses prose only as short captions between them.

This is not a wiki page. It is an output — a derived artifact that lives in `outputs/` at the project root. It is regenerated on demand from current wiki content and overwritten freely.

## The core principle: diagrams first, prose second

A wall of paragraphs with one graph at the bottom is the wrong shape. The page must be **carried by its visuals**.

Every concept has a "natural schema" — the picture you would draw on a whiteboard to explain it. A ladder is drawn as a staircase. A U-curve is drawn as a U. A stack is drawn as layers. A two-axis typology is drawn as a 2×2. A flow is drawn as nodes and arrows. **Find that schema first, then build the page around it.** The schema is the hero.

The bespoke schema is more important than the force-directed connections graph. The connections graph is useful as a secondary "neighbourhood" view; it is not the primary artifact. A page that opens with the d3 force graph and treats prose as the main content has the priorities inverted.

Canonical reference: `outputs/enterprise-adoption-ladder.html` — a staircase as the hero, a U-curve as the second visual, the enabler stack as the third, and the connections graph relegated to a smaller "neighbourhood" section near the end. Prose is reduced to one short italic *lede* per section plus a 2×2 of tension blurbs.

## Output contract

- **Location:** `outputs/<concept-slug>.html`.
- **Format:** single self-contained HTML file. All CSS and JS inline. The only allowed external dependencies are CDN-loaded fonts (Google Fonts or Fontsource) and, if needed, d3.js (`https://cdn.jsdelivr.net/npm/d3@7`). No build step. No npm install. Double-clicking the file opens it in any browser.
- **Size:** keep under ~150KB if possible. A lecture page is not a SPA.
- **Self-contained:** all wiki content needed by the page is baked into the HTML as data (text, neighbor list, edges, citations). Re-running `/visualize` rebuilds the file with current wiki state.

## Workflow

### 1. Resolve the concept

Accept the concept as a slug (e.g. `u-curve-of-value`), a wiki page title, or a free-form name. Find the matching page under `wiki/`. If multiple plausible matches exist or none exists, ask the user.

### 2. Gather material

Read:
- The concept's own page (full text).
- Every page wikilinked from that page (one hop out).
- Every page that links back into the concept.
- Source summary pages cited by any of the above.

From this, build the graph:
- **Nodes:** the concept (centered), neighboring concepts (one hop), source pages cited.
- **Edges:** wikilinks (concept ↔ concept) and citations (concept ↔ source). Distinguish the two visually.
- **Node metadata:** kind (concept | source | hypothesis), one-line summary, status/confidence if hypothesis.

### 3. Find the schema, then plan the visuals

Before writing any prose, decide what the **hero diagram** is. Ask: if you had to explain this concept on a whiteboard with no words, what would you draw?

Common schemas, by concept shape:
- **Ladder / phase / maturity model** → a staircase climbing left-to-right, with anchors floating above each step.
- **U-curve / value-distribution claim** → a literal U-curve, with the relevant positions labelled.
- **Stack / layered architecture** → horizontal bands stacked vertically, with one band highlighted as load-bearing.
- **Typology with N categories** → N boxes in a row or a grid, with the dominant one filled and the others outlined.
- **Flow / pipeline / transition** → labelled nodes with arrows; minimal force simulation.
- **Two orthogonal axes** → a 2×2 with named quadrants and concrete examples in each.
- **Spectrum / slider** → a horizontal axis with markers and a "where most cases sit" indicator.
- **Tension between two positions** → side-by-side columns with a contested zone between them.
- **Empirical artifact (e.g. "74% / 16%")** → bracketed proportion bar, or annotated curve.

The hero diagram should be **bespoke**, hand-coded SVG, not a generic chart type pulled from a library. If the concept has a number worth surfacing (a percentage, a ratio, a productivity gain), the diagram surfaces it as part of the geometry, not as a callout box.

### 4. Plan the page as a sequence of visuals

Sections in order. **Each non-trivial section is anchored by a diagram, not a paragraph.**

1. **Header** — kicker line, title (≤14 words), one-sentence dek (≤25 words), small byline strip with concept slug + date. No hero image with text overlay. Title is the type.
2. **Hero diagram** — the bespoke schema for this concept, full width. Preceded by one short italic *lede* (≤2 sentences) that names what the diagram shows. The diagram itself does the work.
3. **Second visual** — typically the orthogonal angle on the same concept (e.g. the ladder gets a U-curve next to it; the U-curve gets a stack; the stack gets a 2×2). Same pattern: lede + diagram.
4. **Third visual (if material exists)** — the enabling structure, the empirical artifact, the contested zone, or a small-multiples grid of examples. Skip if the wiki doesn't support it.
5. **Connections graph** — the d3 force graph of the neighbourhood, now as a supporting section, not the centrepiece. One italic lede explaining what the graph is for. The graph itself is the content; do not write out edge-by-edge prose.
6. **Tensions** — a 2×2 grid of short blurbs (≤3 sentences each), each with a mono-styled head. Honest, not breezy. Don't pad to fill four — three is fine, two is fine.
7. **Sources** — short list: title, mono-styled metadata line, one italic claim line. No essay.
8. **Footer** — file path + date + project tag, single line.

If a section would only be prose without a diagram, ask whether it earns its place. The default is: cut it.

### Text budget

The whole page should read like long-form figure captions, not an essay. Hard ceilings:
- Section ledes: ≤2 sentences.
- Tension blurbs: ≤3 sentences.
- No section should have more than ~80 words of running prose outside the diagrams.
- No drop caps, no opening essay paragraph, no "let me explain the concept first."

If you find yourself writing a third paragraph, stop. That material belongs in the wiki, not the visualisation. Link to the wiki page instead.

### 5. Generate the HTML

Apply the **design rules** below. Write the file as a single HTML document. Test that it opens correctly (no broken JSON, no missing closing tags).

### 6. Report

Tell the user the file path. Suggest opening it: `open outputs/<concept-slug>.html`. Note any data that was sparse (e.g. "this concept only has two inbound links so the graph is small — consider `/discover` to find sources"). Append to `wiki/log.md`:

```markdown
## [YYYY-MM-DD] visualize | concept-slug
- Output: outputs/<concept-slug>.html
- Nodes: N concepts, M sources
- Edges: K
```

## Design rules (the most important part)

The default look of LLM-generated web pages — centered narrow column on white, Inter, purple-to-blue gradient hero, three rounded-corner feature cards with Lucide icons, soft drop shadows — is unmistakable and ugly. Avoid all of it. The page should look like it was made by a person who cares.

### Typography

- **Body type:** a serif or transitional serif. Use one of: Source Serif 4, Newsreader, EB Garamond, Crimson Pro, Lora, Spectral. Pull from Google Fonts.
- **Display type (titles):** either the same serif at a larger size, or a strong neo-grotesque sans like Inter Tight / Geist / Söhne fallback. Do not use Inter at body sizes — too generic.
- **Mono (for technical detail, edge labels):** JetBrains Mono, IBM Plex Mono, or Berkeley Mono fallback.
- **One typeface family for body.** Two at most overall. No more.
- **Body size:** 18–20px. Generous line-height (1.55–1.7). Measure 60–75 characters.
- **No center-aligned body text.** Left-aligned, ragged right.
- **Small caps for emphasis.** Drop caps optional on the opening paragraph.

### Color

- **Monochrome base.** Off-white background (`#fafaf7`, `#f6f4ee`, or `#ffffff` if cold is intended). Near-black text (`#1a1a1a`, not `#000`).
- **One accent color.** Pick deliberately — terracotta, deep teal, mustard, ink-blue, oxblood, sage. Use it for the graph's primary node, hovers, and rule lines. Not for buttons everywhere.
- **No gradients.** None. Not subtle ones either.
- **No drop shadows on cards.** No cards.

### Layout

- **Wide, single column of visuals.** The page is a vertical stack of diagrams interleaved with short captions. Use a generous max-width (~1200–1280px) so the hero diagram has room to breathe. The Tufte two-column layout with margin notes is acceptable only for the *secondary* tensions/sources sections — not for the main visual flow.
- **Each diagram lives in its own section.** Section head is a short mono-styled label (≤4 words, uppercase, letter-spaced). Followed by one italic lede. Followed by the SVG.
- **Generous whitespace between sections.** ≥56px of vertical breathing room. The page should feel like a museum wall, not a dashboard.
- **No "cards".** Sections are separated by whitespace, hairline rules, or typographic hierarchy. Not by rounded boxes with shadows.
- **No hero image with text overlay.** Open with type, then go straight to the hero diagram.
- **The hero diagram is wider than the body text.** It should clearly be the primary thing on the page.

### Iconography and imagery

- **No emoji as icons.** Especially not 🎯 ✨ 🚀 💡 📊 — they instantly read as AI-generated.
- **No stock icon library splattered across the page.** If an icon is needed, draw it inline as a small SVG, or use a single restrained set (Lucide is acceptable only at small sizes, monochrome, used sparingly — once or twice, not on every heading).
- **Real diagrams over decorative imagery.** If something can be drawn as a diagram, draw it. If it would just be a stock-photo-feeling header, omit it.

### The hero diagram (bespoke SVG)

This is the most important element on the page. Conventions:

- **Hand-coded inline SVG.** No charting library. Coordinates picked to make the geometry mean something — a staircase climbs, a U-curve sags, a stack stacks. The geometry IS the argument.
- **Wide viewBox** (e.g. `0 0 1200 760`) with `preserveAspectRatio="xMidYMid meet"` so it scales gracefully on every screen.
- **Labelled axes when there is direction.** Mono, letter-spaced, faint grey (e.g. `OPERATIONAL DEPTH ↑`, `MATURITY →`). Use SVG `<marker>` for arrowheads, not ASCII.
- **Subtle background grid** via `<pattern>`, low opacity, to give the geometry a sense of measurement without dominating.
- **Anchor cards** when the schema needs to reference real-world examples (firms, deployments, metrics): small rectangles with hairline borders, no fill (or `var(--bg)` fill), connected back to the schema with a thin line and a small terminal dot. Card content: mono kicker (uppercase, letter-spaced) → serif name → small grey context line → accent-coloured metric. No drop shadows.
- **Annotations layered on top.** Use dashed lines and brackets to call out empirical artifacts (thresholds, gaps, percentages). Annotation text is mono for labels, serif italic for the explanatory clause.
- **One accent colour does most of the work.** A second muted accent (e.g. oxblood) is acceptable for tensions/warnings only.
- **No legend if the schema is self-explanatory.** Add one only when the visual encoding genuinely needs explaining.

### The connections graph (secondary)

A supporting view, not the centrepiece. Lives near the end of the page in its own short section.

- Render as inline SVG with d3 force simulation. Vanilla SVG is also fine for small graphs.
- Nodes are circles (or small labeled dots), not card-like rectangles. Concept = filled accent color. Source = outlined. Hypothesis = different shape (e.g. small square) to distinguish kinds. Ladder phases = small squares clustered along an axis.
- Edges are thin lines. Wikilink edges solid; citation edges dashed.
- Hover reveals the node's one-line summary in a subtle tooltip (not a card; just type on a translucent background).
- Force simulation settles after ~2 seconds and stops. The graph does not jiggle continuously.
- Use axis-aligned forces (`forceX`, `forceY`) to give the graph structure — phases along an axis, sources clustered at the bottom, hypotheses at the top. A random hairball is harder to read than a structured one.
- A simple legend underneath is fine here, since the encoding is non-obvious.

### Animation

- Slow. Earned. The page is a lecture, not a demo reel.
- Acceptable: scroll-triggered reveal of sections (~300–500ms fades). One small animated diagram if the concept benefits from it (e.g. a curve that draws in to illustrate the U-curve).
- Not acceptable: bouncing entrance animations, parallax, scroll-jacking, anything that auto-loops.

### "Tells" that the page was AI-generated — avoid

- **A wall of paragraphs with one graph at the bottom.** This is the most common failure. The page must be carried by its visuals; prose is captions, not the spine.
- **The d3 force graph as the only diagram.** Every generated explainer has a force graph. A page that opens with one (or has nothing else) screams "I asked an LLM to visualise this." Build the bespoke schema first.
- **A centered hero with `text-5xl font-bold tracking-tight` and a subheading.**
- **Three feature cards in a grid below the hero.**
- Lucide icons on every section header.
- Purple-to-blue or pink-to-orange gradient.
- `rounded-2xl shadow-lg` rectangles.
- "✨ Key Takeaways" or "🎯 Why This Matters" boxes.
- Sentences that start "Welcome to your guide on…" or "In this lecture, we will explore…".
- The word "comprehensive" anywhere on the page.
- Drop caps on the opening paragraph (the opening paragraph itself is the smell — there shouldn't be one).

### Reference designers and pages (study these before generating)

If unsure what "good" looks like, mentally model after:

- **Bartosz Ciechanowski** (ciechanow.ski) — the gold standard for explorable explanations. Slow, generous, beautiful diagrams, no chrome.
- **Distill.pub** archived articles — academic clean, real typography, interactive diagrams.
- **Stripe Press** book pages — serif-heavy, dense, generous margins.
- **Edward Tufte** layouts — margin notes, small multiples, sparklines.
- **Robin Sloan's newsletter** aesthetic — handcrafted, restrained, occasional one-off illustration.
- **Bret Victor's "Up and Down the Ladder of Abstraction"** — for the explorable feel.

See `references/design-checklist.md` for a final pre-output checklist.

## What not to do

- Do not put more than one concept in a single output. One concept, one file.
- Do not modify the wiki. `visualize` reads only.
- Do not invent content not in the wiki. If a concept is thin, the page is short — that is honest. Suggest `/discover` or `/ingest` to the user.
- Do not skip the design rules. The whole point of this skill is that the artifact looks made, not generated.
- Do not commit `outputs/` files to long-term memory — they are regeneratable. Treat them as throwaway products of the current wiki state.
