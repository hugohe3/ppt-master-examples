<!-- ppt-master-schema: design-spec/v1 -->
# pixel_breakfast_atlas_20260903 - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | pixel_breakfast_atlas_20260903 |
| Canvas Format | PPT 16:9 · 1280×720 |
| Page Count | 16 |
| Primary Language | zh-CN |
| Target Audience | 对饮食文化感兴趣的普通观众，没有餐饮或地方志背景，认得几种早餐但说不清各自的地域、年代与做法 |
| Communication Intent | 以图鉴形式并列陈列各地代表性早餐；每条先给可核查的地域、主料、年代、口味与吃法，再在末尾给跨地区共性与两处争议；不树立中心论点，也不排名高下 |
| Desired Audience Outcome | 观众能逐条辨认 11 种地方早餐、说出各自城市与关键特征，知道哪些数字有出处、哪些本次没有取得可核来源，并能复述"碳水为主、一碗热汤、现做现吃"这组共性 |
| Core Message / Ask / Action | 中国早餐是 11 张各自成立的地方名片；它们的共性在碳水主料、一碗热汤与现做现吃，差异在主料、口味与年代 |
| Delivery Context | 主要为有主讲人的轻松科普放映（约 12 分钟）；次要为会后自行翻阅的图鉴式电子文件 |
| Artifact Afterlife | 收入公开示例库，作为像素风图鉴式 deck 的可复用参考，需保留可编辑的原生文字与表格 |
| Reading Mode | balanced |
| Content Strategy | 平衡：以研究补充件的事实为唯一内容来源，按图鉴条目重新组织；数字必须带来源年份，本次未取得可核来源的字段一律显示 NO DATA，不估算、不补写 |
| Design Style | 8-bit 图鉴：briefing 的并列等重骨架 + pixel-art 的严格像素网格与有限色板；深色瓷砖底上放大号食物 sprite，配 HUD 属性面板与图鉴进度条 |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 用户明确要求"带逐页演讲者备注" |
| Custom Animations | enabled — 用户明确要求跑完终检后执行 customize-animations 并重新导出 |
| Narration Audio | disabled — 用户未要求旁白音频；工作流默认 |
| Created Date | 2026-09-03 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 上下左右各 64px；底部瓷砖地带占 y=656..720，正文不进入 |
| Content Area | x=64..1216, y=64..656 |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: briefing
- **Mode Behavior**: 用 briefing 的中性完整骨架做一本图鉴：页标题是条目名而非论断，11 张条目页形状与权重完全一致以便比对与查找，每页 core message 说这页"陈列了什么"而不是"证明了什么"；条目按图鉴编号 No.01–No.11 顺序排列，前有一页读法与共性、后有争议页与对照表，全卷不设结论页。
- **Visual style**: custom
- **Visual Style References**: pixel-art
- **Visual Style Behavior**: 严格像素网格、无抗锯齿、块状轮廓、无渐变无滤镜无阴影；深色夜蓝底上铺一条底部瓷砖地带，条目页由 HUD 角括号框出内容区、阶梯像素分隔线切分栏位、底部一条 11 格图鉴进度条高亮当前条目；大号食物 sprite 稳稳压住页面左侧并留出四周空白，深浅只靠调色板分层（亮顶暗底）实现。
- **Theme**: 图鉴（Pokédex）——每页一格档案：编号、名称、城市、sprite、HUD 属性面板、要点。跨页母题是"图鉴进度条 + HUD 角括号"，在 11 张条目页上逐格推进，复用模式为固定复现、仅高亮格位变化。
- **Tone**: 轻松、克制、可查；游戏机的中性播报感，不煽情不排名

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | `#1A1C2C` | 全卷夜蓝底，像素游戏的暗场 |
| Secondary background | `#2B2F4A` | HUD 面板与条目卡底板 |
| Primary | `#EF8A3C` | 主体色：食物 sprite 主色、条目编号、进度条已过格 |
| Accent | `#FFCD4D` | 高亮：当前进度格、关键数值、题字描边亮部 |
| Secondary accent | `#41A6B5` | 冷向标签：清淡/无辣/地域格 |
| Body text | `#F4F0E6` | 正文暖白 |
| Secondary text | `#A0A8C0` | 图注、来源年份、NO DATA |
| Divider | `#4A5578` | 阶梯像素分隔线与 HUD 边框 |
| Surface | `#232741` | 面板抬起层（属性面板内条槽） |
| Grid | `#3A4266` | 瓷砖地带网格细线与空条槽 |
| Outline | `#0F1020` | 1 像素深色描边（所有块状形体） |
| Block shade | `#C25A22` | primary 的暗部像素（亮顶暗底分层） |
| Positive | `#7BD455` | 属性条低档/清淡 |
| Negative | `#E4453A` | 属性条高档/主辣 |

### AI Image Strategy

- **Image Rendering**: custom
- **Image Rendering References**: pixel-art
- **Image Rendering Behavior**: 严格 8-bit 像素网格、零抗锯齿、像素大小完全一致；限定 14 色以内的复古色板，形体为块状剪影，1 像素深色描边（填充色的更暗一档）勾定轮廓；深度只靠亮顶暗底的调色板分层，不用渐变、不用模糊、不用投影；正交或轻微俯视，无透视灭点。
- **Visual**: 深色底上的高对比像素 sprite——食物成为可辨认的图标化实体（碗口、面条纹理、蒸汽块都由离散像素块构成），配件与 HUD 元件是同一网格上的小尺寸块状图形
- **Mood**: 怀旧、克制、可收集——像 90 年代掌机 RPG 的道具图鉴页，物品静静躺在暗色格子里等着被翻阅

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 粗壮无衬线、块面感强，撑得住像素框 | Microsoft YaHei | Microsoft YaHei | 无（单一具体字体名） |
| Body | 中性易读无衬线 | Microsoft YaHei | Microsoft YaHei | 无（单一具体字体名） |
| Display | 特大标题与结尾字，与 Title 同族加粗使用 | Microsoft YaHei | Microsoft YaHei | 无（单一具体字体名） |
| Data | 等宽机读感，承载 HUD 数值与价格年份 | Consolas | Consolas | 无（单一具体字体名） |
| Index | 等宽机读感的图鉴编号，块面大 | Consolas | Consolas | 无（单一具体字体名） |
| Annotation | 中性小字 | Microsoft YaHei | Microsoft YaHei | 无（单一具体字体名） |
| Footnote | 中性最小字，承载 Fact ID 与年份 | Microsoft YaHei | Microsoft YaHei | 无（单一具体字体名） |

- **Typography upgrade (Reference)**: 若目标机安装了 Press Start 2P / VT323 等点阵字，Title 与 Data 可整体替换以取得真像素字形；本次导出不依赖它，像素字形由 AI 题字承担
- **Title stack**: Microsoft YaHei
- **Body stack**: Microsoft YaHei
- **Display stack**: Microsoft YaHei
- **Data stack**: Consolas
- **Index stack**: Consolas
- **Annotation stack**: Microsoft YaHei
- **Footnote stack**: Microsoft YaHei
- **Role rationale**: Data 与 Index 用 Consolas 是唯一的家族切换——HUD 数值、价格与年份逐页对齐读取，图鉴编号 No.01–No.11 在 11 张条目页与结尾页反复出现且必须与中文标题拉开机读感；两者字号差一倍，故分列两个锚点。Display 与 Title 同族，只在封面与结尾的特大字号上单列锚点。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 44 |
| Subtitle | 32 |
| Annotation | 18 |
| Display | 64 |
| Data | 20 |
| Index | 40 |
| Footnote | 16 |
| Lead | 30 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 条目页从左侧大 sprite 起读 → 右上编号与名称 → 右中 HUD 属性面板 → 右下要点两三句 → 底部进度条定位；视线一次横穿，不做 Z 字回折
- **Composition tendency**: 左重右轻的双区结构，左区放尺寸压场的单一 sprite 并四周留白，右区用 HUD 角括号框出信息栈；封面、共性页、争议页、表格页与结尾页各自另立构图，不套条目模板
- **Cross-page continuity**: 底部瓷砖地带、HUD 角括号、11 格图鉴进度条在 11 张条目页上固定复现且只有高亮格变化；食物 sprite 一物一页不复用，配件与 HUD 图元跨页复用且保持同一缩放比
- **Spacing posture**: 变化——条目页 dense、共性页与争议页 breathing、封面与结尾 anchor
- **Spacing anchors**: 页边距 64px；块间距 32px；分栏槽 32px；圆角 0px（像素纪律，一律直角）；正文行距 36px

## VI. Icon Usage Specification

- **Primary bundled library**: none

| Icon Path | Suitable Scenarios |
| --- | --- |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P15 | table | record_table | 把 11 条图鉴逐行对照：编号、名称、城市、碳水主料、口味标签、定型年代、可核价格 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| dish_doujiao.png | 1090x1110 | 0.98:1 | No.01 豆汁焦圈主体 sprite | Illustration element | 左区大 sprite 压场，四周留白，不进容器 | no-crop | slice | Generated | 取自 sheet_food_a 第 1 格 | none | local |
| dish_jianbing.png | 1233x987 | 1.25:1 | No.02 煎饼馃子主体 sprite | Illustration element | 左区大 sprite 压场，四周留白 | no-crop | slice | Generated | 取自 sheet_food_a 第 2 格 | none | local |
| dish_sidajingang.png | 1254x1212 | 1.03:1 | No.03 上海四大金刚主体 sprite | Illustration element | 左区大 sprite 压场，四件并排成一组 | no-crop | slice | Generated | 取自 sheet_food_a 第 3 格 | none | local |
| dish_reganmian.png | 1254x1211 | 1.04:1 | No.04 热干面主体 sprite | Illustration element | 左区大 sprite 压场，四周留白 | no-crop | slice | Generated | 取自 sheet_food_a 第 4 格 | none | local |
| dish_changfen.png | 1274x1069 | 1.19:1 | No.05 广州肠粉主体 sprite | Illustration element | 左区大 sprite 压场，配蒸笼配件 | no-crop | slice | Generated | 取自 sheet_food_a 第 5 格 | none | local |
| dish_changshafen.png | 1252x1151 | 1.09:1 | No.06 长沙米粉主体 sprite | Illustration element | 左区大 sprite 压场，四周留白 | no-crop | slice | Generated | 取自 sheet_food_a 第 6 格 | none | local |
| dish_xiaomian.png | 1254x1212 | 1.03:1 | No.07 重庆小面主体 sprite | Illustration element | 左区大 sprite 压场，旁挂辣椒图元 | no-crop | slice | Generated | 取自 sheet_food_a 第 7 格 | none | local |
| dish_roujiamo.png | 1233x1029 | 1.2:1 | No.08 西安肉夹馍主体 sprite | Illustration element | 左区大 sprite 压场，四周留白 | no-crop | slice | Generated | 取自 sheet_food_a 第 8 格 | none | local |
| dish_niuroumian.png | 1254x1130 | 1.11:1 | No.09 兰州牛肉面主体 sprite | Illustration element | 左区大 sprite 压场，四周留白 | no-crop | slice | Generated | 取自 sheet_food_a 第 9 格 | none | local |
| dish_xiaoguomixian.png | 1885x1189 | 1.59:1 | No.10 云南小锅米线主体 sprite | Illustration element | 左区大 sprite 压场，配红铜小锅配件 | no-crop | slice | Generated | 取自 sheet_food_b 第 1 格 | none | local |
| dish_kaobaozi.png | 1721x1230 | 1.4:1 | No.11 新疆烤包子主体 sprite | Illustration element | 左区大 sprite 压场，与奶茶并置 | no-crop | slice | Generated | 取自 sheet_food_b 第 2 格 | none | local |
| dish_naicha.png | 1640x1353 | 40:33 | No.11 咸奶茶配套 sprite | Illustration element | 与烤包子并置的次级元素，尺寸小一档 | no-crop | slice | Generated | 取自 sheet_food_b 第 3 格 | none | local |
| dish_doufunao.png | 1640x1353 | 40:33 | 豆腐脑咸甜争议页主体 sprite | Illustration element | 页面中轴单件，左右两侧各接一路配料标注 | no-crop | slice | Generated | 取自 sheet_food_b 第 4 格 | none | local |
| prop_bowl.png | 598x512 | 1.17:1 | 通用碗配件 | Illustration element | 共性页小图元，跨页复用同一缩放 | no-crop | slice | Generated | 取自 sheet_props 第 1 格 | none | local |
| prop_chopsticks.png | 647x596 | 1.09:1 | 筷子配件 | Illustration element | 共性页小图元，斜置不进容器 | no-crop | slice | Generated | 取自 sheet_props 第 2 格 | none | local |
| prop_steamer.png | 579x630 | 0.92:1 | 蒸笼配件 | Illustration element | 肠粉页次级元素，贴主 sprite 边缘 | no-crop | slice | Generated | 取自 sheet_props 第 3 格 | none | local |
| prop_cup.png | 427x631 | 0.68:1 | 豆浆纸杯配件 | Illustration element | 四大金刚页次级元素 | no-crop | slice | Generated | 取自 sheet_props 第 4 格 | none | local |
| prop_copperpot.png | 698x512 | 1.36:1 | 红铜小锅配件 | Illustration element | 小锅米线页次级元素 | no-crop | slice | Generated | 取自 sheet_props 第 5 格 | none | local |
| prop_spoon.png | 529x359 | 1.47:1 | 勺配件 | Illustration element | 争议页次级元素 | no-crop | slice | Generated | 取自 sheet_props 第 6 格 | none | local |
| hud_chili.png | 394x557 | 0.71:1 | 辣度行图标 | Illustrated icon | HUD 属性面板行首小图标，11 页复用同一尺寸 | no-crop | slice | Generated | 取自 sheet_hud 第 1 格 | none | local |
| hud_coin.png | 536x536 | 1:1 | 价格行图标 | Illustrated icon | HUD 属性面板行首小图标 | no-crop | slice | Generated | 取自 sheet_hud 第 2 格 | none | local |
| hud_clock.png | 536x537 | 1.0:1 | 年代行图标 | Illustrated icon | HUD 属性面板行首小图标 | no-crop | slice | Generated | 取自 sheet_hud 第 3 格 | none | local |
| hud_rice.png | 557x515 | 1.08:1 | 口味行图标 | Illustrated icon | HUD 属性面板行首小图标 | no-crop | slice | Generated | 取自 sheet_hud 第 4 格 | none | local |
| hud_steam.png | 475x515 | 0.92:1 | 蒸汽块图元 | Illustrated icon | 条目页 sprite 上方点缀，位置与角度逐页变化 | no-crop | slice | Generated | 取自 sheet_hud 第 5 格 | none | local |
| hud_star.png | 557x536 | 1.04:1 | 星标图元 | Illustrated icon | 表格页与结尾页的强调点 | no-crop | slice | Generated | 取自 sheet_hud 第 6 格 | none | local |
| hud_tile.png | 556x557 | 1.0:1 | 瓷砖块图元 | Illustrated icon | 共性页地块拼接单元 | no-crop | slice | Generated | 取自 sheet_hud 第 7 格 | none | local |
| hud_bracket.png | 578x557 | 1.04:1 | HUD 角括号图元 | Illustrated icon | 条目页信息区四角，固定复现 | no-crop | slice | Generated | 取自 sheet_hud 第 8 格 | none | local |
| hud_heart.png | 557x515 | 1.08:1 | 心形图元 | Illustrated icon | 结尾页收藏感点缀 | no-crop | slice | Generated | 取自 sheet_hud 第 9 格 | none | local |
| scene_stall.png | 588x634 | 0.93:1 | 早市推车摊位 | Illustration element | 共性页右下角落地元素，接住底部瓷砖带 | no-crop | slice | Generated | 取自 sheet_scene 第 1 格 | none | local |
| scene_signboard.png | 794x358 | 2.22:1 | 早点铺招牌灯箱 | Illustration element | 封面右上，可越出画布边缘 | no-crop | slice | Generated | 取自 sheet_scene 第 2 格 | none | local |
| scene_steamcloud.png | 714x301 | 2.37:1 | 宽蒸汽云 | Illustration element | 封面与共性页题字后方的低对比衬底 | no-crop | slice | Generated | 取自 sheet_scene 第 3 格 | none | local |
| scene_ground.png | 1012x347 | 2.92:1 | 瓷砖地带条 | Illustration element | 封面与结尾页底边满幅铺开 | no-crop | slice | Generated | 取自 sheet_scene 第 4 格 | none | local |
| player_stand.png | 373x649 | 0.57:1 | 玩家小人·站立 | Illustration element | 封面地带上的人形尺度参照 | no-crop | slice | Generated | 取自 sheet_player 第 1 格 | none | local |
| player_walk.png | 445x648 | 0.69:1 | 玩家小人·行走 | Illustration element | 图鉴进度条上的移动标记，相邻两页位置不同 | no-crop | slice | Generated | 取自 sheet_player 第 2 格 | none | local |
| player_bowl.png | 360x649 | 0.55:1 | 玩家小人·端碗 | Illustration element | 共性页"现做现吃"一条的图示 | no-crop | slice | Generated | 取自 sheet_player 第 3 格 | none | local |
| player_eat.png | 408x696 | 17:29 | 玩家小人·吃 | Illustration element | 结尾页与「开吃！」题字并置 | no-crop | slice | Generated | 取自 sheet_player 第 4 格 | none | local |
| player_cheer.png | 529x696 | 0.76:1 | 玩家小人·欢呼 | Illustration element | 结尾页与「图鉴完成」题字并置 | no-crop | slice | Generated | 取自 sheet_player 第 5 格 | none | local |
| player_sit.png | 408x588 | 0.69:1 | 玩家小人·蹲坐 | Illustration element | 争议页中立位置，坐在咸甜两侧之间 | no-crop | slice | Generated | 取自 sheet_player 第 6 格 | none | local |
| letter_title.png | 4128x897 | 4.6:1 | 封面主标题题字「中国早餐图鉴」 | Lettering | 封面上部题字层，旁边另留原生可编辑标题 | no-crop | slice | Generated | 取自 sheet_letter_title 唯一格；精确字符串「中国早餐图鉴」 | embedded | local |
| letter_kaichi.png | 1563x600 | 2.6:1 | 小题字「开吃！」 | Lettering | 共性页右下装饰，贴摊位元素 | no-crop | slice | Generated | 取自 sheet_letter_marks 第 1 格；精确字符串「开吃！」 | embedded | local |
| letter_complete.png | 2526x623 | 4.05:1 | 小题字「图鉴完成」 | Lettering | 结尾页题字层，旁边另留原生可编辑标题 | no-crop | slice | Generated | 取自 sheet_letter_marks 第 2 格；精确字符串「图鉴完成」 | embedded | local |

## IX. Content Outline

### Part 1: 开卷

#### Slide 01 - 封面 · 中国早餐图鉴

- **Audience move**: 只知道"中国早餐"是个泛称 → 认出这是一本按编号排列、可逐条查阅的图鉴
- **Relationships**: 标题、副标题、编号总数（11 条）、场景元素三者是 membership 关系——副标题与总数都从属于图鉴这一整体，彼此无先后
- **Cover impact**: 钩子（binding）——「11 座城市，11 种碳水的醒法」；构图 Reference：题字压上部，玩家小人站在底部瓷砖地带上，招牌灯箱从右上越出画布，蒸汽云低对比衬在题字后方
- **Composition**: 上题字、中留白、下地带的三段式；左下角一行原生可编辑标题与副标题
- **Title**: 中国早餐图鉴
- **Core message**: 本卷收录 11 座城市的代表性早餐，逐条给出地域、主料、年代、口味与可核价格
- **Content**: 题字层「中国早餐图鉴」（AI 像素题字）· 原生可编辑主标题「中国早餐图鉴」与副标题「11 座城市 · 11 张早餐名片」· 一行说明「数字标注来源年份；本次未取得可核来源的字段显示 NO DATA」· 底部瓷砖地带
- **Images**: letter_title 作显示层，原生标题另起一处；scene_signboard 右上越界；scene_steamcloud 题字后方低对比；scene_ground 底边满幅；player_stand 立于地带
- **Motion suggestion**: 封面题字与 sprite 逐块硬切出现（无淡入），大 sprite 组在进入下一页时向图鉴卡位置收拢
- **Fact IDs**: F043, F044

#### Slide 02 - 图鉴读法与四条共性

- **Audience move**: 不知道该怎么读这本图鉴 → 知道每张卡的四行属性怎么看，也知道 11 条之间共享什么
- **Relationships**: 四条共性（碳水为主、一碗热汤、现做现吃、摊贩与早市）之间是 membership，彼此等重无先后；"读法说明"与"四条共性"之间是 link——读法解释了卡面，共性解释了卡与卡的关系
- **Composition**: 上半横排四格共性瓷砖块，下半左侧放一张缩小的样例卡面并用阶梯像素引线标出四行属性的含义
- **Title**: 怎么读这本图鉴
- **Core message**: 每张卡固定四行属性——口味、辣度、价格、年代；四条共性贯穿全部 11 条
- **Content**: 卡面四行属性的读法：口味＝来源里写明的味觉标签／辣度＝三档（不辣·可加辣·以辣为主味）／价格＝有可核来源才填，附年份／年代＝有可核来源才填 · 共性一：碳水为主（2024 年调查中 50.62% 居民早餐为面食类，46.40% 为奶类与豆制品）· 共性二：一碗热汤或热饮横跨南北 · 共性三：现做现吃——现摊、现抻、现煮、现蒸、现烤 · 共性四：在外吃早餐是常态（2024 年 56.97% 每周在外吃 3–4 次）· 价格带很宽（2024 年降价潮中出现 3 元自助早餐）
- **Images**: hud_tile 拼四格地块；prop_bowl 与 prop_chopsticks 斜置于"一碗热汤"格；player_bowl 图示"现做现吃"；scene_stall 右下落地；letter_kaichi 贴摊位作装饰
- **Motion suggestion**: 四格共性按从左到右逐块出现；样例卡的四行属性条自左向右加载
- **Fact IDs**: F005, F018, F032, F036, F041, F043, F044, F045

### Part 2: 图鉴 No.01 – No.11

#### Slide 03 - No.01 北京 · 豆汁 焦圈

- **Audience move**: 只听说过"北京人爱喝豆汁" → 知道它是绿豆粉渣发酵物、乾隆年间入宫、配焦圈同食
- **Relationships**: 豆汁与焦圈是 link（固定同食搭配）；绿豆残渣 → 发酵 → 豆汁是 order（工序先后）
- **Composition**: 左大 sprite，右侧编号名称 + HUD 四行 + 要点三句，底部进度条高亮第 1 格
- **Title**: No.01 北京 · 豆汁 焦圈
- **Core message**: 这一条陈列北京豆汁与焦圈的主料、工艺来源与同食搭配
- **Content**: 主料＝绿豆滤出淀粉后的残渣发酵而成，文字记载约三百年 · 清乾隆十八年（1753）前后传入宫内，清宫御膳房与寿膳房每年旧历九月至次年立夏后五天制作，帝后用以解油腻 · 焦圈又叫"小油鬼"，圈小如镯、焦脆酥香，喝豆汁时一般配食 · HUD：口味＝发酵酸／辣度＝不辣／价格＝NO DATA／年代＝清 1753
- **Images**: dish_doujiao 左区大 sprite；hud_rice、hud_chili、hud_coin、hud_clock 四行行首；hud_bracket 四角；hud_steam 点缀
- **Motion suggestion**: sprite 硬切出现，HUD 四行属性条自左向右依次加载
- **Fact IDs**: F001, F002, F003

#### Slide 04 - No.02 天津 · 煎饼馃子

- **Audience move**: 以为煎饼果子是随便一张饼 → 知道它有绿豆面主料、1933 年文字记载和一份团体标准
- **Relationships**: 面糊 → 摊饼 → 打蛋 → 涂酱 → 卷馃子是 order；绿豆面/小米面/鸡蛋/面粉与面酱/葱末/辣酱/腐乳/芝麻是 parent（原料与辅料两层）
- **Composition**: 左大 sprite，右信息栈；标准数值单独做一个高亮小格
- **Title**: No.02 天津 · 煎饼馃子
- **Core message**: 这一条陈列煎饼馃子的原料构成、成文记载与团体标准数值
- **Content**: 起源与天津码头文化相关；1933 年 11 月 20 日《大公报》天津版副刊出现最早文字记载 · 做法＝绿豆面为主的杂粮面糊摊薄饼，打蛋摊开，涂甜面酱、腐乳、辣椒，卷入馃子（油条）或馃篦 · 团体标准规定原料为绿豆面、小米面、鸡蛋、面粉，辅料为面酱、葱末、辣酱、腐乳、芝麻，薄饼直径 38–45cm · HUD：口味＝咸·辣／辣度＝可加辣／价格＝街边约 10 元（2026 年报道）／年代＝1933
- **Images**: dish_jianbing 左区大 sprite；hud_chili 等四行行首；hud_bracket 四角
- **Motion suggestion**: 「38–45cm」数值格在属性条加载完成后单独硬切强调
- **Fact IDs**: F004, F005, F006, F007

#### Slide 05 - No.03 上海 · 四大金刚

- **Audience move**: 只知道是四样早点 → 知道具体是哪四样、称谓何时出现、最早的店在哪年
- **Relationships**: 大饼、油条、粢饭、豆浆之间是 membership（同属一个组合，等重）；豆浆的淡/甜/咸是 parent（一物三味）
- **Composition**: 左区四件并排成一组占据 sprite 位，右信息栈；豆浆三味做一行小分支
- **Title**: No.03 上海 · 四大金刚
- **Core message**: 这一条陈列上海早点四大金刚的构成、称谓来源与最早店铺记录
- **Content**: 四大金刚＝大饼、油条、粢饭、豆浆；豆浆分淡、甜、咸三种 · 上海最早的大饼店是 1912 年南码头街 108 号"兴隆记"大饼油条店 · 1936 年 11 月 13 日《社会日报》记大饼、油条、豆浆是当时上海最大众化的早餐 · "四大金刚"本指佛教四位护法天神，用于这组早餐的称谓形成于 20 世纪 80 年代 · HUD：口味＝咸·甜·清淡／辣度＝不辣／价格＝NO DATA／年代＝1912
- **Images**: dish_sidajingang 左区一组；prop_cup 贴在豆浆一侧；四行 HUD 图标；hud_bracket 四角
- **Motion suggestion**: 四件按大饼→油条→粢饭→豆浆的顺序逐件硬切出现
- **Fact IDs**: F008, F009, F010, F011

#### Slide 06 - No.04 武汉 · 热干面

- **Audience move**: 知道热干面拌芝麻酱 → 知道碱水面的 pH 区间、蔡林记的黑芝麻酱差异和 2025 年价格带
- **Relationships**: 碱水面与芝麻酱是 membership（构成同一碗的两个要素）；蔡林记黑芝麻酱与其他摊点白/混合芝麻酱是 contrast
- **Composition**: 左大 sprite，右信息栈；价格区间用进度条式的横向刻度表达
- **Title**: No.04 武汉 · 热干面
- **Core message**: 这一条陈列热干面的面体标准、芝麻酱差异与当前价格带
- **Content**: 起源于 20 世纪 30 年代初的汉口；1930 年蔡明纬夫妇开"蔡林记"，店名取自门前两棵茂盛的树 · 碱水面含食用碱、色淡黄，煮后爽利不坨；标准碱水面 pH 值 7.2–9.2 · 芝麻酱是灵魂：蔡林记用黑芝麻酱，其他摊点多用白芝麻酱或混合芝麻酱 · 蔡林记一家店一天可卖出 5000 多碗 · HUD：口味＝咸·芝麻香／辣度＝不辣／价格＝4.5–6 元（2025）／年代＝1930
- **Images**: dish_reganmian 左区大 sprite；四行 HUD 图标；hud_steam 点缀；hud_bracket 四角
- **Motion suggestion**: 价格刻度条自左向右加载到 4.5–6 元区段并停住
- **Fact IDs**: F012, F013, F014, F015, F052

#### Slide 07 - No.05 广州 · 肠粉与早茶

- **Audience move**: 把肠粉当成普通米制品 → 知道它有传说性的唐代来源、清末的咸甜两种和早茶中的位置
- **Relationships**: 龙龛糍 → 油味糍片 → 肠粉是 order（命名演变，且标注为传说性叙述）；咸肠粉与甜肠粉是 contrast
- **Composition**: 左大 sprite 配蒸笼，右信息栈；传说性来源单独用一个带标记的小框，明写"传说"
- **Title**: No.05 广州 · 肠粉与早茶
- **Core message**: 这一条陈列肠粉的来源叙述、咸甜两种与它在早茶中的位置
- **Content**: 来源属传说性叙述：永庆坊肠粉博物馆称肠粉诞生于唐代广东罗定龙龛寺，原名"龙龛糍"，清乾隆下江南品尝后因形似猪肠而建议改名 · 清末广州街头已有肠粉叫卖声，当时分咸、甜两种 · 肠粉是广州茶楼、酒家和夜市的经典品项，也是许多市民早餐的必选 · HUD：口味＝咸·甜／辣度＝不辣／价格＝NO DATA／年代＝清末
- **Images**: dish_changfen 左区大 sprite；prop_steamer 贴主体边缘；四行 HUD 图标；hud_bracket 四角
- **Motion suggestion**: 蒸笼盖上移、蒸汽块出现的两步硬切
- **Fact IDs**: F016, F017, F018

#### Slide 08 - No.06 长沙 · 米粉

- **Audience move**: 只知道湖南有米粉 → 知道圆粉扁粉之别、"码子"的意思与煨码炒码之分
- **Relationships**: 圆粉与扁粉是 contrast；煨码与炒码是 contrast；码子与米粉是 parent（浇头从属于一碗粉）
- **Composition**: 左大 sprite，右信息栈；圆/扁与煨/炒两组对照各占一行像素双格
- **Title**: No.06 长沙 · 米粉
- **Core message**: 这一条陈列长沙米粉的粉型选择、码子分类与汤底做法
- **Content**: 长沙米粉以扁形米粉、骨汤和多样码子为特色，有两千余年历史的说法 · 湖南米粉按形状分圆粉与扁粉；长沙市民多偏好扁粉，因为扁粉更易入味 · "码子"即浇头，分煨码与炒码——炒码现炒，煨码事先做好直接盖上 · 汤底多以猪骨或牛骨长时间熬制，配熟猪油、酱油调味 · 甘长顺传统手工米粉及五大炒码制作技艺源于 1883 年 · HUD：口味＝咸·鲜／辣度＝NO DATA／价格＝NO DATA／年代＝1883
- **Images**: dish_changshafen 左区大 sprite；四行 HUD 图标；hud_bracket 四角
- **Motion suggestion**: 圆粉/扁粉两格与煨码/炒码两格分别成对硬切出现
- **Fact IDs**: F019, F020, F021, F022, F023

#### Slide 09 - No.07 重庆 · 小面

- **Audience move**: 以为小面就是辣面 → 知道它有两版地方标准定义、十几种佐料与清楚的价格分档
- **Relationships**: 面条、时令蔬菜、十几种佐料、可选臊子是 membership（构成一碗的并列要素）；素小面与带臊子的面是 contrast（价格分档）
- **Composition**: 左大 sprite 旁挂辣椒图元，右信息栈；佐料清单排成像素网格小标签
- **Title**: No.07 重庆 · 小面
- **Core message**: 这一条陈列重庆小面的标准定义、佐料构成与价格分档
- **Content**: 2016 年 1 月地方标准《重庆小面烹饪技术指南》获批实施 · 2022 年《重庆小面门店经营服务规范》定义：面粉、食用碱、水制成的鲜面条，配时令蔬菜，沸水煮制，通常用十几种佐料调味，可带或不带臊子，麻辣鲜香 · 佐料通常十余种：酱油、味精、猪油、芽菜、姜水、蒜水、油酥花生、红油辣椒、花椒面等 · 价格：清汤或红汤小面约 7 元；杂酱、牛肉、肥肠等带臊子的面 10–22 元 · HUD：口味＝麻·辣·鲜·香／辣度＝以辣为主味／价格＝7 元起（2024）／年代＝2016 标准
- **Images**: dish_xiaomian 左区大 sprite；hud_chili 放大挂在 sprite 旁；四行 HUD 图标；hud_bracket 四角
- **Motion suggestion**: 辣度条一次拉满到第三档，佐料标签逐块出现
- **Fact IDs**: F024, F025, F026, F027

#### Slide 10 - No.08 西安 · 肉夹馍与肉丸胡辣汤

- **Audience move**: 把陕西和河南的胡辣汤混为一谈 → 知道西安是肉丸胡辣汤配坨坨馍，且知道白吉馍的成型标准
- **Relationships**: 白吉馍与腊汁肉是 link（互相成就）；西安肉丸胡辣汤与河南肉丁胡辣汤是 contrast
- **Composition**: 左大 sprite，右信息栈；"铁圈虎背菊花心"三个特征用三格像素小图标注
- **Title**: No.08 西安 · 肉夹馍与肉丸胡辣汤
- **Core message**: 这一条陈列白吉馍的成型标准、腊汁肉的搭配与西安胡辣汤的形态
- **Content**: 腊汁肉夹馍的白吉馍讲究"铁圈虎背菊花心"，三层圈型花纹、皮薄松脆内心软绵，与汤汁浓郁、糜而不烂的腊汁肉相配 · 西安的胡辣汤是肉丸胡辣汤，除丸子外加大量蔬菜——白菜、土豆块、胡萝卜、菜花、西葫芦，需配"坨坨馍"（有的地方叫白吉饼）· 价格：西安腊汁肉夹馍近年由 5–6 元涨到 10 元以上、个别 20 元；老店 6 元、新店低至 4 元、连锁品质款约 13 元 · HUD：口味＝咸·辣／辣度＝可加辣／价格＝4–13 元（2024）／年代＝NO DATA
- **Images**: dish_roujiamo 左区大 sprite；四行 HUD 图标；hud_bracket 四角
- **Motion suggestion**: 白吉馍三特征标注按"铁圈→虎背→菊花心"顺序硬切
- **Fact IDs**: F028, F029, F030

#### Slide 11 - No.09 兰州 · 牛肉面

- **Audience move**: 只记得"兰州拉面"这个招牌 → 知道 1915 年的成型节点、五色标准与本地/一线的两套价格
- **Relationships**: 一清二白三红四绿五黄的五项是 membership（同一碗的五个可见特征）；兰州本地价与一线城市均价是 contrast
- **Composition**: 左大 sprite，右信息栈；五色标准排成五格像素色板条
- **Title**: No.09 兰州 · 牛肉面
- **Core message**: 这一条陈列兰州牛肉面的成型年代、五色标准与两地价格
- **Content**: 近代地方志记载由回民马保子始创；1915 年开设自己的牛肉面馆，推出免费的"进店一碗汤" · 同年把提前煮好的凉面改为现场抻拉，汤底换成秘制肉汤，"一清二白三红四绿五黄"标准逐渐形成 · 五色＝汤清、萝卜片白、辣子油红、蒜苗和香菜绿、面条微黄 · 价格：兰州本地普遍 6–7 元、高端 8 元；《兰州牛肉面大数据报告（1.0）》（2020）一线城市均价 24 元/碗 · HUD：口味＝咸·辣／辣度＝可加辣／价格＝兰州 6–8 元 · 一线 24 元（2020）／年代＝1915
- **Images**: dish_niuroumian 左区大 sprite；四行 HUD 图标；hud_bracket 四角；hud_steam 点缀
- **Motion suggestion**: 五色色板条按清→白→红→绿→黄逐格点亮
- **Fact IDs**: F031, F032, F033, F034, F035

#### Slide 12 - No.10 云南 · 小锅米线

- **Audience move**: 只知道云南过桥米线 → 知道小锅米线是一锅一碗现煮，以及过桥米线的非遗与传播路线
- **Relationships**: 小锅米线与过桥米线是 contrast（同省两种米线形态）；建水 → 蒙自的传播是 order
- **Composition**: 左大 sprite 配红铜小锅，右信息栈；铜锅的尺寸数值单列一格
- **Title**: No.10 云南 · 小锅米线
- **Core message**: 这一条陈列小锅米线的器具与煮法，并对照同省过桥米线的年代与非遗身份
- **Content**: 小锅米线的锅用红铜制成，直径约 18 厘米、深约 10 厘米，一锅一碗现煮，汤热、味鲜、爽口 · 对照：蒙自过桥米线有 300 多年历史，2014 年列入国家级非物质文化遗产代表性项目名录 · 清咸丰年间（1851–1861）刘家庆在建水开始出售过桥米线；光绪末年因滇越铁路开通、蒙自设立通商口岸而传到蒙自 · HUD：口味＝鲜·爽口／辣度＝NO DATA／价格＝NO DATA／年代＝NO DATA（小锅米线本身）
- **Images**: dish_xiaoguomixian 左区大 sprite；prop_copperpot 贴主体边缘；四行 HUD 图标；hud_bracket 四角
- **Motion suggestion**: 铜锅直径 18cm / 深 10cm 两个数值随一条像素标尺自左向右加载
- **Fact IDs**: F036, F037, F038

#### Slide 13 - No.11 新疆 · 烤包子与奶茶

- **Audience move**: 没把烤包子当早餐 → 知道它是馕坑烤制、配咸奶茶，且早高峰第一炉常备 1000 个以上
- **Relationships**: 烤包子与奶茶是 link（固定早餐搭配）；死面皮 → 包馅 → 贴馕坑壁烤是 order
- **Composition**: 左区烤包子大 sprite 与奶茶次级 sprite 并置，右信息栈
- **Title**: No.11 新疆 · 烤包子与奶茶
- **Core message**: 这一条陈列烤包子的名称、做法与它同咸奶茶的固定搭配
- **Content**: 维吾尔语称"samsa"（萨木萨），流行于新疆及中亚；形状多为方形、三角形，馅料一般为羊肉与洋葱，也有鸡肉、牛肉、奶酪、土豆、南瓜 · 皮不发酵，死面擀薄包入羊肉、洋葱、孜然、胡椒调味的馅，贴在馕坑壁上烤制，成品金黄、皮脆肉嫩多汁 · "奶茶和烤包子是当地人最熟悉的早餐"；因需求量大，店家每天第一炉常准备 1000 个以上 · 新疆奶茶多为咸口，用砖茶或红茶煮开加牛奶反复熬煮搅拌 · HUD：口味＝咸·孜然·胡椒／辣度＝不辣／价格＝NO DATA／年代＝NO DATA
- **Images**: dish_kaobaozi 左区大 sprite；dish_naicha 并置小一档；四行 HUD 图标；hud_bracket 四角；hud_steam 点缀
- **Motion suggestion**: 「1000+」这一数值在属性条加载后单独硬切强调
- **Fact IDs**: F039, F040, F041, F042

### Part 3: 争议、对照与收卷

#### Slide 14 - 两处争议：豆腐脑咸甜 · 胡辣汤南北

- **Audience move**: 以为咸甜之争只是玩笑 → 知道它有明确的起点、工艺差异与南北定位差异，也知道胡辣汤的地域分派
- **Relationships**: 咸党与甜党是 contrast；豆腐脑与豆花是 link（同物异称）；河南肉丁胡辣汤与陕西肉丸胡辣汤是 contrast；逍遥镇/北舞渡/开封素三派与河南胡辣汤是 parent
- **Composition**: 页面中轴放豆腐脑单件 sprite，左右各引出一路——左"咸"右"甜"，玩家小人蹲坐在中轴不站队；下方一条窄带放胡辣汤南北对照
- **Title**: 两处争议
- **Core message**: 这一页陈列豆腐脑咸甜之争的起点与工艺差异，以及河南与陕西胡辣汤的形态区别
- **Content**: 争议起点：2011 年 6 月微博上"在豆腐脑咸甜事上，最见南北差异"一句引发大量争论；吃甜的自称"甜党"，吃咸的自称"咸党" · 称呼与配料：北方称豆腐脑、加酱油香菜葱花偏咸；南方称豆花、加红豆或白糖偏甜 · 工艺：北方用卤水点，质地细腻、勺子轻碰即碎；南方多用石膏点，口感紧实、筷子能夹起 · 定位：北方当早餐，南方当甜品 · 胡辣汤：河南多是肉丁，陕西是肉丸；河南内部又分逍遥镇、北舞渡、开封素三派，逍遥镇以胡椒为主角 · 说明：粽子甜咸不属早餐范围，本卷不收
- **Images**: dish_doufunao 中轴单件；prop_spoon 贴左侧咸路；player_sit 中轴蹲坐
- **Motion suggestion**: 左右两路从中轴向外分别擦出，玩家小人保持不动以示中立
- **Fact IDs**: F046, F047, F048, F049, F050, F051

#### Slide 15 - 图鉴总表

- **Audience move**: 记住了单条 → 能横向比较 11 条的主料、口味、年代与价格，并一眼看出哪些字段本次没有可核来源
- **Relationships**: 11 行之间是 membership（等重并列）；每行的编号/名称/城市/主料/口味/年代/价格是同一记录的字段
- **Composition**: 满幅原生表格，表头一行、数据 11 行；NO DATA 用次级文字色，与有数字的单元格明显分层
- **Title**: 图鉴总表 · No.01–No.11
- **Core message**: 这一页把 11 条图鉴的编号、名称、城市、碳水主料、口味标签、定型年代与可核价格并排列出
- **Content**: 表头＝编号／名称／城市／碳水主料／口味标签／定型年代／可核价格（年份）· 11 行数据与各条目页完全一致 · 无可核来源的价格与年代单元格一律写 NO DATA · 表下一行脚注说明取值规则与来源年份跨度（2020–2026）
- **Visualization**: 原生数据表 `atlas-index`，7 列 × 12 行（含表头）；`Native-ready`: `atlas-index=yes`
- **Images**: hud_star 作表头左侧的小强调点
- **Motion suggestion**: 表格整体一次硬切出现，不逐行动画
- **Fact IDs**: F001, F002, F004, F007, F008, F009, F012, F015, F017, F019, F023, F024, F027, F029, F030, F031, F034, F035, F036, F039, F042

#### Slide 16 - 图鉴完成

- **Audience move**: 读完 11 条 → 带走一句能复述的共性，并知道这本图鉴的取数规则
- **Relationships**: 题字层、原生标题、收束句、取数规则说明与满格进度条是 membership——同属收卷这一整体；11 格进度条与前面 11 张条目页是 parent（全卷对条目）
- **Closing impact**: 收束（binding）——「11 条不同的碳水，同一件事：一天从一碗热的开始」；构图 Reference：题字居中偏上，玩家小人在底部瓷砖地带上欢呼与开吃两个姿态并列，11 格进度条全部点亮
- **Composition**: 中轴题字层 + 下方满格进度条 + 地带上的两个小人
- **Title**: 图鉴完成
- **Core message**: 这一页收束全卷：11 格全部点亮，并复述共性与取数规则
- **Content**: 题字层「图鉴完成」（AI 像素题字）· 原生可编辑标题「图鉴完成 11 / 11」· 一句收束「11 条不同的碳水，同一件事：一天从一碗热的开始」· 取数规则复述：数字均标注来源年份，未取得可核来源的字段显示 NO DATA · 一行注明共 11 条、覆盖 11 座城市与地区
- **Images**: letter_complete 题字层；player_cheer 与 player_eat 立于地带；scene_ground 底边满幅；hud_heart 点缀
- **Motion suggestion**: 11 格进度条自左向右整条点亮后，题字硬切出现
- **Fact IDs**: F043, F044

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 每页备注从该页最终 SVG 的可见内容出发，平实读出这一页陈列了什么；数字照页面复述并带来源年份，NO DATA 的字段要口头说明"本次未取得可核来源"；不加页面上没有的事实，不制造悬念或"所以呢"式的收束
- **Total duration**: 约 12 分钟（封面与结尾各约 30 秒，共性页与争议页各约 60 秒，11 张条目页各约 45 秒，表格页约 60 秒）
- **Notes style**: conversational — 中性平实的播报口吻，句子短，数字念清楚
- **Presentation purpose**: 以图鉴形式并列陈列各地代表性早餐，先给可核查的地域、主料、年代、口味与吃法，再给跨地区共性与两处争议；不树立中心论点
