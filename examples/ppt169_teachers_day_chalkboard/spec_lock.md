<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-Hans-CN
- audience: 中小学师生与到校家长,以及负责出黑板报的宣传委员和班主任
- objective: 用一整卷黑板报把教师节的来历与教师队伍的规模讲清楚,使听众能说出 9 月 10 日的由来、举出一个尊师典故,并愿意当天对老师说一句具体的话
- core_message: 教师节被提了四次、改了四次日期,才在 1985 年落到 9 月 10 日;今天全国有 1870.10 万名专任教师
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: narrative, instructional
- mode_behavior: 全卷主轴按 narrative 的 situation → tension → resolution 走四次改期的曲折;每页内部按 instructional 分块并列,一个主栏讲透一段,两到三个小栏目平行承载可扫读的碎片,转场页用板擦擦过完成幕切。

## visual_style
- visual_style: chalkboard

## colors
- background: #1E2B27
- secondary_bg: #26352F
- primary: #F4F1E8
- accent: #F3C969
- secondary_accent: #9FD0C0
- body_text: #E8E4D8
- secondary_text: #B4AE9E
- divider: #46564F
- chalk_rose: #E8A0A8
- surface: #2B3A34
- grid: #38473F
- block_shade: #24322C
- image_rendering: chalkboard

## typography
- font_family: "Microsoft YaHei", Arial, sans-serif
- title_family: KaiTi, "Trebuchet MS", serif
- body_family: "Microsoft YaHei", Arial, sans-serif
- quote_family: KaiTi, "Times New Roman", serif
- data_family: "Trebuchet MS", "Microsoft YaHei", sans-serif
- annotation_family: "Microsoft YaHei", Arial, sans-serif
- emphasis_family: "Trebuchet MS", "Microsoft YaHei", sans-serif
- body: 24
- title: 44
- subtitle: 32
- cover_title: 84
- column_head: 28
- lead: 30
- quote: 30
- data: 64
- annotation: 18
- emphasis: 40
- footnote: 16

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/chalkboard-teacher, tabler-outline/school, tabler-outline/pencil, tabler-outline/book-2, tabler-outline/calendar-event, tabler-outline/quote, tabler-outline/award, tabler-outline/users-group, tabler-outline/star, tabler-outline/bulb, tabler-outline/ruler-2, tabler-outline/world, tabler-outline/snowflake, tabler-outline/mail-heart, tabler-outline/link

## images
- p01_lettering: images/cover_lettering.png | source=slice | crop=no-crop
- p01_podium: images/art_podium.png | source=slice | crop=no-crop
- p02_head: images/head_p02.png | source=slice | crop=no-crop
- p03_head: images/head_p03.png | source=slice | crop=no-crop
- p04_head: images/head_p04.png | source=slice | crop=no-crop
- p05_head: images/head_p05.png | source=slice | crop=no-crop
- p06_head: images/head_p06.png | source=slice | crop=no-crop
- p07_head: images/head_p07.png | source=slice | crop=no-crop
- p07_stub: images/art_chalk_stub.png | source=slice | crop=no-crop
- p08_head: images/head_p08.png | source=slice | crop=no-crop
- p09_head: images/head_p09.png | source=slice | crop=no-crop
- p10_head: images/head_p10.png | source=slice | crop=no-crop
- p10_globe: images/art_globe_caps.png | source=slice | crop=no-crop
- p11_head: images/head_p11.png | source=slice | crop=no-crop
- p11_snow: images/art_snow_gate.png | source=slice | crop=no-crop
- p11_book: images/art_book_brush.png | source=slice | crop=no-crop
- p12_head: images/head_p12.png | source=slice | crop=no-crop
- p13_head: images/head_p13.png | source=slice | crop=no-crop
- p13_flower: images/art_flower_card.png | source=slice | crop=no-crop

## page_rhythm
- P01: anchor
- P02: breathing
- P03: dense
- P04: dense
- P05: dense
- P06: breathing
- P07: anchor
- P08: dense
- P09: dense
- P10: dense
- P11: dense
- P12: breathing
- P13: anchor

## page_visualizations
- P08: chart/column_chart
- P09: chart/horizontal_bar_chart
- P10: table/record_table

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 不套任何 Style/Brand/Layout 模板 (user)
- 计数类图形(几颗星、几个人)不要交给生图模型,用原生 SVG 画 (user)
- Morph 只配相邻页且不配原生图表 (user)
- 不编数字 (user)
