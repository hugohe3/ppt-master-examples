<!-- ppt-master-schema: design-spec/v1 -->
# tea_six_classes_a4 - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | tea_six_classes_a4 |
| Canvas Format | A4 Print (1240×1754) |
| Page Count | 9 |
| Primary Language | zh-CN |
| Target Audience | 天天喝茶但没系统学过茶的普通读者——办公室泡茶的人、刚开始买茶的人；知道龙井铁观音的名字，但说不清它们凭什么分成不同的类 |
| Communication Intent | 先教会一条判据（茶类由加工工艺决定，不由颜色或产地决定），再把六类逐一讲清；最后让读者能拿着这页纸当场泡对一杯。教学优先于罗列，可查优先于好看 |
| Desired Audience Outcome | 读者能说出六类的分类依据，指着任意一类说出它的关键工序和一两个代表茶，并按页上的水温与时间泡出一杯不苦不淡的茶 |
| Core Message / Ask / Action | 六大茶类不是按颜色分的，是按工艺（尤其氧化/发酵程度）分的——记住工序，就记住了茶 |
| Delivery Context | 读者自持的印刷单页，无讲述者；每页能单独打印夹进本子，也可整册翻阅 |
| Artifact Afterlife | 长期查阅、反复打印、逐页拆用；来源需可回溯核对 |
| Reading Mode | text |
| Content Strategy | balanced（默认）——研究补充件是唯一事实来源，页面按教学顺序重新组织；未取得来源的条目写 NO DATA，冲突条目两说并列 |
| Design Style | ink-notes 手写墨线 × instructional 教学分解：近单色黑墨线承担全部结构，每类只给一个语义色（该类汤色），无纸纹、无投影、无渐变 |
| AI Image Acquisition Path | auto（Path A：image_gen.py --manifest，后端按仓库 .env 解析为 gemini） |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 工作流默认；本页为读者自持印刷物，注记写成"这页怎么用/怎么讲"的补充说明 |
| Custom Animations | enabled — 最终 Stage-2 主动建议：轴与工序链在相邻页之间是同一张地图的不同可见状态，需要 Morph 与逐条入场承担顺序 |
| Narration Audio | disabled — 最终 Stage-2 主动建议 |
| Created Date | 2026-09-04 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | A4 Print |
| Dimensions | 1240 × 1754 |
| viewBox | `0 0 1240 1754` |
| Margins | 上下左右各 72px |
| Content Area | x 72–1168，y 72–1682（1096 × 1610） |

## III. Visual Theme

### Theme Style

- **Mode**: instructional
- **Visual style**: ink-notes
- **Theme**: 一本摊开的手写茶记——墨线画结构，色只用来指认汤色。整册靠一条"发酵度轴"贯穿：封面预告它，总览页画全它，六个类页各取它的一段放大
- **Tone**: 克制、笃定、可照做；像一位讲得清楚的老师在纸上边写边画，不像商业图表

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #FAF9F5 | 纸白页面底色，无纹理 |
| Secondary background | #F0EDE4 | 极少量的浅块底，用于参数区分栏 |
| Primary | #1C1A17 | 墨色：全部线条、框、箭头、题头 |
| Accent | #A62F1F | 主强调（红茶汤色）：轴的高发酵端、重点标记 |
| Secondary accent | #6E9B3A | 次强调（绿茶汤色）：轴的低发酵端、正向标记 |
| Body text | #1C1A17 | 正文墨色 |
| Secondary text | #6B665C | 注释、脚注、来源行 |
| Divider | #C9C3B4 | 细分隔线、表格细线 |
| Tea green | #6E9B3A | 绿茶语义色（汤色嫩绿明亮） |
| Tea white | #D6C079 | 白茶页标识色（页面识别用，非审评汤色；白茶汤色为 NO DATA） |
| Tea yellow | #D9A526 | 黄茶语义色（黄叶黄汤 / 橙黄明净） |
| Tea oolong | #B5761B | 青茶语义色（金黄；整类通用汤色为 NO DATA，取单品描述） |
| Tea red | #A62F1F | 红茶语义色（汤色红艳明亮） |
| Tea dark | #5A3B26 | 黑茶语义色（随氧化加深的深褐） |

### AI Image Strategy

- **Image Rendering**: ink-notes
- **Visual**: 纯净纸场上的黑墨线小图与手写题字：中锋起落有轻微抖动的单色线条，无填色块、无投影、无渐变，形体靠线的疏密与顿挫立起来
- **Mood**: 像一位茶人在白纸上用秀丽笔随手写画的备忘——克制、笃定、有手的温度；接近 Mike Rohde 视觉笔记落在中文茶记本上的样子

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 楷体骨架，手写而克制，承担 ink-notes 要求的手写题头字性 | KaiTi | Georgia | KaiTi |
| Body | 无衬线，笔画均匀，打印小字仍清楚 | Microsoft YaHei | Segoe UI | Microsoft YaHei |
| Display | 与题头同源的放大字，用于封面主字与类页大类名的原生可编辑层 | KaiTi | Georgia | KaiTi |
| Data | 等高数字，温度与时间必须对齐可比 | Times New Roman | Times New Roman | Times New Roman |

- **Title stack**: KaiTi
- **Body stack**: Microsoft YaHei
- **Display stack**: KaiTi
- **Data stack**: Times New Roman
- **Role rationale**: Data 单独立族，因为水温与时间在六页上重复出现且需要等高数字对齐比较；Display 与 Title 同族但尺寸差异达一个量级，单列锚点避免大字落进 Title 的 ±2px 带。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 46 |
| Title | 84 |
| Subtitle | 60 |
| Annotation | 34 |
| Display | 156 |
| Lead | 54 |
| Data | 68 |
| Footnote | 26 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 先看到大类名与它在轴上的位置，再看工序链，再看参数，最后看那句怎么挑；视线自上而下但每页有一处偏心的焦点，避免六页同构
- **Composition tendency**: 每页换一种 ink-notes 构图语汇——圆心概念加分支箭头、大括号归组、划掉重写、轴段放大、贯穿流线、层叠堆——不做"上题字下三行"的重复排版
- **Cross-page continuity**: 发酵度轴是唯一贯穿母题：封面给它一个淡预告，P02 画全，六个类页各在页眉带一段同位置的轴并高亮本类节点；类名题字与语义色圆点在总览与类页之间保持同一对应
- **Spacing posture**: 大面积留白（ink-notes 的空场是风格本身），信息密度靠线的疏密而不是填满
- **Spacing anchors**: 页边距 72px；块间距 40px；分栏间距 48px；圆角 6px；正文行高 70px

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2

| Icon Path | Suitable Scenarios |
| --- | --- |
| tabler-outline/temperature | 水温 |
| tabler-outline/clock | 冲泡与出汤时间 |
| tabler-outline/droplet | 汤色 |
| tabler-outline/leaf | 鲜叶与工序起点 |
| tabler-outline/flame | 杀青、烘焙等火工工序 |
| tabler-outline/arrow-narrow-right | 工序链方向 |
| tabler-outline/star | 代表茶标记 |
| tabler-outline/bulb | 怎么挑的一句提示 |
| tabler-outline/alert-triangle | 冲突两说与 NO DATA 提示 |
| tabler-outline/link | 来源页链接标记 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| leaf_green.png | 242×276 | 121:138 | 绿茶叶态标识 | Illustrated icon | 与大类名题字并置，做该页的身份记号 | no-crop | slice | Generated | Derived from tea_elements_sheet.png 的第 1 格 | none | local |
| leaf_white.png | 212×282 | 106:141 | 白茶叶态标识 | Illustrated icon | 与大类名题字并置，做该页的身份记号 | no-crop | slice | Generated | Derived from tea_elements_sheet.png 的第 2 格 | none | local |
| leaf_yellow.png | 198×240 | 33:40 | 黄茶叶态标识 | Illustrated icon | 与大类名题字并置，做该页的身份记号 | no-crop | slice | Generated | Derived from tea_elements_sheet.png 的第 3 格 | none | local |
| leaf_oolong.png | 259×234 | 259:234 | 青茶叶态标识 | Illustrated icon | 与大类名题字并置，做该页的身份记号 | no-crop | slice | Generated | Derived from tea_elements_sheet.png 的第 4 格 | none | local |
| leaf_red.png | 294×233 | 294:233 | 红茶叶态标识 | Illustrated icon | 与大类名题字并置，做该页的身份记号 | no-crop | slice | Generated | Derived from tea_elements_sheet.png 的第 5 格 | none | local |
| leaf_dark.png | 267×221 | 267:221 | 黑茶叶态标识 | Illustrated icon | 与大类名题字并置，做该页的身份记号 | no-crop | slice | Generated | Derived from tea_elements_sheet.png 的第 6 格 | none | local |
| ware_gaiwan.png | 274×260 | 137:130 | 盖碗器物元素 | Illustrated icon | 落在参数区旁，指认"用盖碗工夫冲泡"这一档 | no-crop | slice | Generated | Derived from tea_elements_sheet.png 的第 7 格 | none | local |
| ware_kettle.png | 291×287 | 291:287 | 执壶器物元素 | Illustrated icon | 落在水温标注旁 | no-crop | slice | Generated | Derived from tea_elements_sheet.png 的第 8 格 | none | local |
| ware_cup.png | 207×202 | 207:202 | 品茗杯器物元素 | Illustrated icon | 封面与来源页的收尾小记号 | no-crop | slice | Generated | Derived from tea_elements_sheet.png 的第 9 格 | none | local |
| word_green.png | 441×238 | 63:34 | 绿茶类名题字 | Illustrated icon | 作大类名的显示层，原生标题另置一行 | no-crop | slice | Generated | Derived from tea_lettering_sheet.png 的第 1 格；精确字串「绿茶」 | embedded | local |
| word_white.png | 412×237 | 412:237 | 白茶类名题字 | Illustrated icon | 作大类名的显示层，原生标题另置一行 | no-crop | slice | Generated | Derived from tea_lettering_sheet.png 的第 2 格；精确字串「白茶」 | embedded | local |
| word_yellow.png | 437×236 | 437:236 | 黄茶类名题字 | Illustrated icon | 作大类名的显示层，原生标题另置一行 | no-crop | slice | Generated | Derived from tea_lettering_sheet.png 的第 3 格；精确字串「黄茶」 | embedded | local |
| word_oolong.png | 432×250 | 216:125 | 青茶类名题字 | Illustrated icon | 作大类名的显示层，原生标题另置一行 | no-crop | slice | Generated | Derived from tea_lettering_sheet.png 的第 4 格；精确字串「青茶」 | embedded | local |
| word_red.png | 432×231 | 144:77 | 红茶类名题字 | Illustrated icon | 作大类名的显示层，原生标题另置一行 | no-crop | slice | Generated | Derived from tea_lettering_sheet.png 的第 5 格；精确字串「红茶」 | embedded | local |
| word_dark.png | 418×231 | 38:21 | 黑茶类名题字 | Illustrated icon | 作大类名的显示层，原生标题另置一行 | no-crop | slice | Generated | Derived from tea_lettering_sheet.png 的第 6 格；精确字串「黑茶」 | embedded | local |

## IX. Content Outline

### Part 1: 一条判据

#### Slide 01 - 封面：颜色不决定茶类

- **Audience move**: 以为六大类按茶叶颜色或产地划分 → 知道判据只有一条，是加工工艺
- **Relationships**: 主张（工艺决定茶类）与六个类名之间是 parent；六个类名之间是 order（按发酵度由低到高）
- **Composition**: 主标题偏上左，正下方一条淡墨横轴自左向右贯穿页面，六枚类名题字稀疏落在轴上；右下角一只品茗杯小图收尾；页脚一行使用说明
- **Cover impact**: hook（binding）——"颜色不决定茶类，工艺才决定"；构图为 Reference
- **Title**: 一张纸讲清楚 · 中国茶六大类
- **Core message**: 六大茶类是按加工工艺分的，不是按颜色分的
- **Content**: 大标题与副题 · hook 一句 · 六个类名沿轴排列 · 页脚一行"每页可单独打印"
- **Images**: 六枚类名题字 word_*.png 沿轴排布，尺寸一致；ware_cup.png 作右下收尾
- **Motion suggestion**: 轴线自左向右生长，六枚类名依次落位，建立"顺序"这一后续全册复用的读法
- **Fact IDs**: F001, F003
- **page_rhythm**: anchor

#### Slide 02 - 总览：一条发酵度的轴

- **Audience move**: 记住了判据但不知道六类如何排布 → 能在一条轴上指出任意一类的位置与邻居
- **Relationships**: 六类之间是 order（发酵/氧化程度由低到高：绿 → 白 → 黄 → 青 → 红 → 黑）；每类与其关键工序之间是 link；绿与黑之间是 contrast（不发酵 ↔ 后发酵）
- **Composition**: 一条贯穿全页的粗墨轴占据中部，六个节点等距落在轴上，每节点上方是类名题字与语义色圆点、下方是关键工序词与叶态小图；轴的两端各写一句极短的对照
- **Title**: 六类站在同一条轴上
- **Core message**: 把六类按发酵程度排成一条轴，工序差异就一目了然
- **Content**: 轴的定义（发酵/氧化程度） · 六个节点：绿茶不发酵—杀青 / 白茶微发酵—萎凋 / 黄茶轻发酵—闷黄 / 青茶半发酵—做青 / 红茶全发酵—发酵 / 黑茶后发酵—渥堆 · 两端对照一句 · 注：黑茶的"后发酵"是微生物参与，与前五类的酶促氧化不同
- **Images**: 六枚 leaf_*.png 沿轴等距落在节点下方，同尺寸同基线；六枚 word_*.png 落在节点上方
- **Motion suggestion**: 轴与六个节点先在场，随后由左至右逐个点亮语义色；本页的轴与下一页页眉的轴段是同一对象的两个可见状态
- **Fact IDs**: F001, F003, F004, F005, F006, F008, F009, F010
- **page_rhythm**: dense

### Part 2: 六类各一页

#### Slide 03 - 绿茶：把酶按住

- **Audience move**: 知道绿茶不发酵 → 知道"不发酵"是杀青这一道工序按住了酶，并能按 80–85℃ 泡对
- **Relationships**: 工序之间是 order（摊晾 → 杀青 → 揉捻 → 干燥）；杀青与"不发酵"之间是 link；代表茶与本类之间是 membership
- **Composition**: 圆心概念加分支箭头——"杀青"圈在页面中偏左的圆心里，四条手绘箭头分别指向不发酵、清汤绿叶、鲜爽、易失鲜；工序链作为一条细带压在圆心下方
- **Title**: 绿茶 · 不发酵
- **Core message**: 杀青灭活了酶，氧化被按在起点，所以绿茶是清汤绿叶
- **Content**: 核心工艺：鲜叶—摊晾—杀青—揉捻（做形）—干燥，杀青是分界 · 代表茶：西湖龙井（色绿香郁味甘形美四绝）/ 碧螺春 · 汤色：清汤绿叶，冲泡得当时嫩绿明亮 · 水温与时间：80–85℃；盖碗工夫首泡 12 秒内出汤，碧螺春按 15/20/30/40 秒递进 · 怎么挑：越嫩越怕烫，水一沸就晾一晾再冲
- **Images**: leaf_green.png 与 word_green.png 组成页眉身份记号；ware_kettle.png 落在水温标注旁
- **Motion suggestion**: 页眉轴段自上一页的整轴收拢而来，绿端节点放大为本页焦点
- **Fact IDs**: F003, F004, F011, F012, F020, F027, F031
- **page_rhythm**: dense

#### Slide 04 - 白茶：只做两件事

- **Audience move**: 以为白茶因产地或颜色得名 → 知道它是工序最少的一类，且知道汤色描述缺乏权威来源
- **Relationships**: 两道工序之间是 order（萎凋 → 干燥）；白茶与其余五类之间是 contrast（不炒不揉）；三个品名之间是 membership
- **Composition**: 大括号归组——一个占据页面大半高的手绘大括号把"萎凋"与"干燥"两个词括在一起，括号外只有一句"就这两步"；页面大面积留白，是全册最空的一页
- **Title**: 白茶 · 微发酵
- **Core message**: 不炒不揉，只有萎凋和干燥两步，所以白毫留在了叶表
- **Content**: 核心工艺：只有萎凋和干燥两步 · 代表茶：白毫银针 / 白牡丹 · 外观与汤色：叶表完整保留银毫呈白色；整类汤色的权威表述 NO DATA · 水温与时间：85–90℃（白毫银针 85–95℃，白牡丹 90–100℃）；新白茶前三泡各 10 秒，第四泡 20 秒，第五泡 30 秒，老白茶每泡加 3–5 秒 · 怎么挑：看毫，白毫完整说明萎凋与干燥都没伤到叶
- **Images**: leaf_white.png 与 word_white.png 组成页眉身份记号
- **Motion suggestion**: 大括号自上而下画出，两个工序词随后落位——空场先在，内容后到
- **Fact IDs**: F003, F005, F014, F027, F028, F033
- **page_rhythm**: breathing

#### Slide 05 - 黄茶：在绿茶上多一道

- **Audience move**: 分不清黄茶与绿茶 → 知道黄茶就是绿茶工序里插进一道闷黄，并知道它有两种插法
- **Relationships**: 黄茶工序与绿茶工序之间是 overlap（共用杀青揉捻干燥）；闷黄与"黄叶黄汤"之间是 link；两种闷黄时机之间是 contrast
- **Composition**: 划掉重写——上排照抄绿茶的工序链并用一道手绘斜线划掉，下排重写成插入闷黄的黄茶链，两排之间用一支弯箭头连接；闷黄二字最大最重
- **Title**: 黄茶 · 轻发酵
- **Core message**: 黄茶是在绿茶工艺上加了闷黄这一道，黄叶黄汤由此而来
- **Content**: 核心工艺：在绿茶工艺基础上增加闷黄；闷黄可在杀青后，也可在毛火后 · 代表茶：君山银针 / 蒙顶黄芽 / 霍山黄芽 · 汤色：黄叶黄汤；君山银针汤色橙黄明净，霍山黄芽有外观金黄、叶底嫩黄、汤色黄绿的三黄之称 · 水温与时间：80–85℃；出汤比绿茶稍长两三秒 · 怎么挑：闷黄到位的黄茶不带绿茶的生青气
- **Images**: leaf_yellow.png 与 word_yellow.png 组成页眉身份记号
- **Motion suggestion**: 绿茶链先在场（承接 P03 的同一条链），划掉的斜线画出后，黄茶链在下方重写——两条链是同一对象的前后两个可见状态
- **Fact IDs**: F003, F006, F007, F015, F016, F017, F027, F032
- **page_rhythm**: dense

#### Slide 06 - 青茶：氧化只做一半

- **Audience move**: 把乌龙当作"半红半绿"的模糊说法 → 知道半发酵是一个有跨度的区间，由做青控制
- **Relationships**: 氧化程度是 order（8% → 85% 的连续跨度）；做青与氧化程度之间是 link；青茶与乌龙茶两个名字之间是 link（国标称乌龙茶，传统六类排序称青茶）
- **Composition**: 轴段放大——把总览页那条轴的中段抽出来横贯本页并放大，8% 与 85% 两个刻度写在两端，做青的动作词标在区间上方，代表茶按由轻到重落在区间的不同位置
- **Title**: 青茶（乌龙茶）· 半发酵
- **Core message**: 半发酵不是一个点而是一段区间，做青决定它停在哪里
- **Content**: 核心工艺：萎凋—做青（摇青碰青）—杀青—揉捻做形—干燥；做青是关键，靠时间与温度把氧化停在想要的位置 · 名字：国标 GB/T 30766-2014 称乌龙茶，传统六类排序称青茶，同指一类 · 代表茶：安溪铁观音 / 武夷岩茶（大红袍为四大名丛之一）/ 凤凰单丛（以能天然模拟多种花果香著称） · 汤色：整类通用汤色的权威表述 NO DATA；单品层面如阿里山乌龙被描述为金黄 · 水温与时间：90–95℃（另一说 80–95℃，见来源页）；盖碗出汤 10 秒内起，武夷岩茶按 5/10/20/40 秒递进 · 怎么挑：先问焙火轻重，再问氧化轻重，这两个问题决定它更像绿茶还是更像红茶
- **Images**: leaf_oolong.png 与 word_oolong.png 组成页眉身份记号
- **Motion suggestion**: 轴段自页眉的整轴拉伸放大到页面中部，刻度与代表茶随后落位
- **Fact IDs**: F001, F003, F008, F021, F022, F023, F018, F027, F034, F036
- **page_rhythm**: dense

#### Slide 07 - 红茶：一路氧化到底

- **Audience move**: 只知道红茶"是发酵的" → 知道发酵是一道独立工序，且知道红茶在国际上叫 black tea
- **Relationships**: 工序之间是 order（萎凋 → 揉捻 → 发酵 → 干燥）；发酵工序与汤色红艳之间是 link；代表茶与本类之间是 membership
- **Composition**: 贯穿流线——一条自左上向右下的连续墨线串起四道工序，线旁的汤色圆点由浅到深依次加大，走到右下角变成最深的那一枚
- **Title**: 红茶 · 全发酵
- **Core message**: 发酵是一道独立工序，氧化跑满，汤色就红艳明亮
- **Content**: 核心工艺：鲜叶—萎凋—揉捻—发酵—干燥，发酵是独立的一道而非自然放置 · 代表茶：祁门红茶 / 正山小种 / 滇红 · 汤色：红艳明亮 · 水温与时间：85–90℃（另一说工夫冲泡 95℃、第五泡 100℃，见来源页）；投茶比约 1:30，出汤约 10 秒起，第五泡 15 秒，通常五泡 · 怎么挑：看干茶条索是否紧细乌润，汤面有金圈通常说明发酵到位
- **Images**: leaf_red.png 与 word_red.png 组成页眉身份记号；ware_gaiwan.png 落在参数区旁
- **Motion suggestion**: 流线自左上向右下画出，四枚汤色圆点随线的推进依次加深
- **Fact IDs**: F003, F004, F013, F027, F030
- **page_rhythm**: dense

#### Slide 08 - 黑茶：交给微生物和时间

- **Audience move**: 把黑茶等同于普洱 → 知道它由渥堆的微生物发酵定义，是唯一一类会在成品后继续变化的茶
- **Relationships**: 工序之间是 order（杀青 → 揉捻 → 渥堆 → 干燥）；渥堆与其余五类的酶促氧化之间是 contrast；普洱熟茶、茯砖、六堡之间是 membership
- **Composition**: 层叠堆——三到四层手绘方框自下而上错位叠起代表渥堆的茶堆，一支从堆里升起的箭头写着"数月到数年"，右侧一列是三个代表茶的名字
- **Title**: 黑茶 · 后发酵
- **Core message**: 渥堆把发酵交给微生物，时间成了工序的一部分
- **Content**: 核心工艺：杀青—揉捻—渥堆—干燥；渥堆是温湿环境下的微生物发酵，主要由霉菌完成，可持续数月到数年 · 与前五类的分界：其余五类是茶叶自身酶促氧化，黑茶是微生物参与的后发酵 · 代表茶：普洱熟茶 / 湖南茯砖 / 广西六堡 · 汤色：随氧化加深而变深；红浓等具体审评术语 NO DATA · 水温与时间：95℃；先洗茶，出汤 20 秒内；煮饮比例 1:80–1:100，每次不超过 3 分钟 · 怎么挑：闻干茶不该有仓味与霉味，堆味与霉味是两回事
- **Images**: leaf_dark.png 与 word_dark.png 组成页眉身份记号
- **Motion suggestion**: 方框自下而上逐层叠起，最后那支写着时间的箭头才升起
- **Fact IDs**: F003, F009, F010, F025, F026, F019, F027, F035
- **page_rhythm**: dense

### Part 3: 回到纸上

#### Slide 09 - 来源、冲突与没查到的

- **Audience move**: 拿到一页可照做的参数 → 知道每个数字出自哪里、哪两处有两说、哪三处本页没有权威来源
- **Relationships**: 来源与页码之间是 link；两处冲突条目之间是 contrast；三条 NO DATA 之间是 membership
- **Composition**: 左栏是来源清单（每条一行，链接为可点的原生超链接），右栏窄，上半是两处冲突两说并列、下半是三条 NO DATA；页脚一句收束
- **Closing impact**: 收束一句（binding）——"这页纸只保证：每个数字都能回到它的出处"；构图为 Reference
- **Title**: 这页纸的出处
- **Core message**: 参数可以照做，因为每一条都能回到出处；查不到的地方写着 NO DATA，不猜
- **Content**: 来源清单六条（国标全文公开 / 中国茶叶博物馆空中茶课堂 / 科普中国·人民网制作工艺 / 界面新闻冲泡水温 / 爱普茶网出汤时间 / Wikipedia Oolong 与 Fermented tea） · 两处两说：红茶水温 85–90℃ 与 95℃；青茶水温 90–95℃ 与 80–95℃ · 三条 NO DATA：白茶整类汤色、青茶整类通用汤色、黑茶具体审评术语 · 一句收束
- **Images**: ware_cup.png 落在页脚右侧收尾
- **Motion suggestion**: 来源逐条落位，两说与 NO DATA 后到
- **Fact IDs**: F001, F002, F003, F004, F008, F010, F027, F030, F036
- **page_rhythm**: anchor

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 每页写"这页在教什么、读者最容易在哪里搞错、这页的数字出自哪条 fact"；所有事实取自 `sources/tea_six_classes_research.md` 与其 facts JSON，不得引入页面外的新事实；NO DATA 与两说条目在注记里再说明一次为什么不给单一数字
- **Total duration**: 无口播场景，按逐页阅读补充计，全册约 9–12 分钟
- **Notes style**: 教学口吻，耐心解释，先定义后使用
- **Presentation purpose**: 先教会"茶类由工艺决定"这一条判据，再把六类逐一讲清，最后让读者能按参数泡对一杯
