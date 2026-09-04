<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1240 1754
- format: A4 Print

## communication
- primary_language: zh-CN
- audience: 天天喝茶但没系统学过茶的普通读者，知道名茶的名字却说不清它们凭什么分类
- objective: 教会读者"茶类由加工工艺决定"这一条判据并逐类讲清，直到读者能指认任意一类的关键工序与代表茶，并按页上的水温与时间泡对一杯
- core_message: 六大茶类不是按颜色分的，是按工艺（尤其氧化/发酵程度）分的
- consumption_mode: text

## mode
- mode: instructional

## visual_style
- visual_style: ink-notes

## colors
- background: #FAF9F5
- secondary_bg: #F0EDE4
- primary: #1C1A17
- accent: #A62F1F
- secondary_accent: #6E9B3A
- body_text: #1C1A17
- secondary_text: #6B665C
- divider: #C9C3B4
- tea_green: #6E9B3A
- tea_white: #D6C079
- tea_yellow: #D9A526
- tea_oolong: #B5761B
- tea_red: #A62F1F
- tea_dark: #5A3B26
- image_rendering: ink-notes

## typography
- font_family: Microsoft YaHei
- title_family: KaiTi
- body_family: Microsoft YaHei
- data_family: Times New Roman
- display_family: KaiTi
- body: 46
- title: 84
- subtitle: 60
- annotation: 34
- display: 156
- lead: 54
- data: 68
- footnote: 26

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/temperature, tabler-outline/clock, tabler-outline/droplet, tabler-outline/leaf, tabler-outline/flame, tabler-outline/arrow-narrow-right, tabler-outline/star, tabler-outline/bulb, tabler-outline/alert-triangle, tabler-outline/link

## images
- p01_word_green: images/word_green.png | source=slice | crop=no-crop
- p01_word_white: images/word_white.png | source=slice | crop=no-crop
- p01_word_yellow: images/word_yellow.png | source=slice | crop=no-crop
- p01_word_oolong: images/word_oolong.png | source=slice | crop=no-crop
- p01_word_red: images/word_red.png | source=slice | crop=no-crop
- p01_word_dark: images/word_dark.png | source=slice | crop=no-crop
- p02_leaf_green: images/leaf_green.png | source=slice | crop=no-crop
- p02_leaf_white: images/leaf_white.png | source=slice | crop=no-crop
- p02_leaf_yellow: images/leaf_yellow.png | source=slice | crop=no-crop
- p02_leaf_oolong: images/leaf_oolong.png | source=slice | crop=no-crop
- p02_leaf_red: images/leaf_red.png | source=slice | crop=no-crop
- p02_leaf_dark: images/leaf_dark.png | source=slice | crop=no-crop
- p03_ware_kettle: images/ware_kettle.png | source=slice | crop=no-crop
- p07_ware_gaiwan: images/ware_gaiwan.png | source=slice | crop=no-crop
- p09_ware_cup: images/ware_cup.png | source=slice | crop=no-crop

## page_rhythm
- P01: anchor
- P02: dense
- P03: dense
- P04: breathing
- P05: dense
- P06: dense
- P07: dense
- P08: dense
- P09: anchor

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 无纸纹、无投影、无渐变 (user)
- font-family 写单一具体名不要逗号栈 (user)
