<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 三星堆博物馆展厅入口的现场观众，以散客、亲子家庭与初次到访者为主，站在触摸屏前自助点选，单次停留约 1–3 分钟
- objective: 让观众自己点到想看的展区，带走至少一件文物的一个确切数字与一个看点，并知道当日开放信息去官网查
- core_message: 三星堆是商代晚期一处古蜀都城的祭祀现场，每件重器都能落到确切的坑号、年代与尺寸上
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: instructional
- mode_behavior: 以 instructional 的拆解后排序为唯一骨架，改造成触摸屏的菜单式讲解——首页拆出四条可点路径并标明长度，每个展区先用章节页交代看什么再逐步展开，七件重点文物页固定同序同深度的年代、坑号、尺寸、看点四件事以便横向比较；页标题写这一页教什么；每页自足，观众可从任意入口进入或退出。

## visual_style
- visual_style: custom
- visual_style_references: dark-tech
- visual_style_behavior: 取 dark-tech 的暗场、发光、几何精准三件事换成青铜与黄金语汇——近黑墨绿满铺作深度，细金线与低透明度巨大编号浮在内容层之后，卡片用 1px 金色描边而非填充块，边角近直角；注意力由局部高对比的金色承担，其余压低；纵深靠外发光与层叠而非投影；文物照片由暗场直接承托、加极轻暗角，不套框；等宽体只用于尺寸与坑号这类需要精确读数的标签。

## colors
- background: #0E1512
- secondary_bg: #17211D
- primary: #C9A227
- accent: #4FB9A5
- secondary_accent: #C6704A
- body_text: #E9E5D9
- secondary_text: #A8A396
- divider: #2A3630
- surface: #1D2A24
- scrim: #0E1512
- grid: #212C27

## typography
- font_family: Microsoft YaHei, Arial, sans-serif
- title_family: SimHei, Arial, sans-serif
- body_family: Microsoft YaHei, Arial, sans-serif
- data_family: Consolas, Microsoft YaHei, monospace
- display_family: SimHei, Arial, sans-serif
- body: 24
- title: 42
- subtitle: 32
- annotation: 18
- display: 72
- lead: 28
- data: 26
- nav_label: 20
- footnote: 16

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/home, tabler-outline/arrow-left, tabler-outline/arrow-right, tabler-outline/list, tabler-outline/ruler, tabler-outline/calendar, tabler-outline/shovel, tabler-outline/certificate, tabler-outline/star, tabler-outline/crown, tabler-outline/tree, tabler-outline/eye, tabler-outline/mask, tabler-outline/coin, tabler-outline/box, tabler-outline/flame, tabler-outline/building-bank, tabler-outline/clock, tabler-outline/ticket, tabler-outline/world, tabler-outline/map-pin, tabler-outline/phone

## images
- p01: images/sanxingdui_museum_exterior.jpg | source=web | crop=adaptive
- p08: images/bronze_standing_figure.jpg | source=web | crop=no-crop
- p09: images/bronze_sacred_tree.jpg | source=web | crop=no-crop
- p10: images/bronze_mask_protruding_eyes.jpg | source=web | crop=no-crop
- p11: images/gold_scepter.jpg | source=web | crop=no-crop

## page_visualizations
- P15: table/record_table

## page_rhythm
- P01: anchor
- P02: anchor
- P03: dense
- P04: dense
- P05: anchor
- P06: dense
- P07: anchor
- P08: dense
- P09: dense
- P10: dense
- P11: dense
- P12: dense
- P13: breathing
- P14: dense
- P15: dense
- P16: anchor

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
