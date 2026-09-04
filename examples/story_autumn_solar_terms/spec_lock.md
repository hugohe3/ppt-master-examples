<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1080 1920
- format: Story/Vertical

## communication
- primary_language: zh-CN
- audience: 对传统文化有轻度兴趣、习惯手机竖屏阅读的普通读者，叫得出六个秋节气的名字但说不准日期，也没读过七十二候原文
- objective: 把秋天拆成六个带确切日期的站点并交出完整三候原文，使读者能按顺序复述六个节气及日期、记住至少一条候文，并在下一个节气到来时真的去做一件事
- core_message: 秋天不是一整块，它有六个可以分别过的日子——挑一个，照着过一次
- consumption_mode: balanced

## mode
- mode: showcase

## visual_style
- visual_style: sketch-notes

## colors
- background: #FBF6EA
- secondary_bg: #F1E5CE
- primary: #A8502A
- accent: #E39A1F
- secondary_accent: #6F8C5A
- body_text: #33302A
- secondary_text: #6B6355
- divider: #D8C9AC
- block_shade: #EDE0C6
- image_rendering: sketch-notes

## typography
- font_family: Microsoft YaHei
- title_family: KaiTi
- body_family: Microsoft YaHei
- display_family: KaiTi
- caption_family: Microsoft YaHei
- annotation_family: Microsoft YaHei
- footnote_family: Microsoft YaHei
- body: 56
- title: 100
- cover_title: 160
- display: 128
- subtitle: 72
- lead: 68
- caption: 40
- annotation: 44
- footnote: 32

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/calendar-event, tabler-outline/leaf, tabler-outline/wind, tabler-outline/droplet, tabler-outline/sun, tabler-outline/moon, tabler-outline/snowflake, tabler-outline/cloud, tabler-outline/bowl, tabler-outline/cup, tabler-outline/wheat, tabler-outline/egg, tabler-outline/mountain, tabler-outline/flame, tabler-outline/link, tabler-outline/feather, tabler-outline/fish, tabler-outline/plant

## images
- let_cover: images/let_cover.png | source=slice | crop=no-crop
- let_liqiu: images/let_liqiu.png | source=slice | crop=no-crop
- let_chushu: images/let_chushu.png | source=slice | crop=no-crop
- let_bailu: images/let_bailu.png | source=slice | crop=no-crop
- let_qiufen: images/let_qiufen.png | source=slice | crop=no-crop
- let_hanlu: images/let_hanlu.png | source=slice | crop=no-crop
- let_shuangjiang: images/let_shuangjiang.png | source=slice | crop=no-crop
- let_seal: images/let_seal.png | source=slice | crop=no-crop
- term_liqiu: images/term_liqiu.png | source=slice | crop=no-crop
- term_chushu: images/term_chushu.png | source=slice | crop=no-crop
- term_bailu: images/term_bailu.png | source=slice | crop=no-crop
- term_qiufen: images/term_qiufen.png | source=slice | crop=no-crop
- term_hanlu: images/term_hanlu.png | source=slice | crop=no-crop
- term_shuangjiang: images/term_shuangjiang.png | source=slice | crop=no-crop
- ph_coolwind: images/ph_coolwind.png | source=slice | crop=no-crop
- ph_cicada: images/ph_cicada.png | source=slice | crop=no-crop
- ph_goose: images/ph_goose.png | source=slice | crop=no-crop
- ph_swallow: images/ph_swallow.png | source=slice | crop=no-crop
- ph_chrysanthemum: images/ph_chrysanthemum.png | source=slice | crop=no-crop
- ph_frost: images/ph_frost.png | source=slice | crop=no-crop
- decor_star: images/decor_star.png | source=slice | crop=no-crop
- decor_arrow: images/decor_arrow.png | source=slice | crop=no-crop
- decor_route: images/decor_route.png | source=slice | crop=no-crop
- decor_ribbon: images/decor_ribbon.png | source=slice | crop=no-crop
- food_watermelon: images/food_watermelon.png | source=slice | crop=no-crop
- food_duck: images/food_duck.png | source=slice | crop=no-crop
- food_longan: images/food_longan.png | source=slice | crop=no-crop
- food_qiucai: images/food_qiucai.png | source=slice | crop=no-crop
- food_sesame: images/food_sesame.png | source=slice | crop=no-crop
- food_persimmon: images/food_persimmon.png | source=slice | crop=no-crop

## page_visualizations
- P12: table/record_table

## page_rhythm
- P01: anchor
- P02: breathing
- P03: anchor
- P04: dense
- P05: dense
- P06: breathing
- P07: dense
- P08: dense
- P09: breathing
- P10: dense
- P11: dense
- P12: dense
- P13: anchor
- P14: anchor

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- sketch-notes 的手绘感靠 `<path>` 不齐点的抖线，不用 `<rect rx>` 冒充手绘 (user)
- 纸底可加淡纸纹但不用投影、不用渐变 (user)
- font-family 写单一具体名不要逗号栈 (user)
- 平台留白：story 画布的表意文字/标题/CTA 守 y=120..1740 (user)
