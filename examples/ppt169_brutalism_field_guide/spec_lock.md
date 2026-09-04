<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: en
- audience: English-reading adults interested in architecture who recognise brutalist buildings but not their origin, ethic, or history
- objective: Explain where brutalism came from and what its material ethic was, inform completely about its architects, buildings and the demolition-versus-listing record, and leave the reader able to judge a concrete building on the terms the style set for itself
- core_message: Brutalism was an ethic before it was a look — show the plan, show the structure, show the material as found — and that honesty is what made it both hated and worth saving
- consumption_mode: text

## mode
- mode: custom
- mode_references: narrative
- mode_behavior: One arc across five parts — a Swedish house gets a name, the name hardens into an ethic, the ethic becomes public buildings worldwide, the public turns on them and they come down, then the style is listed and rebuilt. Titles read as beats that advance the story rather than topic labels; each part opens on a visibly reset page, and the two evidence tables land as the story's factual floor rather than an appendix.

## visual_style
- visual_style: custom
- visual_style_references: brutalist
- visual_style_behavior: Newsprint field guide. Irregular two-, three-, and four-column measures mixed on one 12-column ruleset; hairline column dividers with 6-10 px full-bleed rule bars slicing sections; an oversized masthead numeral crossing the top rule as the deck's continuity carrier; one grid cell per page inverted to solid ink with paper-light type as the focal cell; a single rotated stamp box breaking the grid at one deliberate point on anchor pages; rx=0 everywhere, strictly flat, halftone dot pattern as the only texture. Photography enters only as high-contrast duotone cropped hard into a ruled box. Colour is punctuation — the spot red appears at most twice per page.

## colors
- background: #F2F0EA
- secondary_bg: #E2DFD5
- primary: #14110F
- accent: #C8331E
- secondary_accent: #6E6A62
- body_text: #1C1A17
- secondary_text: #55514A
- divider: #9A958B
- surface: #E2DFD5
- grid: #C9C5BA
- block_shade: #D8D4C8

## typography
- font_family: Cambria
- title_family: Arial Black
- body_family: Cambria
- subtitle_family: Cambria
- cover_title_family: Arial Black
- display_numeral_family: Arial Black
- lead_family: Cambria
- data_family: Consolas
- annotation_family: Consolas
- table_body_family: Consolas
- footnote_family: Consolas
- body: 20
- title: 36
- subtitle: 26
- annotation: 16
- cover_title: 80
- lead: 24
- display_numeral: 120
- data: 22
- table_body: 16
- footnote: 12

## icons
- library: chunk-filled
- inventory: chunk-filled/building, chunk-filled/block-quote, chunk-filled/calendar, chunk-filled/trash, chunk-filled/bookmark, chunk-filled/globe, chunk-filled/hammer, chunk-filled/user, chunk-filled/book, chunk-filled/link

## images
- p01: images/cover_beton_brut_duo.png | source=web | crop=adaptive
- p07: images/boston_city_hall_half.png | source=web | crop=no-crop
- p12: images/demolition_mono.png | source=web | crop=adaptive
- p14: images/ningbo_museum_duo.png | source=web | crop=no-crop

## page_visualizations
- P09: table/record_table
- P13: table/record_table

## page_rhythm
- P01: anchor
- P02: dense
- P03: dense
- P04: breathing
- P05: dense
- P06: dense
- P07: dense
- P08: dense
- P09: dense
- P10: dense
- P11: breathing
- P12: dense
- P13: dense
- P14: dense
- P15: anchor
- P16: anchor

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- font-family 写单一具体名不要逗号栈 (user)
- 英文 deck 不要出现 CJK 字体名做主字体 (user)
- 不能整张彩照直贴 (user)
- 不为原生而降级图型 (user)
- 音效不配 (user)
- 配对两端都不能是 Native-ready 对象 (user)
- 入场用 entrance 家族,别全部 fade (user)
