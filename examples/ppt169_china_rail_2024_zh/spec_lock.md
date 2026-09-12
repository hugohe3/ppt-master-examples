<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 来访的省交通运输部门代表团,熟悉交通运输统计口径,未系统读过《2024年铁道统计公报》
- objective: 完整汇报 2024 年全国铁路的运输生产、建设、装备、路网与节能减排数据,使来访方能复述关键数值及其同比方向并说出每个数字的出处
- core_message: 2024 年全国铁路客运创历史高位(43.12 亿人,+11.9%),货运总量稳中有升而周转量小幅回落,路网与装备继续扩张,能耗强度微升而主要污染物持续下降
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: pyramid, briefing
- mode_behavior: 开篇用 pyramid 把全年判断提到第二页,主体按 briefing 的等权板块推进,每个板块标题写成一句可复述的判断句,板块内先给数字再给结构,末页回到三条判断收束。

## visual_style
- visual_style: custom
- visual_style_references: data-journalism, swiss-minimal, photo-editorial
- visual_style_behavior: 数据页由 data-journalism 负责多栏证据密度、边注与页底来源条,由 swiss-minimal 负责左对齐栅格、直角容器、发丝分隔线与大留白(容器一律直角,不用圆角卡片堆叠);现场页由 photo-editorial 负责整幅出血照片、压暗安静区承接文字、极小字号的边缘署名。白底高密度的数据页与深色低密度的现场页交替出现。

## colors
- background: #FFFFFF
- secondary_bg: #F2F5F9
- primary: #0B3A6F
- accent: #C8102E
- secondary_accent: #1E6FB8
- body_text: #1E2733
- secondary_text: #5A6775
- divider: #D8DEE6
- surface: #F8FAFC
- grid: #E6EBF1
- scrim: #0A1B2E
- positive: #2E7D32
- negative: #C62828

## typography
- font_family: Microsoft YaHei, Arial, sans-serif
- title_family: SimHei, Arial, sans-serif
- body_family: Microsoft YaHei, Arial, sans-serif
- display_family: SimHei, Arial, sans-serif
- annotation_family: Microsoft YaHei, Arial, sans-serif
- footnote_family: Microsoft YaHei, Arial, sans-serif
- body: 24
- title: 40
- subtitle: 32
- cover_title: 76
- lead: 28
- display: 64
- annotation: 18
- footnote: 15

## icons
- library: chunk-filled
- inventory: icons/chunk-filled/train.svg, icons/chunk-filled/users.svg, icons/chunk-filled/truck.svg, icons/chunk-filled/box.svg, icons/chunk-filled/fire.svg, icons/chunk-filled/factory.svg, icons/chunk-filled/droplet.svg, icons/chunk-filled/seedling.svg, icons/chunk-filled/leaf.svg, icons/chunk-filled/recycle.svg, icons/chunk-filled/bridge.svg, icons/chunk-filled/route.svg, icons/chunk-filled/coin.svg, icons/chunk-filled/shield-check.svg, icons/chunk-filled/badge-check.svg, icons/chunk-filled/trophy.svg, icons/chunk-filled/lightbulb.svg, icons/chunk-filled/globe.svg, icons/chunk-filled/gauge-high.svg, icons/chunk-filled/file.svg

## images
- p01: images/fuxing_train.jpg | source=user | crop=adaptive
- p04: images/beijing_south_station.jpg | source=user | crop=adaptive
- p05: images/shanghai_hongqiao.jpg | source=user | crop=adaptive
- p09: images/fuxing_interior.jpg | source=user | crop=adaptive
- p10: images/danyang_kunshan_bridge.jpg | source=user | crop=adaptive
- p13: images/qinghai_tibet_railway.jpg | source=user | crop=adaptive
- p15: images/fuxing_train_wash.jpg | source=user | crop=adaptive

## page_visualizations
- P03: chart/column_chart
- P04: table/hierarchical_table
- P06: chart/column_chart
- P07: chart/horizontal_bar_chart
- P08: chart/area_chart
- P09: table/record_table
- P11: chart/line_chart
- P13: chart/line_chart

## page_rhythm
- P01: anchor
- P02: dense
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
- P14: breathing
- P15: anchor

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 数字只用附件里的 (user)
- 不要用 AI 生图代替真实照片 (user)
