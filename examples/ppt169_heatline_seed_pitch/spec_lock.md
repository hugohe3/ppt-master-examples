<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: en-GB
- audience: Seed-stage investors at climate-tech and vertical-software funds, reading both in the room and forwarded
- objective: Establish that installer capacity is the binding constraint on residential heat-pump deployment and that Heatline lifts it, so investors can distinguish achieved from projected and take a first-meeting decision on the £4.2M seed ask
- core_message: Home-heating electrification is limited by installer capacity, not demand; Heatline sells the capacity-planning layer and is raising a £4.2M seed round
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: narrative, pyramid
- mode_behavior: Run the investor arc as a story with one turn at the problem-to-solution pair, carried by a continuing object rather than a new frame; inside that arc every page states its conclusion in the title as a claim with its evidence directly beneath, so a forwarded page argues alone; appendix pages drop the arc and become retrieval surfaces.

## visual_style
- visual_style: custom
- visual_style_references: editorial, blueprint
- visual_style_behavior: A warm paper field organised by an editorial column grid and heavy horizontal hairline rules — one rule under the claim line at a fixed height on every page, a second closing the evidence block, and no card unless a real container is needed. Type carries the page: a large statement scale for claims and hero numerals, a quiet monospace for measurements, definitions and attribution. The blueprint contribution is an annotation layer rather than a field — leader lines, tick marks and monospace callouts label the product surface, the capacity curve and the market derivation. Decoration is otherwise near zero, and the ember accent appears at most twice per page and only on evidence.

## colors
- background: #FBF7F1
- secondary_bg: #EFE7DA
- primary: #16233A
- accent: #D65A1E
- secondary_accent: #2E6F5E
- body_text: #1F2733
- secondary_text: #6B6154
- divider: #C9BCA8
- image_rendering: custom
- image_rendering_references: corporate-photo, editorial
- image_rendering_behavior: Real editorial photography of ordinary working situations in warm low-angle daylight, one clear subject with usable quiet space on one side for type, natural colour inside the deck's warm paper and deep-ink range, visible material texture in metal, brick and workwear; no studio gloss, no anonymous stock professionals, no abstract technology, and no synthetic text, screens or interfaces in frame.

## typography
- font_family: Calibri, sans-serif
- title_family: Arial Black, sans-serif
- body_family: Calibri, sans-serif
- data_family: Consolas, monospace
- display_family: Arial Black, sans-serif
- body: 24
- title: 42
- subtitle: 32
- annotation: 18
- display: 108
- lead: 30
- data: 20
- footnote: 16

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/tools, tabler-outline/home, tabler-outline/calendar, tabler-outline/users, tabler-outline/trending-up, tabler-outline/building-factory, tabler-outline/certificate, tabler-outline/clock, tabler-outline/route, tabler-outline/target, tabler-outline/alert-triangle, tabler-outline/coin, tabler-outline/chart-line, tabler-outline/file-text, tabler-outline/flame, tabler-outline/bolt

## images
- p01: images/cover_installation_dawn.jpg | source=ai | crop=adaptive
- p03: images/problem_capacity_yard.jpg | source=ai | crop=adaptive
- p04: images/solution_survey_handover.jpg | source=ai | crop=adaptive

## page_visualizations
- P02: chart/column_chart
- P06: chart/line_chart
- P07: chart/waterfall_chart
- P08: table/record_table
- P09: table/comparison_matrix
- P10: chart/column_chart
- P12: chart/stacked_bar_chart
- P14: table/record_table
- P15: table/metric_table

## page_rhythm
- P01: anchor
- P02: dense
- P03: dense
- P04: breathing
- P05: dense
- P06: dense
- P07: dense
- P08: dense
- P09: dense
- P10: dense
- P11: breathing
- P12: dense
- P13: anchor
- P14: dense
- P15: dense

## pptx_structure
- mode: flat
- template_reuse_scope: style

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- Never use a real company's name, logo or brand as the pitching company. (user)
- The company, product, team, customers and all traction / revenue / pipeline / financial figures are fictional and must be labeled "illustrative" on the cover, on every page where they appear, and in the notes. (user)
- no screenshot, no AI-rendered fake UI (user)
- no AI faces of real people (user)
- never fill display text with a scene or gradient, never put a title over a busy image without a scrim (user)
