<!-- ppt-master-schema: design-spec/v1 -->
# 我们为什么要睡觉 - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | sleep_science_explainer_ppt43_20260910 |
| Canvas Format | PPT 4:3 (1024×768) |
| Page Count | 15 |
| Primary Language | zh-CN |
| Target Audience | 没有生物学背景的成年听众:上班族、学生家长、熬夜的人;他们知道"睡不够会难受",但没想过睡眠内部有结构,也不知道那些睡眠建议是怎么来的 |
| Communication Intent | 先解释、后说服:用一条从熟悉经验出发的链条,把"睡眠是一个有结构、有功能的主动过程"讲通;在此基础上让听众重新掂量"少睡一点没关系"这句话;全程把共识、争议、罕见特例分开 |
| Desired Audience Outcome | 听众能用自己的话说出"睡眠压力"和"生物钟"两股力量各是什么、怎么互相作用,能说出 7 小时建议的来源,并能指出"睡眠清洗大脑"目前仍有争议 |
| Core Message / Ask / Action | 睡眠不是关机,而是一段被两股力量安排好的主动工作;把它当成可以随时挪用的时间,代价是可核查的 |
| Delivery Context | 主讲人现场讲解(科普讲座 / 公司分享 / 课堂),约 25 分钟;次要用途是讲后把文件发给听众自读 |
| Artifact Afterlife | 传阅与复用:听众自读、被引用其中的数字、来源页可点开核查 |
| Reading Mode | presentation |
| Content Strategy | 事实全部来自已导入的研究对(`sources/sleep_science_research.md` 与 `.facts.json`),叙述结构自由重组;不引入未溯源数字,凡范围与估算都写明;小鼠实验不改写成人类结论 |
| Design Style | 纸层夜谈:分层剪纸的暖纸底,深夜蓝与暖橙两色各自承担固定的解释职责,每页一层新纸盖上去 |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 工作流默认(final Stage-2 proactive value `true`) |
| Custom Animations | enabled — 用户在任务书中明确要求自定义动画,并要求压测原生图表的分阶段出现 |
| Narration Audio | disabled — 工作流默认 |
| Created Date | 2026-09-10 |

- **Template Application**: 采用已安装的 Science Explainer Style 的方法层:instructional 的讲解顺序、§III 的整套页面角色(熟悉的地面 → 谜题 → building block → 类比并标出失效点 → 机制 → 尺度 → 证据 → 误解 → 知识边缘 → 为什么重要 → 继续探索)、以及"每页一个想法、标题用大白话、术语首次出现处附白话释义、类比必须标出边界、图表先讲坐标轴再上数据并直接在标记上标注"的表达纪律。视觉层沿用 Style 的 paper-cut 偏好与"颜色承担固定解释职责"的规则;偏离一处:Style §VI 的 Preferred Image Rendering 写的是 `vector-illustration`,本项目改用 `paper-cut` 渲染,理由是 Style §V 已把视觉风格定为 paper-cut,而 catalog 中 paper-cut 风格的配对渲染就是 paper-cut,沿用 vector-illustration 会让插画与页面材质分裂。Style 只提供方法与视觉默认,不提供画布、结构、原型与身份,页面保持 flat 自由设计。

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 4:3 |
| Dimensions | 1024 × 768 |
| viewBox | `0 0 1024 768` |
| Margins | 上下左右各 56px |
| Content Area | x: 56–968, y: 56–712(可用宽 912,可用高 656) |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Visual style**: custom
- **Mode References**: instructional
- **Mode Behavior**: 按 instructional 的分解—排序骨架讲解,但每一步都必须由上一步"欠下的问题"引出:先给共享经验,再制造谜题,之后每页只加一块必需的积木;类比页必须在同页写出类比失效的地方;结尾回到开头那个经验并重新解释它。标题写"这个想法"的白话说法,术语只在其所指之物出现之后才登场,并与白话释义同页。
- **Visual Style References**: paper-cut
- **Visual Style Behavior**: 每个元素都是一张剪下来的纸,层叠而非描边:形状用略不规则的 polygon/path 切边,层与层之间只用 8–12% 的柔影表示高度;暖纸底作为"桌面",内容纸盖在上面;跨页保留一条底部的夜色波浪纸带作为累积容器,同一元素在相邻页保持同位置以便叠加;顶层允许小块镂空口子(die-cut window)露出下层。装饰即层次,不额外加边框与图标网格。
- **Theme**: 一夜是一张张叠上去的纸:白天那张纸越叠越厚(睡眠压力),另一张纸每天准点起落(生物钟),两张纸叠在一起才决定你什么时候睡着。
- **Tone**: 温和、具体、克制;不吓唬,不许诺,不把小鼠实验说成人类结论。

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #FBF5E9 | 暖纸底,所有剪纸层的"桌面" |
| Secondary background | #F0E4CE | 第二层纸:分区块、图表底板、引文块 |
| Primary | #2E4A7D | 固定语义=夜 / 睡眠 / 睡眠压力(Process S);深睡 N3 也用它 |
| Accent | #E08A32 | 固定语义=光 / 清醒 / 生物钟(Process C);仅用于大色块与标记,不做小字 |
| Secondary accent | #B4553E | 固定语义=REM(做梦)与风险提示;可做正文级小字 |
| Body text | #2A2622 | 正文与标题墨色 |
| Secondary text | #5C554C | 注释、图注、脚注、来源行 |
| Divider | #D9C9AC | 纸层切边、细分隔线 |
| Surface | #FFFDF7 | 最上层纸(卡片 / 图表面板)的纸面 |
| Block shade | #E6D8BE | 纸层落影与底纹块,比 Divider 深一档 |
| Light sleep | #6E8FBF | 固定语义=浅睡 N1/N2,是 Primary 的浅一档,与深睡形成同族梯度 |

### AI Image Strategy

- **Image Rendering**: custom
- **Image Rendering References**: paper-cut
- **Mood**: 温暖、可触摸、手工感——像 Eric Carle 绘本里那种用彩色卡纸剪贴出来的夜晚场景。
- **Visual**: 彩色卡纸剪贴:形状由略不规则的剪切边定义,不画轮廓线;每层纸带 10–15% 纸纹,层与层之间落 8–12% 柔影;造型极简到能一眼认出的程度,不追求写实。所有插画都要在解释一件事(容器里的水位、被挡住的接收口、方向盘上打盹的手),不出现漂浮分子、发光大脑、实验室器皿这类只标示学科不解释内容的装饰。
- **Image Rendering Behavior**: 以 paper-cut 渲染为唯一基底:线条=无轮廓,只有纸的剪切边;纹理=每张纸 12% 纸纹;深度=层间 10% 柔影,禁止渐变与投射高光;材质=哑光卡纸;情绪=暖、手作、夜晚但不阴郁。图内不出现任何文字。

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 温暖、人文的无衬线;标题可坐在剪纸横幅上 | Microsoft YaHei | Trebuchet MS | sans-serif |
| Body | 高易读的无衬线,远距离可读 | Microsoft YaHei | Verdana | sans-serif |
| Data | 数字必须是等高数字,图表刻度与英文缩写在此角色 | Microsoft YaHei | Verdana | sans-serif |

- **Title stack**: `Microsoft YaHei, Trebuchet MS, sans-serif`
- **Body stack**: `Microsoft YaHei, Verdana, sans-serif`
- **Data stack**: `Microsoft YaHei, Verdana, sans-serif`
- **Role rationale**: 中文面只用一款(微软雅黑)是有意的——讲堂后排的可读性优先于字族对比,层级由字号、字重与颜色承担;拉丁面分两支:标题走 Trebuchet MS 取其人文的暖调,正文与数据走 Verdana 取其等高数字与远距离辨识度,避免 Georgia 一类旧式数字在图表中高低不齐。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 28 |
| Title | 52 |
| Subtitle | 36 |
| Annotation | 20 |
| Cover title | 84 |
| Lead | 34 |
| Hero number | 72 |
| Footnote | 18 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 视线先落在页面唯一的那个视觉物(插画、图表或大数字),再向下读一行白话结论;标题在顶部横幅纸上,是入口不是重点。
- **Composition tendency**: 每页一个想法一个视觉;大量留白由暖纸底承担;避免卡片网格与并列多栏,除非内容本身就是并列。
- **Cross-page continuity**: 底部的夜色波浪纸带贯穿全卷,水位/曲线类元素在相邻页保持同一位置累积;颜色的语义职责全卷固定不变(蓝=睡眠压力/夜,橙=光/生物钟,赤陶=REM 与风险)。
- **Spacing posture**: breathing 为主,数据页与证据页允许 dense。
- **Spacing anchors**: 页边距 56px;块间距 32px;栏间距 40px;圆角 12px;正文行高 42px。

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-filled

| Icon Path | Suitable Scenarios |
| --- | --- |
| tabler-filled/moon | 夜 / 睡眠状态标记 |
| tabler-filled/sun | 白天 / 光照输入 |
| tabler-filled/mug | 咖啡因 |
| tabler-filled/clock | 时长与时刻 |
| tabler-filled/bed | 就寝 / 睡眠时段 |
| tabler-filled/alert-triangle | 风险与警示 |
| tabler-filled/book | 继续阅读的来源 |
| tabler-filled/link | 可点开的外部链接 |
| tabler-filled/droplet | 腺苷 / 水位隐喻 |
| tabler-filled/steering-wheel | 驾驶场景 |
| tabler-filled/calendar-week | 工作日与周末的节律 |
| tabler-filled/microscope | 实验与证据 |
| tabler-filled/bulb | 想法 / 结论 |
| tabler-filled/hourglass | 半衰期与流逝 |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P04 | chart | donut_chart | 一夜里四个睡眠阶段各占多少 |
| P05 | chart | line_chart | 一整夜的睡眠深度如何在四到五个周期里起伏 |
| P09 | chart | line_chart | 咖啡因按约 5 小时半衰期衰减 |
| P10 | chart | horizontal_bar_chart | 各年龄段的每日建议睡眠时长区间 |
| P12 | table | comparison_matrix | 两个常见说法与实际证据的逐条对照 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cover_night_third.jpg | 1920x1072 | 16:9 | 封面主视觉:夜色里被剪成三段的一天,其中一段是睡眠 | Illustration | 满幅横带压在封面下半,标题压在其上方的暖纸空处 | adaptive | ai | Generated | 剪纸夜晚:一条水平的时间带被剪成三段,最左那段是深蓝的夜,城市与床的极简剪影卧在夜段里;不要文字与刻度 | none | hero_page |
| el_night_window.png | 781x765 | 781:765 | 熟悉的地面:夜里亮着的窗与一张床 | Illustration | 放在页面右侧,与左侧的白话句子并排 | no-crop | slice | Generated | 切自 sheet_elements_a.png 左上格 | none | local |
| el_water_vessel.png | 670x811 | 670:811 | 类比与机制:一个装着水的容器,水位越醒越高 | Illustration | 页面中部偏右,水位线与相邻页保持同一高度以便承接 | no-crop | slice | Generated | 切自 sheet_elements_a.png 右上格;与 el_tide_arc 同族,可在相邻页共存 | none | local |
| el_tide_arc.png | 866x609 | 866:609 | 类比:每天准点起落的潮汐弧线与太阳月亮 | Illustration | 压在容器元素之上或之侧,表示两股力量叠加 | no-crop | slice | Generated | 切自 sheet_elements_a.png 左下格 | none | local |
| el_coffee_block.png | 816x694 | 816:694 | 机制:一只杯子挡住了一个接收口 | Illustration | 与咖啡因衰减图表同页,置于图表标题一侧 | no-crop | slice | Generated | 切自 sheet_elements_a.png 右下格 | none | local |
| el_wheel_nod.png | 663x835 | 663:835 | 证据:方向盘与一只垂下的手 | Illustration | 与困倦驾驶的大数字并排,数字为主图为辅 | no-crop | slice | Generated | 切自 sheet_elements_b.png 左上格 | none | local |
| el_two_papers_question.png | 836x546 | 836:546 | 知识边缘:两张方向相反的纸并排,中间留空 | Illustration | 居中,两侧各留一段说明位 | no-crop | slice | Generated | 切自 sheet_elements_b.png 左下格 | none | local |
| el_pillow_book.png | 770x614 | 770:614 | 为什么重要 / 继续探索:枕头上摊开的一本书 | Illustration | 页面一角,安静收束 | no-crop | slice | Generated | 切自 sheet_elements_b.png 右下格 | none | local |

## IX. Content Outline

### Part 1: 从你已经有的经验出发

#### Slide 01 - 封面:把一生的三分之一交给黑夜

- **Audience move**: 以为这是又一场"劝你早睡"的讲座 → 意识到问题是"这三分之一到底在干什么"
- **Relationships**: 一天被分成的三段与"其中一段是睡眠"之间是 membership 关系;三分之一这个量与建议时长之间是 link(由后者推算得出)
- **Cover impact**: 钩子(binding)=按建议时长推算,人一天有大约三分之一在睡觉——这不是一句抒情,而是从 7–9 小时的建议直接算出来的量级
- **Composition**: 夜色横带压住下半页,主标题坐在上半的暖纸空处,副标题一行小字说明"三分之一"的来源
- **Title**: 我们为什么要睡觉
- **Core message**: 一天有三分之一交给了黑夜,而我们几乎从不问它在干什么
- **Content**: 主标题《我们为什么要睡觉》·副标题"把一生的三分之一交给黑夜"·一行来源说明:成人建议 7–9 小时,约占一天的三分之一(按建议时长推算)
- **Images**: cover_night_third.jpg 作为下半页主视觉
- **Fact IDs**: F002
- **Motion suggestion**: 夜色横带先落位,标题随后从纸面浮出

#### Slide 02 - 熬夜之后的第二天

- **Audience move**: 把"困"当成一种可以靠意志力压过去的情绪 → 认出那是身体在收账
- **Relationships**: 几种熬夜后的具体体感之间是 membership(同属一个共享经验),它们与"第二天补觉后的缓解"之间是 order(先欠后还)
- **Composition**: 左侧三行白话短句,右侧一个亮着的窗与一张床
- **Title**: 每个人都熬过一次夜
- **Core message**: 那种第二天的迟钝不是心情问题,是有生理原因的欠账
- **Content**: 熬夜第二天的共享体感:反应慢半拍 / 情绪易碎 / 眼睛发涩 · 这一页不出现任何术语 · 一句过渡:这种感觉从哪来
- **Images**: el_night_window.png
- **Motion suggestion**: 窗与床先在场,三行短句依次出现;此页的窗保持位置不变,进入下一页

#### Slide 03 - 如果只是休息,为什么不能少睡一点

- **Audience move**: 认为睡觉是"没事干的时候才做的事" → 意识到它是一件不能取消的事
- **Relationships**: "睡眠只是休息"这一常识与"它无法被意志力取消"之间是 contrast;后者与 7 小时建议之间是 link
- **Composition**: 沿用上一页的窗与床位置,页面上叠一层问号形状的镂空纸,把安静的场景变成一个悬而未决的问题
- **Title**: 可它为什么不能少睡一点
- **Core message**: 如果睡眠只是"休息",它不该是强制的——但事实上你无法用意志力取消它
- **Content**: 谜题:休息可以少做,睡觉不能 · 权威机构给出的不是"尽量多睡",而是一条下限:成人 18–60 岁每晚 7 小时或以上 · 长期低于 7 小时与体重增加、糖尿病、高血压、心血管疾病、抑郁及死亡风险上升相关 · 悬而未决:一件"只是休息"的事,不该有下限
- **Fact IDs**: F001, F016
- **Motion suggestion**: 承接上一页的窗与床(同位置),问号镂空纸后落

### Part 2: 一夜内部发生了什么

#### Slide 04 - 睡着以后,大脑并没有关机

- **Audience move**: 以为睡眠是一段均匀的空白 → 知道它由几种不同的状态组成,各占多少
- **Relationships**: 四个睡眠阶段之间是 membership(共同构成一夜的总睡眠时间);N1/N2/N3 与 REM 之间是 contrast(非快速眼动 vs 快速眼动)
- **Composition**: 左侧圆环图占据主要视觉,右侧四行标注直接对应色块,不用图例
- **Title**: 睡着以后,大脑分成了几种状态
- **Core message**: 一夜不是一段均匀的空白,而是四种状态按固定比例分掉的时间
- **Content**: 术语首次登场并附白话:非快速眼动睡眠(NREM,眼球不动的三档,越往后越深)/ 快速眼动睡眠(REM,眼球快速转动、做梦最多的一档)· 各阶段占总睡眠时间的大致比例:N1 约 5%、N2 约 45%、N3 约 25%、REM 约 25% · 一句提醒:比例是平均值,不是每个人每晚的实测
- **Visualization**: 圆环图 `sleep-stage-share`,四段=N1/N2/N3/REM,直接在段上标注名称与百分比,不用图例;Native-ready: sleep-stage-share=yes
- **Fact IDs**: F004
- **Motion suggestion**: 先出现空的圆环与坐标说明,再逐段填入四个阶段,顺序按 N1→N2→N3→REM

#### Slide 05 - 一夜要绕四到五圈

- **Audience move**: 以为深睡是"睡得越久越深" → 看见深睡集中在前半夜、做梦集中在后半夜
- **Relationships**: 一夜的四到五个周期之间是 order;每个周期内 N1→N2→N3→N2→REM 是 order;前半夜与后半夜之间是 contrast
- **Composition**: 整页一张横跨的睡眠深度曲线,横轴是入睡后的小时数,纵轴向下越深;先讲两根轴,再落数据
- **Title**: 一夜要绕四到五圈
- **Core message**: 深睡集中在前半夜,做梦集中在后半夜——所以少睡的那两小时,砍掉的主要是 REM
- **Content**: 一个完整周期约 90–110 分钟,一夜通常 4–5 个周期 · 周期内的推进顺序:N1→N2→N3→N2→REM · 越到后半夜,REM 段越长,深睡越少 · 说明:这张图是按上述规律画的示意,不是某一次实测记录
- **Visualization**: 阶梯状折线图 `one-night-cycles`,横轴=入睡后小时数 0–8,纵轴=睡眠深度(清醒 / REM / N1 / N2 / N3),直接在曲线段上标注阶段名;Native-ready: one-night-cycles=no(原生 line 图的数值轴只能显示数字刻度,无法承载"清醒/REM/N1/N2/N3"这一分类深度轴;半小时粒度的类别标签也无法与绘制的整点刻度一致。保留完整图形,按 native-data-interface §2 判定为不可原生表达。)
- **Fact IDs**: F005, F004
- **Motion suggestion**: 先出两根轴与轴的说明,再一段一段推进曲线,让四到五个周期依次成形

### Part 3: 是什么决定你什么时候困

#### Slide 06 - 两股力量,不是一股

- **Audience move**: 以为"困"只有一个来源 → 分得清"越醒越困"和"到点就困"是两回事
- **Relationships**: 睡眠压力与生物钟之间是 overlap(两条同时存在、互相叠加的力量);两者与"什么时候睡着"之间是 parent(共同决定)
- **Composition**: 页面中部并排两个剪纸物:左边一个越来越满的容器,右边一条每天起落的潮汐弧;下方一行写明类比在哪里失效
- **Title**: 让你困的,是两件不同的事
- **Core message**: 一个是越醒越满的水位,一个是每天准点涨落的潮汐;睡意是它们叠在一起的结果
- **Content**: 白话版:醒着越久越困(水位),但半夜三点最困、下午两点也困(潮汐)· 术语登场:稳态过程 Process S = 水位;昼夜过程 Process C = 潮汐;两者相互作用共同决定睡与醒的时机(双过程模型)· **类比在这里失效**:水位不是一种可以称重的物质储量,模型描述的是脑电活动的定量规律,不是某个分子的浓度读数;下一页要讲的腺苷只是其中一个被研究得较多的中介信号
- **Fact IDs**: F015, F007
- **Motion suggestion**: 容器先出现并注水到当前水位,潮汐弧再叠加进来;两个元素的位置在下一页保持不变

#### Slide 07 - 水位是什么:一个整天都在堆积的信号

- **Audience move**: 把"睡眠压力"当成比喻 → 知道它对应一个可测量的物质信号
- **Relationships**: 清醒时长与腺苷累积之间是 order(前者驱动后者);腺苷累积与困意之间是 link;恢复性睡眠与水位下降之间是 link
- **Composition**: 承接上一页的容器(同位置),水位升高,容器旁多出一行说明这是什么
- **Title**: 水位其实有实物
- **Core message**: 清醒时,腺苷在脑内随能量代谢一点点累积;睡够了,它才降下去
- **Content**: 腺苷(adenosine):清醒期间随神经元能量代谢在基底前脑等区域累积的一种物质 · 它在恢复性睡眠中回落,因此被当作睡眠稳态的中介信号 · 所以"补觉"补的是这条曲线,不是补时长本身
- **Images**: el_water_vessel.png(与上一页同位置,水位更高)
- **Fact IDs**: F007
- **Motion suggestion**: 承接上一页的容器与潮汐弧位置,只让水位继续上升

#### Slide 08 - 潮汐是什么:眼睛看见的光

- **Audience move**: 以为生物钟是个抽象说法 → 知道它有具体位置和具体输入
- **Relationships**: 光照与视交叉上核之间是 order(输入在前);视交叉上核与褪黑素分泌之间是 parent(前者控制后者);褪黑素与困意之间是 link
- **Composition**: 承接上一页的容器与潮汐弧位置,潮汐一侧点亮:加入太阳与眼睛的路径
- **Title**: 潮汐由光对时
- **Core message**: 主时钟在脑内一个具体的位置,它按你眼睛收到的光量来决定什么时候放出困意
- **Content**: 视交叉上核(SCN):下丘脑里的"主时钟" · 它按眼睛接收到的光量控制褪黑素分泌,傍晚光线减弱时分泌增加,人开始犯困 · 昼夜节律 = 约 24 小时周期内的生理、心理与行为变化 · 一句实用推论:夜里的强光不是让你"精神",而是让主时钟以为天还没黑
- **Images**: el_tide_arc.png(与上一页同位置)
- **Fact IDs**: F012
- **Motion suggestion**: 保留容器与水位不动,只让光的路径与潮汐弧的当前点亮起

#### Slide 09 - 咖啡因不给你能量,它只是挡住信号

- **Audience move**: 以为咖啡"提供能量" → 知道它只是挡住了报困的信号,而且挡得很久
- **Relationships**: 咖啡因与腺苷受体之间是 contrast(拮抗关系);摄入时间与残余量之间是 order
- **Composition**: 左上一个杯子挡住接收口的剪纸,右侧整幅衰减曲线;先讲两根轴,再落点
- **Title**: 咖啡因不给你能量
- **Core message**: 它拮抗腺苷受体,把"我困了"的信号挡在门外;半衰期约 5 小时,下午三点那杯,睡前还剩一小半
- **Content**: 机制:咖啡因拮抗全部 4 种腺苷受体亚型,其中 A2a 与促觉醒关系最直接 · 半衰期:普通成年人体内约 5 小时 · 由此推算(算术,非实测):下午 15:00 摄入,20:00 还剩约一半,凌晨 01:00 还剩约四分之一 · 注意:半衰期因人而异,吸烟者可缩短约一半
- **Images**: el_coffee_block.png
- **Visualization**: 折线图 `caffeine-decay`,横轴=摄入后小时数 0/5/10/15/20,纵轴=体内剩余比例 100%/50%/25%/12.5%/6.25%,直接在点上标注百分比;Native-ready: caffeine-decay=yes
- **Fact IDs**: F006
- **Motion suggestion**: 先出两根轴与"每过 5 小时减半"的读法,再让曲线从左向右衰减

### Part 4: 我们怎么知道,以及还不知道什么

#### Slide 10 - 到底该睡多久:一条随年龄下移的线

- **Audience move**: 记得"8 小时"这个孤零零的数字 → 知道建议是分年龄的区间,并且知道它来自谁
- **Relationships**: 六个年龄段与各自的建议时长之间是 link;各年龄段之间是 order(按年龄递增,时长递减)
- **Composition**: 整页一组横向条,每条直接标注年龄段与小时区间;成人一条用主色强调
- **Title**: 该睡多久,看你多大
- **Core message**: 建议时长随年龄递减,成人落在 7–9 小时;这是机构给出的区间,不是某个人的实测
- **Content**: 4–12 个月 12–16 小时 / 1–2 岁 11–14 小时 / 3–5 岁 10–13 小时 / 6–12 岁 9–12 小时 / 13–18 岁 8–10 小时 / 成人 7–9 小时 · 来源:美国国立心肺血液研究所(NHLBI)· 与前面的下限对照:成人 7 小时是共识下限,不是目标值
- **Visualization**: 横向条形图 `sleep-by-age`,每条=一个年龄段的建议区间(起点=下限,终点=上限),直接在条上标注小时数;Native-ready: sleep-by-age=yes
- **Fact IDs**: F002, F001
- **Motion suggestion**: 六条从最长到最短依次伸出,成人那条最后出现并被强调

#### Slide 11 - 我们怎么知道少睡有代价

- **Audience move**: 觉得"缺觉有害"是一句劝诫 → 看到一个具体、可核查、有口径说明的数字
- **Relationships**: 困倦驾驶事故数与其统计口径之间是 parent(口径限定数字的含义);这一证据与"普遍睡眠不足"之间是 link
- **Composition**: 左侧一个大数字与一行口径说明,右侧方向盘与垂下的手;口径说明必须与数字同样醒目
- **Title**: 代价是可以数出来的
- **Core message**: 2017 年美国,困倦驾驶涉及约 91,000 起警方报告事故、约 50,000 人受伤、795 人死亡——而官方说这还是低估
- **Content**: 大数字:795(2017 年美国困倦驾驶死亡人数)· 同一年:约 91,000 起警方报告事故,约 50,000 人受伤 · 口径必须同页写明:仅基于警方报告,NHTSA 本身说明这会低估真实规模 · 背景:2022 年美国各州成年人睡眠不足比例从 30%(佛蒙特)到 46%(夏威夷)不等
- **Images**: el_wheel_nod.png
- **Fact IDs**: F011, F003
- **Motion suggestion**: 数字先到位,口径说明紧随其后出现,不让数字单独停留

#### Slide 12 - 两句你大概说过的话

- **Audience move**: 相信"周末能补回来"和"有人天生睡得少" → 知道前者被实验否定,后者是极罕见的基因特例
- **Relationships**: 两个常见说法与各自的对照证据之间是 contrast;两行之间是 membership(同属"听起来合理但站不住"的一类)
- **Composition**: 一张三列两行的小对照表:说法 / 实际 / 依据;上方一个被涂厚了周末两格的周历
- **Title**: 两句你大概说过的话
- **Core message**: 周末补觉没能挡住代谢紊乱;天生短睡者存在,但那是极罕见的基因特例,不是可以练成的能力
- **Content**: 说法一"周末补回来就行"→ 实际:在"工作日不足+周末自由补觉"的反复模式下,补觉未能阻止代谢紊乱,补觉组的肌肉与肝脏胰岛素敏感性反而更差(Depner 等,2019)· 说法二"我天生只需要五小时"→ 实际:DEC2 基因点突变携带者平均每天睡约 6 小时,但极为罕见,且这是天生的,不是训练出来的(UCSF)· 周历对照(工作日薄、周末两格加厚)由原生 SVG 绘制,不用位图 · 一句不嘲笑的收束:这两个说法都很合理——它们只是刚好和证据相反
- **Visualization**: 三列两行对照表 `myth-vs-evidence`,列=说法 / 实际 / 依据,表头用白话;Native-ready: myth-vs-evidence=yes
- **Fact IDs**: F014, F013
- **Motion suggestion**: 两行依次出现,每行先出"说法"再出"实际"

#### Slide 13 - 还没定论的那一块

- **Audience move**: 以为"睡觉是为了清洗大脑"已成定论 → 知道这正是当前争论的焦点,并且知道分歧在哪
- **Relationships**: 2013 年与 2024 年两项研究之间是 contrast(结论方向相反);两者与"睡眠的核心功能"这一问题之间是 membership
- **Composition**: 两张方向相反的纸并排居中,各自写一段结论;中间留出空白,不做裁决
- **Title**: 这一块还在吵
- **Core message**: "睡觉是为了洗脑子"这句流行说法,目前有两组方向相反的小鼠实验结果,尚无定论
- **Content**: 2013 年《Science》:小鼠睡眠与麻醉期间皮层细胞间隙体积增加逾 60%(从约 14% 扩大到 23–24%),β-淀粉样蛋白清除速度约为清醒时的两倍 · 2024 年《Nature Neuroscience》:在小鼠中测得示踪分子的清除在睡眠与麻醉期间显著降低而非升高,作者称结果挑战了"睡眠的核心功能是清除废物"的观点 · 两者都是小鼠实验,不能直接写成人类结论 · 已确立的是另一件事:睡眠参与记忆的系统固化,慢波睡眠期间新近编码的表征被重新激活并逐步转移到新皮层
- **Images**: el_two_papers_question.png
- **Fact IDs**: F008, F009, F010
- **Motion suggestion**: 两张纸左右同时进场,谁也不先于谁

### Part 5: 所以今晚

#### Slide 14 - 回到熬夜的第二天

- **Audience move**: 记住了一堆机制 → 能把机制换算成今晚的一个具体动作
- **Relationships**: 开头那个共享经验与现在的解释之间是 link(同一件事被重新解释);三条可执行的动作与各自对应的机制之间是 link
- **Closing impact**: 收束(binding)=你熬掉的不是"时间",是被两股力量安排好的一段工作;今晚能做的最小一件事,是把最后一杯咖啡往前挪
- **Composition**: 回到第二页那个窗与床的位置,画面不变,旁边多出三行由机制推出的动作
- **Title**: 回到熬夜的第二天
- **Core message**: 睡眠不是关机,而是一段被安排好的工作;知道是哪两股力量之后,能动的地方就变得很具体
- **Content**: 那种迟钝有名字了:水位没降下去,潮汐还没到点 · 今晚可以做的三件事,每件都对应前面讲过的一个机制:把最后一杯咖啡提前到下午三点前(半衰期约 5 小时)/ 睡前把强光调暗(主时钟按光对时)/ 别指望周末还账(补觉未能阻止代谢紊乱)· 一句收束:睡眠是这一天里唯一一段你不参与、却决定明天的时间
- **Images**: el_pillow_book.png
- **Fact IDs**: F006, F012, F014
- **Motion suggestion**: 窗与床先回到原位,三行动作依次出现

#### Slide 15 - 想自己查下去

- **Audience move**: 愿意相信这场讲解 → 拿到可以自己点开核查的入口
- **Relationships**: 每条来源与它支撑的页面之间是 link;来源之间是 membership(同属可自行核查的公开材料)
- **Composition**: 安静收尾:一列可点击的来源行,每行一句它回答了哪个问题;不做花哨版式
- **Title**: 想自己查下去
- **Core message**: 这场讲解里的每个数字都能点开核查,包括那条还在吵的
- **Content**: 睡多久:AASM/SRS 2015 共识声明 https://aasm.org/aasm-and-srs-publish-new-sleep-duration-consensus-statement/ · 分年龄建议:NHLBI https://www.nhlbi.nih.gov/health/sleep/how-much-sleep · 睡眠阶段与周期:StatPearls https://www.ncbi.nlm.nih.gov/books/NBK526132/ · 咖啡因:StatPearls https://www.ncbi.nlm.nih.gov/books/NBK519490/ · 双过程模型:Borbély 等 2016 https://onlinelibrary.wiley.com/doi/abs/10.1111/jsr.12371 · 争议的两篇:Xie 等 2013 https://pmc.ncbi.nlm.nih.gov/articles/PMC3880190/ 与 Miao 等 2024 https://www.nature.com/articles/s41593-024-01638-y · 困倦驾驶:NHTSA https://www.nhtsa.gov/risky-driving/drowsy-driving
- **Fact IDs**: F001, F002, F004, F005, F006, F008, F009, F011, F015
- **Motion suggestion**: 来源行自上而下依次出现,节奏平缓

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 每页讲稿承担页面刻意不写的深度:术语的第二层解释、数字的口径、类比失效的补充说明、以及到下一页的过渡句("现在我们有了水位,就可以问潮汐是什么")。事实只用 `sources/sleep_science_research.facts.json` 里的条目,讲稿不得引入页面上没有的新数字;小鼠实验在讲稿里也必须说明是小鼠。
- **Total duration**: 约 25 分钟(每页 90–120 秒)
- **Notes style**: 耐心的讲解口吻:先定义后使用,先类比后原理,预判听众会问的那一句并当场回答
- **Presentation purpose**: 先解释、后说服:把睡眠讲成一个有结构、有功能的主动过程,并让听众重新掂量"少睡一点没关系"
