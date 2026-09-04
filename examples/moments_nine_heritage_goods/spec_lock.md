<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1080 1080
- format: Moments/Instagram

## communication
- primary_language: zh-CN
- audience: 微信朋友圈里刷到九宫格的普通中文读者，对老物件与上海制造有兴趣但不了解具体年份与厂家
- objective: 让每一张单独成立地讲清一件老国货的年份、产地与当年风靡的理由，并把怀旧收束到今天还能怎么遇见它，读者看完能说出其中几件的诞生年份与产地、知道哪几件今天仍买得到或看得到
- core_message: 这九件 1935–1972 年的中国国货大多还在生产、还在货架上、还在博物馆里，今天仍然遇得到
- consumption_mode: balanced

## mode
- mode: showcase

## visual_style
- visual_style: vintage-poster

## colors
- background: #F4E7CE
- secondary_bg: #E3CFA4
- primary: #B3402F
- accent: #E0952B
- secondary_accent: #2F6B5E
- body_text: #2A2420
- secondary_text: #6B5C4A
- divider: #C3AC80
- image_rendering: vintage-poster

## typography
- font_family: Microsoft YaHei
- title_family: SimHei
- body_family: Microsoft YaHei
- numeral_family: SimHei
- body: 30
- title: 54
- subtitle: 38
- lead: 36
- annotation: 22
- footnote: 18
- numeral: 88

## icons
- library: chunk-filled
- inventory: icons/chunk-filled/calendar.svg, icons/chunk-filled/factory.svg, icons/chunk-filled/fire.svg, icons/chunk-filled/shop.svg, icons/chunk-filled/trophy.svg

## images
- p01_word: images/word_cover.png | source=slice | crop=no-crop
- p01_stamp: images/deco_stamp.png | source=slice | crop=no-crop
- p02_word: images/word_huili.png | source=slice | crop=no-crop
- p02_good: images/good_shoe.png | source=slice | crop=no-crop
- p03_word: images/word_yongjiu.png | source=slice | crop=no-crop
- p03_good: images/good_bike.png | source=slice | crop=no-crop
- p03_rays: images/deco_rays.png | source=slice | crop=no-crop
- p04_word: images/word_guangming.png | source=slice | crop=no-crop
- p04_good: images/good_icebrick.png | source=slice | crop=no-crop
- p04_sun: images/deco_sun.png | source=slice | crop=no-crop
- p05_word: images/word_shanghai.png | source=slice | crop=no-crop
- p05_good: images/good_watch.png | source=slice | crop=no-crop
- p06_word: images/word_dabaitu.png | source=slice | crop=no-crop
- p06_good: images/good_candy.png | source=slice | crop=no-crop
- p06_badge: images/deco_badge.png | source=slice | crop=no-crop
- p07_word: images/word_yingxiong.png | source=slice | crop=no-crop
- p07_good: images/good_pen.png | source=slice | crop=no-crop
- p08_word: images/word_haiou.png | source=slice | crop=no-crop
- p08_good: images/good_camera.png | source=slice | crop=no-crop
- p09_word: images/word_hudie.png | source=slice | crop=no-crop
- p09_good: images/good_sewing.png | source=slice | crop=no-crop
- p10_word: images/word_hongdeng.png | source=slice | crop=no-crop
- p10_good: images/good_radio.png | source=slice | crop=no-crop

## page_rhythm
- P01: anchor
- P02: dense
- P03: dense
- P04: breathing
- P05: dense
- P06: dense
- P07: breathing
- P08: dense
- P09: dense
- P10: breathing
- P11: anchor

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 大块平涂有限色、圆角几何、略微离轴、半调网点或纸纹用原生 pattern，无渐变无投影 (user)
- font-family 写单一具体名不要逗号栈 (user)
- 查不到写 NO DATA 不编造 (user)
