<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 一半中国同事(产业研究、销售与战略)、一半海外合作伙伴(经销商与合资方),双方熟悉行业但对中国统计口径与政策细节掌握不同
- objective: 用口径明确的公开数据讲清 2025 年出海规模与结构,解释关税与本地化的因果,使中外双方能用同一套数字描述格局并对 2026 年增量重心转向海外生产形成共识
- core_message: 2025 年中国新能源汽车出口翻倍至 261.5 万辆(中汽协口径),增长方式已从卖整车转向在当地造车与建网络,2026 年增量要靠海外产能与价格承诺机制
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: briefing, pyramid
- mode_behavior: 每个部分的首页先给一句可引用的判断句,部分内各页按等权可扫读方式铺事实与口径,标题写判断不写话题词,结尾把四个部分的判断收束为双方可共同使用的议题。

## visual_style
- visual_style: custom
- visual_style_references: data-journalism, swiss-minimal, editorial
- visual_style_behavior: 12 栏硬栅格与大留白承载同页双语,中文主行在上、英文副行在下并以更小字号、次级文字色与细线左缘标记为副层;多栏证据密度、微型图注与常驻来源条来自数据新闻版面,中文衬线标题与拉丁衬线副标题构成层级互文,圆角为零、装饰近零,分层只靠栅格与细规则线。

## colors
- background: #FFFFFF
- secondary_bg: #F2F4F7
- primary: #0E3A66
- accent: #D4541E
- secondary_accent: #2E7D8F
- body_text: #1B2430
- secondary_text: #5C6673
- divider: #D8DEE6
- surface: #FAFBFC
- grid: #E8ECF1
- positive: #2E7D32
- negative: #C62828
- warning: #F57C00
- image_rendering: custom
- image_rendering_references: editorial, minimalist-swiss
- image_rendering_behavior: 扁平矢量编辑插画,等宽 1.5px 深蓝轮廓与纯平色块,深度靠体块重叠而非渐变,哑光纸面质感,情绪安静可引用,不含任何品牌标识与文字。

## typography
- font_family: Microsoft YaHei
- title_family: SimSun
- body_family: Microsoft YaHei
- en_title_family: Cambria
- en_body_family: Cambria
- display_family: SimSun
- body: 22
- title: 40
- subtitle: 28
- lead: 26
- annotation: 17
- footnote: 14
- display: 64
- en_title: 24
- en_body: 18

## icons
- library: chunk-filled
- inventory: icons/chunk-filled/ship.svg, icons/chunk-filled/factory.svg, icons/chunk-filled/truck.svg, icons/chunk-filled/plug.svg, icons/chunk-filled/globe.svg, icons/chunk-filled/map-pin.svg, icons/chunk-filled/chart-bar.svg, icons/chunk-filled/chart-line.svg, icons/chunk-filled/table.svg, icons/chunk-filled/percent.svg, icons/chunk-filled/shield-check.svg, icons/chunk-filled/circle-exclamation.svg, icons/chunk-filled/circle-checkmark.svg, icons/chunk-filled/calendar.svg, icons/chunk-filled/coin.svg, icons/chunk-filled/building.svg, icons/chunk-filled/target.svg, icons/chunk-filled/arrow-trend-up.svg

## images
- p01: images/cover_port_roro.jpg | source=ai | crop=adaptive
- p09: images/local_plant.jpg | source=ai | crop=adaptive
- p11: images/charging_array.jpg | source=ai | crop=adaptive

## page_visualizations
- P04: chart/donut_chart
- P05: chart/column_chart
- P07: chart/horizontal_bar_chart
- P08: table/metric_table
- P10: table/record_table

## page_rhythm
- P01: anchor
- P02: anchor
- P03: breathing
- P04: dense
- P05: dense
- P06: breathing
- P07: dense
- P08: dense
- P09: breathing
- P10: dense
- P11: dense
- P12: dense
- P13: breathing
- P14: dense
- P15: anchor

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 不要用真实品牌 logo (user)
