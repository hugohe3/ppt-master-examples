<!-- ppt-master-schema: design-spec/v1 -->
# 千里江山图·十八岁的青绿 - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | 千里江山图·十八岁的青绿 |
| Canvas Format | PPT 16:9 (1280×720) |
| Page Count | 14 |
| Primary Language | zh-CN |
| Target Audience | 对中国艺术与历史有兴趣的普通文化受众：知道《千里江山图》的名字与"只此青绿"，多数人只在展柜前或屏幕上见过它的一小段，不清楚它是谁画的、怎样画的、为什么难得一见 |
| Communication Intent | 先让人"看见"这幅画（它的长度、颜色、细节），再讲清一个十八岁少年半年成画的故事与它九百年的流转，最后把"珍贵与稀见"落成一个可执行的邀请：下次它打开时去看，并慢慢看 |
| Desired Audience Outcome | 听完能复述三件事：它由十八岁的希孟在半年内画成、颜料是石青石绿层层叠出、2017 年才首次全卷打开；并把"再展出时要去看"记在心里 |
| Core Message / Ask / Action | 一卷近十二米的青绿，是一个十八岁少年半年的功夫，也是九百年里无数双手的接力；它极少打开，值得你等一次、看一次 |
| Delivery Context | 主要为有主讲人的现场分享（文化沙龙 / 读书会 / 讲座，约 15 分钟），页面配合讲述而不是替代讲述；次要为分享后独立翻阅的图文版 |
| Artifact Afterlife | 作为可再次讲述的素材与示例保存；来源页保留出处便于核对 |
| Reading Mode | presentation |
| Content Strategy | balanced（默认）：调研事实为准，叙事顺序自建，引语原文照录 |
| Design Style | 青绿绢本·叙事讲述：narrative 模式承载"熟悉—张力—转折—回望—邀请"的弧线；视觉以 ink-wash 的留白与印章纪律为底，用石青、石绿、赭石三种矿物色替代水墨的近单色，绢本暖底为主场，深青墨场只在张力与收束处出现 |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — final Stage-2 proactive policy (default true) |
| Custom Animations | enabled — final Stage-2 proactive policy: 相邻节拍共享同一张画的不同视窗与同一枚印章，承接关系需要对象级动画表达 |
| Narration Audio | disabled — final Stage-2 proactive policy (default false) |
| Created Date | 2026-09-07 |

- **Template Application**: 采用 narrative-keynote 的讲述方法与页面角色词汇（开场图、熟悉的世界、张力、证据、人物细节、转折、重构、含义、收束、出处），每页只做一个节拍、只留一个主导元素；证据页只放一个数字或一段引文并标注来源；出处页放在收束之后、密而安静。Style 不提供结构与身份，版式、色板、字体均由本项目决定；不使用持续页脚、页码与进度条。

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 72 px 左右，64 px 上下（满版图页可出血） |
| Content Area | x 72–1208，y 64–656 |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: narrative
- **Mode Behavior**: 以 narrative 的"情境—张力—转折—回望—邀请"为唯一骨架：P01–P02 建立熟悉的世界（你见过它，但没看完），P03–P04 收紧张力（46 天、77 个字），P05–P06 用人物与工艺把抽象落地，P07–P08 是画面本身的证据节拍，P09 是最克制的转折（他没有留下名字），P10–P11 回望流转与后人的评价，P12 讲它今天怎样活着，P13 收束为邀请，P14 出处。标题写成推进节拍的句子而非标签；一页一个主导元素。
- **Visual style**: custom
- **Visual Style References**: ink-wash
- **Visual Style Behavior**: 取 ink-wash 的绢纸留白、极少装饰、一枚印章作焦点的纪律，但把近单色水墨换成青绿重彩：石青作主色块与大面积字色，石绿作第二色带，赭石作衬底与暖色过渡，朱砂只在印章与一处强调出现。页面主要用三类载体：出血的画卷视窗（真迹局部）、绢面暖底上的大字与一枚印章、透明底的矿物与画具插画元素；构图靠一条低矮的横向"水平线"（画卷带、细横线或赭石底带）统一节奏，标题大而透气，正文极少；不用卡片网格、不用圆角容器、不用投影，深度靠留白与色块的轻重。文字压在真迹上时用同色系 scrim 或画面本身的安静区域。
- **Theme**: 绢本青绿——暖米绢面为主场，深青墨场为张力与收束，横向长卷视窗与一枚朱砂印章作为贯穿全卷的母题（印章在 P04/P09/P10/P11 之间保持身份、改变位置，承担"谁在这幅画上留下了名字"的连续叙事）
- **Tone**: 静、克制、带一点惊叹；像在展柜前压低声音说话

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #F3ECDA | 绢本暖米，主场底色 |
| Secondary background | #10282C | 深青墨场：封面下缘、张力页、收束页与压字 scrim 的基色 |
| Primary | #2B5C8A | 石青：大字、主色块、标题强调 |
| Accent | #B5382B | 朱砂：印章、唯一强调点，稀少使用 |
| Secondary accent | #3F8F6C | 石绿：第二色带、序列标记、表格表头 |
| Body text | #1F2422 | 墨色正文 |
| Secondary text | #6E675B | 图注、出处、脚注 |
| Divider | #D8CDB2 | 细横线、表格网格线 |

补充稳定角色：`ochre` #A8734A（赭石，底带与过渡）、`surface` #FAF6EC（绢面上的浅一阶面）、`scrim` #10282C（压字层基色，透明度页面局部决定）。

### AI Image Strategy

- **Image Rendering**: custom
- **Image Rendering References**: watercolor
- **Image Rendering Behavior**: 青绿重彩的矿物颜料质感——形体由墨线轻勾轮廓，再以石青、石绿、赭石的颗粒状矿物色层层堆出体积，颜色不透明、有细微颗粒与绢纹，边缘保留一点 watercolor 式的洇开；不用现代插画的平涂与描边，不用真实摄影质感。深度靠颜色饱和度的前后差，不加投影。整体像宋代院体画里的一件器物或一个人物被单独提出来。
- **Visual**: 透明底的矿物原石、颜料碟、毛笔、印章、绢卷与一个伏案的少年，以及"千里江山"四字的瘦金体式题字
- **Mood**: 安静、工致、带宫廷画院的精细感——像故宫修复室的工作台上摆着的几件实物

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 楷书 / 舒展、有书写感 | KaiTi | Times New Roman | serif |
| Body | 现代黑体 / 中性、清晰 | Microsoft YaHei | Arial | sans-serif |
| Display | 楷书 / 巨大的单字或数字 | KaiTi | Times New Roman | serif |
| Quote | 楷书 / 引文与题跋原文 | KaiTi | Times New Roman | serif |
| Annotation | 现代黑体 / 图注、出处 | Microsoft YaHei | Arial | sans-serif |

- **Title stack**: KaiTi, Times New Roman, serif
- **Body stack**: Microsoft YaHei, Arial, sans-serif
- **Display stack**: KaiTi, Times New Roman, serif
- **Quote stack**: KaiTi, Times New Roman, serif
- **Annotation stack**: Microsoft YaHei, Arial, sans-serif
- **Role rationale**: Display 承担 P01/P03/P12 的巨型数字与单词，Quote 承担 P04/P11 的题跋与诗句原文，Annotation 承担所有真迹图注与出处行；三者在全卷反复出现。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 28 |
| Title | 48 |
| Subtitle | 36 |
| Lead | 32 |
| Annotation | 20 |
| Footnote | 16 |
| Display | 120 |
| Quote | 34 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 先看画或大字，再看一行标题，最后才是一两行说明；每页只有一个主导元素
- **Composition tendency**: 横向长卷感——出血的画卷视窗、低矮的横向带、贴近下缘或上缘的标题；大量绢面留白；印章作为不对称的配重
- **Cross-page continuity**: 同一张真迹局部在相邻页只改变视窗（P07→P08）；同一枚印章在 P04/P09/P10/P11 之间保持身份改变位置；图注与出处行的写法全卷一致
- **Spacing posture**: open；张力页与出处页允许更密
- **Spacing anchors**: page margin 72 px；block gap 32 px；column gutter 40 px；corner radius 0 px；body leading 44 px

## VI. Icon Usage Specification

- **Primary bundled library**: none

| Icon Path | Suitable Scenarios |
| --- | --- |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P06 | table | record_table | 五层设色：每层的颜料、矿物来源与作用 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| scroll_start.jpg | 2349x1600 | 1.47:1 | 封面：画卷起首段（含乾隆题诗与钤印）；P11 另取题诗区域局部 | Painting scan | 满版出血作封面场，标题与题字压在画面上方或水面的安静区，下缘深青 scrim 承接说明行 | adaptive | web | Sourced | 维基共享资源公有领域文件 "Wang Ximeng - A Thousand Li of River (Start).jpg"：《千里江山图》卷首段落的高分辨率扫描，青绿山峰与水面，横幅；须是故宫藏原作扫描而非临摹或舞台剧照 | — | — |
| scroll_strip.png | 3840x154 | 24.94:1 | P02：按真实比例横贯页面的整卷细带 | Painting scan | 以真实长宽比横贯整页，作为"你只看过其中一段"的尺子，一枚小括号标出展柜里常见的那一段 | no-crop | web | Sourced | Derived from scroll_complete.jpg; treatment=fit 3840x154; 保留整卷比例 | — | — |
| scroll_section1.jpg | 5354x1600 | 3.35:1 | P07–P08：长桥段落，两页共用同一张图、只移动视窗（Executor 调换：此段含著名亭桥） | Painting scan | 出血的横向视窗，P07 对准长桥，P08 视窗向左推移到水村与渔舟；标题落在上方深青带 | adaptive | web | Sourced | 维基共享资源公有领域文件 "A Thousand Li of Rivers and Mountains Section 1.jpg"：画卷中段的山水局部，横幅 | — | — |
| scroll_bridge.jpg | 7496x1600 | 4.68:1 | P07–P08：长桥段落，两页共用同一张图、只移动视窗 | Painting scan | 出血的横向视窗，P07 对准长桥全貌，P08 视窗向右推移到水村与渔舟；标题落在画面上缘的天空留白 | adaptive | web | Sourced | 维基共享资源公有领域文件 "Wang Ximeng - A Thousand Li of River (Bridge).jpg"：画中著名的跨江长桥段落，横幅高分辨率扫描 | — | — |
| scroll_river1_faded.png | 2560x543 | 4.71:1 | P10：流转时间线后面褪淡的画卷带 | Painting scan | 作为整页下半部的低对比横向底带，时间线的节点压在它上面 | adaptive | web | Sourced | Derived from scroll_river1.jpg; treatment=desaturate 0.55 + brightness 1.18 + fit 2560x543; 压低对比让文字可读 | — | — |
| scroll_end.jpg | 7446x1600 | 4.65:1 | P13：收束页的画面场；同一文件的卷尾纸本区域另作 P04 蔡京题跋、P11 溥光题跋的局部裁切 | Painting scan | 满版出血，右侧卷尾的远山与留白承接邀请句，下缘深青 scrim 放图注 | adaptive | web | Sourced | 维基共享资源公有领域文件 "Wang Ximeng - A Thousand Li of River (End).jpg"：画卷末段的远山与开阔水面，横幅 | — | — |
| obj_azurite.png | 524x396 | 1.32:1 | P06：石青的矿物来源 | Illustration | 与表格同页，作为"石青"行旁的实物锚点 | no-crop | slice | Generated | Derived from sheet_objects.png; treatment=slice; | none | local |
| obj_malachite.png | 522x368 | 1.42:1 | P06：石绿的矿物来源 | Illustration | 与表格同页，作为"石绿"行旁的实物锚点 | no-crop | slice | Generated | Derived from sheet_objects.png; treatment=slice; | none | local |
| obj_ochre.png | 499x391 | 1.28:1 | P06：赭石 | Illustration | 与表格同页，作为"赭石"行旁的实物锚点 | no-crop | slice | Generated | Derived from sheet_objects.png; treatment=slice; | none | local |
| obj_dish.png | 521x304 | 1.71:1 | P05：少年身边的颜料碟 | Illustration | 作为人物页的配角小件，靠近序列的"亲授其法"一步 | no-crop | slice | Generated | Derived from sheet_objects.png; treatment=slice; | none | local |
| obj_brush.png | 512x567 | 1:1.11 | P05：毛笔 | Illustration | 作为序列末尾"乃以此图进"的收笔物件 | no-crop | slice | Generated | Derived from sheet_objects.png; treatment=slice; | none | local |
| obj_seal.png | 286x529 | 1:1.85 | P04/P09/P10/P11：贯穿的朱砂印章 | Illustration | 作为页面的不对称配重与"名字"母题，在四页间保持身份、改变位置与大小 | no-crop | slice | Generated | Derived from sheet_objects.png; treatment=slice; | none | local |
| obj_scroll.png | 589x354 | 1.66:1 | P02/P12：卷起的绢卷 | Illustration | 作为"打开/合上"的物件，P02 在细带一端，P12 在舞台与画卷之间 | no-crop | slice | Generated | Derived from sheet_objects.png; treatment=slice; | none | local |
| obj_pine.png | 523x551 | 1:1.05 | P14：出处页的一处安静装饰 | Illustration | 放在出处列表的对角空处，小而克制 | no-crop | slice | Generated | Derived from sheet_objects.png; treatment=slice; | none | local |
| fig_painter_desk.png | 961x1130 | 1:1.18 | P05：伏案作画的少年 | Illustration | 页面的主导人物，占据左半或下半，序列文字绕其排布 | no-crop | slice | Generated | Derived from sheet_figures.png; treatment=slice; | none | local |
| fig_painter_scroll.png | 711x1152 | 1:1.62 | P09：展卷的少年背影 | Illustration | 转折页唯一的具象元素，与一句话和一枚印章相对 | no-crop | slice | Generated | Derived from sheet_figures.png; treatment=slice; | none | local |
| fig_visitor.png | 409x1136 | 1:2.78 | P12：展柜前的当代观众 | Illustration | 与"只此青绿"的数字并置，代表今天看画的人 | no-crop | slice | Generated | Derived from sheet_figures.png; treatment=slice; | none | local |
| word_qianli.png | 3584x799 | 4.49:1 | P01：封面题字 display 层 | Lettering | 作为封面的显示层压在画面上方留白处；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering.png; treatment=slice; | embedded | hero_page |

## IX. Content Outline

### Part 1: 你见过它

#### Slide 01 - 封面：十八岁的青绿

- **Audience move**: 知道这幅画的名字 → 被"十八岁"与"近十二米"两个数字抓住
- **Relationships**: none
- **Composition**: 满版真迹起首段作场，上方留白压题字与原生标题，深青底带承接一行钩子；印章不出现在封面
- **Cover impact (binding)**: 钩子——「十八岁的少年，半年，画了一卷近十二米的江山」
- **Title**: 千里江山图
- **Core message**: 一个十八岁少年半年画成的近十二米青绿长卷
- **Content**: 题字"千里江山"（display 层）· 原生标题《千里江山图》与副标题"十八岁的青绿" · 钩子句 · 出处小字：北宋 王希孟 绢本设色 51.5 × 1191.5 cm 故宫博物院藏
- **Images**: scroll_start.jpg 满版；word_qianli.png 作题字层
- **Fact IDs**: F001, F004
- **Motion suggestion**: 画面先在，题字后落定，钩子句最后出现

#### Slide 02 - 你见过它，但没有看完过它

- **Audience move**: 以为自己看过 → 意识到自己只见过一小段
- **Relationships**: 整卷 与 展柜里常见的一段：parent（部分属于整体）
- **Composition**: 整卷按真实比例缩成一条横贯页面的细带，一枚小括号标出常见的"那一段"，标题在带子上方，卷起的绢卷在带子一端
- **Title**: 你见过它，但很可能没有看完过它
- **Core message**: 它有近十二米长，面积是《清明上河图》的两倍多；我们看到的往往只是一段
- **Content**: 细带（整卷真实比例） · 标注"1191.5 cm" 与 "51.5 cm" · 一句：面积约为《清明上河图》的两倍多 · 一句：2017 年才第一次全卷打开展出
- **Images**: scroll_strip.png 横贯；obj_scroll.png 在细带一端
- **Fact IDs**: F001, F014, F016
- **Motion suggestion**: 细带从卷轴一端向右展开，括号最后出现

#### Slide 03 - 四十六天

- **Audience move**: 觉得"随时能去看" → 明白它极少打开
- **Relationships**: 900 余年 与 46 天：contrast；2400 张票/天 与 半小时售罄：link
- **Composition**: 深青场压住真迹，只留一条清晰的"展柜窗"；巨大的"46 天"作主导，三个小数字排在下方
- **Title**: 九百年里，它这样打开过四十六天
- **Core message**: 2017 年首次全卷展出 46 天即撤，随后三年休养
- **Content**: Display "46 天" · 三条小数字：每天 2400 张票 / 开门半小时售罄 / 撤展后约三年休养 · 注：2013 年武英殿只展过一天
- **Images**: scroll_bridge.jpg 满版压 scrim（与 §VIII 调换后）
- **Fact IDs**: F014, F015, F018
- **Motion suggestion**: 展柜窗先亮，"46 天"后落，三条小数字依次出现

### Part 2: 他是谁

#### Slide 04 - 关于他，只有七十七个字

- **Audience move**: 想知道作者是谁 → 发现史料只有一段题跋
- **Relationships**: 题跋原文 与 印章：link（同一段纸上的两种痕迹）
- **Composition**: 绢面上一段竖排的题跋原文作主导，右下一枚朱砂印章作配重（印章母题第一次出现），标题放在左上
- **Title**: 关于他，我们只知道七十七个字
- **Core message**: 蔡京的题跋是关于作者的唯一同时代记录
- **Content**: 题跋原文（Quote，竖排或分行）：政和三年闰四月一日赐。希孟年十八岁，昔在画学为生徒，召入禁中文书库，数以画献，未甚工。上知其性可教，遂诲谕之，亲授其法，不逾半岁，乃以此图进。上嘉之，因以赐臣京，谓天下士在作之而已。 · 注："政和三年"即 1113 年；题跋作者蔡京 · 出处行
- **Images**: obj_seal.png 作配重
- **Fact IDs**: F004, F006
- **Motion suggestion**: 题跋逐句出现，印章最后落下

#### Slide 05 - 从画学生徒到半年成画

- **Audience move**: 只知道"十八岁" → 看见他走过的五步
- **Relationships**: 画学生徒 → 召入文书库 → 数以画献未甚工 → 徽宗亲授其法 → 不逾半岁以此图进：order
- **Composition**: 伏案作画的少年占据左半，右侧一条纵向或横向的五步序列，颜料碟与毛笔作为序列的起止小件
- **Title**: 他先被退回过，然后皇帝亲自教他
- **Core message**: 一个没考进画院的少年，在徽宗亲授后不到半年画出此卷
- **Content**: 五步序列：画学生徒 / 召入禁中文书库（据考证做档案登记） / 数以画献，未甚工 / 徽宗"知其性可教"，亲授其法 / 不逾半岁，以此图进 · 一句注：画上没有作者款印，"王"姓由清初藏家梁清标题签时确立
- **Images**: fig_painter_desk.png 主导；obj_dish.png、obj_brush.png 作序列小件
- **Fact IDs**: F006, F009
- **Motion suggestion**: 五步按顺序逐个出现

#### Slide 06 - 五层颜色

- **Audience move**: 以为青绿是"涂上去的" → 知道它是矿石层层堆出来的
- **Relationships**: 线稿 → 赭石 → 石绿（两遍）→ 石青：order；石青—蓝铜矿、石绿—孔雀石：link
- **Composition**: 左侧一个自上而下的五层剖面（绢底、墨线、赭石、石绿两层、石青），右侧原生表格逐层说明，三块矿物原石贴在对应行旁
- **Title**: 青绿不是画上去的，是一层层堆出来的
- **Core message**: 线稿、赭石、两遍石绿、最后石青，共五层矿物颜料
- **Content**: 五层剖面 · 表格（层次 / 颜料 / 来源 / 作用）：第一层 线稿 墨 勾勒山石；第二层 赭石 赭石 铺底与远山、水天交界；第三、四层 石绿 孔雀石 大面积上两遍；第五层 石青 蓝铜矿 最上层的青 · 一句：九百余年后仍"散发出宝石般的光芒"
- **Visualization**: 原生表格 `pigment-layers`（五行四列）；剖面为页面局部的定性构图
- **Native-ready**: pigment-layers=yes
- **Images**: obj_azurite.png、obj_malachite.png、obj_ochre.png 贴在对应行旁
- **Fact IDs**: F003, F012, F013
- **Motion suggestion**: 五层自下而上依次叠加，表格行与之同步出现

### Part 3: 看这幅画

#### Slide 07 - 桥

- **Audience move**: 听故事 → 真正盯着画看
- **Relationships**: none
- **Composition**: 长桥段落出血占满整页，视窗对准长桥，标题落在画面上缘天空的留白；只有一行图注
- **Title**: 现在，看这座桥
- **Core message**: 画中的桥梁、水村、舟船与人物"笔墨工致，位置得宜"
- **Content**: 标题 · 一行图注：跨江长桥段落，《千里江山图》局部，故宫博物院藏 · 出处小字：图片 Wikimedia Commons，公有领域
- **Images**: scroll_section1.jpg 出血视窗，P07 与 P08 共用同一文件，只改变视窗位置
- **Fact IDs**: F003
- **Motion suggestion**: 本页与下一页共享同一张画，视窗在两页之间连续推移

#### Slide 08 - 再往右

- **Audience move**: 看到一座桥 → 发现桥之外还有水村与渔舟
- **Relationships**: 长桥 → 水村 → 渔舟：order（手卷自右向左展开，视线向左推移）
- **Composition**: 同一张画向右推移的视窗，三处小标注点出水村、渔舟与远山，标题仍在上缘留白
- **Title**: 再往左，是水村、渔舟和更远的山
- **Core message**: 每一段都有可看的细节，这就是"独步千载"的功夫
- **Content**: 标题 · 三处小标注：水村 / 渔舟 / 远山 · 一行图注同 P07
- **Images**: scroll_section1.jpg 视窗左移（手卷自右向左展开），与 P07 承接
- **Fact IDs**: F003
- **Motion suggestion**: 视窗从上一页的位置连续推移到本页，三处标注随后出现

### Part 4: 谁留下了名字

#### Slide 09 - 他没有留下名字

- **Audience move**: 以为"王希孟"是署名 → 意识到画上根本没有款印
- **Relationships**: 画上无款印 与 后人给的名字：contrast
- **Composition**: 全卷最克制的一页——绢面上一句话，右侧展卷少年的背影，印章从上一次出现的位置移到画面中央偏下
- **Title**: 他没有在画上留下名字
- **Core message**: "希孟"来自蔡京题跋，"王"姓与画名都是五百多年后由梁清标题签确立
- **Content**: 一句主句 · 两行小字：蔡京题跋只写"希孟"二字 / "王希孟千里江山图"是清初梁清标装裱时的外签
- **Images**: fig_painter_scroll.png；obj_seal.png（承接 P04 的印章）
- **Fact IDs**: F009
- **Motion suggestion**: 印章保留身份从 P04 的位置移到本页位置；主句最后出现

#### Slide 10 - 九百年的接力

- **Audience move**: 只知道"故宫藏" → 看见它经过了哪些手
- **Relationships**: 1113 徽宗赐蔡京 → 1126 查抄 → 1127 金兵掠走 → 南宋内府 → 1303 溥光 → 清初梁清标 → 1786 乾隆题诗 → 1922 溥仪带出宫 → 1953 拨交故宫：order
- **Composition**: 页面下半是褪淡的画卷带，一条横向时间线压在它上面，九个节点，年份大、事件小；印章从上一页移到时间线"梁清标"节点旁，表示"名字从这里来"
- **Title**: 九百年里，它经过了这些手
- **Core message**: 从徽宗到故宫，九次易手
- **Content**: 九节点时间线：1113 徽宗赐蔡京 / 1126 蔡京贬黜被查抄 / 1127 金兵掠走 / 复归南宋内府（宋理宗"缉熙殿宝"印） / 1303 溥光收藏 / 清初 梁清标题签定名 / 1786 乾隆题诗钤印 / 1922 溥仪带出宫 / 1953 拨交故宫博物院
- **Images**: scroll_river1_faded.png 底带；obj_seal.png 承接
- **Fact IDs**: F008, F009
- **Motion suggestion**: 印章从 P09 移到"梁清标"节点旁；节点按年代依次出现

#### Slide 11 - 后来的人怎么说

- **Audience move**: 知道流转 → 听到两位后人的评价
- **Relationships**: 溥光的评价 与 乾隆的题诗：membership（两种后人的回应）
- **Composition**: 两段引文一左一右分列，溥光在左（元）、乾隆在右（清），印章缩小落在两段之间作分隔
- **Title**: 后来看到它的人，这样说
- **Core message**: 元人称它"独步千载"，清帝题诗给了它今天的名字
- **Content**: 引文一（Quote）：在古今丹青小景中，自可独步千载，殆众星之孤月耳。——元 溥光 · 引文二（Quote）：江山千里望无垠。——清 乾隆题诗首句 · 注：宋荦《论画绝句》"进得一图身便死"是后世追记，早逝说由此而来
- **Images**: obj_seal.png 承接
- **Fact IDs**: F005, F010, F011
- **Motion suggestion**: 印章从时间线节点移到两段引文之间；引文左后右出现

### Part 5: 它今天还活着

#### Slide 12 - 只此青绿

- **Audience move**: 以为它只在展柜里 → 知道它以另一种形式活在今天
- **Relationships**: 2021 首演 → 2022 春晚 → 2024 近 400 场：order
- **Composition**: 左侧展柜前的当代观众，右侧三个大数字纵向排列，卷起的绢卷在两者之间
- **Title**: 它今天还在被看见
- **Core message**: 舞蹈诗剧《只此青绿》让这幅画走进了五十座城市
- **Content**: Display 三个数字：400 场 / 50 座城市 / 2022 春晚 · 说明：舞蹈诗剧《只此青绿——舞绘〈千里江山图〉》2021 年 8 月国家大剧院首演；2022 年 1 月 31 日登上央视春晚；至 2024 年 1 月演出近 400 场 · 注：总编导周莉亚、韩真
- **Images**: fig_visitor.png；obj_scroll.png
- **Fact IDs**: F017
- **Motion suggestion**: 三个数字自上而下依次出现

#### Slide 13 - 下一次它打开的时候

- **Audience move**: 听完故事 → 决定下次去看，并慢慢看
- **Relationships**: none
- **Composition**: 卷尾远山出血占满整页，邀请句落在右侧的开阔水面，下缘深青带放图注
- **Closing impact (binding)**: 「下一次它打开的时候，去看它。慢一点，看完它。」
- **Title**: 下一次它打开的时候
- **Core message**: 它极少打开；值得等一次、看一次、看完一次
- **Content**: 邀请句 · 一行小字：1949 年后它只公开亮相过寥寥几次 · 图注：《千里江山图》卷尾局部
- **Images**: scroll_end.jpg 满版
- **Fact IDs**: F015
- **Motion suggestion**: 画面先在，邀请句分两行先后出现

#### Slide 14 - 出处

- **Audience move**: 想核对 → 能找到每个数字与图片的来源
- **Relationships**: none
- **Composition**: 密而安静的出处列表，分"事实来源"与"图片来源"两栏，三条可点击链接；松树小件放在对角空处
- **Title**: 出处
- **Core message**: 每个数字、引文与图片都有出处
- **Content**: 事实来源：故宫博物院藏品页（超链接 https://www.dpm.org.cn/collection/paint/228354.html）/ 国家人文历史《层层迷雾》2023 / 新京报《京华物语》 / 光明日报 2017-09-13 / 新浪收藏 2017-10-29 / 新华网 2024-01-05（超链接 http://www.news.cn/gangao/20240105/b53d4993afb3495181523db8257acb36/c.html）/ 雅昌艺术网 2024-06-08 / 维基百科 · 图片来源：王希孟《千里江山图》，故宫博物院藏，扫描件来自 Wikimedia Commons，公有领域（超链接 https://commons.wikimedia.org/wiki/Category:A_Thousand_Li_of_Rivers_and_Mountains）· 插画元素为 AI 生成示意 · 注：蔡京题跋日期"闰四月一日"另有"八日"之说，本卷采多数来源
- **Hyperlinks**: "故宫博物院藏品页" → https://www.dpm.org.cn/collection/paint/228354.html；"新华网 2024-01-05" → http://www.news.cn/gangao/20240105/b53d4993afb3495181523db8257acb36/c.html；"Wikimedia Commons" → https://commons.wikimedia.org/wiki/Category:A_Thousand_Li_of_Rivers_and_Mountains
- **Images**: obj_pine.png
- **Fact IDs**: F001, F005, F006, F008, F012, F013, F014, F015, F017, F019

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 以每页最终 SVG 为准写讲述稿；调研事实与引语照录，不加入未在 sources 中的事实；每页从上一页自然接过来
- **Total duration**: 约 15 分钟
- **Notes style**: conversational——像在展柜前压低声音讲故事
- **Presentation purpose**: 先让人"看见"这幅画，再讲清少年半年成画与九百年流转，最后落成"下次它打开时去看、慢慢看"的邀请
