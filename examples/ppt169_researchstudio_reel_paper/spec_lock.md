<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: en-US
- audience: researchers and research engineers at a lab meeting or reading group
- objective: let a skeptical audience trace every conclusion of the paper back to a figure, a table, or a stated method
- core_message: a native-editable, section-aligned dissemination workspace with testable release gates produces posters judged above the authors' own on aesthetics while keeping every artifact editable and cross-linked; the evaluation is proxy-bound and the deck says so
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: instructional, pyramid
- mode_behavior: follow the paper's constructive order — question, prior work, contribution, each skill as one teaching unit (requirements → solution → gate), results, analysis, cost, applications, limitations, conclusion; inside that order every page keeps a pyramid's discipline: the title is an assertion of what the page establishes and the claim line under it names the evidence on the page; sibling skills share one page shape; signposts orient the listener.

## visual_style
- visual_style: swiss-minimal

## colors
- background: #FFFFFF
- secondary_bg: #F3F5F8
- primary: #1B2430
- accent: #1D4ED8
- secondary_accent: #0E9F8A
- body_text: #2F3A48
- secondary_text: #6B7684
- divider: #C9D0D8
- grid: #E6EAEF
- surface: #F3F5F8
- positive: #2E8B57
- warning: #E0A100
- negative: #C0392B

## typography
- font_family: Arial
- title_family: Arial
- body_family: Arial
- data_family: Arial
- body: 16
- title: 28
- subtitle: 18
- lead: 20
- annotation: 12
- footnote: 10
- display: 44
- data: 13

## icons
- library: none
- inventory: none

## page_rhythm
- P01: anchor
- P02: breathing
- P03: dense
- P04: dense
- P05: dense
- P06: dense
- P07: dense
- P08: dense
- P09: dense
- P10: dense
- P11: dense
- P12: dense
- P13: dense
- P14: dense
- P15: dense
- P16: dense
- P17: breathing
- P18: anchor

## images
- p01a: images/poster_beit.jpg | source=user | crop=no-crop
- p01b: images/video_frame_citransnet.jpg | source=user | crop=no-crop
- p01c: images/blog_docx_en.jpg | source=user | crop=no-crop
- p04: images/fig2_pipeline.png | source=user | crop=no-crop
- p06: images/fig3_poster_pipeline.png | source=user | crop=no-crop
- p07a: images/fig4a_fill_initial.png | source=user | crop=no-crop
- p07b: images/fig4b_fill_progress.png | source=user | crop=no-crop
- p07c: images/fig4c_fill_done.png | source=user | crop=no-crop
- p08: images/fig5_video_pipeline.png | source=user | crop=no-crop
- p09: images/fig7_blog_pipeline.png | source=user | crop=no-crop
- p10: images/fig9_reel_interaction.jpg | source=user | crop=no-crop
- p13a: images/fig10a_author_gt.jpg | source=user | crop=no-crop
- p13b: images/fig10b_claude_max.jpg | source=user | crop=no-crop
- p13c: images/fig10c_claude_48.jpg | source=user | crop=no-crop
- p13d: images/fig10d_claude_47.jpg | source=user | crop=no-crop
- p13e: images/fig10e_claude_46.jpg | source=user | crop=no-crop
- p13f: images/fig10f_codex.jpg | source=user | crop=no-crop

## page_visualizations
- P03: table/comparison_matrix
- P06: table/record_table
- P07: chart/stacked_bar_chart
- P08: table/record_table
- P09: table/record_table
- P11: table/comparison_matrix
- P12: chart/scatter_chart
- P14: chart/horizontal_bar_chart
- P16: table/record_table

## pptx_structure
- mode: flat
- template_reuse_scope: style

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
