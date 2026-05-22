# Pre-output design checklist

Run through this list before writing the final HTML. If any answer is wrong, fix before shipping.

## Visual-first (the most important check)

- [ ] The page leads with a **bespoke hero diagram** specific to this concept (a staircase for a ladder, a U for a U-curve, layered bands for a stack, a 2×2 for a typology, etc.) — NOT the d3 force graph.
- [ ] The hero diagram is wider than the body text and clearly the primary thing on the page.
- [ ] There are at least **two diagrams** on the page (hero + at least one secondary visual on an orthogonal angle), in addition to the connections graph.
- [ ] The d3 force graph lives in a supporting section near the end, labelled as "the neighbourhood" or similar — not at the top.
- [ ] Each section is anchored by a diagram. If a section is pure prose, it has been cut or its content moved into a diagram annotation.
- [ ] Section ledes are ≤2 sentences. There is no opening essay paragraph.
- [ ] No section has more than ~80 words of running prose outside diagrams.

## Typography

- [ ] Body type is a serif (Source Serif 4 / Newsreader / EB Garamond / Crimson Pro / Lora / Spectral).
- [ ] Inter is **not** used at body size.
- [ ] Body size is 18–20px, line-height 1.55–1.7.
- [ ] Measure is 60–75 characters per line.
- [ ] Body text is left-aligned, ragged right.
- [ ] At most two typefaces total on the page (body + optional display/mono).

## Color

- [ ] Background is off-white or near-white (`#fafaf7`, `#f6f4ee`, `#ffffff`), not gray.
- [ ] Text is near-black (`#1a1a1a`), not pure `#000`.
- [ ] Exactly one accent color, used sparingly.
- [ ] **No gradients anywhere.**
- [ ] **No drop shadows.**

## Layout

- [ ] Layout is a wide single column of visuals (~1200–1280px max-width) with generous whitespace between sections.
- [ ] No centered narrow column on white.
- [ ] No "cards" (rounded rectangles with shadows).
- [ ] No hero image with overlaid title text.
- [ ] Section heads are short mono-styled labels (uppercase, letter-spaced), not large serif headings.
- [ ] Section breaks are whitespace or hairline rules, not boxes.
- [ ] At least 56px of vertical whitespace between sections.

## Icons and imagery

- [ ] **Zero emoji used as iconography.** None.
- [ ] No icon on every section header.
- [ ] Any icons present are monochrome and used at most twice.
- [ ] Any imagery is a real diagram, not decorative stock-feel art.

## Hero diagram (bespoke SVG)

- [ ] Hand-coded inline SVG, not a charting library.
- [ ] Wide viewBox (e.g. `0 0 1200 760`) with `preserveAspectRatio="xMidYMid meet"`.
- [ ] Geometry means something — the staircase climbs, the U sags, the stack stacks. The shape IS the argument.
- [ ] Axes labelled if direction matters. Mono, letter-spaced, faint grey. Arrowheads via `<marker>`, not ASCII.
- [ ] Subtle background grid via `<pattern>` if it adds a sense of measurement.
- [ ] Real-world anchors (firms, deployments, metrics) appear as small hairline rectangles connected to the schema, not as bulleted lists below.
- [ ] Annotations (thresholds, percentages, contested zones) are layered on top with dashed lines, brackets, mono labels.
- [ ] One accent colour does most of the work. A second muted accent (e.g. oxblood) is acceptable for warnings/tensions only.

## Connections graph (secondary)

- [ ] Lives near the end of the page, not at the top.
- [ ] Rendered as inline SVG with d3 force simulation.
- [ ] Nodes are dots or small circles. Not card rectangles.
- [ ] Uses axis-aligned forces (`forceX`/`forceY`) to give the graph structure — phases along an axis, sources clustered, hypotheses placed. Not a random hairball.
- [ ] Wikilink edges solid, citation edges dashed.
- [ ] Hover tooltip is plain type on translucent background, not a card with shadow.
- [ ] Force simulation settles within ~2 seconds and stops. Does not jiggle continuously.

## Animation

- [ ] No bouncing or wobbling entrance animations.
- [ ] No parallax.
- [ ] No auto-looping animations.
- [ ] Scroll-triggered reveals (if any) are 300–500ms fades, nothing more aggressive.

## Forbidden patterns

- [ ] No `rounded-2xl shadow-lg` cards.
- [ ] No "✨ Key Takeaways" / "🎯 Why This Matters" / "💡 Insights" boxes.
- [ ] No `text-5xl font-bold tracking-tight` centered hero with subheading and CTA.
- [ ] No three-feature-card grid.
- [ ] No purple-to-blue gradient. No pink-to-orange gradient. No gradient.
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
