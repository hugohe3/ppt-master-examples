<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: en-US
- audience: Working designers, front-end developers and marketers who choose colours every week and have no formal training in optics, colour science or accessibility
- objective: Teach the minimum physical and perceptual model of colour and have it applied live, so each participant can name why a colour pair fails, check it against a WCAG threshold, extract and repair a five-colour palette, and explain why a rainbow ramp is the wrong default for ordered data
- core_message: Most colour decisions that feel like taste are lightness decisions — separate hue from lightness, measure the lightness, and what is left is judgement you can defend
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: instructional
- mode_behavior: Run the deck as one 90-minute teaching cycle — state the observable capability first, introduce each concept only where it is needed to act, demonstrate the whole task with real input and real output, hand the same task over for timed practice, show the two mistakes with their actual cause, and close with a check that asks for application rather than recall. Titles say what the page teaches or what the learner does. Every claim is labelled RULE, CONVENTION, RECOMMENDATION or PREFERENCE, and every deliberate simplification is marked as one.

## visual_style
- visual_style: custom
- visual_style_references: swiss-minimal, editorial, sketch-notes
- visual_style_behavior: swiss-minimal owns the skeleton — strict modular grid, flush-left alignment, exact square-cornered geometry, one large organizing plane per page, vast whitespace, strictly flat with no shadow or material. editorial owns the hierarchy — a kicker above each title, hairline rules instead of repeated cards, asymmetric column splits, and small labelled asides carrying the claim chips and source lines. sketch-notes contributes only its functional annotation layer: a hand-weight arrow pointing at one exact target, a ring around the part that changed, a short inline label beside it; no doodles, ribbons, wobbled containers or pastel blocks. The page field stays warm near-white and near-monochrome so swatches, ramps, wheels and contrast pairs are the only saturated marks on the canvas.

## colors
- background: #FAF8F4
- secondary_bg: #EDE7DC
- primary: #23201C
- accent: #A8452B
- secondary_accent: #3E5C6B
- body_text: #2E2A25
- secondary_text: #6B6259
- divider: #D8D0C3
- surface: #FFFFFF
- grid: #E8E1D5
- positive: #2E7D32
- negative: #C62828
- warning: #F57C00
- image_rendering: custom
- image_rendering_references: ink-notes, editorial
- image_rendering_behavior: Explanatory pen-on-paper drawing on the deck's warm paper field. ink-notes owns the mark — confident medium-weight ink line work in the body-text tone with a slight human wobble, flat, no shadow, no grain, fills left mostly empty so the line carries the explanation. editorial owns the composition — one dominant focal subject, deliberate alignment to invisible columns, generous negative space, simple geometric forms drawn with editorial confidence rather than cartoon warmth. Colour stays under 10% of each image and comes only from the accent and secondary-accent roles, except where the subject is light itself and the spectrum it disperses may be fully saturated.

## typography
- font_family: Segoe UI
- title_family: Trebuchet MS
- body_family: Segoe UI
- display_family: Consolas
- data_family: Consolas
- body: 24
- title: 42
- subtitle: 32
- annotation: 18
- cover_title: 72
- lead: 30
- display: 64
- data: 22
- footnote: 16

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/eye, tabler-outline/bulb, tabler-outline/palette, tabler-outline/color-swatch, tabler-outline/contrast, tabler-outline/droplet, tabler-outline/device-desktop, tabler-outline/printer, tabler-outline/ruler, tabler-outline/alert-triangle, tabler-outline/circle-check, tabler-outline/circle-x, tabler-outline/clock, tabler-outline/pencil, tabler-outline/help-circle, tabler-outline/link, tabler-outline/chart-bar

## images
- p01: images/prism_bench.jpg | source=ai | crop=adaptive
- p03: images/eye_cones.png | source=slice | crop=no-crop
- p04: images/press_and_screen.png | source=slice | crop=no-crop
- p08: images/great_wave_fit.jpg | source=web | crop=no-crop

## page_visualizations
- P03: chart/column_chart
- P07: table/comparison_matrix
- P12: chart/horizontal_bar_chart

## page_rhythm
- P01: anchor
- P02: anchor
- P03: dense
- P04: breathing
- P05: dense
- P06: dense
- P07: dense
- P08: dense
- P09: dense
- P10: breathing
- P11: dense
- P12: dense
- P13: dense
- P14: anchor

## pptx_structure
- mode: flat
- template_reuse_scope: style

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
