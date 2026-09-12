<!-- ppt-master-schema: design-spec/v1 -->
# dujiangyan_zh_sparse - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | dujiangyan_zh_sparse |
| Canvas Format | ppt169 (1280×720) |
| Page Count | 14 |
| Primary Language | zh-CN |
| Target Audience | 对都江堰只有"课本印象"的一般成年读者与高中/大学通识听众：知道它古老、知道它在四川，但说不清三大工程各自做什么、也不知道它今天还在运行 |
| Communication Intent | 先解释机制（三大主体工程如何分水、排沙、引水），再说明它为何能运行两千余年（治水口诀与岁修制度），最后用今天的灌区数据回收"它还在上班"这个判断；解释优先于赞叹 |
| Desired Audience Outcome | 听众能用自己的话说出鱼嘴、飞沙堰、宝瓶口各自做什么、三者如何配合，并能举出一个今天仍在运行的具体数字 |
| Core Message / Ask / Action | 都江堰不是一处古迹，而是一套仍在运行的系统：它靠"顺着水势布置"的三级分工和写进制度的岁修，把公元前 256 年的方案一直用到今天 |
| Delivery Context | 主要为有主讲人的现场科普讲解，约 15–18 分钟；次要为讲后自行翻阅的电子稿 |
| Artifact Afterlife | 作为科普/通识讲解材料留存与重复使用，可被他人直接拿去讲 |
| Reading Mode | balanced |
| Content Strategy | 用户未提出任何材料取舍要求（`content_divergence` 留空），按 balanced 默认处理：事实全部来自 `sources/dujiangyan_research.facts.json`，叙述结构由本卷自建并在页面上标注"整理" |
| Design Style | 方向 B「工程图纸」— 深色蓝图纸 × 数据出版：以工程制图的细线、引线、尺寸标注作为版面语言，数据页按新闻信息图的栅格排布 |
| AI Image Acquisition Path | not applicable |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 流程默认（用户未表态，最终 Stage 2 主动值取默认 `true`） |
| Custom Animations | enabled — 本轮执行任务书的硬性要求（dogfood 框架要求，非用户要求；流程默认本应为 `disabled`） |
| Narration Audio | disabled — 流程默认（用户未表态，最终 Stage 2 主动值取默认 `false`） |
| Created Date | 2026-09-12 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | ppt169 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 上下 56 px，左右 72 px |
| Content Area | x: 72–1208，y: 56–664 |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: instructional, narrative
- **Mode Behavior**: 以"问题 → 机制拆解 → 机制合拢 → 制度 → 今天"的教学序列推进：先立成都平原涝旱并存的矛盾（narrative 的张力开场），再用三页并列拆解鱼嘴／飞沙堰／宝瓶口（instructional 的概念分解），随即把三件放回同一张总图讲一次洪水中的动作顺序（合拢），最后由治水口诀与岁修制度过渡到今天的灌区数字收束开篇的矛盾。每页标题写成一句可复述的机制判断，不写名词标签。
- **Visual style**: custom
- **Visual Style References**: blueprint, data-journalism
- **Visual Style Behavior**: 版面即图纸——深色蓝图纸底，全部结构用单一线色的细线框、引线、尺寸括号与极淡的底纹网格构成，几乎不用实心色块与圆角；原理页让示意图本身充当版式骨架，文字挂在引线端点上，角落留一个图纸标题栏（页码／页名／来源）。数据页换成 data-journalism 的多栏栅格：发丝分隔线、等宽数字、超大英雄数字、页脚来源行，图表是版面的脊柱而不是被框住的插图。全卷只有一个暖色重点色，用来标"当前正在讲的那一件"，其余一律保持低调线条。
- **Theme**: 工程图纸上的活体系统——把两千年的水工原理当成一份仍在使用的施工图来读
- **Tone**: 克制、精确、可复述；不抒情、不用"奇迹/智慧结晶"一类赞叹句撑场

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #0B1B2E | 蓝图纸深底，全卷页面底色 |
| Secondary background | #11263D | 次级区块、侧栏、表格带状底 |
| Primary | #4A90C2 | 图纸线色：所有示意图线框、连接线、分隔线与结构线 |
| Accent | #E8A33D | 唯一暖色重点：当前讲解对象、关键数字、关键路径高亮 |
| Secondary accent | #7FD1C3 | 第二数据系列与对照项（外江／洪水期一侧） |
| Body text | #D6E4F0 | 正文与主要标签 |
| Secondary text | #93AEC8 | 注记、图例、来源行、次级说明 |
| Divider | #1E3A57 | 发丝分隔线、表格框线、栅格边界 |
| Surface | #16314C | 面板抬升：数据页卡片与侧栏面板 |
| Grid | #17304A | 图纸底纹网格线（比 Divider 更弱） |

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 刚直黑体：中国工程图纸标题栏的字面性格，端正、笔画等粗、无修饰 | SimHei | Consolas | sans-serif |
| Body | 人文无衬线，深底上笔画稳定不糊 | Microsoft YaHei | Consolas | sans-serif |
| Display | 与标题同族，用于超大英雄数字与章节数字，拉丁数字走等宽以对齐 | SimHei | Consolas | sans-serif |
| Annotation | 与正文同族的小号注记，图例／引线标签／图表刻度 | Microsoft YaHei | Consolas | sans-serif |
| Footnote | 与正文同族的最小号，来源行与页码 | Microsoft YaHei | Consolas | sans-serif |
| Lead | 与正文同族的导语，页面首段判断句 | Microsoft YaHei | Consolas | sans-serif |

- **Title stack**: SimHei, Consolas, sans-serif
- **Body stack**: Microsoft YaHei, Consolas, sans-serif
- **Display stack**: SimHei, Consolas, sans-serif
- **Annotation stack**: Microsoft YaHei, Consolas, sans-serif
- **Footnote stack**: Microsoft YaHei, Consolas, sans-serif
- **Lead stack**: Microsoft YaHei, Consolas, sans-serif
- **Role rationale**: Display／Annotation／Footnote／Lead 四个角色在全卷反复出现（英雄数字 5 页、引线注记 6 页、来源行 14 页、导语句 9 页），各自需要一个固定锚点，不依赖执行期的显示例外；四者不引入新字体族，只固定字号与栈。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 42 |
| Subtitle | 32 |
| Annotation | 18 |
| Cover title | 88 |
| Chapter title | 56 |
| Lead | 30 |
| Display | 72 |
| Footnote | 16 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 先读左上角的判断句标题，再进入画面中部的图纸主体，最后沿引线落到右侧或下方的注记与数字；来源行始终在页脚最后被读到
- **Composition tendency**: 原理页让示意图占据整页并充当骨架，文字挂在引线端点；数据页改用多栏栅格，图表横跨主栏、注记退到侧栏；章节与结语页让大留白与一条贯通的水平基线承担全部结构
- **Cross-page continuity**: 岷江水道的那条带状轮廓是全卷母题——封面、总图、三张原理页、合拢页反复出现同一条河道轮廓，只改变取景与高亮位置；角落的图纸标题栏（页码／页名／来源）逐页保留
- **Spacing posture**: variable by page rhythm — 原理页与数据页偏紧凑，章节与口诀页大幅留白
- **Spacing anchors**: page margin 72 px；block gap 32 px；column gutter 40 px；corner radius 2 px；body leading 38 px

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2

| Icon Path | Suitable Scenarios |
| --- | --- |
| icons/tabler-outline/droplet.svg | 水量、供水、用水口径 |
| icons/tabler-outline/mountain.svg | 玉垒山、出山口、地形落差 |
| icons/tabler-outline/arrows-split.svg | 分水、内外江分流 |
| icons/tabler-outline/ripple.svg | 弯道环流、水面 |
| icons/tabler-outline/ruler-measure.svg | 尺寸、水则、堰高口宽 |
| icons/tabler-outline/calendar-repeat.svg | 岁修、年度重复的维护动作 |
| icons/tabler-outline/award.svg | 世界遗产、名录 |
| icons/tabler-outline/wheat.svg | 灌溉农田、水稻、粮食产能 |
| icons/tabler-outline/alert-triangle.svg | 洪灾、旱情、风险 |
| icons/tabler-outline/chart-line.svg | 趋势、历史演变 |
| icons/tabler-outline/map-pin.svg | 地点、覆盖市县 |
| icons/tabler-outline/topology-star.svg | 渠系网络、灌区结构 |
| icons/tabler-outline/wave-sine.svg | 水流、流量变化 |
| icons/tabler-outline/history.svg | 年代、时间线 |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P05 | chart | stacked_bar_chart | 对比枯水期与洪水期内江／外江的分水比例 |
| P11 | chart | line_chart | 展示灌溉面积在选定里程碑年份上的增长 |
| P12 | table | record_table | 列出灌区渠系分级的条数与长度 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| dujiangyan_weir_aerial.jpg | 1280×720 | 16:9 | 封面的实地锚点：让读者先确认这是一处真实存在、今天仍在运转的场所 | Photo | 满幅铺底，压暗后让标题落在江面较暗的一侧，河道走向与全卷的水道母题对齐 | adaptive | web | Sourced | 都江堰渠首鱼嘴分水处的俯瞰实景，岷江被分为内外两江的河道形态清晰可辨；白天、无人物特写；画面一侧留出较暗的安静区以承载标题 | none | hero_page |
| dujiangyan_channel_scene.jpg | 1280×720 | 16:9 | 口诀页的呼吸面：把六字诀放回真实的河道与堰体上 | Photo | 满幅铺底并整体压暗，引言文字居中悬浮，画面本身不承担信息 | adaptive | web | Sourced | 都江堰渠首堰体或内江渠道的地面实景，可见卵石河床与堰体线条；构图平静、中部留白，便于叠加引言 | none | local |

## IX. Content Outline

### Part 1: 问题

#### Slide 01 - 封面：一座还在上班的两千岁工程

- **Audience move**: 从"都江堰是个古迹景点"→"它是今天仍在配水的基础设施"
- **Relationships**: 建成年份与今日供水规模两个事实构成 contrast（时间跨度对比）；两者共同 link 到标题判断
- **Composition**: 满幅实景压暗铺底，主标题压在江面暗部；副标题与年份带沿底部一条贯通细线排开
- **Cover impact**: 钩子（binding）——"公元前 256 年动工的工程，2025 年仍在为 1164.7 万亩农田配水"
- **Title**: 都江堰：一座还在上班的两千岁工程
- **Core message**: 都江堰不是遗址，它今天仍在运行
- **Content**: 主标题 · 副标题一句（把"两千年"与"今年的灌面数字"并置） · 年份带：公元前 256 年 — 2025 年 · 页脚来源行
- **Images**: 使用 dujiangyan_weir_aerial.jpg 作满幅底图；若该资源最终不可得，改为原生 SVG 绘制的岷江分水河道轮廓作封面钩子
- **Motion suggestion**: 标题与年份带依次进入；年份带右端的"2025"是 P02 的延续单元，作为 Morph 候选
- **Fact IDs**: F001, F022

#### Slide 02 - 本讲的四段路（整理）

- **Audience move**: 从"不知道要听什么"→"知道接下来按问题—机制—制度—现状四段走"
- **Relationships**: 四个段落构成 order（讲解顺序），每段与其对应页码 link
- **Composition**: 左侧一列超大编号，右侧四行段名与一句话说明，一条竖直细线把两者串起来
- **Title**: 本讲的四段路
- **Core message**: 先看它要解决什么问题，再看它怎么工作，然后看它为什么没坏，最后看它今天在做什么
- **Content**: 页面标注"整理" · 01 为什么要修：成都平原的涝旱之困 · 02 它怎么工作：分水—排沙—引水三件一套 · 03 它为什么能活两千年：口诀与岁修 · 04 它今天在做什么：全国第一大灌区
- **Motion suggestion**: 四行按 order 依次进入；每行的说明文字排在该行编号与段名之后
- **Fact IDs**: —

#### Slide 03 - 问题：一条出山就发脾气的江

- **Audience move**: 从"不知道为什么非修不可"→"理解涝与旱同时存在，且根源是地形"
- **Relationships**: 地形落差（parent）导致汛期急流与东旱西涝两个后果（membership）；两个后果之间是 contrast
- **Composition**: 整页一张纵剖面示意：左高右低，岷江自玉垒山口跌入成都平原；落差与距离用尺寸括号标出，两侧分别挂"涝"与"旱"的注记
- **Title**: 一条出山就发脾气的江
- **Core message**: 都江堰要同时解决两件相反的事——汛期太多水，枯期太少水
- **Content**: 导语句：问题不是水少，是水来得不是时候 · 纵剖面注记：都江堰市距成都市区 50 公里，海拔落差 273 米 · 汛期：江水顺势而下、水流湍急，易成灾害 · 玉垒山阻隔造成东旱西涝 · 页脚来源行
- **Visualization**: 纵剖面为定性结构示意，非数据图表，不设 Native-ready 键
- **Motion suggestion**: 先出剖面地形轮廓，再出江水带，最后两侧注记进入；注记必须排在地形与水带之后
- **Fact IDs**: F019, F002

### Part 2: 机制

#### Slide 04 - 分水—排沙—引水：三件一套（整理）

- **Audience move**: 从"三个名字记不住"→"知道三件在河道上的位置与先后关系"
- **Relationships**: 鱼嘴、飞沙堰、宝瓶口三者构成 order（水流经过的先后）并同属渠首枢纽（membership）
- **Composition**: 整页一张俯视总图：岷江河道自上而下贯穿画面，三处工程按真实相对位置用编号圆点标出，引线拉到画面右侧的三行短说明
- **Title**: 分水—排沙—引水：三件一套
- **Core message**: 三件工程按水流顺序排在同一条河道上，各管一件事
- **Content**: 页面标注"整理" · ① 鱼嘴：把岷江分成内外两江 · ② 飞沙堰：把多余的水和沙送回外江 · ③ 宝瓶口：控制进入成都平原的水量 · 一句话：渠首位于海拔 726 米、距都江堰市 1 公里，是成都平原的最高点 · 页脚来源行
- **Visualization**: 俯视总图为定性结构示意，不设 Native-ready 键
- **Motion suggestion**: 河道轮廓先出，三个编号圆点按 order 依次点亮，引线说明跟在各自圆点之后；河道轮廓与①号鱼嘴标记是 P05 的延续单元，作为 Morph 候选
- **Fact IDs**: F003, F011

#### Slide 05 - 鱼嘴：把一条江分成会看季节的两条

- **Audience move**: 从"知道鱼嘴分水"→"知道它按季节分成不同比例，且这是靠形状而不是靠闸门做到的"
- **Relationships**: 枯水期与洪水期两种工况构成 contrast；每种工况下内江与外江的占比构成 membership（合计为一）
- **Composition**: 左侧放大的鱼嘴局部图纸（从上一页总图放大而来），右侧一组分水比例图表；一句机制判断压在两者之上
- **Title**: 鱼嘴：把一条江分成会看季节的两条
- **Core message**: 鱼嘴的作用是"平旱潦，分四六"——枯水期把六成水留给灌区，洪水期把六成水推给外江
- **Content**: 导语句：它不靠闸门，靠河床与堤形 · 枯水期：内江约占六成，保证灌溉 · 洪水期：外江约占六成，减轻洪灾 · 注记：这一分配随水位自动改变，无人工调节动作
- **Visualization**: 分水比例堆叠条形图（key：`flow-split-ratio`），两根条分别为枯水期与洪水期，每根按内江／外江两段构成；Native-ready `flow-split-ratio=yes`
- **Motion suggestion**: 鱼嘴局部图先到位（承接上一页总图的同一形体），随后两根比例条按 contrast 顺序出现，读法注记排在条形之后
- **Fact IDs**: F004, F003

#### Slide 06 - 飞沙堰：让弯道替人排沙

- **Audience move**: 从"以为排沙靠挖"→"理解排沙是弯道水流自己完成的"
- **Relationships**: 内江弯道（parent）产生环流，环流与溢流两个动作 link 到同一处堰体；水与沙的去向构成 overlap（同一道堰同时排两样东西）
- **Composition**: 整页一张弯道局部图纸：内江在此处转弯，堰体位于凸岸一侧；环流用一组弧形箭头表示，堰顶高程用尺寸线标出
- **Title**: 飞沙堰：让弯道替人排沙
- **Core message**: 水一转弯就会自己把沙甩向堰口，多余的水和沙从这里回到外江
- **Content**: 导语句：这道堰的本事在"低" · 堰口宽 240 米，堰坝高出河床 2 米 · 内江水量超过宝瓶口能吃下的量时，多余的水自堰顶溢出 · 全卷原理一句话：凹岸取水、凸岸排沙 · 注记：拦引春水、排泄洪水、排砂石三件事由同一道堰完成
- **Visualization**: 弯道环流为定性结构示意，不设 Native-ready 键
- **Motion suggestion**: 先出弯道河道与堰体轮廓，再出环流箭头，最后出尺寸标注与注记；尺寸与注记必须排在几何之后
- **Fact IDs**: F006, F005

#### Slide 07 - 宝瓶口：一道不会关上的闸门

- **Audience move**: 从"以为宝瓶口只是入水口"→"理解狭窄断面本身就是限流装置"
- **Relationships**: 断面宽度（parent）决定进水上限；水则刻度与进水量 link（可读的测量与被控制的量）
- **Composition**: 左侧宝瓶口正面剖口图纸，口宽用尺寸括号标注；右侧一列水则刻度作为竖向标尺，与剖口等高对齐
- **Title**: 宝瓶口：一道不会关上的闸门
- **Core message**: 它靠断面狭窄天然限流——进得来多少水，是形状决定的，不是人决定的
- **Content**: 导语句：没有闸门，所以永远不会忘记开关 · 内江灌区总进水口，平均口宽 20 米 · 过水断面狭窄，具有天然节制闸的作用 · 左岸石壁刻有"水则"二十四划，每划一市尺（1/3 米），用以观测水位涨落 · 注记：多出来的水由上一页的飞沙堰处理
- **Visualization**: 剖口与水则标尺为定性结构示意，不设 Native-ready 键
- **Motion suggestion**: 剖口轮廓先出，尺寸括号随后，水则刻度自下而上依次点亮，说明文字排在刻度之后；剖口轮廓是 P08 总图中同一形体的延续，作为 Morph 候选
- **Fact IDs**: F007, F008

#### Slide 08 - 一次洪水里，三件工程的动作顺序（整理）

- **Audience move**: 从"分别记住三件"→"能按顺序复述一次完整的分水—排沙—限流过程"
- **Relationships**: 三个动作构成 order（时间先后），三者共同 link 到同一次洪水事件
- **Composition**: 回到第四页的同一张俯视总图，画面不变，只按顺序点亮三处并在旁标出该步动作
- **Title**: 一次洪水里，三件工程的动作顺序
- **Core message**: 三件工程不是三个景点，是一条流水线上的三道工序
- **Content**: 页面标注"整理" · 第一步 鱼嘴：洪水期把约六成水推入外江 · 第二步 飞沙堰：内江多余的水与泥沙从堰顶溢回外江 · 第三步 宝瓶口：狭窄断面把进入成都平原的水量压在上限之内 · 收束句：分流分沙、泄洪排沙、限洪引水，三件相辅相成
- **Visualization**: 与 P04 同一张总图，不设 Native-ready 键
- **Motion suggestion**: 总图形体承接 P07 的宝瓶口剖口回到总图位置（Morph 候选），随后三步按 order 依次点亮，每步说明排在该步高亮之后
- **Fact IDs**: F005, F004

### Part 3: 制度

#### Slide 09 - 六个字，管了两千年

- **Audience move**: 从"以为靠工程本身"→"意识到维护规则被写成了可背诵的口诀"
- **Relationships**: 六字诀与八字真言构成 membership（同属传下来的维护规则）；两者与岁修动作 link
- **Composition**: 满幅实景压暗，引言居中大字悬浮，下方一行小字给出两句口诀的现代读法
- **Title**: 六个字，管了两千年
- **Core message**: 都江堰把"怎么维护"写成了能背下来的六个字，而不是留在图纸里
- **Content**: 引言大字："深淘滩，低作堰" · 第二句："逢正抽心，遇弯截角" · 一行读法：滩要淘到规定深度，堰不能筑高——高了就挡住洪水与泥沙的出路 · 注记：这两句作为遗迹保存至今，"深淘滩，低作堰"镶嵌于二王庙石壁
- **Images**: 使用 dujiangyan_channel_scene.jpg 作满幅底图；若不可得，改为原生 SVG 的深色河床纹理面作为呼吸页底
- **Motion suggestion**: 六字先出并停留，第二句随后，读法与注记最后进入
- **Fact IDs**: F009

#### Slide 10 - 岁修：把维护变成每年都要做的事

- **Audience move**: 从"以为它两千年没动过"→"理解它一直在被重修，制度才是长寿的原因"
- **Relationships**: 制度确立与历次改建构成 order（时间序）；历次改建同属"鱼嘴的重建史"（membership）；2008 年地震的结果与全序列 link（制度有效性的验证）
- **Composition**: 一条贯通画面的水平时间基线，节点向上下交替挂出年份与事件；右端单独留出地震一项作为验证点
- **Title**: 岁修：把维护变成每年都要做的事
- **Core message**: 工程能活两千年，不是因为它没坏，而是因为修它这件事被写进了制度
- **Content**: 页面标注"整理" · 宋代：岁修成为定制 · 1936 年：现鱼嘴始建 · 1974 年：修建外江闸时以混凝土和浆砌卵石覆盖加固 · 2002 年冬修：以钢筋混凝土加固基础 · 验证点 2008 年 5 月 12 日四川地震：都江堰水利工程基本未受损坏
- **Visualization**: 时间线为定性结构示意，不设 Native-ready 键
- **Motion suggestion**: 时间基线先贯通，节点按 order 依次出现，每个节点的说明排在该节点之后；末端的地震验证点最后单独进入
- **Fact IDs**: F010, F014

### Part 4: 今天

#### Slide 11 - 灌溉面积：一条走了两千年的上升线（整理）

- **Audience move**: 从"知道它还在用"→"看见它的服务规模一直在扩大，并且最近几年仍在增长"
- **Relationships**: 各里程碑的灌溉面积构成 order（时间序）且共同构成一条 link（同一指标的连续演变）
- **Composition**: 折线横跨主栏充当版面脊柱，左侧留一列侧栏放口径说明；右端的最新数字放大为英雄数字
- **Title**: 灌溉面积：一条走了两千年的上升线
- **Core message**: 从建成之初约 100 万亩到 2025 年计划 1164.7 万亩，这条线到今天还在往上走
- **Content**: 页面标注"整理" · 折线节点：建成之初约 100 万亩 · 1949 年前 280 万亩 · 2018 年 1076 万亩 · 2021 年 1090.6 万亩 · 2023 年 1133.2 万亩 · 2024 年 1154.8 万亩 · 2025 年计划 1164.7 万亩 · 英雄数字：1164.7 万亩 · 口径注记：横轴为选取的里程碑年份，非等距时间轴；2025 年为计划用水面积，其余为当年灌溉面积 · 页脚来源行
- **Visualization**: 里程碑折线图（key：`irrigated-area-growth`），单系列，横轴为 7 个里程碑标签；Native-ready `irrigated-area-growth=yes`
- **Motion suggestion**: 坐标与刻度先出，折线自左向右生长，英雄数字在折线到达右端后出现，口径注记最后进入；右端的"1164.7"是 P12 的延续单元，作为 Morph 候选
- **Fact IDs**: F017, F018, F020, F022
- **Native-ready**: irrigated-area-growth=yes

#### Slide 12 - 今天的都江堰灌区：全国第一大

- **Audience move**: 从"一个抽象的大数字"→"知道这套系统覆盖多少人、多少地、由多长的渠道构成"
- **Relationships**: 覆盖规模、粮食任务、渠系构成三组事实同属"今天的灌区"（membership）；渠系三级之间是 parent（干渠—支渠—末级渠道）
- **Composition**: 上部一排英雄数字带（覆盖市县／常住人口／水稻保栽面积），下部渠系分级表格横跨主栏，侧栏放智慧化管理的补充事实
- **Title**: 今天的都江堰灌区：全国第一大
- **Core message**: 它今天供的是 8 市 41 县、3142 万常住人口的生产生活用水，不只是农田
- **Content**: 英雄数字：8 市 41 县（市、区）· 3142 万常住人口 · 605 万亩水稻保栽面积（2025 年计划）· 渠系分级表：干渠及分干渠 111 条／3567 公里；万亩以上支渠 268 条／3354 公里；支渠以下各级末级渠道／3.5 万余公里（2018 年数据）· 侧栏：2025 年首次向川南经济区供水，计划全年向资中县供水 1044 万立方米 · 侧栏：关键控制断面 1264 处计量设施、293 处闸门自动化改造 · 页脚来源行
- **Visualization**: 渠系分级表格（key：`canal-network`），三行记录、三列（渠系层级／条数／长度）；Native-ready `canal-network=yes`
- **Motion suggestion**: 英雄数字带先进入（承接上一页的 1164.7 数字，Morph 候选），表格逐行出现，侧栏补充事实排在表格之后
- **Fact IDs**: F022, F023, F024, F027, F026
- **Native-ready**: canal-network=yes

#### Slide 13 - 两块牌子：2000 与 2018

- **Audience move**: 从"知道它是世界遗产"→"知道是哪两块牌子、分别由谁在哪一年授予、依据是什么"
- **Relationships**: 两项遗产构成 order（授予时间先后）并与同一处工程 link；两者的授予机构与依据构成 contrast
- **Composition**: 左右两栏对称的图纸标题栏式卡片，每栏一块牌子；中间一条竖直细线分隔，底部一行把两者与 2006 年那项并列成"三个世界遗产"
- **Title**: 两块牌子：2000 与 2018
- **Core message**: 一块认的是它的历史价值，另一块认的是它今天仍在灌溉
- **Content**: 左栏 2000 年：青城山—都江堰列入联合国教科文组织《世界遗产名录》（编号 1001），依据文化遗产标准 (ii)(iv)(vi)；标准 (ii) 评语称它是水管理与技术发展史上的重大里程碑，至今仍在完美履行其功能 · 右栏 2018 年：8 月 13 日晚（加拿大时间）在加拿大萨斯卡通召开的国际灌溉排水委员会第 69 届国际执行理事会上列入世界灌溉工程遗产名录 · 底行：连同 2006 年的世界自然遗产"四川大熊猫栖息地"重要组成部分，都江堰成为全球为数不多同时拥有 3 个世界遗产的城市
- **Motion suggestion**: 左栏先出，右栏随后（按授予年份 order），底行并列句最后进入
- **Fact IDs**: F012, F013, F015, F016

#### Slide 14 - 它给出的答案不是更高的坝

- **Audience move**: 从"记住了一批数字"→"带走一句能复述的判断"
- **Relationships**: 顺势布置（工程侧）与岁修制度（管理侧）两条原因 link 到同一个结果——两千年仍在运行
- **Composition**: 大留白，一条贯通的水平基线把画面分成上下两部分：上部是收束判断，下部一行并列两条原因；页脚给出完整来源列表
- **Closing impact**: 收束判断（binding）——都江堰给出的答案不是更高的坝，而是把顺应水势的做法固定成每年都要做的事
- **Title**: 它给出的答案不是更高的坝
- **Core message**: 无坝引水加上写进制度的岁修，才是这套系统活到今天的原因
- **Content**: 收束判断句 · 原因一（工程侧）：利用地形与河湾水流，凹岸取水、凸岸排沙，不靠拦河坝 · 原因二（管理侧）：岁修自宋代成为定制，维护动作被写成可背诵的规则 · 结果行：2025 年计划用水面积 1164.7 万亩，覆盖 8 市 41 县 · 来源列表：联合国教科文组织世界遗产中心、水利文明网、人民网、中国新闻网、四川在线、中国水利网（检索日期 2026-09-12）
- **Motion suggestion**: 收束判断先出，两条原因并列进入，结果行与来源列表最后
- **Fact IDs**: F011, F005, F010, F022, F023

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 每页备注以该页最终 SVG 上真实存在的元素为准展开：先给主讲人一句过渡，再解释页面上的图形在说什么，最后补充页面没有写下的背景（如"无坝引水"为何区别于拦河坝、四六分水为何随水位自动改变）。所有外部事实只引用 `sources/dujiangyan_research.facts.json` 中已有的 fact_id，不引入新数字；自建框架页在备注中明确说明"这一分段是整理出来的讲解顺序，不是史料原有分法"。
- **Total duration**: 15–18 分钟（14 页，平均每页约 70 秒）
- **Notes style**: 讲解式口语，短句为主，可直接照读
- **Presentation purpose**: 先解释三大主体工程如何分水、排沙、引水，再说明它为何能运行两千余年，最后用今天的灌区数据收束"它还在运行"这一判断
