<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 对都江堰只有课本印象的一般成年读者与通识听众
- objective: 先讲清三大主体工程如何分水、排沙、引水，再用口诀、岁修与今天的灌区数据说明它为何仍在运行，使听众能自行复述三者分工并举出一个今天仍在运行的具体数字
- core_message: 都江堰不是古迹而是仍在运行的系统，靠顺应水势的三级分工与写进制度的岁修把公元前 256 年的方案用到今天
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: instructional, narrative
- mode_behavior: 按问题—机制拆解—机制合拢—制度—今天五段推进：以成都平原涝旱并存的矛盾开场，用三页并列拆解鱼嘴／飞沙堰／宝瓶口，再把三件放回同一张总图讲一次洪水中的动作顺序，最后由治水口诀与岁修制度过渡到今天的灌区数字收束开篇矛盾；每页标题写成一句可复述的机制判断。

## visual_style
- visual_style: custom
- visual_style_references: blueprint, data-journalism
- visual_style_behavior: 版面即图纸——深底上以单一线色的细线框、引线、尺寸括号与极淡底纹网格构成全部结构，几乎不用实心色块与圆角；原理页让示意图充当版式骨架、文字挂在引线端点，角落保留图纸标题栏；数据页改用多栏栅格、发丝分隔线、等宽数字、超大英雄数字与页脚来源行，图表横跨主栏充当版面脊柱；全卷只有一个暖色重点色用来标注当前正在讲的那一件。

## colors
- background: #0B1B2E
- secondary_bg: #11263D
- primary: #4A90C2
- accent: #E8A33D
- secondary_accent: #7FD1C3
- body_text: #D6E4F0
- secondary_text: #93AEC8
- divider: #1E3A57
- surface: #16314C
- grid: #17304A

## typography
- font_family: Microsoft YaHei, Consolas, sans-serif
- title_family: SimHei, Consolas, sans-serif
- body_family: Microsoft YaHei, Consolas, sans-serif
- display_family: SimHei, Consolas, sans-serif
- annotation_family: Microsoft YaHei, Consolas, sans-serif
- footnote_family: Microsoft YaHei, Consolas, sans-serif
- lead_family: Microsoft YaHei, Consolas, sans-serif
- body: 24
- title: 42
- subtitle: 32
- annotation: 18
- cover_title: 88
- chapter_title: 56
- lead: 30
- display: 72
- footnote: 16

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/droplet, tabler-outline/mountain, tabler-outline/arrows-split, tabler-outline/ripple, tabler-outline/ruler-measure, tabler-outline/calendar-repeat, tabler-outline/award, tabler-outline/wheat, tabler-outline/alert-triangle, tabler-outline/chart-line, tabler-outline/map-pin, tabler-outline/topology-star, tabler-outline/wave-sine, tabler-outline/history

## images
- p01: images/dujiangyan_weir_aerial.jpg | source=web | crop=adaptive
- p09: images/dujiangyan_channel_scene.jpg | source=web | crop=adaptive

## page_rhythm
- P01: anchor
- P02: anchor
- P03: dense
- P04: breathing
- P05: dense
- P06: dense
- P07: dense
- P08: dense
- P09: breathing
- P10: dense
- P11: dense
- P12: dense
- P13: breathing
- P14: anchor

## page_visualizations
- P05: chart/stacked_bar_chart
- P11: chart/line_chart
- P12: table/record_table

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
