<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1024 768
- format: PPT 4:3

## communication
- primary_language: zh-CN
- audience: 没有生物学背景的成年听众(上班族、学生家长、熬夜的人),知道睡不够会难受,但没想过睡眠内部有结构
- objective: 用一条从共享经验出发的链条把睡眠讲成有结构、有功能的主动过程,使听众能自己说出睡眠压力与生物钟两股力量各是什么、7 小时建议来自谁,并指出脑内清除说尚有争议
- core_message: 睡眠不是关机,而是一段被两股力量安排好的主动工作;把它当成可随时挪用的时间,代价是可核查的
- consumption_mode: presentation

## mode
- mode: custom
- mode_references: instructional
- mode_behavior: 按分解—排序骨架讲解,每一步由上一步欠下的问题引出;每页只加一块必需的积木,类比页在同页写出失效点,结尾回到开头的共享经验重新解释它;标题用白话说出这个想法,术语只在其所指之物出现后登场并同页附白话释义。

## visual_style
- visual_style: custom
- visual_style_references: paper-cut
- visual_style_behavior: 每个元素都是一张剪下来的纸,靠层叠而非描边:切边用略不规则的 polygon/path,层间只用 8–12% 柔影表示高度;暖纸底作为桌面,内容纸盖在上面;底部保留一条贯穿全卷的夜色波浪纸带作为累积容器,同一元素在相邻页保持同位置以便叠加;顶层允许小块镂空口子露出下层。

## colors
- background: #FBF5E9
- secondary_bg: #F0E4CE
- primary: #2E4A7D
- accent: #E08A32
- secondary_accent: #B4553E
- body_text: #2A2622
- secondary_text: #5C554C
- divider: #D9C9AC
- surface: #FFFDF7
- block_shade: #E6D8BE
- light_sleep: #6E8FBF
- image_rendering: custom
- image_rendering_references: paper-cut
- image_rendering_behavior: 彩色卡纸剪贴,无轮廓线,只有略不规则的剪切边;每张纸 12% 纸纹,层间 10% 柔影,不用渐变与高光;哑光卡纸材质,情绪暖而手作;插画必须在解释一件事,图内不出现文字。

## typography
- font_family: Microsoft YaHei, Verdana, sans-serif
- title_family: Microsoft YaHei, Trebuchet MS, sans-serif
- body_family: Microsoft YaHei, Verdana, sans-serif
- data_family: Microsoft YaHei, Verdana, sans-serif
- body: 28
- title: 52
- subtitle: 36
- annotation: 20
- cover_title: 84
- lead: 34
- hero_number: 72
- footnote: 18

## icons
- library: tabler-filled
- inventory: tabler-filled/moon, tabler-filled/sun, tabler-filled/mug, tabler-filled/clock, tabler-filled/bed, tabler-filled/alert-triangle, tabler-filled/book, tabler-filled/link, tabler-filled/droplet, tabler-filled/steering-wheel, tabler-filled/calendar-week, tabler-filled/microscope, tabler-filled/bulb, tabler-filled/hourglass

## images
- p01: images/cover_night_third.jpg | source=ai | crop=adaptive
- p02: images/el_night_window.png | source=slice | crop=no-crop
- p07: images/el_water_vessel.png | source=slice | crop=no-crop
- p08: images/el_tide_arc.png | source=slice | crop=no-crop
- p09: images/el_coffee_block.png | source=slice | crop=no-crop
- p11: images/el_wheel_nod.png | source=slice | crop=no-crop
- p13: images/el_two_papers_question.png | source=slice | crop=no-crop
- p14: images/el_pillow_book.png | source=slice | crop=no-crop

## page_visualizations
- P04: chart/donut_chart
- P05: chart/line_chart
- P09: chart/line_chart
- P10: chart/horizontal_bar_chart
- P12: table/comparison_matrix

## page_rhythm
- P01: anchor
- P02: breathing
- P03: breathing
- P04: dense
- P05: dense
- P06: anchor
- P07: breathing
- P08: breathing
- P09: dense
- P10: dense
- P11: dense
- P12: dense
- P13: breathing
- P14: anchor
- P15: anchor

## pptx_structure
- mode: flat
- template_reuse_scope: style

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 不编数字。找不到的就不写,或写成范围并注明"估计" (user)
- 插画要"解释",不要漂浮的分子/发光大脑/实验室 stock 味 (user)
- 不要为此降级图表 (user)
