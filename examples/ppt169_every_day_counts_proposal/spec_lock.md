<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: en-US
- audience: Riverbend Unified board of education plus the superintendent's cabinet and two site principals — skeptical of consultant promises, focused on cost, staff load, and what changes by June
- objective: Establish chronic absenteeism as a measured structural condition, persuade the board that a district-run three-tier system is the right response, and succeed only if the board can separate evidence from proposal and votes to fund Phase 1 with named owners
- core_message: Attendance is an operating system, not a motivation problem — fund Phase 1 of a three-tier attendance system now, because the year that changes the trend is the cheapest year to start
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: pyramid
- mode_behavior: Situation in the client's terms, then an evidence arc proving the condition is structural and unevenly distributed, then one dominant recommendation, then only what makes that recommendation credible — mechanism, sequence, scope boundary, price, projected effect and its assumptions — closing on one action with an owner and a date. Every title states what the district gets or learns; every page carries one commitment, one component of the approach, or one piece of proof; every claim is visibly typed as measured evidence, proposed commitment, or illustrative assumption.

## visual_style
- visual_style: custom
- visual_style_references: soft-rounded, editorial
- visual_style_behavior: soft-rounded owns containers and rhythm — 16 px radii, low soft elevation, generous gutters, white cards on a warm paper field. editorial owns the evidence pages — hairline rules under titles and above source lines, a strict left-aligned column grid, small-caps eyebrow labels, and a visible source line under every chart and table. Density is deliberately unequal: argument and decision pages breathe, scope and pricing pages carry real detail under one grid. Decoration stays calm — no gradient banners, no heavy corporate ornament, no full-bleed decorative imagery.

## colors
- background: #FFFFFF
- secondary_bg: #F4F1EC
- primary: #1F4B57
- accent: #E07A3F
- secondary_accent: #6A9AA8
- body_text: #23282D
- secondary_text: #5A6368
- divider: #DDD8D0
- surface: #FAF8F5
- grid: #EAE5DD
- positive: #2E7D32
- warning: #B0722B
- negative: #C62828
- image_rendering: custom
- image_rendering_references: vector-illustration, editorial
- image_rendering_behavior: Restrained editorial vector illustration — flat shapes, one confident outline weight, no gradients and no photographic texture, built from the deck anchors with a single warm light source per image; subjects are ordinary school-morning objects seen from a middle distance, figures absent or distant silhouettes, and no lettering, signage, numeral, or interface text anywhere in the artwork.

## typography
- font_family: Calibri, sans-serif
- title_family: Trebuchet MS, sans-serif
- body_family: Calibri, sans-serif
- data_family: Calibri, sans-serif
- cover_title_family: Trebuchet MS, sans-serif
- hero_number_family: Trebuchet MS, sans-serif
- body: 24
- title: 40
- subtitle: 32
- lead: 28
- cover_title: 88
- hero_number: 72
- data: 20
- annotation: 18
- footnote: 16

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: icons/tabler-outline/calendar-event.svg, icons/tabler-outline/clock.svg, icons/tabler-outline/flag.svg, icons/tabler-outline/target.svg, icons/tabler-outline/checks.svg, icons/tabler-outline/alert-triangle.svg, icons/tabler-outline/shield-check.svg, icons/tabler-outline/users.svg, icons/tabler-outline/user-check.svg, icons/tabler-outline/home.svg, icons/tabler-outline/phone-call.svg, icons/tabler-outline/message-circle.svg, icons/tabler-outline/bus.svg, icons/tabler-outline/stethoscope.svg, icons/tabler-outline/school.svg, icons/tabler-outline/heart-handshake.svg, icons/tabler-outline/clipboard-check.svg, icons/tabler-outline/report.svg, icons/tabler-outline/chart-line.svg, icons/tabler-outline/currency-dollar.svg, icons/tabler-outline/arrow-narrow-right.svg

## images
- p01: images/cover_classroom_first_light.jpg | source=ai | crop=adaptive
- p06: images/morning_threshold.jpg | source=ai | crop=adaptive
- p14: images/open_entrance.jpg | source=ai | crop=adaptive

## page_rhythm
- P01: anchor
- P02: dense
- P03: dense
- P04: dense
- P05: dense
- P06: breathing
- P07: anchor
- P08: dense
- P09: dense
- P10: dense
- P11: dense
- P12: dense
- P13: dense
- P14: anchor

## page_visualizations
- P03: chart/line_chart
- P04: chart/column_chart
- P05: chart/area_chart
- P11: table/feature_matrix
- P12: table/hierarchical_table
- P13: chart/waterfall_chart

## pptx_structure
- mode: flat
- template_reuse_scope: style

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- no text inside images (user)
- never fill display text with a scene or gradient (user)
