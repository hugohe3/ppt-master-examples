<!-- ppt-master-schema: design-spec/v1 -->
# 二十四节气手账·秋 - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | 二十四节气手账·秋 |
| Canvas Format | Story/Vertical 1080×1920 |
| Page Count | 14 |
| Primary Language | zh-CN |
| Target Audience | 对传统文化有轻度兴趣、习惯手机竖屏阅读的普通读者：叫得出六个秋节气的名字，但说不准日期，也没读过七十二候原文 |
| Communication Intent | 先把秋天拆成六个可以分别过的日子并给出确切日期，再把七十二候原文完整交到读者手里；每一站结尾都落到一件今天就能做的事 |
| Desired Audience Outcome | 读者能按顺序说出 2026 年秋季六个节气及其日期，记住至少一条三候原文，并在下一个节气到来时真的去做一件事 |
| Core Message / Ask / Action | 秋天不是一整块，它有六个可以分别过的日子——挑一个，照着过一次 |
| Delivery Context | 主要为手机竖屏自读（社媒滑动式浏览，无主讲人）；次要为打印成手账内页夹在本子里 |
| Artifact Afterlife | 2026 年秋天反复回查节气日期与物候原文；打印留存为手账内页 |
| Reading Mode | balanced |
| Content Strategy | 平衡：以研究补充中的事实为准重新组织为手账叙事，日期与七十二候原文逐字保留，查不到的字段标 NO DATA 不推算 |
| Design Style | showcase 视觉主导叙事 × sketch-notes 手绘手账视觉 |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 最终 Stage-2 proactive 值 |
| Custom Animations | enabled — 用户明确指令（本轮必须包含 Morph 与 path 轨迹动画） |
| Narration Audio | disabled — 最终 Stage-2 proactive 值 |
| Created Date | 2026-09-04 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | Story/Vertical |
| Dimensions | 1080 × 1920 |
| viewBox | `0 0 1080 1920` |
| Margins | 左右 80；表意文字、标题与行动提示守 y=120..1740，纸底与插画可出血 |
| Content Area | x 80..1000，y 120..1740 |

## III. Visual Theme

### Theme Style

- **Mode**: showcase
- **Visual style**: sketch-notes
- **Theme**: 一本翻开的秋日手账——暖纸底、黑墨抖线、蜡笔色块；六个节气是路线上的六站，一条手绘波浪路线贯穿全卷作为跨页母题，节气页取其中一段作为页面骨架
- **Tone**: 亲切、慢、带点手写的随意；不端着，也不卖萌

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #FBF6EA | 暖纸底，全卷统一画布 |
| Secondary background | #F1E5CE | 次级纸块、便签、表格底 |
| Primary | #A8502A | 秋叶赭：标题墨色之外的主色、主要色块与关键线条 |
| Accent | #E39A1F | 金桂黄：每页只留 1–2 处强调（关键箭头、被圈出的日期） |
| Secondary accent | #6F8C5A | 残绿：物候、草木、次要色块 |
| Body text | #33302A | 墨褐：正文与全部手绘线条的墨色 |
| Secondary text | #6B6355 | 注释、图注、脚注 |
| Divider | #D8C9AC | 手绘分隔线、虚线路线、表格线 |
| Block shade | #EDE0C6 | 蜡笔色块的底层平涂，比纸底低一档 |

### AI Image Strategy

- **Image Rendering**: sketch-notes
- **Visual**: 暖奶油纸上黑色手绘抖线，蜡笔／粉彩色块略微溢出线框；简笔卡通造型，无渐变、无投影、无高光
- **Mood**: 温暖、可亲、像一位耐心的老师在笔记本边缘随手画的插图

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 楷体书写感，带手写笔意 | KaiTi | Georgia | serif |
| Body | 清晰人文无衬线，长句可读 | Microsoft YaHei | Trebuchet MS | sans-serif |
| Display | 与标题同源的大字书写体，用于大日期与节气序号 | KaiTi | Georgia | serif |
| Caption | 与正文同源，用于物候候名与图注 | Microsoft YaHei | Trebuchet MS | sans-serif |
| Annotation | 与正文同源，缩小档 | Microsoft YaHei | Trebuchet MS | sans-serif |
| Footnote | 与正文同源，最小档 | Microsoft YaHei | Trebuchet MS | sans-serif |

- **Title stack**: KaiTi
- **Body stack**: Microsoft YaHei
- **Display stack**: KaiTi
- **Caption stack**: Microsoft YaHei
- **Annotation stack**: Microsoft YaHei
- **Footnote stack**: Microsoft YaHei
- **Role rationale**: Display 与 Title 同族但独立锚定，因为大日期数字与节气序号在 8 页上重复出现且尺寸远超页面标题；Caption 承载六页节气页反复出现的三候候名与图注，Annotation 与 Footnote 沿用正文族，三者仅锁尺寸不换族。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 56 |
| Title | 100 |
| Cover title | 160 |
| Display | 128 |
| Subtitle | 72 |
| Lead | 68 |
| Caption | 40 |
| Annotation | 44 |
| Footnote | 32 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 竖屏自上而下——题字或主视觉先抓眼，接住日期，再落到三候，最后一行口语提示收尾
- **Composition tendency**: 每页换一种 sketch-notes 几何：波浪箭头旅程路线、放射思维图、手绘横幅、编号圆沿虚线跳、云朵框；不允许连续两页用同一种
- **Cross-page continuity**: 一条手绘波浪路线是全卷母题，六个节气页各取其中一段并保留编号圆；纸底与墨色恒定，色块随节气冷暖推移
- **Spacing posture**: 可变——节气页 dense，色卡与食物页 breathing，封面/总览/收尾/来源 anchor
- **Spacing anchors**: 页边距 80；块间距 56；分栏槽 40；圆角 28；正文行距 84

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2

| Icon Path | Suitable Scenarios |
| --- | --- |
| icons/tabler-outline/calendar-event.svg | 日期、交节时刻 |
| icons/tabler-outline/leaf.svg | 草木、秋叶 |
| icons/tabler-outline/wind.svg | 凉风至 |
| icons/tabler-outline/droplet.svg | 白露、露水 |
| icons/tabler-outline/sun.svg | 昼、暑气 |
| icons/tabler-outline/moon.svg | 夜、祭月 |
| icons/tabler-outline/snowflake.svg | 霜、寒 |
| icons/tabler-outline/cloud.svg | 天气、天地始肃 |
| icons/tabler-outline/bowl.svg | 汤、秋汤 |
| icons/tabler-outline/cup.svg | 茶、白露茶 |
| icons/tabler-outline/wheat.svg | 禾乃登、丰收 |
| icons/tabler-outline/egg.svg | 竖蛋 |
| icons/tabler-outline/mountain.svg | 登高 |
| icons/tabler-outline/flame.svg | 进补、灶 |
| icons/tabler-outline/link.svg | 来源链接 |
| icons/tabler-outline/feather.svg | 鸿雁、玄鸟 |
| icons/tabler-outline/fish.svg | 鱼片滚汤 |
| icons/tabler-outline/plant.svg | 秋菜、草木 |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P12 | table | record_table | 六个节气各一行，日期与三候原文按固定字段并置对照 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| sheet_terms.png | 1024×1024 | 1:1 | 六个节气主视觉 doodle 的母表 | Illustration Sheet | 不落页，仅供切片 | no-crop | ai | Generated | 3列2行纯键色底，每格一个节气主视觉简笔画：啃秋西瓜、处暑鸭与河灯、白露草叶露珠与龙眼、秋分稻穗与天平、寒露黄菊与芝麻、霜降软柿与霜叶 | none | local |
| sheet_phenology.png | 1024×1024 | 1:1 | 六个物候小图的母表 | Illustration Sheet | 不落页，仅供切片 | no-crop | ai | Generated | 3列2行纯键色底，每格一个物候小图：凉风、寒蝉、鸿雁、玄鸟、黄菊、霜晶 | none | local |
| sheet_decor.png | 1024×1024 | 1:1 | 装饰件母表 | Illustration Sheet | 不落页，仅供切片 | no-crop | ai | Generated | 2列2行纯键色底：星星簇、波浪箭头、虚线路线段、手绘横幅飘带 | none | local |
| sheet_food.png | 1024×1024 | 1:1 | 时令食物小图母表 | Illustration Sheet | 不落页，仅供切片 | no-crop | ai | Generated | 3列2行纯键色底：西瓜块、烤鸭腿、龙眼、秋菜鱼片汤、芝麻、软柿 | none | local |
| sheet_lettering_terms.png | 1376×768 | 34:19 | 六个节气名的手绘题字母表 | Illustration Sheet | 不落页，仅供切片 | no-crop | ai | Generated | 3列2行纯键色底，每格一个横排两字手写题字：立秋／处暑／白露／秋分／寒露／霜降 | embedded | local |
| sheet_lettering_title.png | 1376×768 | 34:19 | 封面题字与落款印章的母表 | Illustration Sheet | 不落页，仅供切片 | no-crop | ai | Generated | 1列2行纯键色底，上格封面题字「二十四节气手账·秋」，下格「秋」字印章 | embedded | local |
| term_liqiu.png | 268×269 | 1:1 | 立秋页主视觉 | Illustration element | 页面上半区主视觉，压在波浪路线的第一站上 | no-crop | slice | Generated | Derived from sheet_terms.png; 第1格 | none | local |
| term_chushu.png | 294×309 | 19:20 | 处暑页主视觉 | Illustration element | 横幅标题右侧，与河灯栏并置 | no-crop | slice | Generated | Derived from sheet_terms.png; 第2格 | none | local |
| term_bailu.png | 257×307 | 5:6 | 白露页主视觉 | Illustration element | 页面下半区，承接雁的飞行弧线终点 | no-crop | slice | Generated | Derived from sheet_terms.png; 第3格 | none | local |
| term_qiufen.png | 258×289 | 17:19 | 秋分页主视觉 | Illustration element | 中轴对称构图的轴心 | no-crop | slice | Generated | Derived from sheet_terms.png; 第4格 | none | local |
| term_hanlu.png | 268×265 | 1:1 | 寒露页主视觉 | Illustration element | 上坡路线的坡顶 | no-crop | slice | Generated | Derived from sheet_terms.png; 第5格 | none | local |
| term_shuangjiang.png | 269×252 | 16:15 | 霜降页主视觉 | Illustration element | 云朵框内的主体 | no-crop | slice | Generated | Derived from sheet_terms.png; 第6格 | none | local |
| ph_coolwind.png | 240×204 | 20:17 | 凉风至 | Illustration element | 三候行的行首小图 | no-crop | slice | Generated | Derived from sheet_phenology.png; 第1格 | none | local |
| ph_cicada.png | 184×251 | 11:15 | 寒蝉鸣 | Illustration element | 三候行的行首小图 | no-crop | slice | Generated | Derived from sheet_phenology.png; 第2格 | none | local |
| ph_goose.png | 270×215 | 5:4 | 鸿雁来 | Illustration element | 沿手绘飞行弧线移动的主体，白露与寒露两页复用 | no-crop | slice | Generated | Derived from sheet_phenology.png; 第3格 | none | local |
| ph_swallow.png | 238×232 | 21:20 | 玄鸟归 | Illustration element | 三候行的行首小图 | no-crop | slice | Generated | Derived from sheet_phenology.png; 第4格 | none | local |
| ph_chrysanthemum.png | 262×225 | 7:6 | 菊有黄花 | Illustration element | 三候行的行首小图 | no-crop | slice | Generated | Derived from sheet_phenology.png; 第5格 | none | local |
| ph_frost.png | 237×231 | 21:20 | 霜与草木黄落 | Illustration element | 三候行的行首小图 | no-crop | slice | Generated | Derived from sheet_phenology.png; 第6格 | none | local |
| decor_star.png | 349×348 | 1:1 | 星星簇装饰 | Illustration element | 空白角落点缀 | no-crop | slice | Generated | Derived from sheet_decor.png; 第1格 | none | local |
| decor_arrow.png | 367×268 | 26:19 | 波浪箭头 | Illustration element | 连接两块内容的指向 | no-crop | slice | Generated | Derived from sheet_decor.png; 第2格 | none | local |
| decor_route.png | 438×54 | 73:9 | 虚线路线段 | Illustration element | 总览页与收尾页的路线装饰 | no-crop | slice | Generated | Derived from sheet_decor.png; 第3格 | none | local |
| decor_ribbon.png | 452×166 | 49:18 | 手绘横幅飘带 | Illustration element | 承载页面标题的横幅 | no-crop | slice | Generated | Derived from sheet_decor.png; 第4格 | none | local |
| food_watermelon.png | 277×240 | 15:13 | 啃秋西瓜 | Illustration element | 食物页拼盘中的一件 | no-crop | slice | Generated | Derived from sheet_food.png; 第1格 | none | local |
| food_duck.png | 274×213 | 9:7 | 处暑鸭 | Illustration element | 食物页拼盘中的一件 | no-crop | slice | Generated | Derived from sheet_food.png; 第2格 | none | local |
| food_longan.png | 250×282 | 8:9 | 白露龙眼 | Illustration element | 食物页拼盘中的一件 | no-crop | slice | Generated | Derived from sheet_food.png; 第3格 | none | local |
| food_qiucai.png | 261×316 | 14:17 | 秋分秋汤 | Illustration element | 食物页拼盘中的一件 | no-crop | slice | Generated | Derived from sheet_food.png; 第4格 | none | local |
| food_sesame.png | 257×214 | 6:5 | 寒露芝麻 | Illustration element | 食物页拼盘中的一件 | no-crop | slice | Generated | Derived from sheet_food.png; 第5格 | none | local |
| food_persimmon.png | 235×281 | 5:6 | 霜降柿子 | Illustration element | 食物页拼盘中的一件 | no-crop | slice | Generated | Derived from sheet_food.png; 第6格 | none | local |
| let_cover.png | 1237×173 | 143:20 | 封面题字「二十四节气手账·秋」 | Lettering element | 封面横幅上方的显示层，原生标题另置 | no-crop | slice | Generated | Derived from sheet_lettering_title.png; 第1格 | embedded | hero_page |
| let_liqiu.png | 366×170 | 28:13 | 题字「立秋」 | Lettering element | 节气页顶部显示层，原生标题另置 | no-crop | slice | Generated | Derived from sheet_lettering_terms.png; 第1格 | embedded | local |
| let_chushu.png | 344×204 | 27:16 | 题字「处暑」 | Lettering element | 节气页顶部显示层，原生标题另置 | no-crop | slice | Generated | Derived from sheet_lettering_terms.png; 第2格 | embedded | local |
| let_bailu.png | 335×191 | 7:4 | 题字「白露」 | Lettering element | 节气页顶部显示层，原生标题另置 | no-crop | slice | Generated | Derived from sheet_lettering_terms.png; 第3格 | embedded | local |
| let_qiufen.png | 361×181 | 2:1 | 题字「秋分」 | Lettering element | 节气页顶部显示层，原生标题另置 | no-crop | slice | Generated | Derived from sheet_lettering_terms.png; 第4格 | embedded | local |
| let_hanlu.png | 360×214 | 32:19 | 题字「寒露」 | Lettering element | 节气页顶部显示层，原生标题另置 | no-crop | slice | Generated | Derived from sheet_lettering_terms.png; 第5格 | embedded | local |
| let_shuangjiang.png | 361×215 | 32:19 | 题字「霜降」 | Lettering element | 节气页顶部显示层，原生标题另置 | no-crop | slice | Generated | Derived from sheet_lettering_terms.png; 第6格 | embedded | local |
| let_seal.png | 253×254 | 1:1 | 「秋」字印章 | Lettering element | 收尾页的落款印记 | no-crop | slice | Generated | Derived from sheet_lettering_title.png; 第2格 | embedded | local |

## IX. Content Outline

### Part 1: 打开这本手账

#### Slide 01 - 封面：二十四节气手账·秋

- **Audience move**: 只知道"秋天" → 知道这本手账把秋天拆成六站，并看到第一站与最后一站的日期
- **Relationships**: 标题、时间跨度、六站承诺三个单元，标题为父，时间跨度与六站承诺并列说明它
- **Composition**: 手绘横幅飘带托住题字，纸底出血，落叶与星星散在四角；下方一行小字给出时间跨度
- **Cover impact**: 秋天不是一整块，它有六个可以分别过的日子
- **Title**: 二十四节气手账·秋
- **Core message**: 秋天有六站，这本手账带你一站一站过
- **Content**: 主标题「二十四节气手账·秋」· 副标题「立秋到霜降，六个可以分别过的日子」· 时间跨度「2026.8.7 — 2026.10.23」· 一行小字「日期与三候原文均有出处，见末页」
- **Images**: let_cover.png 作显示层题字，原生标题同址另置；decor_ribbon.png 承载题字；decor_star.png 点缀
- **Motion suggestion**: 题字与横幅先落位，落叶随后飘入，建立"翻开手账"的起手
- **Fact IDs**: F001, F006

#### Slide 02 - 节气是什么

- **Audience move**: 以为节气是老黄历里的说法 → 知道它是被联合国教科文组织列入名录的时间知识体系，且每个节气自带三候
- **Relationships**: 节气的身份、节气的结构（一气三候）、本手账的读法三个单元，前两个是背景，第三个由它们推出
- **Composition**: 一个云朵框圈住"什么是节气"的核心句，框外用波浪线牵出"一气 = 三候"的小图解
- **Title**: 一个节气，三候
- **Core message**: 节气不只是日期，它自带一套五天一变的物候观察
- **Content**: 2016年11月30日二十四节气列入联合国教科文组织人类非物质文化遗产代表作名录 · 五日为一候，三候为一气 · 三候原文出自元代吴澄《月令七十二候集解》 · 这本手账每一站给你：日期 / 三候 / 一条习俗 / 一件今天能做的事
- **Fact IDs**: F019

#### Slide 03 - 秋天的六站

- **Audience move**: 记不住顺序 → 一眼看到六个节气的名字、顺序与日期，知道自己现在在哪一站
- **Relationships**: 六个节气构成一条时间上的有序序列，两两相邻约隔十五天
- **Composition**: 一条手绘波浪路线从左上斜穿到右下，六个编号圆沿虚线跳落其上，每个圆旁写节气名与日期
- **Title**: 秋天的六站
- **Core message**: 从 8 月 7 日到 10 月 23 日，秋天分六段走完
- **Content**: 立秋 8.7 19:43 · 处暑 8.23 10:19 · 白露 9.7 22:41 · 秋分 9.23 08:05 · 寒露 10.8 14:29 · 霜降 10.23 17:38 · 均为东八区时间 · 农历对照 NO DATA
- **Images**: decor_route.png 作虚线路线段
- **Motion suggestion**: 六个编号圆沿路线依次跳落；本页的第一站圆与下一页的主视觉是同一个单元的两个可见状态
- **Fact IDs**: F001, F002, F003, F004, F005, F006

### Part 2: 六站

#### Slide 04 - 立秋

- **Audience move**: 以为立秋就是天凉了 → 知道立秋当天的确切时刻、三候原文，并拿到"啃秋"这件能做的事
- **Relationships**: 日期、三候、习俗、行动四个单元，三候在日期之下按时间顺序排列，习俗与行动由三候的"暑气未退"推出
- **Composition**: 放射思维图——中央是啃秋西瓜的主视觉，三候沿三个方向辐射出去，行动提示压在底部横条上
- **Title**: 立秋
- **Core message**: 秋字开头，暑气还在，先把西瓜的最后一口啃完
- **Content**: 2026年8月7日 19:43 · 三候：一候凉风至 / 二候白露降 / 三候寒蝉鸣 · 习俗：立秋悬秤称人与立夏比轻重，瘦了要"贴秋膘"；南方"啃秋"，这天多吃西瓜防秋燥 · 这个节气怎么过：秤一秤，别急着进补，先把西瓜的最后一口啃完
- **Images**: let_liqiu.png 题字显示层；term_liqiu.png 中央主视觉；ph_coolwind.png 与 ph_cicada.png 作三候行首小图
- **Motion suggestion**: 上一页的第一站编号圆放大为本页主视觉，保持圆形锚点不变
- **Fact IDs**: F001, F007, F013

#### Slide 05 - 处暑

- **Audience move**: 分不清处暑和立秋 → 知道"处"是终止的意思，记住鹰乃祭鸟三候，并想起去放一盏河灯
- **Relationships**: 日期、三候、习俗、行动四个单元；习俗内部鸭子与河灯是并列的两件事
- **Composition**: 手绘横幅承载标题，横幅下左右分栏——左栏鸭子与谚语，右栏河灯与悼念之意，底部一行行动提示
- **Title**: 处暑
- **Core message**: 暑气到此为止，天地开始收敛
- **Content**: 2026年8月23日 10:19 · 三候：一候鹰乃祭鸟 / 二候天地始肃 / 三候禾乃登 · 习俗：处暑吃鸭子，江苏谚语"处暑送鸭，无病各家"；处暑放河灯（荷花灯），寄托对逝者的悼念与对安康的祝福 · 这个节气怎么过：暑气打包退场，找个傍晚去水边，把一盏灯放走
- **Images**: let_chushu.png 题字显示层；term_chushu.png 右栏主视觉；decor_ribbon.png 承载标题
- **Fact IDs**: F002, F008, F014

#### Slide 06 - 秋天的颜色

- **Audience move**: 秋天在脑子里只有一个"黄" → 看到秋天沿六站从暑气橙走到霜白的一条色带
- **Relationships**: 六个色块与六个节气一一对应，构成一条从暖到冷的有序渐变
- **Composition**: 六个蜡笔色块沿一条波浪线排开，色块略微溢出线框，每块下写节气名与一个颜色的口语名字；大量留白
- **Title**: 秋天的颜色
- **Core message**: 秋天的颜色是一路凉下去的
- **Content**: 立秋·瓜瓤红 · 处暑·鸭黄 · 白露·露水青 · 秋分·稻穗金 · 寒露·菊花黄 · 霜降·霜白 · 一行小字：颜色是这本手账的说法，不是节气本身的规定
- **Fact IDs**: 无

#### Slide 07 - 白露

- **Audience move**: 只把白露当成"凉了" → 记住鸿雁来、玄鸟归的迁徙画面，并知道该泡一壶秋白露
- **Relationships**: 日期、三候、习俗、行动四个单元；三候内部鸿雁来与玄鸟归是一来一去的对照关系
- **Composition**: 一条手绘飞行弧线从页面左上划到右下，雁沿弧线飞过，弧线下方依次落三候，主视觉在弧线终点承接
- **Title**: 白露
- **Core message**: 露水开始结在草上，鸟开始动身
- **Content**: 2026年9月7日 22:41 · 三候：一候鸿雁来 / 二候玄鸟归 / 三候群鸟养羞 · 习俗：饮白露茶，民谚"春茶苦，夏茶涩，要喝茶，秋白露"；福州"白露必吃龙眼"；民间"收清露"，《本草纲目》载秋露可收作煎膏 · 这个节气怎么过：早晚加一件；泡一壶秋白露，看院子里的露水什么时候结上
- **Images**: let_bailu.png 题字显示层；ph_goose.png 沿飞行弧线移动；ph_swallow.png 作三候行首小图；term_bailu.png 弧线终点主视觉
- **Motion suggestion**: 雁沿那条手绘弧线从左上飞到右下，飞行结束时正好落在主视觉旁——迁徙的方向本身就是这一候的意思
- **Fact IDs**: F003, F009, F015

#### Slide 08 - 秋分

- **Audience move**: 只知道秋分昼夜等长 → 知道它同时是中国农民丰收节，并记住"雷始收声"的收敛感
- **Relationships**: 日期、三候、习俗、制度、行动五个单元；昼与夜是一组对称对照，丰收节由秋分的农事意义推出
- **Composition**: 严格中轴对称——一条竖直手绘线把页面分成昼与夜两半，主视觉压在轴心，三候与丰收节分列两侧
- **Title**: 秋分
- **Core message**: 昼夜刚好平分，这天全国的农民过节
- **Content**: 2026年9月23日 08:05 · 三候：一候雷始收声 / 二候蛰虫坯户 / 三候水始涸 · 习俗：秋祭月、送秋牛、放风筝、吃秋菜喝秋汤；岭南采野苋菜与鱼片"滚汤"名曰秋汤；"秋分到，蛋儿俏"的竖蛋游戏 · 制度：2018年起国务院批复将每年农历秋分设立为中国农民丰收节，第一个在国家层面专门为农民设立的节日 · 这个节气怎么过：昼夜刚好一样长，去田里或菜场逛逛，这天全国的农民过节
- **Images**: let_qiufen.png 题字显示层；term_qiufen.png 轴心主视觉
- **Fact IDs**: F004, F010, F016, F018

#### Slide 09 - 秋天吃什么

- **Audience move**: 想不起秋天该吃什么 → 看到六站各自的一件时令食物，可以照单去买
- **Relationships**: 六件食物与六个节气一一对应，彼此并列无先后
- **Composition**: 云朵框圈住整盘食物，六件食物在框内错落摆开，每件旁一个手写标签；框外一行行动提示
- **Title**: 秋天吃什么
- **Core message**: 六站各有一件当季的东西，照单买就行
- **Content**: 立秋·西瓜（啃秋防秋燥）· 处暑·鸭（处暑送鸭，无病各家）· 白露·龙眼（福州白露必吃龙眼）· 秋分·秋菜鱼片汤（岭南秋汤）· 寒露·芝麻（寒露吃芝麻）· 霜降·柿子（霜降吃灯柿，不会流鼻涕）
- **Images**: food_watermelon.png / food_duck.png / food_longan.png / food_qiucai.png / food_sesame.png / food_persimmon.png 六件在云朵框内错落摆开，大小相近、互不重叠
- **Fact IDs**: F013, F014, F015, F016, F017

#### Slide 10 - 寒露

- **Audience move**: 把寒露当白露的重复 → 知道寒露是"露要结霜了"的转折，并想起去登一次高
- **Relationships**: 日期、三候、习俗、行动四个单元；寒露与白露构成一组冷暖对照，被明确点出
- **Composition**: 上坡构图——一条手绘上坡虚线从左下升到右上，编号圆沿坡跳落，主视觉在坡顶，行动提示在坡底
- **Title**: 寒露
- **Core message**: 露从白到寒，只差一步就结霜
- **Content**: 2026年10月8日 14:29 · 三候：一候鸿雁来宾 / 二候雀入大水为蛤 / 三候菊有黄花 · 与白露对照：同是露，白露是"降"，寒露是"寒"，下一站就结霜了 · 习俗：寒露吃芝麻；寒露前三后四所采之茶谓之正秋茶；近重阳，有登高、赏枫、饮菊花酒之俗 · 这个节气怎么过：把凉鞋收起来，登一次高，回家吃点芝麻
- **Images**: let_hanlu.png 题字显示层；term_hanlu.png 坡顶主视觉；ph_goose.png 复用于"鸿雁来宾"；ph_chrysanthemum.png 作"菊有黄花"行首小图
- **Fact IDs**: F005, F011, F017

#### Slide 11 - 霜降

- **Audience move**: 不知道秋天怎么结束 → 知道霜降是秋天最后一个节气，并拿到"买几只软柿子"这件收尾的事
- **Relationships**: 日期、三候、习俗、行动四个单元；本页与前五站构成"最后一站"的收束关系
- **Composition**: 一个大云朵框把柿子主视觉整个圈住占据页面上三分之二，三候在框下横排，行动提示单独一行
- **Title**: 霜降
- **Core message**: 秋天最后一站，草木黄落，虫也睡了
- **Content**: 2026年10月23日 17:38 · 三候：一候豺乃祭兽 / 二候草木黄落 / 三候蛰虫咸俯 · 习俗：柿子在霜降前后成熟，皮薄肉多味鲜美，民谚"霜降吃灯柿，不会流鼻涕"；登高山、赏菊花是霜降雅事 · 这个节气怎么过：秋天最后一站，买几只软柿子，给秋天收个尾
- **Images**: let_shuangjiang.png 题字显示层；term_shuangjiang.png 云朵框内主视觉；ph_frost.png 作"草木黄落"行首小图
- **Fact IDs**: F006, F012, F017

### Part 3: 合起来看

#### Slide 12 - 六站一览

- **Audience move**: 六站分散在六页 → 在一张表里同时看到六个日期与十八条候，可以直接抄进自己的本子
- **Relationships**: 六个节气各为一条记录，日期与三候是每条记录上并列的固定字段
- **Composition**: 一张手绘线框表格占满内容区，表头三列，六行分别是六个节气；行底交替铺次级纸块
- **Title**: 六站一览
- **Core message**: 六个日期、十八条候，一张表抄走
- **Content**: 表头：节气 / 2026年日期 / 三候 · 立秋 / 8月7日 19:43 / 凉风至·白露降·寒蝉鸣 · 处暑 / 8月23日 10:19 / 鹰乃祭鸟·天地始肃·禾乃登 · 白露 / 9月7日 22:41 / 鸿雁来·玄鸟归·群鸟养羞 · 秋分 / 9月23日 08:05 / 雷始收声·蛰虫坯户·水始涸 · 寒露 / 10月8日 14:29 / 鸿雁来宾·雀入大水为蛤·菊有黄花 · 霜降 / 10月23日 17:38 / 豺乃祭兽·草木黄落·蛰虫咸俯 · 表下脚注：时刻为东八区时间；三候依《月令七十二候集解》
- **Visualization**: 六节气 × 日期 / 三候 的纯文本单元格对照表；`Native-ready`: autumn-terms-overview=yes
- **Motion suggestion**: 前面那条波浪路线上的六个编号圆收拢成表格的六行——同一组单元换一种排布
- **Fact IDs**: F001, F002, F003, F004, F005, F006, F007, F008, F009, F010, F011, F012

#### Slide 13 - 挑一站，过一次

- **Audience move**: 读完就放下 → 认领一站，并知道秋天在 11 月 7 日交给冬天
- **Relationships**: 行动召唤与截止时间两个单元，截止时间给行动召唤加上时限
- **Closing impact**: 秋天有六个可以分别过的日子，挑一个，照着过一次
- **Composition**: 波浪路线在这里收束成一个终点圆，大字 takeaway 压在中央，右下角落一枚「秋」字印章
- **Title**: 挑一站，过一次
- **Core message**: 别等下一个秋天——挑一站，照着过一次
- **Content**: 大字：挑一站，过一次 · 六件事回收：啃个瓜 / 放盏灯 / 泡壶茶 / 逛趟菜场 / 登次高 / 买几只柿子 · 截止提示：2026年11月7日 17:52 立冬，秋天就交班了
- **Images**: let_seal.png 作落款印章；decor_route.png 收束成终点圆
- **Fact IDs**: F020

#### Slide 14 - 这些说法从哪来

- **Audience move**: 不确定日期与原文可信 → 看到每一类事实对应的具体来源并可点开
- **Relationships**: 四类事实（交节时刻 / 三候原文 / 习俗 / 制度背景）各自链接到一个来源，彼此并列
- **Composition**: 竖排四条来源，每条一个图标、一行说明、一条可点的链接文字；底部一行免责小字
- **Title**: 这些说法从哪来
- **Core message**: 日期、原文、习俗都能查到出处
- **Content**: 交节时刻：香港天文台 二十四节气日期及时间资料（https://www.hko.gov.hk/tc/gts/astronomy/data/files/24SolarTerms_2026.xml）· 三候原文：《月令七十二候集解》体系，见维基百科「七十二候」（https://zh.wikipedia.org/zh-hans/七十二候）· 习俗与时令食物：北京市园林绿化局节气科普（https://yllhj.beijing.gov.cn/ztxx/lhysh/sh/202311/t20231120_3305348.shtml）、中国气象网·秋分（https://www.cma.gov.cn/ztbd/2025zt/24jq/qiufen/index.html）· 制度背景：中国政府网 中国农民丰收节（https://www.gov.cn/zhengce/2018-06/22/content_5300368.htm）、文化和旅游部 二十四节气列入人类非遗名录（https://www.mct.gov.cn/whzx/bnsj/dwwhllj/201612/t20161214_773196.html）· 小字：农历对照日期未取到权威逐条数据，本手账标 NO DATA，不作推算
- **Fact IDs**: F001, F007, F017, F018, F019

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Content**: 每页一段口语旁白，讲清这一页在整条秋线上的位置与情绪；事实一律以页面上已有的日期、三候原文与习俗为准，不引入页面之外的新事实；节气页的旁白以那一句"这个节气怎么过"收尾
- **Total duration**: 约 7 分钟（14 页，每页 25–35 秒）
- **Notes style**: conversational
- **Presentation purpose**: 先把秋天拆成六个可以分别过的日子并给出确切日期，再把七十二候原文完整交到读者手里；每一站结尾都落到一件今天就能做的事
