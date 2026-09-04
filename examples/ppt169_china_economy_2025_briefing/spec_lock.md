<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 没有统计学背景、希望在 15 分钟内看懂 2025 年中国经济全貌的普通读者
- objective: 按读者视角重排统计公报的官方数字，使读者建立总量与结构的坐标系并能自行判断走向，成功标志是能复述五个关键数字与三条主要走向
- core_message: 2025 年国内生产总值 1401879 亿元、增长 5.0%；人口减少 339 万人、投资下降 3.8% 的同时，消费、外贸与新质生产力支撑了这个增速
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: briefing
- mode_behavior: 中性完整可扫读；页标题写主题不写论断，每页 core message 说这一页铺开了什么；同级事实等权，不制造转折与悬念，不替读者下结论；按读者视角分组并给出组标签，顺序可预期。

## visual_style
- visual_style: custom
- visual_style_references: data-journalism
- visual_style_behavior: 出版级密度；图表是版面脊椎，版面绕着可视化排而不装进卡片；发丝分隔线与横贯规则线代替重卡片，规则线落进统计带；侧栏切进栅格承载口径；小倍数条带优于单个大图；数字按含义着色，图表用同族色阶；整体平面，无发光与装饰阴影。

## colors
- background: #F4F1EA
- secondary_bg: #FFFFFF
- primary: #123B57
- accent: #C0392B
- secondary_accent: #2E6F4E
- body_text: #1F2A30
- secondary_text: #5F6B72
- divider: #CFC7B8
- surface: #FFFFFF
- grid: #E4DED0
- positive: #2E6F4E
- warning: #C98B2E
- negative: #C0392B

## typography
- font_family: Microsoft YaHei
- title_family: SimSun
- body_family: Microsoft YaHei
- display_family: Times New Roman
- data_family: Arial
- annotation_family: Microsoft YaHei
- footnote_family: Microsoft YaHei
- body: 24
- title: 42
- subtitle: 32
- cover_title: 84
- display: 72
- lead: 30
- data: 20
- annotation: 18
- footnote: 16

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/chart-bar, tabler-outline/chart-line, tabler-outline/chart-pie, tabler-outline/building-factory-2, tabler-outline/plant-2, tabler-outline/building-store, tabler-outline/users, tabler-outline/home, tabler-outline/briefcase, tabler-outline/coin, tabler-outline/shopping-cart, tabler-outline/building-bridge-2, tabler-outline/ship, tabler-outline/world, tabler-outline/bolt, tabler-outline/leaf, tabler-outline/bulb, tabler-outline/cpu, tabler-outline/school, tabler-outline/heartbeat, tabler-outline/shield-check, tabler-outline/file-text, tabler-outline/link, tabler-outline/trending-up, tabler-outline/trending-down

## page_rhythm
- P01: anchor
- P02: breathing
- P03: dense
- P04: dense
- P05: breathing
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
- P16: breathing
- P17: anchor

## page_visualizations
- P03: chart/line_chart
- P04: chart/donut_chart
- P05: chart/waterfall_chart
- P06: table/hierarchical_table
- P07: chart/column_chart
- P08: chart/horizontal_bar_chart
- P09: chart/stacked_bar_chart
- P10: chart/horizontal_bar_chart
- P11: chart/grouped_bar_chart
- P12: table/metric_table
- P13: chart/pie_chart
- P14: chart/column_chart
- P15: table/metric_table

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 公报没有的数字不写、不推算（需要标注的写 NO DATA） (user)
- font-family 写单一具体名不要逗号栈 (user)
- 音效不配 (user)
