# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 科技/金融行业研究者、AI 从业者、风险投资圈、媒体编辑
- objective: 用十八张数据图按全景、三巨头、中国阵营、二线梯队、基础设施闭环、泡沫六个部分铺开 2026 年的 AI 资本格局，最后交出六条判断
- core_message: 2026 年全球 AI 资本以前所未有的集中度涌入少数公司，而资本开支与商业收入的剪刀差已超过 2001 年电信泡沫
- consumption_mode: presentation

## colors
- bg: #0E1116
- secondary_bg: #1A1F26
- primary: #E8E6E1
- accent: #E63946
- secondary_accent: #F4A261
- text: #C9C5BE
- text_secondary: #8A857E
- text_tertiary: #5C5852
- border: #2A2F36
- success: #52B788
- warning: #E63946
- image_rendering: editorial
- image_palette: dark-cinematic

## typography
- font_family: "Microsoft YaHei", Arial, sans-serif
- body_family: "Microsoft YaHei", Arial, sans-serif
- title_family: Cambria, "Microsoft YaHei", serif
- subtitle_family: Cambria, serif
- emphasis_family: Georgia, "Microsoft YaHei", serif
- code_family: Consolas, "Courier New", monospace
- body: 16
- title: 28
- subtitle: 20
- annotation: 12
- hero_number: 80
- cover_title: 72
- chapter_title: 44
- chapter_mark: 180
- big_quote_mark: 120
- footnote: 10
- lead: 24
- chapter_lead: 32
- stat: 40
- kpi: 48
- display_m: 56
- hero_stat: 64

## icons
- library: tabler-outline
- stroke_width: 1.5
- brand_library: simple-icons
- inventory: trending-up, currency-dollar, building, chart-bar, server, bolt, alert-triangle, globe, cpu, trending-down, arrow-right, bookmark, world, link, percentage, target, scale, briefcase
- brand_inventory: openai, anthropic, nvidia, google, microsoft, amazon, meta, oracle, softbank

## images
- cover_atmosphere: images/cover_atmosphere.jpg
- nvidia_circular: images/nvidia_circular.jpg
- bubble_tension: images/bubble_tension.jpg

## page_rhythm
- P01: anchor
- P02: breathing
- P03: anchor
- P04: dense
- P05: dense
- P06: dense
- P07: dense
- P08: dense
- P09: dense
- P10: dense
- P11: dense
- P12: dense
- P13: breathing
- P14: dense
- P15: dense
- P16: dense
- P17: breathing
- P18: dense
- P19: dense
- P20: anchor

## page_charts
- P04: kpi_cards
- P05: bar_chart
- P06: dumbbell_chart
- P07: bubble_chart
- P08: donut_chart
- P10: horizontal_bar_chart
- P11: comparison_table
- P14: sankey_chart
- P15: pareto_chart
- P16: hub_spoke
- P18: dual_axis_line_chart
- P19: quadrant_text_bullets

## pptx_structure
- mode: flat

## forbidden
- Mixing icon libraries
- `<style>`, `class`, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<script>`, `<iframe>`, `<symbol>`+`<use>`
- HTML named entities in text (`&nbsp;`, `&mdash;`, `&copy;`, `&ndash;`, `&reg;`, `&hellip;`, `&bull;` …) — write as raw Unicode (`—`, `©`, `→`, NBSP, etc.); XML reserved chars `& < > " '` must be escaped as `&amp; &lt; &gt; &quot; &apos;`
