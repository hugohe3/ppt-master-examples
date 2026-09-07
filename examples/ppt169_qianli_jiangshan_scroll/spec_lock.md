<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 对中国艺术与历史有兴趣的普通文化受众，多数人只见过这幅画的一小段
- objective: 让听众"看见"这幅画并复述三件事（十八岁半年成画、矿物颜料五层叠出、2017 年首次全卷打开），并把"再展出时去看、慢慢看"记在心里
- core_message: 一卷近十二米的青绿，是一个十八岁少年半年的功夫，也是九百年里无数双手的接力；它极少打开，值得你等一次、看一次
- consumption_mode: presentation

## mode
- mode: custom
- mode_references: narrative
- mode_behavior: 以 narrative 的情境—张力—转折—回望—邀请为唯一骨架：P01–P02 熟悉的世界，P03–P04 张力，P05–P06 人物与工艺，P07–P08 画面证据，P09 最克制的转折，P10–P11 回望，P12 今天，P13 邀请，P14 出处；标题是推进节拍的句子，一页一个主导元素。

## visual_style
- visual_style: custom
- visual_style_references: ink-wash
- visual_style_behavior: 取 ink-wash 的绢纸留白、极少装饰、一枚印章作焦点的纪律，把近单色水墨换成青绿重彩：石青作主色块与大字，石绿作第二色带，赭石作衬底与过渡，朱砂只在印章与一处强调出现；载体是出血的画卷视窗、绢面大字与印章、透明底矿物与画具元素；一条低矮的横向线统一节奏，不用卡片网格、圆角容器与投影；文字压画时用同色系 scrim 或画面安静区。

## colors
- background: #F3ECDA
- secondary_bg: #10282C
- primary: #2B5C8A
- accent: #B5382B
- secondary_accent: #3F8F6C
- body_text: #1F2422
- secondary_text: #6E675B
- divider: #D8CDB2
- ochre: #A8734A
- surface: #FAF6EC
- scrim: #10282C
- image_rendering: custom
- image_rendering_references: watercolor
- image_rendering_behavior: 青绿重彩的矿物颜料质感——墨线轻勾轮廓，以石青、石绿、赭石的颗粒状矿物色层层堆出体积，颜色不透明、有细微颗粒与绢纹，边缘保留一点 watercolor 式洇开；不用平涂描边与摄影质感，深度靠饱和度前后差，不加投影。

## typography
- font_family: Microsoft YaHei, Arial, sans-serif
- title_family: KaiTi, Times New Roman, serif
- body_family: Microsoft YaHei, Arial, sans-serif
- display_family: KaiTi, Times New Roman, serif
- quote_family: KaiTi, Times New Roman, serif
- annotation_family: Microsoft YaHei, Arial, sans-serif
- body: 28
- title: 48
- subtitle: 36
- lead: 32
- annotation: 20
- footnote: 16
- display: 120
- quote: 34

## icons
- library: none
- inventory: none

## images
- scroll_start: images/scroll_start.jpg | source=web | crop=adaptive
- scroll_strip: images/scroll_strip.png | source=web | crop=no-crop
- scroll_section1: images/scroll_section1.jpg | source=web | crop=adaptive
- scroll_bridge: images/scroll_bridge.jpg | source=web | crop=adaptive
- scroll_river1_faded: images/scroll_river1_faded.png | source=web | crop=adaptive
- scroll_end: images/scroll_end.jpg | source=web | crop=adaptive
- obj_azurite: images/obj_azurite.png | source=slice | crop=no-crop
- obj_malachite: images/obj_malachite.png | source=slice | crop=no-crop
- obj_ochre: images/obj_ochre.png | source=slice | crop=no-crop
- obj_dish: images/obj_dish.png | source=slice | crop=no-crop
- obj_brush: images/obj_brush.png | source=slice | crop=no-crop
- obj_seal: images/obj_seal.png | source=slice | crop=no-crop
- obj_scroll: images/obj_scroll.png | source=slice | crop=no-crop
- obj_pine: images/obj_pine.png | source=slice | crop=no-crop
- fig_painter_desk: images/fig_painter_desk.png | source=slice | crop=no-crop
- fig_painter_scroll: images/fig_painter_scroll.png | source=slice | crop=no-crop
- fig_visitor: images/fig_visitor.png | source=slice | crop=no-crop
- word_qianli: images/word_qianli.png | source=slice | crop=no-crop

## page_visualizations
- P06: table/record_table

## page_rhythm
- P01: anchor
- P02: breathing
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
- P13: anchor
- P14: dense

## pptx_structure
- mode: flat
- template_reuse_scope: style

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
