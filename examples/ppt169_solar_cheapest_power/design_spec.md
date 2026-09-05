<!-- ppt-master-schema: design-spec/v1 -->
# 光伏为什么成了最便宜的电 - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | 光伏为什么成了最便宜的电 |
| Canvas Format | PPT 16:9 (1280×720) |
| Page Count | 15 |
| Primary Language | zh-CN |
| Target Audience | 能源、电力与产业投资的决策者及其幕僚：熟悉 LCOE 这个词，但价格认知大多停在 2018–2020 年，需要在项目立项、采购与并网排序上做判断 |
| Communication Intent | 先用一句结论纠正过时的价格认知，再用结构化证据解释便宜从哪来；随后主动暴露两个反面事实——成本曲线已在 2021 年触底回升、真正的约束在电网侧；最后推动决策者把注意力和预算从"买便宜组件"转向"买可调度性与并网位置"。说服与决策在先，信息完整性在后 |
| Desired Audience Outcome | 决策者能说出成本下降的因果机制（学习率），能指出成本中心已从组件转移，能解释为什么 2021 年后 LCOE 反而上升，并接受"约束是并网与消纳而非价格"的判断，进而在下一次投资排序中把并网位置与可调度性排在组件价格之前 |
| Core Message / Ask / Action | 光伏已经是多数市场最便宜的新增电源，但它不会自动继续变便宜；决定项目价值的已经不是组件价格，而是并网位置与可调度性 |
| Delivery Context | 主要为有主讲人的 25 分钟决策会现场演示；次要为会后独立阅读的判断备忘 |
| Artifact Afterlife | 作为投资与采购排序讨论的判断依据留存，其数据口径可被直接引用与复核 |
| Reading Mode | balanced |
| Content Strategy | 无用户素材，全部事实来自导入的研究对；口径冲突并列写出，不做平均、不做跨口径换算，缺失数据写 NO DATA |
| Design Style | pyramid × swiss-minimal：结论先行的咨询式论证，配严格瑞士网格、单一强调色与大而准的排版 |
| AI Image Acquisition Path | not applicable |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 工作流默认（final Stage-2 proactive value `true`，无更晚的显式指令） |
| Custom Animations | enabled — 用户在任务书中显式要求（"自定义动画必须做：Morph ≥ 2 组且有承接物；入场按阅读路径；框架整卷一致"） |
| Narration Audio | disabled — 工作流默认（final Stage-2 proactive value `false`，用户未要求配音） |
| Created Date | 2026-09-04 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 上下左右 72px（栅格外边距） |
| Content Area | x 72–1208，y 72–648（1136 × 576） |

## III. Visual Theme

### Theme Style

- **Mode**: pyramid
- **Visual style**: swiss-minimal
- **Theme**: 一张十二列栅格上的成本论证。整卷用同一套模数（12 列 × 84px 列宽 + 24px 沟槽）作为构图骨架，其中两页把栅格线本身画出来当可见结构；每页一个大而准的几何面或一个建筑尺度的数字承担视觉重量，红色只做标点。
- **Tone**: 克制、精确、不留装饰余地；语气是顾问在董事会上给判断，不是科普。

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #FFFFFF | 主画面场，整卷近全白，负空间承担与内容同等的重量 |
| Secondary background | #F2F2F2 | 栅格区块底色，同时充当图表与表格的面板底（本卷不另设 surface 角色，避免两个几乎同值的灰） |
| Primary | #111111 | 近黑：标题、大几何面、主数据系列——瑞士卷里真正的"主色" |
| Accent | #C8102E | 唯一强调色：关键数字、拐点、一条 4px 规则线；用作标点而非装饰 |
| Secondary accent | #6E6E6E | 中灰：对照系列、次级数据、被比较的一方 |
| Body text | #1A1A1A | 正文与标签 |
| Secondary text | #6E6E6E | 注释、来源行、页脚、图注 |
| Divider | #D4D4D4 | 分隔规则线与表格横线 |
| Grid | #E8E8E8 | 图表网格与可见栅格模数线，比 divider 更轻 |

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 新怪诞体（neo-grotesque）：中性、精确、无衬线，靠字重与尺度拉开层级 | Microsoft YaHei | Arial | sans-serif |
| Body | 同一族的常规字重，小而准 | Microsoft YaHei | Arial | sans-serif |
| Display | 建筑尺度的重量级怪诞体，只承担数字与章节序号 | Arial Black | Arial Black | sans-serif |
| Numeral | 同 Display，用于章节巨大序号 | Arial Black | Arial Black | sans-serif |
| Data | 等高线性数字，保证图表刻度与表格数值可读 | Arial | Arial | sans-serif |

- **Title stack**: `"Microsoft YaHei", Arial, sans-serif`
- **Body stack**: `"Microsoft YaHei", Arial, sans-serif`
- **Display stack**: `"Arial Black", "Microsoft YaHei", sans-serif`
- **Numeral stack**: `"Arial Black", "Microsoft YaHei", sans-serif`
- **Data stack**: `Arial, "Microsoft YaHei", sans-serif`
- **Role rationale**: Display / Numeral 用 Arial Black，因为 swiss-minimal 的"建筑尺度巨大数字"是本卷反复出现的构图骨架（封面对照数、三个章节序号、五处 hero 数字），中性正文族撑不起这个角色；Data 用 Arial 领先，是因为八个原生图表与一张原生表格的刻度、数值与年份全部是拉丁数字，需要等高线性数字而不是 CJK 族的数字形。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 44 |
| Subtitle | 32 |
| Lead | 30 |
| Annotation | 18 |
| Footnote | 16 |
| Display | 96 |
| Numeral | 160 |
| Data | 20 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 每页从左上角的断言标题起读，向下或向右交给一个占版面主导的几何面（图表、表格、巨大数字）；红色标点标出这一页唯一要被记住的数值。
- **Composition tendency**: 非对称分割，内容齐同一条轴；每页恰好一个建筑尺度的元素（大几何面 / 巨大数字 / 满宽图表）；有意留出 40–60% 负空间的页与信息密集页交替。
- **Cross-page continuity**: 标题永远左上齐 x=72；一条 4px 强调色规则线在标题下方复现并按页角色变长度；章节序号用同一 Numeral 角色；页脚来源行永远在 y≈672 左齐。
- **Spacing posture**: 变化：anchor 与 breathing 页大留白，dense 页在栅格内紧凑但不越过沟槽。
- **Spacing anchors**: page margin 72px；block gap 32px；column gutter 24px；corner radius 0px（瑞士方角，圆角为 0 是本卷的身份）；body leading 36px。

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 1.5
- **Brand-logo library**: 无（内容中不出现需要真实品牌标识的公司、产品或服务）

| Icon Path | Suitable Scenarios |
| --- | --- |
| icons/tabler-outline/solar-panel.svg | 光伏本体、发电侧主题标记 |
| icons/tabler-outline/building-factory-2.svg | 制造、产能、供应链 |
| icons/tabler-outline/battery-3.svg | 储能、电池成本 |
| icons/tabler-outline/plug-connected.svg | 并网、接入、电网连接 |
| icons/tabler-outline/clock.svg | 等待时长、排队、时间成本 |
| icons/tabler-outline/trending-down.svg | 成本下降、价格下行 |
| icons/tabler-outline/trending-up.svg | 成本回升、反向趋势 |
| icons/tabler-outline/alert-triangle.svg | 边界条件、指标免责、反面事实 |
| icons/tabler-outline/link.svg | 来源链接 |
| icons/tabler-outline/arrow-narrow-right.svg | 判断到建议的指向 |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P02 | chart | line_chart | 呈现光伏 LCOE 十七年逐年变化与 2021 年拐点 |
| P03 | chart | horizontal_bar_chart | 在同一口径下比较十种新增电源的成本区间 |
| P06 | chart | area_chart | 呈现组件价格随年份塌缩的量级 |
| P09 | chart | stacked_bar_chart | 对比 2010 与 2024 年系统成本的五个分项构成 |
| P10 | chart | line_chart | 呈现储能度电成本 2020–2026 的区间走向 |
| P12 | chart | column_chart | 比较三个年份的并网中位等待时长 |
| P13 | chart | grouped_bar_chart | 比较四个欧洲市场同月负电价小时数的同比变化 |
| P14 | table | comparison_matrix | 对照四家机构 LCOE 口径的地域、补贴、单位与最新值 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

## IX. Content Outline

### Part 1: 结论与情境

#### Slide 01 - 封面

- **Audience move**: 从"光伏便宜是个已知的好消息"→ 意识到同一条成本曲线里藏着两个方向相反的事实，必须重新看。
- **Relationships**: contrast — 两个方向相反的成本变化率（2009–2026 累计 −81% 与 2021–2026 回升 +85%）来自同一条 Lazard 序列，互为对照。
- **Composition**: 建筑尺度的两个对照数字占据版面主导，断言标题在其上或其左；红色只落在其中一个数字上。
- **Cover impact**: 钩子（binding）——同一条成本曲线，先降 81%，又涨 85%。构图为 Reference。
- **Title**: 光伏已是最便宜的新增电源，但它不会自动更便宜
- **Core message**: 同一条曲线上的两个数字，决定了这份材料要讲的全部内容。
- **Content**:
  · −81%：公用事业级光伏 LCOE 2009–2026 累计降幅（Lazard，美国无补贴口径，CAGR −10%）
  · +85%：同一序列自 2021 年低点到 2026 年的回升（CAGR +12%）
  · 副标题：为什么会降、为什么又涨、以及现在真正卡住它的是什么
  · 页脚口径行：全卷数值均标注来源与年份；Lazard 与 IRENA 口径不同，不做平均
- **Fact IDs**: F003, F004
- **Motion suggestion**: 两个对照数字按"先降后涨"的语义顺序先后进入；红色规则线作为承接物，从封面交给 P02。

#### Slide 02 - 成本曲线与拐点

- **Audience move**: 从"光伏一直在变便宜"→ 看到曲线在 2021 年触底并已连续数年上行，且知道原因与技术无关。
- **Relationships**: order — 2009 至 2026 的逐年 LCOE 构成一条时间序列；contrast — 2009–2021 的下降段与 2021–2026 的上升段在同一条线上方向相反。
- **Composition**: 满宽折线占据下三分之二，拐点是全页唯一的红色焦点；标题与一句 takeaway 压在左上；资本成本敏感性作为右上角的小注解块。
- **Title**: 十七年降 81% 之后，光伏成本在 2021 年触底、回升 85%
- **Core message**: 成本曲线已经转向，"会一直更便宜"不再是可以默认的前提。
- **Content**:
  · Lazard 公用事业级光伏 LCOE 均值序列（USD/MWh，美国无补贴）：2009 $359 · 2010 $248 · 2011 $157 · 2012 $125 · 2013 $98 · 2014 $79 · 2015 $64 · 2016 $55 · 2017 $50 · 2018 $43 · 2019 $40 · 2020 $37 · 2021 $36（历史最低）· 2023 $60 · 2024 $61 · 2025 $58 · 2026 $69
  · Lazard 未发布 2022 年版本，序列在 2021 与 2023 之间断一年，图上必须留断点、不得插值
  · 对照锚：同期陆上风电只降 52%（CAGR −4%），光伏是所有电源里下降最快的
  · 转向的原因是资本成本：同一版 Lazard 敏感性表里，税后 IRR/WACC 4.2% 时 $53、基准 7.7% 时 $69、10.0% 时 $83——利率本身就能让光伏贵约六成，与技术进步无关
  · 来源行：Lazard LCOE+ 2026 Edition（LCOE v19.0），美国、无补贴
- **Visualization**: `lcoe-trend` — 值驱动折线，横轴为年份（2022 缺口保留），纵轴 USD/MWh；拐点标注 2021 $36 与 2026 $69。
- **Native-ready**: lcoe-trend=yes
- **Fact IDs**: F001, F002, F003, F004, F005, F081
- **Motion suggestion**: 折线沿阅读路径由左至右建立后，拐点标注最后出现；红色规则线自 P01 承接。

#### Slide 03 - 今天的位置

- **Audience move**: 从"光伏大概比较便宜"→ 能在同一张标尺上说出光伏相对天然气、燃煤、核电的确切位置，同时知道这张标尺没算什么。
- **Relationships**: order — 十种电源按成本下限排序；contrast — 每种电源的下限与上限构成一个区间，区间之间互相比较；overlap — 光伏、陆上风电与天然气联合循环的区间彼此重叠，最便宜不等于永远更便宜。
- **Composition**: 横条区间图占版面主导并靠右延伸，标题与免责块在左；地域差异作为底部一行小字对照。
- **Title**: 在同一口径下，光伏与陆上风电是最便宜的两种新增电源
- **Core message**: 光伏的成本优势是真的，但它成立在一张明确排除了并网成本的标尺上。
- **Content**:
  · Lazard LCOE v19.0（2026，美国、无补贴，USD/MWh）：陆上风电 $37–$99 · 公用事业级光伏 $40–$98 · 陆上风电+储能 $49–$140 · 天然气联合循环 $51–$129 · 光伏+储能 $61–$156 · 燃煤 $72–$177 · 社区级与工商业光伏 $88–$197 · 海上风电 $105–$167 · 天然气调峰 $144–$276 · 美国核电 $175–$255
  · 必须随图的假设：天然气 $3.45/MMBTU、燃煤 $1.47/MMBTU、核燃料 $0.85/MMBTU；资本结构 60% 债务（8%）+ 40% 权益（12%）
  · 燃煤区间由 LCOE v14.0 结果按通胀调整而来，不宜作强论据；核电区间基于 Vogtle 3、4 号机组公开造价
  · Lazard 自述边界：该分析不考虑部分可再生能源的间歇性特征，也不考虑新增可再生部署带来的电网影响
  · 全球口径的另一面（IRENA，不与上表同图）：2024 年新建光伏比成本最低的化石方案便宜 41%，陆上风电便宜 53%；当年投产的新建可再生项目 91% 成本低于新建化石机组
  · "最便宜"不是全球均匀的：中国 2025 年 0.036、印度 0.035、美国 0.062、德国 0.065、日本 2024 年 0.123（IRENA，constant 2025 USD/kWh）
- **Visualization**: `source-cost-range` — 值驱动横条，每种电源由"成本下限"与"区间宽度"两段构成，合计为上限；条端直接标注 `$低–$高`。
- **Native-ready**: source-cost-range=yes
- **Fact IDs**: F011, F012, F013, F014, F015, F016, F017, F018, F019, F020, F024, F025, F026, F084

#### Slide 04 - 三条判断

- **Audience move**: 从"知道两个事实"→ 拿到接下来三段论证的完整地图，知道每一段回答哪个问题。
- **Relationships**: parent — 一个总判断分解为三条子判断，按生产端 / 系统端 / 电网端划分，覆盖成本从产生到兑现的完整链条且彼此不重叠；order — 三条判断按"成本从哪来 → 成本挪到哪 → 现在卡在哪"的论证次序展开。
- **Composition**: 顶部一条总判断横贯全宽，其下三个等宽分支自左向右并置，分支之间用可见的栅格模数线分隔；三个序号用 Numeral 角色。
- **Title**: 三个问题，三条判断：成本从哪来、还会不会降、真正卡在哪
- **Core message**: 便宜是可解释的，不便宜也是可预期的，而现在的瓶颈已经不在价格上。
- **Content**:
  · 总判断：光伏的成本优势由制造规模的学习率产生，已经转移到系统侧，并正在被电网侧的稀缺重新定价
  · 01 成本下降来自学习率——累计装机每翻一番，组件价格下降 20%，四十余年未变（Q：便宜从哪来）
  · 02 成本中心已从组件挪到 BOS 与储能——2024 年组件只占系统成本的 30%（Q：还会继续便宜吗）
  · 03 真正的稀缺是并网容量与消纳空间——美国并网中位等待已达 61 个月（Q：什么时候它不便宜）
  · 每条判断后续用一到两页证据展开，最后一页给决策建议
- **Fact IDs**: F027, F045, F060
- **Motion suggestion**: 总判断先出现，三个分支按 01→02→03 的阅读路径依次进入；三个序号块分别作为承接物交给 P05 / P08 / P11。

### Part 2: 判断一 · 便宜来自制造规模

#### Slide 05 - 判断一

- **Audience move**: 从"三条判断的地图"→ 进入第一条判断，接受成本下降有一个可命名的机制。
- **Relationships**: none
- **Composition**: 建筑尺度的 `01` 占据左侧整高，断言句在右侧齐上边；大面积留白，无其他元素。
- **Title**: 便宜来自学习率，不是补贴，也不是运气
- **Core message**: 光伏的价格下降有一条可以命名、可以外推、也可以证伪的因果机制。
- **Content**:
  · 章节序号 01
  · 一句提问：如果不是补贴，那 81% 是从哪里来的
- **Motion suggestion**: `01` 序号块自 P04 的第一个分支承接过来，是本卷第一组 Morph 端点。

#### Slide 06 - 学习率

- **Audience move**: 从"成本下降是趋势"→ 能说出这条趋势的定量规律，以及它为什么不适用于煤电。
- **Relationships**: link — 累计装机翻番与组件价格下降 20% 之间是源文陈述的因果关系；order — 1975 至 2024 的组件价格构成一条时间序列。
- **Composition**: 左侧一对建筑尺度的起止价格数字，右侧是价格塌缩的面积图；机制句压在两者之间的横向规则线上。
- **Title**: 累计装机每翻一番，组件价格下降 20%——四十年未变
- **Core message**: 光伏与煤电在因果结构上不同：它遵循 Wright's Law，价格下降速率随累计产量保持恒定。
- **Content**:
  · 学习率：全球累计光伏装机每翻一番，组件价格下降 20%，已持续四十余年（Our World in Data）
  · 同一规律以 SunPower 创始人 Richard Swanson 命名为 Swanson's law
  · 量级：组件价格 1975 年 132.38 美元/瓦 → 2024 年 0.265 美元/瓦（constant 2025 USD）
  · 可画的近段序列（constant 2025 USD/W）：2010 $2.51 · 2015 $0.736 · 2020 $0.370 · 2021 $0.332 · 2022 $0.366 · 2023 $0.322 · 2024 $0.265
  · 分母：全球累计装机 1975 年 0.54 MW → 2010 年 39,849 MW → 2020 年 710,726 MW → 2025 年 2,378,042 MW
  · 为什么这条规律要单独占一页：大多数技术不遵循 Wright's Law——自行车、冰箱、燃煤电厂的价格都不呈指数下降；只有光伏、电池与计算机做到了
  · 整理（本卷的读法，非源文结构）：1975–2005 的价格区间在线性坐标上无法与近段同图呈现，因此图只画 2010 年以后，早期量级以数字给出
- **Visualization**: `module-price-decline` — 值驱动面积图，横轴年份 2010–2024，纵轴 constant 2025 USD/W。
- **Native-ready**: module-price-decline=yes
- **Fact IDs**: F027, F028, F029, F030, F031, F032

#### Slide 07 - 规模与当前低价的成分

- **Audience move**: 从"便宜是学习率的结果"→ 意识到当前这个价位里还含着一层制造商亏损，不能直接外推。
- **Relationships**: link — 产能过剩、低于成本的价格与制造商亏损构成源文陈述的因果链；contrast — 全球均价与美国、印度到岸价之间存在数倍差异。
- **Composition**: 三个 KPI 数字沿顶部一条基线并置，其下用一条横向规则线分开因果链叙述与地域差异；无图表，纯排版承担密度。
- **Title**: 今天的组件价格里含着制造商的亏损，它不是可持续的均衡价
- **Core message**: 学习率解释了长期趋势，但当前这个具体价位是产能过剩造成的，不能拿来外推。
- **Content**:
  · 规模：2025 年全球新增光伏 647 GW 创纪录，较 2024 年 582 GW 增长 11%（Ember）；IEA 口径为同比约 +12%、首次突破 600 GW，并预计 2030 年达 700 GW/年
  · 光伏占 2025 年全球可再生电力新增装机的近 80%；中国 2025 年投运近 370 GW（IEA）/ 378 GWdc（Ember，占全球 58%），同比 +13%
  · 产能：2024 年全球组件制造产能 1,100–1,350 GW，是当年装机量的两倍以上；产能利用率从 2023 年的 60–80% 降至 55–65%，短期可能跌破 50%
  · 价格：2024 年全球组件批发现货均价同比下跌近 45% 至 USD 0.09/W，2025 上半年稳定于该水平，且低于包括中国头部企业在内的多数制造商的生产成本
  · 亏损：中国光伏价格自 2023 年以来跌超 60%，头部制造商利润率降至 −10%，2024 年初以来累计亏损接近 USD 50 亿
  · 这个价格不是全世界都能买到：2025 上半年运往美国的组件均价 USD 0.27/W（全球均价三倍），印度本土制造组件 USD 0.15/W（高约 70%）
  · 集中度不会消失：到 2030 年中国仍将占供应链制造产能的 75–95%，关键环节集中度维持在 90% 以上
- **Fact IDs**: F033, F034, F035, F036, F037, F039, F040, F041, F042, F043

### Part 3: 判断二 · 钱已经从组件挪走

#### Slide 08 - 判断二

- **Audience move**: 从"理解了成本从哪来"→ 转向"这些钱现在花在哪里"。
- **Relationships**: none
- **Composition**: 与 P05 同构：建筑尺度的 `02` 占据左侧整高，断言句在右侧齐上边。
- **Title**: 成本中心已经从组件挪到了 BOS 与储能
- **Core message**: 继续盯着组件价格谈判，是在为一个已经不是主要成本项的东西付出注意力。
- **Content**:
  · 章节序号 02
  · 一句提问：组件降了九成之后，剩下的钱在哪里
- **Motion suggestion**: `02` 序号块自 P04 的第二个分支承接过来。

#### Slide 09 - 成本结构

- **Audience move**: 从"组件是光伏成本的主体"→ 看到组件已不再占多数，并且系统总成本本身也在 2021 年见底。
- **Relationships**: parent — 系统总成本分解为组件、逆变器、BOS、人工、软成本五个分项；contrast — 2010 与 2024 两个年份的构成在同一标尺上对比。
- **Composition**: 两根堆叠柱并置于版面中部偏右，同一标尺；左侧是分项变化的读法与 IRENA 全球口径的对照；系统总成本的 2021 年低点作为红色标点。
- **Title**: 组件从系统成本的 44% 降到 30%，系统总成本却在 2021 年见底
- **Core message**: 组件的绝对值降了近九成，但它已经不是最大的那一项，而总成本已经不再单调下降。
- **Content**:
  · NREL 美国公用事业级光伏系统成本分项（2024 USD，$/Wdc）——2010 年：组件 $3.08 · 逆变器 $0.35 · BOS $0.96 · 人工 $0.79 · 软成本 $1.77，合计 $6.94
  · 2024 年：组件 $0.35 · 逆变器 $0.03 · BOS $0.33 · 人工 $0.24 · 软成本 $0.20，合计 $1.15
  · 读法（本卷整理）：2010 年组件是最大单项；2024 年组件 $0.35 与 BOS+人工 $0.57 已经易位
  · 系统总成本序列（$/Wdc，2024 USD）：2010 $6.94 · 2012 $4.03 · 2014 $2.76 · 2016 $1.99 · 2018 $1.43 · 2020 $1.23 · 2021 $1.08（最低）· 2022 $1.14 · 2023 $1.24 · 2024 $1.15；基准系统为 100 MWdc 单轴跟踪电站
  · 全球口径对照：IRENA 称 2010–2024 年总安装成本降 87% 至 USD 708/kW；IRENA 另一份报告给出 2024 年 USD 691/kW——两个数出自不同报告，择一使用并注明报告名，不做平均
- **Visualization**: `system-cost-split` — 值驱动堆叠柱，两个类别（2010、2024），五个分项系列，单位 $/Wdc。
- **Native-ready**: system-cost-split=yes
- **Fact IDs**: F044, F045, F046, F047, F048

#### Slide 10 - 储能的两个相反方向

- **Audience move**: 从"电池在变便宜所以储能会变便宜"→ 分清电芯价格与项目度电成本是两件事，并拿到一个可用的合成指标。
- **Relationships**: contrast — 电芯价格下行与储能 LCOS 上行是两个方向相反的事实；order — 2020 至 2026 的 LCOS 构成一条时间序列。
- **Composition**: 左列三个 KPI 数字自上而下排列（电池组均价、储能专用电芯、firm LCOE），右侧是 LCOS 区间折线；两者之间一条竖直规则线把"降"与"涨"分在两边。
- **Title**: 电芯价格在创新低，储能度电成本却涨了 39%
- **Core message**: 电芯便宜不等于储能便宜；决策要看的是项目级的度电成本，不是电芯报价。
- **Content**:
  · 在降：BNEF 2025 年调查，全球电池组均价同比 −8% 至历史新低 USD 108/kWh，自 2010 年（约 USD 1,474/kWh，real 2025 USD）以来降 93%
  · 储能专用电池组已降至 USD 70/kWh，同比 −45%，成为最便宜的细分市场；电动车电池组 USD 99/kWh
  · IRENA 口径：电池储能成本 2010–2024 年降 93%，从 USD 2,634/kWh 到 USD 197/kWh，2025 年再降约 30%
  · 在涨：Lazard 公用事业级独立储能（100 MW/4 小时）LCOS 序列（$/MWh）：2020 $132–$245 · 2021 $131–$232 · 2023 $200–$257 · 2024 $170–$296 · 2025 $115–$254 · 2026 $210–$292；2020–2026 累计上涨 39%（CAGR 6%）
  · 原因：2026 年 LCOS 逆转上一年降势，主因是锂电池进口关税落地，切断了此前压低成本的低价中国电芯供应
  · 可用的合成指标：IRENA 2026 年 5 月提出 firm LCOE（可持续稳定供电的项目级成本），2025 年高资源区为 USD 54–82/MWh，预计 2030 年再降约 30%、2035 年降约 40% 且最优站点低于 USD 50/MWh
  · firm LCOE 案例：中国在 90% 可靠性下低至 USD 30/MWh，99% 可靠性下约 USD 46/MWh；巴西、印度、南非、澳大利亚与海湾地区为 USD 65–82/MWh
  · Lazard 同口径的"光伏+储能"为 $61–$156/MWh
- **Visualization**: `storage-lcos-range` — 值驱动折线，两条系列（LCOS 下限、上限），横轴年份 2020–2026（2022 无版本，保留断点），纵轴 $/MWh。
- **Native-ready**: storage-lcos-range=yes
- **Fact IDs**: F012, F049, F050, F051, F052, F053, F054, F055, F056, F057

### Part 4: 判断三 · 真正的约束在电网

#### Slide 11 - 判断三

- **Audience move**: 从"成本账已经算清"→ 转向"便宜的电为什么送不出去"。
- **Relationships**: none
- **Composition**: 与 P05 / P08 同构：建筑尺度的 `03` 占据左侧整高，断言句在右侧齐上边。
- **Title**: 稀缺的不是价格，是并网容量与消纳空间
- **Core message**: 排在队列里的便宜电，不产生任何度电价值。
- **Content**:
  · 章节序号 03
  · 一句提问：如果价格已经不是问题，那什么是
- **Motion suggestion**: `03` 序号块自 P04 的第三个分支承接过来。

#### Slide 12 - 并网排队

- **Audience move**: 从"电网是个模糊的障碍"→ 拿到三个可引用的量：等待时长、队列容量、电网投资缺口。
- **Relationships**: order — 2008、2015、2025 三个年份的中位等待时长构成一条上升序列；membership — 队列中的 2,061 GW 按光伏、储能、风电、天然气分组。
- **Composition**: 三根柱子占据左半版面并向上生长，2025 年的 61 个月用红色标点；右半是队列构成与全球尺度的三行数字；柱与数字共用同一条基线。
- **Title**: 并网中位等待从 22 个月拉长到 61 个月，排队里压着 2,061 GW
- **Core message**: 项目从"能建"到"能发电"之间的时间成本，已经超过了组件降价能带来的收益。
- **Content**:
  · Berkeley Lab《Queued Up: 2026 Edition》：2025 年建成投运项目从提出并网申请到商业运行的中位耗时 61 个月；2015 年建成的项目为 36 个月，2008 年为 22 个月——十七年间翻了近三倍
  · 截至 2025 年底，美国输电并网队列中有 8,244 个在途项目、合计约 2,061 GW（发电 1,312 GW + 储能 749 GW）
  · 队列构成：光伏 773 GW（同比 −19%）· 储能 749 GW（−16%）· 风电 220 GW（−19%）；而天然气容量同比激增 86% 至 253 GW
  · 另有 549 GW 已签或已出草签并网协议但尚未投运（光伏 256 GW、储能 161 GW、风电 76 GW、天然气 45 GW）
  · 全球尺度（IEA）：至少 3,000 GW 可再生项目在电网接入队列等待，其中 1,500 GW 已进入后期阶段，相当于 2022 年全球新增风光装机的五倍
  · 要实现各国既定目标，2040 年前需新增或更换 8,000 万公里输配电线路，相当于现有全球电网的总长度
  · 电网年投资自 2015 年以来长期停滞在约 USD 3,000 亿，需在 2030 年前翻倍至每年 USD 6,000 亿以上
- **Visualization**: `queue-wait-months` — 值驱动柱状，三个类别（2008、2015、2025），单位为月。
- **Native-ready**: queue-wait-months=yes
- **Fact IDs**: F058, F059, F060, F061, F062, F063, F064

#### Slide 13 - 弃电、负电价与价值贬损

- **Audience move**: 从"消纳是个技术问题"→ 看到它已经变成价格问题：同样的度电成本，卖出的钱在变少。
- **Relationships**: contrast — 2025 与 2026 同月负电价小时数在四个市场上逐一对照；link — 渗透率上升、弃电与负电价、捕获率下降构成源文陈述的因果链。
- **Composition**: 分组横条占据右侧，左侧自上而下是中国、加州、德国三段证据；捕获率的崩塌数字作为红色标点压在最下方。
- **Title**: 弃电与负电价同步上升，光伏卖出的每度电正在贬值
- **Core message**: LCOE 在跌，但每度电能卖到的钱跌得更快——这是"最便宜的电"最锋利的反例。
- **Content**:
  · 弃光可治理，但治理有代价（IEA）：中国 2010 年代初弃风弃光率曾高达 15%，通过 2018 年起的省级 <5% 目标、电价机制改革与年均 USD 880 亿电网投资降至 3% 以下
  · 2024 年为缓解拥堵，中国把高渗透率省份的上限由 5% 提高到 10%，当年弃光率升至 3.2%、弃风率 4.1%，各升逾一个百分点
  · 加州（EIA）：2024 年 CAISO 弃掉风光出力 340 万 MWh，同比 +29%，其中光伏占 93%，最集中于春季；风光装机从 2014 年 9.7 GW 增至 2024 年底 28.2 GW，当年通过 WEIM 避免逾 274,000 MWh 弃电（约占弃电量 8%）
  · 负电价小时（IEA，2023→2024）：法国增 12 倍至约 350 小时 · 德国翻倍至约 460 小时 · 英国增 9 倍至约 230 小时；西班牙 2021 年年中前不允许负电价，2025 年 1–7 月已出现 460 个
  · 月度对照（Pexapark，2025→2026 同月）：法国 4 月 90→139 小时 · 德国 75→123 · 波兰 75→87 · 西班牙 2 月 0→148
  · 捕获系数同步崩塌：法国 4 月 0.42→0.10（−75%）· 德国 0.40→0.26 · 波兰 0.54→0.40 · 意大利 0.75→0.71 · 西班牙 2 月 0.71→0.18
  · 德国 2024 年光伏捕获电价 EUR 47/MWh、捕获率 59%（欧洲最低），2025 年降至约 54%，而 2022 年曾达 98%
  · 成本已经出现但仍不大：德国电网补救成本 >EUR 5/MWh（欧洲最高）、西班牙约 EUR 4/MWh，拥堵管理约占居民电费 0.5–1.5%；美国从 ISO New England 不足 USD 1/MWh 到 MISO 的 USD 12/MWh。这组数字支撑"约束在电网"，不支撑"电网成本已抵消光伏优势"
  · IEA 的判断：弃电与负电价是系统灵活性不足的信号；需求响应与加强互联可抑制弃电、降低负电价频率并限制价格自噬
- **Visualization**: `negative-price-hours` — 值驱动分组横条，四个市场类别，两个系列（2025 同月、2026 同月），单位为小时。
- **Native-ready**: negative-price-hours=yes
- **Fact IDs**: F065, F066, F067, F068, F069, F070, F086, F087, F088, F089

### Part 5: 边界与建议

#### Slide 14 - 口径与边界

- **Audience move**: 从"记住了一堆数字"→ 知道哪些数字可以放在一起比，哪些不可以，以及 LCOE 这个指标本身没算什么。
- **Relationships**: contrast — 四家机构的口径在地域、补贴处理、单位与最新值四个维度上逐项对照，可比维度相同但数值不可互换。
- **Composition**: 原生对照表占据版面主体并齐左边距，表下一条规则线，其下是 LCOE 指标未纳入项的三行清单；红色只落在"不可平均"这一句上。
- **Title**: "最便宜"有四种口径，它们不可平均、也不可互换
- **Core message**: 引用任何一个 LCOE 数字之前，先说清它是哪一家、哪个地域、含不含补贴、以哪一年的美元计。
- **Content**:
  · 对照表四行（机构 / 地域与口径 / 单位与基年 / 最新值）：
    Lazard LCOE v19.0 — 美国、无补贴、新建项目区间 — USD/MWh — 2026 年公用事业级光伏 $40–$98（均值 $69）
    IRENA — 全球加权平均、实际投产项目 — USD/kWh，报告当年美元 — 2024 年 0.043，2025 年 USD 44/MWh
    NREL — 美国基准电站（100 MWdc 单轴跟踪） — ¢/kWh，2024 USD — 2024 年 4.8¢
    BloombergNEF — 全球电池组价格调查 — USD/kWh，real 2025 USD — 2025 年 108（储能专用 70）
  · 同一年可以相差一倍以上：2024 年 Lazard 均值 $61/MWh vs IRENA $43/MWh——这是口径差异，不是矛盾
  · Lazard 明确未纳入：输电队列改革与网络升级等输电事项 · 拥堵、弃电或其他并网整合成本 · 许可与其他开发成本
  · 正面回应：Lazard 另有 Cost of Firming Intermittency 分析，结论是即便计入调峰成本，可再生能源与新建燃气联合循环相比总体仍具竞争力
  · 权威原话（限定条件是原文的一部分，不得删除）："For projects with low-cost financing that tap high-quality resources, solar PV is now the cheapest source of electricity in history."——IEA《World Energy Outlook 2020》，2020 年 10 月
- **Visualization**: `lcoe-methodology-table` — 纯文字单元格网格，行为机构，列为地域与口径、单位与基年、最新值。
- **Native-ready**: lcoe-methodology-table=yes
- **Fact IDs**: F002, F007, F008, F010, F011, F049, F051, F079, F084, F085, F090

#### Slide 15 - 决策建议与来源

- **Audience move**: 从"接受了三条判断"→ 拿到四条可以立刻改变投资排序的动作，并能自己复核每一个数字。
- **Relationships**: order — 四条建议按"先纠正认知、再放弃假设、然后换指标、最后换稀缺资源"的执行次序排列；link — 每条建议对应前面的一条判断。
- **Composition**: 四条建议以编号横向条带自上而下排列，占版面主体；来源链接压在底部作为一条紧凑的规则线下清单。
- **Closing impact**: 收束（binding）——把预算从最便宜的组件，移到最好的并网位置。构图为 Reference。
- **Title**: 把预算从最便宜的组件，移到最好的并网位置
- **Core message**: 三条判断只指向一个动作：重新排序稀缺资源。
- **Content**:
  · 01 不要用 2020 年前的价格表做 2026 年的决策——同一口径下光伏 LCOE 已降 81–90%，且已是多数市场最便宜的新增电源
  · 02 也不要假设它会一直更便宜——两条独立序列都在 2021 年触底并回升，当前低组件价含卖方亏损成分，而资本成本是与技术进步无关的第二个变量
  · 03 把投资重心从"买便宜组件"转向"买可调度性与并网位置"——成本中心已从组件转向 BOS 与储能，储能 LCOS 正在上行，而 firm LCOE 已是可用的决策指标
  · 04 稀缺资源是并网容量与消纳空间，不是价格——美国队列中位等待 61 个月、全球 3,000 GW 排队、2040 年前需再造一个全球电网、欧洲捕获率与负电价同步恶化
  · 来源（原生超链接）：Lazard LCOE+ 2026 Edition · IEA Renewables 2025 · IRENA Renewable Power Generation Costs in 2024 · NREL/TP-7A40-92536 · Berkeley Lab Queued Up 2026 · BloombergNEF 2025 电池价格调查 · Our World in Data 学习曲线与组件价格 · IEA Electricity Grids and Secure Energy Transitions
  · 取数纪律行：每个数字均标注来源与年份；不同机构口径并列写出，不做平均、不做跨口径换算
- **Fact IDs**: F003, F004, F009, F024, F040, F042, F045, F054, F056, F060, F062, F063, F081, F086
- **Motion suggestion**: 四条建议按编号顺序依次进入；来源清单最后整体出现。

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 每页以该页的判断句开场，再用连贯散文补上支撑事实；数字口径（哪一家、哪个地域、含不含补贴、哪一年的美元）在口头讲清楚，页面上未写下的限定条件由讲述补齐；不引入源文以外的事实；百分数与货币按中文口语读法展开
- **Total duration**: 约 25 分钟，15 页平均每页 90–110 秒；anchor 与 breathing 页更短，数据页更长
- **Notes style**: 结论驱动、克制、有权威感——顾问在决策会上给判断的语气
- **Presentation purpose**: 先纠正过时的价格认知并解释成本下降的机制，再主动暴露成本曲线转向与电网侧约束，最后推动决策者把预算从组件价格转向并网位置与可调度性
