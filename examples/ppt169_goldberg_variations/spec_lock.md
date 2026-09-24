<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: ppt169

## communication
- primary_language: zh-CN
- audience: 公司古典音乐爱好者小组,多数没学过乐理
- objective: 让零乐理听众看懂哥德堡变奏曲的结构(咏叹调首尾、30 变奏、每三首一卡农、卡农音程递升、共用低音线)并说出古尔德 1955 与 1981 两版的差别,能带着结构地图去听
- core_message: 《哥德堡变奏曲》是一座以低音线为地基、以卡农为梁柱的对称建筑;看懂结构图就能听出它的秩序与自由
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: instructional, narrative
- mode_behavior: 以 instructional 为主轴,先总图再逐层拆解,每页只教一件事、标题直说这页教什么;古尔德两版与收束两页借 narrative 的对照与回环收尾。

## visual_style
- visual_style: custom
- visual_style_references: editorial, ink-notes
- visual_style_behavior: 奶油纸面上的墨色线条系统——editorial 负责衬线标题/无衬线正文对位、细规则线、页边批注与出处小字;ink-notes 负责以墨线而非卡片承载结构:五根平行谱线为贯穿母题,拱形、阶梯、括号、连线用墨线勾勒,节点用小圆点或音符头;暗红只标卡农与当页唯一重点,灰蓝只标小调;几乎不用阴影与卡片网格。

## colors
- background: #F4EFE4
- secondary_bg: #E9E1D0
- primary: #1F2A36
- accent: #9E2A2B
- secondary_accent: #A88452
- body_text: #2B2621
- secondary_text: #6E655A
- divider: #CBBFA8
- minor_key: #4F6A80
- image_rendering: custom
- image_rendering_behavior: Copperplate engraving and etching aesthetic with fine parallel hatching and cross-hatching, uniform dark-ink line weight, no gradients or photographic texture, warm cream paper and at most one tiny muted red touch; depth only from hatch density; calm archival mood of an 18th-century engraved music title page.

## typography
- font_family: Microsoft YaHei, Segoe UI, sans-serif
- title_family: SimSun, Cambria, serif
- body_family: Microsoft YaHei, Segoe UI, sans-serif
- display_family: SimSun, Cambria, serif
- body: 22
- title: 38
- subtitle: 28
- lead: 26
- annotation: 16
- footnote: 14
- display: 88
- cover_title: 60

## icons
- library: tabler-outline
- stroke_width: 1.5
- inventory: tabler-outline/headphones, tabler-outline/ear, tabler-outline/vinyl, tabler-outline/piano, tabler-outline/repeat, tabler-outline/moon, tabler-outline/feather, tabler-outline/calendar, tabler-outline/microphone, tabler-outline/stairs-up, tabler-outline/building-arch, tabler-outline/quote, tabler-outline/clock, tabler-outline/music

## images
- cover_arch: images/cover_arch.jpg | source=ai | crop=adaptive
- studio_chair: images/studio_chair.jpg | source=ai | crop=adaptive
- bach_portrait: images/bach_portrait.jpg | source=web | crop=adaptive
- title_page_1741: images/title_page_1741.jpg | source=web | crop=no-crop

## page_rhythm
- P01: anchor
- P02: dense
- P03: dense
- P04: dense
- P05: dense
- P06: breathing
- P07: dense
- P08: dense
- P09: breathing
- P10: dense
- P11: dense
- P12: anchor

## page_visualizations
- P10: table/comparison_matrix

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 别做成普通的商务模板 (user)
