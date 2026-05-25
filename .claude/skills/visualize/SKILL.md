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

Structural reference: `outputs/enterprise-adoption-ladder.html` — a staircase as the hero, a U-curve as the second visual, the enabler stack as the third, and the connections graph relegated to a smaller "neighbourhood" section near the end. Prose is reduced to one short *lede* per section plus a 2×2 of tension blurbs. Treat this file as a guide to the **sequence of visuals**, not to the visual identity — its finish is the older serif/museum-wall language and is now superseded by the design rules below. Pull the visual identity from `raw/design/` and from the "Design rules" section.

## Output contract

- **Location:** `outputs/<concept-slug>.html`.
- **Format:** single self-contained HTML file. All CSS and JS inline. The only allowed external dependencies are CDN-loaded fonts (Google Fonts or Fontsource) and, if needed, d3.js (`https://cdn.jsdelivr.net/npm/d3@7`). No build step. No npm install. Double-clicking the file opens it in any browser.
- **Size:** keep under ~150KB if possible. A lecture page is not a SPA.
- **Self-contained:** all wiki content needed by the page is baked into the HTML as data (text, neighbor list, edges, citations). Re-running `/visualize` rebuilds the file with current wiki state.
- **Back nav (required):** every output must include a secondary-button navigation element at the top of the hero section — before the kicker line — so readers can return to the wiki or the GitHub repo. It is an inline bordered element (no rounded corners, no shadow, hairline border `1px solid #d8d6cf`), not a fixed top bar. Add the following CSS and HTML:

```css
/* ── Back nav (S2) ── */
.back-nav{display:inline-flex;align-items:center;gap:0;margin-bottom:20px;border:1px solid #d8d6cf;}
.back-nav a{color:#6b6b6b;text-decoration:none;font-family:'Inter Tight','Inter',-apple-system,sans-serif;font-size:11px;letter-spacing:-0.01em;padding:6px 12px;transition:color 150ms cubic-bezier(0.4,0,0.2,1);}
.back-nav a:hover{color:#FF4A1C}
.back-nav__home{font-family:'Kalam',cursive;font-size:13px;color:#2a2a2a;}
.back-nav__sep{display:block;width:1px;height:26px;background:#d8d6cf;flex-shrink:0;}
```

Place this HTML at the top of the hero/header content, before the kicker `<p>`:
```html
<div class="back-nav">
  <a class="back-nav__home" href="https://supgrade.github.io/where-ai-value-lands/">← where value lands</a>
  <span class="back-nav__sep" aria-hidden="true"></span>
  <a class="back-nav__gh" href="https://github.com/Supgrade/where-ai-value-lands" target="_blank" rel="noopener">GitHub ↗</a>
</div>
```

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
6. **Tensions** — a 2×2 grid of short blurbs (≤3 sentences each), each with a handwritten head (the orange-period mark is acceptable on tension heads too). Honest, not breezy. Don't pad to fill four — three is fine, two is fine.
7. **Sources** — short list: title, handwritten metadata line, one short claim line in sans. No essay.
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

The visual identity is **eco-brutalism / technical-organic, with a pencil-on-blueprint voice**. A stark, deliberate juxtaposition between the precise, cold, blueprint world of engineering and the raw, ethereal beauty of nature — and a third register, the designer's handwriting, that softens the engineering frame without breaking it. The page should feel like a museum-grade technical spec sheet annotated by hand — premium, scientific, highly intentional — not like an LLM-generated explainer or a generic SaaS landing page.

Reference identity (screenshots in `raw/design/`): oversized **verb-word section markers with orange-period accents** (`Frame.`, `See.`, `Compose.`) used as graphic elements; full-bleed industrial-orange panels next to white spec panels; isometric blueprint diagrams; handwritten annotation type (Kalam) where engineering-spec mono would traditionally go; full-bleed organic imagery (moss, fog, forest) as the counterweight to the engineering frame.

### Color

- **Two primary backgrounds, used in large unbroken blocks.** Stark white (`#ffffff`, or near-white `#fafaf7` for warmth) and deep charcoal / true black (`#0e0e10`, `#111111`, `#1a1a1a`). Most sections are one or the other. The contrast between adjacent sections IS the separation.
- **Hero accent — industrial / safety orange.** `#FF4A1C` / `#FF5722` / `#F0451A`. Vibrant, highly saturated. Used aggressively: full-section background blocks, oversized typographic elements, sidebars, accent rules. Not just for buttons.
- **Secondary organic accents.** A small spectrum of natural greens — deep forest (`#2D4A2B`), olive (`#6B7A2A`), sage / mint (`#A8C09A`, `#C8DCB8`) — plus quiet stone greys. Use sparingly (one or two places per page), never as the dominant colour.
- **No gradients.** None. Not subtle ones. Only solid blocks.
- **No drop shadows.** None. Separation comes from colour blocks, hairline rules, or whitespace.

### Typography

Two families, used for very different jobs. Body type is Swiss-clean; secondary type is handwritten as a deliberate counterweight to the architectural frame — the same eco-brutalist tension between precise and organic, applied to type.

- **One sans-serif family for the structural body.** A grotesque or neo-grotesque sans — Inter Tight (default), Inter, Helvetica Neue, Söhne, Geist, ABC Diatype-style. Pull from Google Fonts / Fontsource. No serifs. No display fonts. No mixing two sans families. Used for: h1, h2, h3, dek, body, chips, button labels, big numerals, the section identifier word.
- **One handwritten family as the secondary voice.** Kalam (default — confident marker pen) is the canonical choice. Acceptable alternatives if Kalam doesn't fit: Caveat (friendly, fluid), Architects Daughter (drafting / blueprint annotation), Shadows Into Light (narrow, schoolbook). Used for: kicker lines, title-strip values, byline values, section ledes' meta hints, cat-blurbs, dim descriptions, the hint line, mind-map labels on the dark panel, tooltip headers. It replaces what would traditionally be uppercase letter-spaced mono metadata — the handwritten line carries the engineering-annotation feel without being all-caps and stiff.
- **Do not use a mono family.** No JetBrains Mono / IBM Plex Mono / Berkeley Mono on the page. The handwritten family covers every job mono used to do (axis ticks, spec strips, side annotations). Two families total: sans + handwritten.
- **Headings** medium-to-bold weight, **tight tracking** (-0.02em to -0.04em), title or sentence case. Not all-caps.
- **Body copy** small (15–17px, not 18–20px), highly legible, **left-aligned ragged right**, clustered into tight column-shaped paragraphs with **line-height 1.4–1.5** (tight, not airy). Measure 50–70 characters per line.
- **Handwritten micro-type** at 15–18px (slightly larger than the equivalent mono would have been because handwritten faces have lower x-height), natural case (not uppercase), normal letter-spacing. Frequently paired with a thin horizontal rule above or below. Reads as a designer's pencil annotation on a technical drawing — that is the intended effect.

### Layout, spacing, grid

The layout must feel architectural and blueprint-inspired.

- **Strict columnar grid.** 8 or 12 columns, clearly visible. Content snaps to columns. No overlapping, no organic placement, no jaunty offsets.
- **Hairline 1px solid dividers** between content zones, rows, and columns. Used deliberately to reinforce the technical-drawing aesthetic. Colour: `#1a1a1a` on light sections, `#3a3a3a` on dark sections.
- **Macro-whitespace generous; micro-whitespace tight.** Large empty zones around content blocks (≥72px between major sections). Inside a block, lines and labels cluster (small gaps, tight leading).
- **Section-as-panel.** Each section can be its own colour block — a white panel, a black panel, an orange panel. Adjacent panels touch edge-to-edge; the colour change IS the divider.
- **Wide canvas.** Page max-width ~1280–1440px so the hero diagram has blueprint room.
- **Header and footer strips** as full-width thin handwritten bars carrying metadata (date, slug, project tag, section list). Think title block on a technical drawing — but drawn in pencil. **Values only, no field labels:** show `2026 · 05 · 25`, not `Date: 2026 · 05 · 25`. Each item type (a date, a slug, a project name) is self-evident from its shape — labels are LLM-style padding.
- **No "cards".** No rounded corners anywhere on layout elements. No floating elements. Everything lives inside the grid.

### Section identifiers (the brutalist signature)

Every major visual section is anchored by an oversized **single-word identifier** — a verb that names what the reader does in that section. Examples for a typical 3-section visualisation: `Frame.` (the hero — set the question), `See.` (the overview diagram — show the shape), `Compose.` (the interactive part — let the reader play). Each word ends with a period rendered in the industrial-orange accent — the dot is the only colour on an otherwise monochrome word, and it is what unmistakably marks the page's visual language.

Do not use abstract labels like `S1` / `S2` / `S3` or bare numerals like `01` / `02` / `03` as the identifier. They are decoded as "AI-generated section markers" — the reader can't tell what they mean. The verb does both jobs: it names the section AND it acts as the oversized graphic element.

Layout rules:

- **Hero** carries a **vertical ghost stack** of the section words — the current section as a solid near-black word with the orange period; the next sections as outlined ghosts (`-webkit-text-stroke:1px var(--hair-soft)`) stacked above or below, the farther ones at lower opacity. Centred vertically in the right column of the hero grid. Font-size around 92–110px (must fit comfortably without overflowing — measure widest word first).
- **Subsequent section heads** carry a smaller version: a handwritten progress tag (`02 / 03`) above the word, then the word itself at ~140px with the orange period. Bottom-aligned in the left column of the section's two-column head; the section's h2 + lede sit in the right column.
- **One word is foregrounded per section**; the dot is always orange; the rest of the word is monochrome (near-black on light panels, near-white on dark panels).

This is the most distinctive move of the language and **must be present** on every page.

### Iconography and imagery

- **No emoji as icons.** Especially not 🎯 ✨ 🚀 💡 📊.
- **No icon library splattered on every heading.** Icons are absent by default. If something must be shown, draw it as an inline SVG primitive (a square, a line, a dot) — not a Lucide glyph.
- **Imagery, when used,** is either borderless and full-bleed across a section, or contained inside a strict square/rectangular grid box with a hairline border. No rounded corners, no shadows, no text overlaid on the image — captions live in the handwritten spec strip below.
- **Technical wireframes / isometric line drawings** are the preferred imagery style. A single full-bleed organic band per page (moss, fog, forest) is acceptable as the page's organic counterweight, never decoratively scattered.

### The hero diagram (bespoke SVG)

Functional rules unchanged — the hero is a hand-coded SVG, schema-specific (staircase, U-curve, stack, 2×2, etc.). The geometry must still mean something. Only the *finish* changes:

- **Drawn as a technical wireframe / blueprint** — thin (1–1.5px) solid lines, monochrome (near-black on white sections, near-white on dark sections), no fills. The staircase climbs, the U sags, the stack stacks.
- **Hero accent applied to one load-bearing element** — the contested step, the bottom of the curve, the current position, the highlighted band. The orange does the storytelling work; everything else is structural line work.
- **Wide viewBox** (`0 0 1280 760` or similar) with `preserveAspectRatio="xMidYMid meet"`.
- **Axes labelled in handwritten** (natural case, 12–14px). Arrowheads via SVG `<marker>`, not ASCII.
- **Subtle background grid** via `<pattern>` at very low opacity (`#1a1a1a` at 6–10%) to reinforce the spec-sheet feel.
- **Anchor boxes** for real-world examples are square, hairline-bordered, no fill. Inside: handwritten kicker → sans-serif name → handwritten metadata line → one orange metric. No drop shadows.
- **Annotations** are dashed lines + square brackets + handwritten labels. The handwritten face is the page's annotation voice — pencil-on-blueprint.
- **Two-colour discipline.** Black/white line work + one orange element. A muted secondary (deep forest green, olive) is acceptable for warnings/tensions only.

### The connections graph (secondary)

Functional rules unchanged. Stylistic finish:

- Nodes as small circles or squares. Concept = filled orange. Source = outlined black/white. Hypothesis = small square. Ladder phases = small squares clustered along an axis.
- Edges as thin solid lines (wikilinks) and thin dashed lines (citations).
- Use axis-aligned forces (`forceX`, `forceY`) to give the graph blueprint structure — not a hairball.
- Force simulation settles in ~2s and stops.
- Tooltip header in handwritten (the accent voice); body in sans for readability. Translucent panel, square corners, hairline border. No card, no shadow.
- Legend below in handwritten, natural case, 16–18px.

### Animation and motion

Two registers, applied per element:

- **Organic register** — for full-bleed imagery, hero panel transitions, scroll reveals of nature bands. Slow ethereal fades and crossfades, 600–900ms, ease-out. Like fog rolling in.
- **Technical register** — for menus, diagram reveals, grid transitions, hover states. Sharp, precise, instantaneous. Snap-to-grid, crisp slide, 150–250ms with `cubic-bezier(0.4, 0, 0.2, 1)`. No bounce, no spring, no overshoot.
- No parallax. No auto-loops. No scroll-jacking.

### "Tells" that the page was AI-generated — avoid

- **A wall of paragraphs with one graph at the bottom.** The most common failure. Prose is captions, not the spine.
- **The d3 force graph as the only diagram.** Build the bespoke schema first.
- A centered narrow column on white with `text-5xl font-bold tracking-tight` hero and subheading.
- Three feature cards in a grid.
- Lucide icons on every section header.
- Any gradient. Purple-to-blue, pink-to-orange, even "subtle" ones.
- `rounded-2xl shadow-lg`. Any rounded corners on layout elements.
- "✨ Key Takeaways" / "🎯 Why This Matters" boxes.
- "Welcome to your guide on…" / "In this lecture, we will explore…".
- The word "comprehensive" anywhere on the page.
- Generic SaaS-blue accent. The accent must be the specific industrial orange.
- Pastel palette. The palette is stark, not soft.
- Abstract section identifiers like `S1`, `S2`, `S3` or bare numerals `01`, `02`, `03` standing alone. The signature is a **single-verb word** with an orange period (`Frame.`, `See.`, `Compose.`). If the verb-word + orange-dot is absent, the language is not present.
- Uppercase letter-spaced mono metadata everywhere. The voice is handwritten (Kalam), not engineering-spec mono.
- Title-block strips that include field labels (`Date: …`, `Project: …`). Strips carry values only — the shape of the value names itself.

### Reference identity (study before generating)

Mentally model after:

- **The screenshots in `raw/design/`** — primary reference. Oversized sequence labels with ghost stack, industrial-orange full-bleed panels, isometric blueprint drawings, full-bleed organic imagery as counterweight.
- **Eco-brutalist / technical-organic studio sites** — strict columnar layouts, monumental numerals, hairline rules, handwritten annotation type, organic counter-imagery.
- **Engineering / architectural spec sheets** — title blocks at the bottom, handwritten metadata strips, hairline rules, isometric line drawings.
- **Swiss editorial design** — strict grid, neo-grotesque type, micro-typography for metadata.
- **Bret Victor / Distill interaction quality** — slow, deliberate diagram reveals — applied inside a brutalist frame, not a museum-soft serif frame.

See `references/design-checklist.md` for the final pre-output checklist.

## What not to do

- Do not put more than one concept in a single output. One concept, one file.
- Do not modify the wiki. `visualize` reads only.
- Do not invent content not in the wiki. If a concept is thin, the page is short — that is honest. Suggest `/discover` or `/ingest` to the user.
- Do not skip the design rules. The whole point of this skill is that the artifact looks made, not generated.
- Do not commit `outputs/` files to long-term memory — they are regeneratable. Treat them as throwaway products of the current wiki state.
