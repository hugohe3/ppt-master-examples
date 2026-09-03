<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 对饮食文化感兴趣的普通观众，没有餐饮或地方志背景
- objective: 以并列等重的图鉴条目陈列 11 种地方早餐的地域、主料、年代、口味与吃法，让观众能逐条辨认并说出关键特征，同时分清哪些数字有出处、哪些显示 NO DATA
- core_message: 中国早餐是 11 张各自成立的地方名片，共性在碳水主料、一碗热汤与现做现吃
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: briefing
- mode_behavior: 用 briefing 的中性完整骨架做一本图鉴——页标题是条目名而非论断，11 张条目页形状与权重完全一致，每页只说陈列了什么，不设结论页。

## visual_style
- visual_style: custom
- visual_style_references: pixel-art
- visual_style_behavior: 严格像素网格、无抗锯齿、块状轮廓、直角零圆角；深色夜蓝底加底部瓷砖地带，条目页用 HUD 角括号框内容区、阶梯像素分隔线切栏、底部 11 格图鉴进度条高亮当前条目；大 sprite 压左侧并留白，深浅只靠亮顶暗底的调色板分层。

## colors
- background: #1A1C2C
- secondary_bg: #2B2F4A
- primary: #EF8A3C
- accent: #FFCD4D
- secondary_accent: #41A6B5
- body_text: #F4F0E6
- secondary_text: #A0A8C0
- divider: #4A5578
- surface: #232741
- grid: #3A4266
- outline: #0F1020
- block_shade: #C25A22
- positive: #7BD455
- negative: #E4453A
- image_rendering: custom
- image_rendering_references: pixel-art
- image_rendering_behavior: 严格 8-bit 像素网格、零抗锯齿、像素尺寸一致；14 色以内复古色板，块状剪影加 1 像素深色描边；深度只靠亮顶暗底分层，无渐变无模糊无投影；正交或轻微俯视，无透视灭点。

## typography
- font_family: Microsoft YaHei
- title_family: Microsoft YaHei
- body_family: Microsoft YaHei
- display_family: Microsoft YaHei
- data_family: Consolas
- index_family: Consolas
- annotation_family: Microsoft YaHei
- footnote_family: Microsoft YaHei
- body: 24
- title: 44
- subtitle: 32
- lead: 30
- display: 64
- data: 20
- index: 40
- annotation: 18
- footnote: 16

## icons
- library: none
- inventory: none

## images
- letter_title: images/letter_title.png | source=slice | crop=no-crop
- letter_kaichi: images/letter_kaichi.png | source=slice | crop=no-crop
- letter_complete: images/letter_complete.png | source=slice | crop=no-crop
- dish_doujiao: images/dish_doujiao.png | source=slice | crop=no-crop
- dish_jianbing: images/dish_jianbing.png | source=slice | crop=no-crop
- dish_sidajingang: images/dish_sidajingang.png | source=slice | crop=no-crop
- dish_reganmian: images/dish_reganmian.png | source=slice | crop=no-crop
- dish_changfen: images/dish_changfen.png | source=slice | crop=no-crop
- dish_changshafen: images/dish_changshafen.png | source=slice | crop=no-crop
- dish_xiaomian: images/dish_xiaomian.png | source=slice | crop=no-crop
- dish_roujiamo: images/dish_roujiamo.png | source=slice | crop=no-crop
- dish_niuroumian: images/dish_niuroumian.png | source=slice | crop=no-crop
- dish_xiaoguomixian: images/dish_xiaoguomixian.png | source=slice | crop=no-crop
- dish_kaobaozi: images/dish_kaobaozi.png | source=slice | crop=no-crop
- dish_naicha: images/dish_naicha.png | source=slice | crop=no-crop
- dish_doufunao: images/dish_doufunao.png | source=slice | crop=no-crop
- prop_bowl: images/prop_bowl.png | source=slice | crop=no-crop
- prop_chopsticks: images/prop_chopsticks.png | source=slice | crop=no-crop
- prop_steamer: images/prop_steamer.png | source=slice | crop=no-crop
- prop_cup: images/prop_cup.png | source=slice | crop=no-crop
- prop_copperpot: images/prop_copperpot.png | source=slice | crop=no-crop
- prop_spoon: images/prop_spoon.png | source=slice | crop=no-crop
- hud_chili: images/hud_chili.png | source=slice | crop=no-crop
- hud_coin: images/hud_coin.png | source=slice | crop=no-crop
- hud_clock: images/hud_clock.png | source=slice | crop=no-crop
- hud_rice: images/hud_rice.png | source=slice | crop=no-crop
- hud_steam: images/hud_steam.png | source=slice | crop=no-crop
- hud_star: images/hud_star.png | source=slice | crop=no-crop
- hud_tile: images/hud_tile.png | source=slice | crop=no-crop
- hud_bracket: images/hud_bracket.png | source=slice | crop=no-crop
- hud_heart: images/hud_heart.png | source=slice | crop=no-crop
- scene_stall: images/scene_stall.png | source=slice | crop=no-crop
- scene_signboard: images/scene_signboard.png | source=slice | crop=no-crop
- scene_steamcloud: images/scene_steamcloud.png | source=slice | crop=no-crop
- scene_ground: images/scene_ground.png | source=slice | crop=no-crop
- player_stand: images/player_stand.png | source=slice | crop=no-crop
- player_walk: images/player_walk.png | source=slice | crop=no-crop
- player_bowl: images/player_bowl.png | source=slice | crop=no-crop
- player_eat: images/player_eat.png | source=slice | crop=no-crop
- player_cheer: images/player_cheer.png | source=slice | crop=no-crop
- player_sit: images/player_sit.png | source=slice | crop=no-crop

## page_rhythm
- P01: anchor
- P02: breathing
- P03: dense
- P04: dense
- P05: dense
- P06: dense
- P07: dense
- P08: dense
- P09: dense
- P10: dense
- P11: dense
- P12: dense
- P13: dense
- P14: breathing
- P15: dense
- P16: anchor

## page_visualizations
- P15: table/record_table

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 不要画中国地图轮廓（任何形式的地图边界都不要出现） (user)
- 不用渐变、不用滤镜 (user)
- font-family 只写单一具体字体名，不要逗号 fallback 栈 (user)
- 不要网图 (user)
- 不要堆满 (user)
