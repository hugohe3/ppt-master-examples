# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 音乐节观众（18-35）、品牌赞助方与媒体
- objective: 按 WHAT / WHO / WHERE / VIBES 四章交出音乐节的理念、阵容、场地、日程与票务，让读者看完就知道哪天去、看谁、怎么买票
- core_message: 当全世界都在变热，SUGAR RUSH 决定让这个夏天变甜
- consumption_mode: reading

## colors
- bg: #FFF8EE
- bg_secondary: #FFE9C7
- primary: #FF3DA5
- accent: #00B8D9
- secondary_accent: #FFD93D
- tertiary_accent: #00C896
- quaternary_accent: #FF6B4A
- text: #1A1A2E
- text_secondary: #5C5C7A
- border: #1A1A2E
- success: #00C896
- warning: #FF6B4A
- image_rendering: flat
- image_palette: vivid-launch

## typography
- font_family: Arial, "Microsoft YaHei", "PingFang SC", sans-serif
- title_family: Impact, "Arial Black", "Microsoft YaHei", sans-serif
- body_family: Arial, "Microsoft YaHei", "PingFang SC", sans-serif
- emphasis_family: Impact, "Microsoft YaHei", sans-serif
- code_family: Consolas, "Courier New", monospace
- body: 20
- title: 40
- subtitle: 30
- annotation: 15
- cover_title: 96
- chapter_hero: 200
- chapter_title: 64
- hero_number: 140
- caption: 11
- lead: 24
- display_m: 48
- poster_numeral: 100

## icons
- library: chunk-filled
- inventory: calendar, music, microphone, users, clock, bolt, heart, star, map-pin, sun, sparkles, headphones, shopping-bag, game-controller, ticket, gift, arrow-right

## images
- cover_bg: images/cover_bg.jpg
- ch1_what: images/ch1_what.jpg
- ch2_who: images/ch2_who.jpg
- headliners: images/headliners.jpg
- ch3_where: images/ch3_where.jpg
- ch4_vibes: images/ch4_vibes.jpg
- market: images/market.jpg
- installation: images/installation.jpg
- closing: images/closing.jpg

## page_rhythm
- P01: anchor
- P02: breathing
- P03: dense
- P04: dense
- P05: breathing
- P06: dense
- P07: dense
- P08: breathing
- P09: dense
- P10: dense
- P11: breathing
- P12: dense
- P13: dense
- P14: anchor

## page_charts
- P03: kpi_cards
- P04: vertical_pillars
- P06: icon_grid
- P07: quadrant_text_bullets
- P09: hub_spoke
- P10: timeline
- P12: comparison_columns
- P13: comparison_columns

## pptx_structure
- mode: flat

## forbidden
- Mixing icon libraries
- `<style>`, `class`, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<script>`, `<iframe>`, `<symbol>`+`<use>`
- HTML named entities in text (`&nbsp;`, `&mdash;`, `&copy;`, `&ndash;`, `&reg;`, `&hellip;`, `&bull;` …) — write as raw Unicode (`—`, `©`, `→`, NBSP, etc.); XML reserved chars `& < > " '` must be escaped as `&amp; &lt; &gt; &quot; &apos;`. See shared-standards.md §1.0
