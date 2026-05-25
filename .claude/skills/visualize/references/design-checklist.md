# Pre-output design checklist

Run through this list before writing the final HTML. If any answer is wrong, fix before shipping.

The visual identity is **eco-brutalism / technical-organic**: stark white/black blocks + industrial orange accent + organic green counterweights, set in a strict architectural grid with a clean neo-grotesque sans-serif.

## Visual-first (the most important check)

- [ ] The page leads with a **bespoke hero diagram** specific to this concept (a staircase for a ladder, a U for a U-curve, layered bands for a stack, a 2×2 for a typology, etc.) — NOT the d3 force graph.
- [ ] The hero diagram is wider than the body text and clearly the primary thing on the page.
- [ ] There are at least **two diagrams** on the page (hero + at least one secondary visual on an orthogonal angle), in addition to the connections graph.
- [ ] The d3 force graph lives in a supporting section near the end, labelled as "the neighbourhood" or similar — not at the top.
- [ ] Each section is anchored by a diagram. If a section is pure prose, it has been cut or its content moved into a diagram annotation.
- [ ] Section ledes are ≤2 sentences. There is no opening essay paragraph.
- [ ] No section has more than ~80 words of running prose outside diagrams.

## Brutalist signature

- [ ] Every major visual section is anchored by an **oversized single-verb identifier** — `Frame.`, `See.`, `Compose.`, `Read.`, `Pick.`, etc. — that names what the reader does in that section. NOT `S1` / `S2` / `S3` or bare `01` / `02` / `03`.
- [ ] Each section word ends with a **period rendered in industrial orange** (`color:var(--accent)` via `::after`). The dot is what marks the visual language.
- [ ] The **hero** carries a vertical ghost stack of the section words — current word as solid near-black, others as outlined ghosts (`-webkit-text-stroke`), centred vertically in the right column.
- [ ] **Each subsequent section head** carries the word at ~140px with a small handwritten progress tag (`02 / 03`) above it.
- [ ] A full-width thin handwritten **header strip and footer strip** carry metadata (date, slug, project tag, section list) — title-block style. **Values only, no field labels** (`2026 · 05 · 25`, not `Date: 2026 · 05 · 25`).
- [ ] At least one section uses a **full-bleed colour block** (industrial orange, deep charcoal, or stark white) edge-to-edge, with no card or container around it.

## Typography

- [ ] Body type is a clean neo-grotesque sans-serif (Inter Tight default; Inter / Helvetica Neue / Söhne / Geist / ABC Diatype-style acceptable).
- [ ] **No serifs anywhere on the page.**
- [ ] **No mono typeface** anywhere on the page — no JetBrains Mono, IBM Plex Mono, Berkeley Mono. The handwritten face replaces it.
- [ ] Body size is 15–17px (not 18–20px), line-height 1.4–1.5 (tight, not airy).
- [ ] Measure is 50–70 characters per line.
- [ ] Body text is left-aligned, ragged right.
- [ ] Headings use tight tracking (-0.02em to -0.04em), title or sentence case (not all-caps).
- [ ] Secondary type (kickers, byline values, title-strip values, ledes' meta, cat-blurbs, dim descriptions, hints, mind-map labels, tooltip headers) uses a **handwritten** family: **Kalam** (default), or Caveat / Architects Daughter / Shadows Into Light. Natural case, NOT uppercase, normal letter-spacing, 15–18px.
- [ ] Exactly two typeface families total on the page (sans body + handwritten secondary).

## Color

- [ ] Backgrounds are **stark white** (`#ffffff` or `#fafaf7`) and/or **deep charcoal / true black** (`#0e0e10`, `#111111`, `#1a1a1a`) in large unbroken blocks.
- [ ] Industrial / safety **orange** (`#FF4A1C` / `#FF5722` / `#F0451A`) appears as a hero accent — full panel block, oversized type element, or accent rule. Not just as a button colour.
- [ ] Natural green accents (deep forest, olive, sage / mint) appear in at most one or two places, never as the dominant colour.
- [ ] **No gradients anywhere.** Solid blocks only.
- [ ] **No drop shadows.** None.
- [ ] No generic SaaS blue. No pastels.

## Layout

- [ ] Layout uses a **strict 8- or 12-column grid**. Content snaps to columns.
- [ ] Page max-width is ~1280–1440px.
- [ ] **Hairline 1px solid dividers** are used between content zones (`#1a1a1a` on light sections, `#3a3a3a` on dark).
- [ ] Macro-whitespace between sections is generous (≥72px); micro-whitespace inside blocks is tight.
- [ ] At least one section pair uses **panel-touches-panel** colour-block separation (white touching black, or white touching orange) — not just whitespace.
- [ ] **No "cards"**, no rounded corners on any layout element, no floating elements.
- [ ] No hero image with overlaid title text.
- [ ] No centered narrow column on white.

## Icons and imagery

- [ ] **Zero emoji used as iconography.** None.
- [ ] No icon on every section header.
- [ ] Any inline iconography is drawn as SVG primitives (square, line, dot), not pulled from Lucide or another glyph set.
- [ ] Imagery, if used, is either **borderless full-bleed** across a section, or contained inside a strict square/rectangular **hairline-bordered grid box** — no rounded corners, no shadows.
- [ ] If organic imagery (moss, fog, forest) appears, it appears at most as a single full-bleed band serving as the page's organic counterweight — not decoratively scattered.

## Hero diagram (bespoke SVG)

- [ ] Hand-coded inline SVG, not a charting library.
- [ ] Wide viewBox (e.g. `0 0 1280 760`) with `preserveAspectRatio="xMidYMid meet"`.
- [ ] Drawn as a **technical wireframe / blueprint**: thin (1–1.5px) solid lines, monochrome (near-black on white sections, near-white on dark sections), no fills.
- [ ] Geometry means something — the staircase climbs, the U sags, the stack stacks. The shape IS the argument.
- [ ] **One load-bearing element is the industrial orange.** Everything else is structural line work.
- [ ] Axes labelled in handwritten, natural case, 12–14px, faint. Arrowheads via SVG `<marker>`, not ASCII.
- [ ] Subtle background grid via `<pattern>` at 6–10% opacity gives a spec-sheet feel.
- [ ] Real-world anchors (firms, deployments, metrics) appear as square hairline-bordered boxes with no fill — handwritten kicker, sans-serif name, handwritten metadata line, one orange metric.
- [ ] Annotations use dashed lines + square brackets + handwritten labels. Handwritten is the page's annotation voice.

## Connections graph (secondary)

- [ ] Lives near the end of the page, not at the top.
- [ ] Rendered as inline SVG with d3 force simulation.
- [ ] Nodes are small circles or squares. Concept = filled orange. Source = outlined. Hypothesis = small square.
- [ ] Uses axis-aligned forces (`forceX`/`forceY`) to give the graph blueprint structure — not a random hairball.
- [ ] Wikilink edges solid, citation edges dashed. Thin lines.
- [ ] Hover tooltip: handwritten header (the accent voice) + sans body, on a translucent panel with square corners and a hairline border. No card, no shadow.
- [ ] Force simulation settles within ~2 seconds and stops. Does not jiggle continuously.
- [ ] Legend below in handwritten, natural case, 16–18px.

## Animation

- [ ] Organic-register transitions (full-bleed imagery, hero panel) are slow fades / crossfades, 600–900ms, ease-out.
- [ ] Technical-register transitions (menus, diagram reveals, hover) are sharp, 150–250ms, `cubic-bezier(0.4, 0, 0.2, 1)`.
- [ ] No bouncing or spring entrance animations. No overshoot.
- [ ] No parallax. No auto-looping animations. No scroll-jacking.

## Forbidden patterns

- [ ] No `rounded-2xl shadow-lg` cards.
- [ ] No rounded corners on any layout element.
- [ ] No "✨ Key Takeaways" / "🎯 Why This Matters" / "💡 Insights" boxes.
- [ ] No `text-5xl font-bold tracking-tight` centered hero with subheading and CTA.
- [ ] No three-feature-card grid.
- [ ] No gradient of any kind.
- [ ] No serif body text.
- [ ] No mono typeface anywhere.
- [ ] No generic SaaS-blue accent. No pastel palette.
- [ ] No abstract section identifiers (`S1`, `S2`, …) and no bare numerals (`01`, `02`, …) as the section marker. Verb-words with orange period only.
- [ ] No title-block field labels (`Date:`, `Project:`, etc.). Strips carry values only.
- [ ] The word "comprehensive" does not appear.
- [ ] No sentence starts with "Welcome to your guide on…" or "In this lecture, we will explore…".

## Content honesty

- [ ] Page content comes from the wiki, not invented.
- [ ] If the concept is thin in the wiki, the page is short. Do not pad.
- [ ] Contradictions and uncertainty flagged in the wiki are preserved, not smoothed away.
- [ ] Hypothesis pages' `Confidence` is reflected — a low-confidence claim is shown as low-confidence.

## File hygiene

- [ ] Single self-contained `.html` file.
- [ ] All CSS inline in `<style>`. All JS inline in `<script>`. Only CDN deps allowed: fonts and d3.
- [ ] File under ~150KB if reasonable.
- [ ] Opens correctly when double-clicked. No console errors.
