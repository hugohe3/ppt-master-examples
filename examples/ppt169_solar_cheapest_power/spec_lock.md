<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 能源、电力与产业投资的决策者及其幕僚，熟悉 LCOE 但价格认知停在 2018–2020 年
- objective: 先纠正过时的价格认知并解释成本下降的机制，再主动暴露成本曲线转向与电网侧约束，使决策者能自述学习率机制、成本中心转移与 2021 年拐点，并在下一次投资排序中把并网位置与可调度性排在组件价格之前
- core_message: 光伏已经是多数市场最便宜的新增电源，但它不会自动继续变便宜；决定项目价值的已经不是组件价格，而是并网位置与可调度性
- consumption_mode: balanced

## mode
- mode: pyramid

## visual_style
- visual_style: swiss-minimal

## colors
- background: #FFFFFF
- secondary_bg: #F2F2F2
- primary: #111111
- accent: #C8102E
- secondary_accent: #6E6E6E
- body_text: #1A1A1A
- secondary_text: #6E6E6E
- divider: #D4D4D4
- grid: #E8E8E8

## typography
- font_family: "Microsoft YaHei", Arial, sans-serif
- title_family: "Microsoft YaHei", Arial, sans-serif
- body_family: "Microsoft YaHei", Arial, sans-serif
- display_family: "Arial Black", "Microsoft YaHei", sans-serif
- numeral_family: "Arial Black", "Microsoft YaHei", sans-serif
- data_family: Arial, "Microsoft YaHei", sans-serif
- body: 24
- title: 44
- subtitle: 32
- lead: 30
- annotation: 18
- footnote: 16
- display: 96
- numeral: 160
- data: 20

## icons
- library: tabler-outline
- stroke_width: 1.5
- inventory: tabler-outline/solar-panel, tabler-outline/building-factory-2, tabler-outline/battery-3, tabler-outline/plug-connected, tabler-outline/clock, tabler-outline/trending-down, tabler-outline/trending-up, tabler-outline/alert-triangle, tabler-outline/link, tabler-outline/arrow-narrow-right

## page_rhythm
- P01: anchor
- P02: dense
- P03: dense
- P04: anchor
- P05: breathing
- P06: dense
- P07: dense
- P08: breathing
- P09: dense
- P10: dense
- P11: breathing
- P12: dense
- P13: dense
- P14: dense
- P15: anchor

## page_visualizations
- P02: chart/line_chart
- P03: chart/horizontal_bar_chart
- P06: chart/area_chart
- P09: chart/stacked_bar_chart
- P10: chart/line_chart
- P12: chart/column_chart
- P13: chart/grouped_bar_chart
- P14: table/comparison_matrix

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 不做柔影、不做渐变 (user)
- 不要自己平均 (user)
- 拿不到的数据写 NO DATA，不估算 (user)
- 不为原生降级 (user)
