<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 公司读书会成员,来自不同部门、非物流专业,对"一个铁盒子怎么会那么重要"普遍存疑
- objective: 用 1956 年那一船切入,讲清标准化与多式联运两个机制,交代代价与今天的量级,使听众能复述三个成立条件与两组带年份的量化对照,并愿意就"下一个集装箱是什么"发言
- core_message: 改变世界的不是那个铁盒子,而是所有人同意用同一个盒子
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: narrative, showcase
- mode_behavior: 以 1956 年 4 月 26 日那一船的具体数字开场,按"旧世界的代价 → 那一船 → 为什么它没有立刻改变世界 → 标准怎么成立 → 战争把它推向亚洲 → 代价与今天的量级 → 留给现场的问题"推进张力弧,每章以一句可争论的判断收束;页面节奏一页一个主张,数字以版面焦点的大字对照出现,解释留给讲者与备注。

## visual_style
- visual_style: custom
- visual_style_references: photo-editorial, editorial, data-journalism
- visual_style_behavior: 满幅照片承担论证,每页图片至少触及一条画布边,文字反白压在黑色渐变 scrim 上;层级靠一根 6 px 橙色短棒起笔与固定 24 px 块间距建立,正文自左上起排;每一页带外部事实的版面在 80 px 文字下边距内贴一条 16 px 来源行写明出处与年份,自建归类框架在页面右端标「整理」;唯一热点色是集装箱橙,只给数字和一个关键词。

## colors
- background: #0B1220
- secondary_bg: #16212F
- primary: #4A86B4
- accent: #E2761C
- secondary_accent: #BCD4E8
- body_text: #E8EFF6
- secondary_text: #C7D3DE
- divider: #2B3A4C
- scrim: #000000
- surface: #16212F
- image_rendering: custom
- image_rendering_references: corporate-photo, editorial
- image_rendering_behavior: 线条与材质走 corporate-photo 的纪实摄影语言,真实焦段与自然光、保留实际质感与真实景深,不插画化,画面内不出现文字、标牌字样或可辨认商标;构图与色彩纪律走 editorial,一个主焦区、对齐隐形栏线、留一块低反差安静区给压字,调色收敛到深蓝黑加一处集装箱橙;历史段落在同一摄影语言内降饱和、暖灰高光、轻微颗粒,当代段落保持全彩冷色夜景;深度靠光而不是靠滤镜。

## typography
- font_family: Microsoft YaHei, Cambria, sans-serif
- title_family: SimHei, Cambria, sans-serif
- body_family: Microsoft YaHei, Cambria, sans-serif
- display_family: SimHei, Cambria, sans-serif
- chapter_title_family: SimHei, Cambria, sans-serif
- chapter_number_family: Cambria, SimHei, serif
- quote_family: SimHei, Cambria, sans-serif
- hero_number_family: Cambria, SimHei, serif
- body: 24
- title: 40
- subtitle: 30
- annotation: 20
- footnote: 16
- display: 64
- chapter_title: 52
- chapter_number: 56
- quote: 44
- hero_number: 150

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: icons/tabler-outline/ruler.svg, icons/tabler-outline/lock.svg, icons/tabler-outline/stack-2.svg, icons/tabler-outline/ship.svg, icons/tabler-outline/clock.svg, icons/tabler-outline/world.svg

## images
- p01: images/cover_night_gantry.jpg | source=ai | crop=adaptive
- p02: images/chapter1_duotone.jpg | source=ai | crop=adaptive
- p03: images/breakbulk_1950s.jpg | source=ai | crop=adaptive
- p04: images/idealx_deck.jpg | source=ai | crop=adaptive
- p05: images/quote_blur.jpg | source=ai | crop=adaptive
- p07: images/iso_container_doors.jpg | source=ai | crop=adaptive
- p08a: images/std_band_size.jpg | source=slice | crop=adaptive
- p08b: images/std_band_lock.jpg | source=slice | crop=adaptive
- p08c: images/std_band_count.jpg | source=slice | crop=adaptive
- p09: images/vietnam_supply_port.jpg | source=ai | crop=adaptive
- p11a: images/scale_cell_piers.jpg | source=slice | crop=adaptive
- p11b: images/scale_cell_elizabeth.jpg | source=slice | crop=adaptive
- p11c: images/scale_cell_yard.jpg | source=slice | crop=adaptive
- p11d: images/scale_cell_megaship.jpg | source=slice | crop=adaptive
- p12: images/closing_shanghai_dawn.jpg | source=ai | crop=adaptive

## page_rhythm
- P01: anchor
- P02: anchor
- P03: dense
- P04: dense
- P05: breathing
- P06: anchor
- P07: anchor
- P08: dense
- P09: dense
- P10: breathing
- P11: dense
- P12: anchor

## pptx_structure
- mode: structured
- template_reuse_scope: layout
- template_adherence: strict

## pptx_masters
- editorial_bleed_master: Editorial Bleed

## pptx_layouts
- hero_full: editorial_bleed_master | Hero Full | template:01_hero_full
- hero_side_scrim: editorial_bleed_master | Hero with Side Scrim | template:02_hero_side_scrim
- split_bleed: editorial_bleed_master | Split Bleed | template:03_split_bleed
- split_bleed_reverse: editorial_bleed_master | Split Bleed Reverse | template:04_split_bleed_reverse
- chapter_full: editorial_bleed_master | Chapter Full | template:05_chapter_full
- quote_over_image: editorial_bleed_master | Quote over Image | template:06_quote_over_image
- triptych: editorial_bleed_master | Triptych | template:07_triptych
- image_grid_four: editorial_bleed_master | Four-Image Grid | template:08_image_grid_four
- full_statement: editorial_bleed_master | Full Statement | template:09_full_statement
- closing_full: editorial_bleed_master | Closing Full | template:10_closing_full

## page_pptx_layouts
- P01: hero_full
- P02: chapter_full
- P03: split_bleed
- P04: split_bleed_reverse
- P05: quote_over_image
- P06: full_statement
- P07: chapter_full
- P08: triptych
- P09: hero_side_scrim
- P10: full_statement
- P11: image_grid_four
- P12: closing_full

## page_layouts
- P01: 01_hero_full
- P02: 05_chapter_full
- P03: 03_split_bleed
- P04: 04_split_bleed_reverse
- P05: 06_quote_over_image
- P06: 09_full_statement
- P07: 05_chapter_full
- P08: 07_triptych
- P09: 02_hero_side_scrim
- P10: 09_full_statement
- P11: 08_image_grid_four
- P12: 10_closing_full

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
