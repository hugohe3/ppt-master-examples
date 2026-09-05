<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: en
- audience: Site-reliability and platform engineers, incident commanders, and the engineering leaders they report to, at organizations whose availability depends on Cloudflare
- objective: Hand a reader who was not there an accurate, source-anchored account of the 18 November 2025 Cloudflare outage, so they can restate its trigger, mechanism, impact window, and detection-versus-diagnosis gap, tell observed fact from inference, and name both the committed corrective actions and what the published account leaves open
- core_message: A database permissions change at 11:05 UTC doubled a Bot Management feature file past a fixed 200-feature preallocation limit, turning it into an unhandled panic in the core proxy; detection took three minutes and diagnosis two hours and fifty-three, and the propagation condition behind it is the same one behind the 2 July 2019 outage
- consumption_mode: text

## mode
- mode: briefing

## visual_style
- visual_style: swiss-minimal

## colors
- background: #FFFFFF
- secondary_bg: #F2F4F6
- primary: #1F2933
- accent: #B4342C
- secondary_accent: #B7791F
- body_text: #1F2933
- secondary_text: #5A6673
- divider: #D7DDE3
- surface: #F2F4F6
- grid: #E8ECEF
- severity_normal: #4A5568
- severity_degraded: #B7791F
- severity_critical: #B4342C
- severity_recovered: #2E7D5B
- severity_normal_tint: #EDEFF2
- severity_degraded_tint: #FAF0DC
- severity_critical_tint: #F7E4E2
- severity_recovered_tint: #E4F0EA

## typography
- font_family: Arial
- title_family: Arial
- body_family: Arial
- data_family: Consolas
- code_family: Consolas
- display_family: Consolas
- body: 20
- title: 36
- subtitle: 28
- annotation: 16
- lead: 26
- data: 18
- code: 16
- display: 56
- cover_title: 64
- footnote: 12

## icons
- library: chunk-filled
- inventory: chunk-filled/circle-minus, chunk-filled/triangle-exclamation, chunk-filled/circle-x, chunk-filled/circle-checkmark, chunk-filled/clock, simple-icons/cloudflare

## page_rhythm
- P01: anchor
- P02: dense
- P03: dense
- P04: breathing
- P05: dense
- P06: dense
- P07: dense
- P08: breathing
- P09: dense
- P10: dense
- P11: dense
- P12: breathing
- P13: dense
- P14: breathing
- P15: anchor

## page_visualizations
- P03: table/record_table
- P05: chart/line_chart
- P06: table/record_table
- P07: table/record_table
- P13: table/record_table

## pptx_structure
- mode: flat
- template_reuse_scope: style

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- Do not download the screenshots or monitoring charts from the blog into the deck (user)
- No AI image generation and no web image search (user)
- No sound effects and no path animation (user)
- Output entirely in English; SVG text, notes, and the bodies of design_spec / spec_lock carry no CJK characters (user)
- Write a single concrete font name, never a comma-separated stack (user)
- Do not downgrade the visual work in order to make an object natively editable (user)
