<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 来访的省交通部门代表团,关心宏观数据、建设成效与安全绿色治理
- objective: 汇报2024年全国铁路运输生产、建设、装备、科技与治理成效,使代表团记住核心增长数字并认可铁路发展进展
- core_message: 2024年铁路运输生产量质齐升、建设与装备持续扩能、安全绿色底线守住,支撑经济回升向好
- consumption_mode: balanced

## mode
- mode: pyramid

## visual_style
- visual_style: data-journalism

## colors
- background: #F6F7FA
- secondary_bg: #E7EAF1
- primary: #14335C
- accent: #C81E3A
- secondary_accent: #1D7A8C
- body_text: #232B36
- secondary_text: #5B6472
- divider: #D7DBE3
- positive: #2E7D32
- negative: #C62828

## typography
- font_family: Microsoft YaHei, SimHei
- title_family: SimSun, FangSong
- body_family: Microsoft YaHei, SimHei
- data_family: Consolas, Courier New
- hero_family: Consolas, Courier New
- cover_display_family: SimSun, FangSong
- body: 24
- title: 40
- subtitle: 30
- lead: 28
- hero: 64
- cover_display: 88
- annotation: 18
- footnote: 16

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/users, tabler-outline/train, tabler-outline/truck, tabler-outline/route, tabler-outline/building-skyscraper, tabler-outline/coin, tabler-outline/bolt, tabler-outline/leaf, tabler-outline/shield-check, tabler-outline/award, tabler-outline/gavel, tabler-outline/target, tabler-outline/globe, tabler-outline/map-2, tabler-outline/flag-2

## images
- p01: images/fuxing_train_cover.jpg | source=user | crop=adaptive
- p02: images/beijing_south_station.jpg | source=user | crop=adaptive
- p04: images/shanghai_hongqiao.jpg | source=user | crop=adaptive
- p08: images/bridge_hero.jpg | source=user | crop=adaptive
- p09: images/bridge_detail.jpg | source=user | crop=adaptive
- p10: images/fuxing_train_device.jpg | source=user | crop=adaptive
- p11: images/fuxing_interior.jpg | source=user | crop=adaptive
- p14: images/qinghai_green.jpg | source=user | crop=adaptive

## page_rhythm
- P01: anchor
- P02: anchor
- P03: dense
- P04: dense
- P05: dense
- P06: dense
- P07: breathing
- P08: dense
- P09: breathing
- P10: dense
- P11: breathing
- P12: dense
- P13: dense
- P14: dense
- P15: anchor

## pptx_structure
- mode: flat

## page_visualizations
- P04: table/metric_table
- P05: table/metric_table
- P06: chart/column_chart
- P08: chart/progress_bar_chart
- P10: table/metric_table
- P12: chart/line_chart
- P14: chart/column_chart

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 数字只用附件里的,每个数字标出处 (user)
- 照片要用上并按许可署名,不要用AI生图代替真实照片 (user)
