# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 对独立出版 / zine / 艺术书感兴趣的入门读者
- objective: 从 zine 的定义与百年浪潮讲到 Risograph 工艺与一张纸折八页的做法，再带读者逛遍东京、巴黎、柏林与中国大陆的独立书店，最后交出做第一本 zine 的四步
- core_message: zine 是世界上最小的出版社，一张纸加一台复印机就能开始：印一份、送一份、换一份
- consumption_mode: reading

## colors
- bg: #F5EFE0
- secondary_bg: #EAE2CC
- primary: #1E4DBC
- accent: #FF5C8A
- secondary_accent: #E8A02E
- text: #1A1A1A
- text_secondary: #5A5A5A
- text_tertiary: #8C8275
- border: #1A1A1A
- image_rendering: screen-print
- image_palette: duotone

## typography
- font_family: 'Microsoft YaHei', 'PingFang SC', Arial, sans-serif
- title_family: Impact, 'Arial Black', 'Microsoft YaHei', sans-serif
- body_family: 'Microsoft YaHei', 'PingFang SC', Arial, sans-serif
- emphasis_family: Impact, 'Arial Black', SimHei, 'Microsoft YaHei', sans-serif
- code_family: Consolas, 'Courier New', monospace
- body: 20
- title: 36
- subtitle: 26
- annotation: 15
- cover_title: 88
- hero_number: 64
- chapter_opener: 56
- caption: 11
- lead: 32
- section_title: 44
- display_m: 48
- display_l: 84
- poster_numeral: 100

## icons
- library: chunk-filled
- inventory: book, book-open, books, newspaper, sticky-note, printer, copy, brush, scissors, pencil, pen-nib, toolbox, map, map-pin, globe, calendar, clock, heart, star, flag, arrow-right, circle-arrow-right, building, home, shopping-bag, folders, grid, hand, users

## images
- cover_hero: images/cover_hero.jpg
- zine_history_collage: images/zine_history_collage.jpg
- risograph_machine: images/risograph_machine.jpg
- risograph_process_banner: images/risograph_process_banner.jpg
- zine_folding_hands: images/zine_folding_hands.jpg
- jimbocho_hero: images/jimbocho_hero.jpg
- three_cities_triptych: images/three_cities_triptych.jpg
- berlin_bucherbogen: images/berlin_bucherbogen.jpg
- zine_fair_scene: images/zine_fair_scene.jpg
- zine_action_outro: images/zine_action_outro.jpg

## page_rhythm
- P01: anchor
- P02: anchor
- P03: breathing
- P04: dense
- P05: dense
- P06: dense
- P07: dense
- P08: dense
- P09: breathing
- P10: dense
- P11: breathing
- P12: dense
- P13: dense
- P14: dense
- P15: dense
- P16: breathing
- P17: anchor
- P18: anchor

## page_charts
- P02: agenda_list
- P04: timeline
- P05: vertical_list
- P06: numbered_steps
- P07: numbered_steps
- P08: icon_grid
- P10: vertical_pillars
- P12: basic_table
- P13: labeled_card
- P14: vertical_list
- P15: vertical_list
- P16: numbered_steps

## pptx_structure
- mode: flat

## forbidden
- Mixing icon libraries
- `<style>`, `class`, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<script>`, `<iframe>`, `<symbol>`+`<use>`
- HTML named entities in text (`&nbsp;`, `&mdash;`, `&copy;`, `&ndash;`, `&reg;`, `&hellip;`, `&bull;` …) — write as raw Unicode (`—`, `©`, `→`, NBSP, etc.); XML reserved chars `& < > " '` must be escaped as `&amp; &lt; &gt; &quot; &apos;`
- Card border-radius > 0 (Risograph 美学 = 硬边、无圆角)
