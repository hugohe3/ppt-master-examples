<!-- ppt-master-schema: design-spec/v1 -->
# 电动车增长的下一站 - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | 电动车增长的下一站:2026–2028 车企市场优先级决策 |
| Canvas Format | PPT 16:9 (1280 × 720) |
| Page Count | 14 |
| Primary Language | zh-CN |
| Target Audience | 整车企业的高管团队与海外业务/战略负责人;熟悉本国市场,但对各海外市场的真实增速与结构变化只有零散印象 |
| Communication Intent | 先给出判断——全球电动车的增量重心正在从欧美转向新兴市场、PHEV 是低渗透市场的破冰产品——再用 IEA 数据逐条证明,最后请管理层对 2026–2028 的市场优先级与产品组合节奏做出决定 |
| Desired Audience Outcome | 管理层接受"美国停滞、欧洲分化、新兴市场加速"三个事实判断,批准三级市场优先级和 PHEV 先行的产品节奏,并指定本季度要落实的三件事 |
| Core Message / Ask / Action | 2025 年全球电动车 2,100 万辆、渗透率 25%,但增量结构已变:美国销量首次下滑、欧洲靠英德反弹、中国之外的新兴市场增量首次超过欧洲。2026–2028 的增量投入应按"中国深耕、欧洲选点、东南亚/拉美/印度抢滩、美国守势"分级,并以 PHEV 打开低渗透市场 |
| Delivery Context | 以阅读为主的管理层讨论稿:先作为会前预读发出,会上由战略负责人逐页讲解、当场讨论;每页要能独立成立 |
| Artifact Afterlife | 作为决策记录留档,后续可按季度用同口径数据更新;数字与来源要经得起追问 |
| Reading Mode | text(文档密度:正文 14px,咨询文档惯例) |
| Content Strategy | 事实与数值全部来自导入的 IEA 工作簿;结论、分级和路线图由这些数字推导,推导公式写在备注中;不引入工作簿之外的事实 |
| Design Style | 麦肯锡式咨询决策文档:金字塔论证 + 瑞士网格的克制版式,行动标题、编号图表、每页来源行、追踪器与页码 |
| AI Image Acquisition Path | not applicable |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — workflow default (proactive policy true);备注承载推导公式与讲解口径 |
| Custom Animations | enabled — explicit user instruction(示例库要求每份示例带自定义动画);对象级动画 + Morph 承接 |
| Narration Audio | disabled — workflow default |
| Created Date | 2026-09-05 |

- **Template Application**: 采用已安装的 mbb-consulting 方法模板(自 consulting-decision 继承论证方法,视觉改为文档密度惯例):答案先行的论证链(总答案 → 关键支撑 → 页面信息 → 证据)、事实/假设/推论/建议四类表述分开、每页一个行动标题;其 swiss-minimal 视觉种子在本项目扩展为咨询文档惯例(见 §III),页面为自由设计的扁平结构,不引入模板原型或原生结构。

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 上 56 / 下 48 / 左 56 / 右 56 |
| Content Area | x 56–1224,y 56–648;标题区 y 56–120,正文区 y 140–620,页脚(来源行 + 页码)y 656–690 |

## III. Visual Theme

### Theme Style

- **Mode**: pyramid
- **Visual style**: custom
- **Visual Style References**: swiss-minimal
- **Visual Style Behavior**: 白底黑字的咨询决策文档,取文档密度而非演示密度(正文 14px ≈ 10.5pt,与咨询公司 11–12pt 的惯例一致)。每页一个两行以内的行动标题(陈述句,写清"所以呢")顶在页首,标题下一行灰色单位/副题行,再一条深色细横线;右上角追踪器与「讨论稿」贴纸,页脚编号脚注加来源行,右下角页码;正文区左 2/3 并置两到三个证据面板(各自带加粗小标题、单位行、直接标注、CAGR 括注),右 1/3 是「关键信息」编号要点栏,图上用编号圆点 callout 与要点对应;所有面为纯平面,只用发丝线(1px 灰)和留白分隔,不用卡片、圆角、阴影、渐变;色彩只做语义:藏青为主系列与标题,电蓝只标当页要读者看的那一个数字或系列,灰色承担其余;深色满版只出现在封面与章节页;表格是细横线表,数字右对齐、等宽字体;字号层级靠字重与大小,不靠装饰。
- **Theme**: 一份把答案写在标题里的决策文档——读者只读 14 个标题就能复述结论,再往下看是逐页的证据
- **Tone**: 冷静、精确、克制;每一句都可追溯到工作簿里的一个单元格或一个公式

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #FFFFFF | 页面底色 |
| Secondary background | #F2F2F2 | 附录与表格的隔行底、章节页的浅色分区 |
| Primary | #051C2C | 标题、主系列(中国/全球)、封面与章节页满版 |
| Accent | #2251FF | 当页唯一的强调:被讨论的数字、系列或表格行 |
| Secondary accent | #8FB8FF | 次要系列(欧洲/PHEV 等)与强调色的浅阶 |
| Body text | #333333 | 正文、表格正文 |
| Secondary text | #7F7F7F | 来源行、页码、追踪器、轴标签、注释 |
| Divider | #B7B7B7 | 标题下横线、表格表头线 |
| Grid | #E3E3E3 | 图表网格线、表格隔行线 |
| Surface | #F7F7F7 | 图表底板、结论框(仅作面,无边框) |
| Negative | #B3261E | 下滑/风险的唯一警示色(美国销量下滑、风险触发) |

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 无衬线 / 粗体,行动标题的权威感 | Microsoft YaHei | Arial | sans-serif |
| Body | 无衬线 / 常规,紧凑可读 | Microsoft YaHei | Arial | sans-serif |
| Data | 无衬线 / 等高数字,右对齐对位 | Arial | Arial | sans-serif |

- **Title stack**: Microsoft YaHei
- **Body stack**: Microsoft YaHei
- **Data stack**: Arial
- **Role rationale**: `data` 用于图表数值、轴标签、表格数字列和英雄数字,Arial 的等高数字在右对齐列里对位整齐;中文标签仍用 Body。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 14 |
| Title | 24 |
| Subtitle | 14 |
| Lead | 16 |
| Annotation | 12 |
| Footnote | 10 |
| Display | 40 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 先读行动标题,再读被电蓝标出的那个数字或系列,最后读图表其余部分与来源行
- **Composition tendency**: 标题区固定在页首;正文区一到三个证据区块沿 12 列网格横向排布,图表占大区块、结论要点占窄栏;结论与建议页用编号列表占满宽度
- **Cross-page continuity**: 追踪器、标题下横线、来源行、页码四件固定;图表编号连续;区域配色固定(中国藏青、欧洲次蓝、美国灰、新兴市场电蓝);Morph 承接:P03 的全球柱承接到 P04 的分区堆叠柱,P07 的新兴市场柱承接到 P10 的优先级表首行
- **Spacing posture**: 证据页 dense,结论与建议页 breathing,封面/章节/附录 anchor
- **Spacing anchors**: 页边距 48;区块间距 20;栏间距 24;圆角 0;正文行距 20

## VI. Icon Usage Specification

- **Primary bundled library**: none

| Icon Path | Suitable Scenarios |
| --- | --- |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P03 | chart | dual_axis_line_chart | 2015–2025 全球电动车销量(柱,左轴)与渗透率(线,右轴) |
| P04 | chart | stacked_bar_chart | 2020–2025 全球销量按中国/欧洲/美国/其他堆叠 |
| P05 | chart | line_chart | 2019–2025 美国、日本、欧洲渗透率走势 |
| P06 | chart | horizontal_bar_chart | 2025 年欧洲主要国家渗透率及两年变化 |
| P07 | chart | grouped_bar_chart | 新兴市场 2023 vs 2025 渗透率对比 |
| P08 | chart | stacked_area_chart | 2019–2025 全球 BEV 与 PHEV 销量堆叠 |
| P09 | chart | waterfall_chart | 2025→2035 STEPS 情景增量按地区分解 |
| P10 | table | comparison_matrix | 市场三级优先级:各市场 2025 销量、渗透率、2035 情景、进入方式 |
| P12 | table | record_table | 风险登记:风险、触发指标、影响、应对 |
| P14 | table | metric_table | 附录:各地区 2020–2025 销量与渗透率 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

## IX. Content Outline

### Part 1: 结论

#### Slide 01 - 封面

- **Audience move**: 不知道这份材料要谈什么 → 知道它回答一个问题:2026–2028 年电动车的增量投向哪里
- **Relationships**: none
- **Composition**: 藏青满版,左侧一枚硕大的白色"25%"作为钩子(2025 年全球渗透率),右侧标题与副题;底部一行"讨论稿 · 数据截至 IEA GEVO 2025"
- **Cover impact**: 钩子=「25%:全球每四辆新车就有一辆是电动车,但增量已经不在欧美」(binding);构图为参考
- **Title**: 电动车增长的下一站
- **Core message**: 2026–2028 年车企的市场优先级需要按新的增量地图重排
- **Content**: 主标题「电动车增长的下一站」 · 副题「2026–2028 车企市场优先级决策」 · 钩子数字 25% + 一句解释 · 底部「管理层讨论稿 · 2026 年 9 月 · 数据来源 IEA Global EV Outlook 2025」

#### Slide 02 - 核心结论

- **Audience move**: 期待一堆图表 → 先拿到三条判断和一个决策请求,知道后面每页在证明什么
- **Relationships**: parent — 总答案统领三条支撑判断;order — 三条判断按"事实 → 推论 → 建议"排列;link — 每条判断指向后文证据页
- **Composition**: 页面上半一句总答案(粗体两行),下半三栏编号判断,每栏末尾标注"见第 N 页";右下角一行"本次请管理层决定的事项"
- **Title**: 增量重心已从欧美转向新兴市场,2026–2028 应分级投入并以 PHEV 打开低渗透市场
- **Core message**: 三个事实判断推出一个分级投入的建议
- **Content**: 总答案一句 · 判断 1「成熟市场见顶:美国 2025 年销量 160 万→150 万首次下滑、渗透率两年停在 10%」 · 判断 2「欧洲靠英德反弹到 28%,但法国持平,增量集中」 · 判断 3「新兴市场加速:东南亚渗透率 8.4%→18%,中美欧之外的市场增量 110 万辆首次超过欧洲的 100 万」 · 推论「PHEV 占全球电动车销量 34%,是低渗透市场的破冰产品」 · 决策请求「批准三级优先级与 PHEV 先行节奏;指定 90 天行动」

### Part 2: 现状与张力

#### Slide 03 - 全球总量

- **Audience move**: 模糊知道"电动车在涨" → 记住两个锚点数:2,100 万辆、25%,五年七倍
- **Relationships**: order — 2015–2025 逐年;link — 销量与渗透率同步抬升
- **Composition**: 左 2/3 为图 1(柱+线双轴),右 1/3 三个要点(2,100 万辆、25%、五年 7 倍)
- **Title**: 2025 年全球电动车销量达 2,100 万辆、渗透率 25%,五年增长七倍
- **Core message**: 电动车已是主流市场而非利基
- **Content**: 图 1「全球电动车销量与渗透率,2015–2025」(销量单位百万辆;渗透率 %) · 要点:2020 年 300 万→2025 年 2,100 万,7.0 倍 · 渗透率 4.4%→25% · 2025 为 IEA 全年估计 · 来源行
- **Visualization**: `world-sales` = 全球销量柱(2015–2025,百万辆,面板 A);`world-share` = 渗透率折线(2015–2025,%,面板 B);Native-ready: world-sales=yes; world-share=yes; key-years=yes

#### Slide 04 - 增长引擎分化

- **Audience move**: 以为增长是普遍的 → 看到 2025 年 400 万辆增量里中国 200 万、欧洲 100 万、美国 −10 万、其他市场 +110 万
- **Relationships**: membership — 全球销量由中国/欧洲/美国/其他四部分构成;contrast — 各部分增量方向相反(美国为负);order — 2020–2025 逐年
- **Composition**: 左 2/3 为图 2 堆叠柱,右 1/3 一张"2025 年增量拆分"小表(四行,美国一行用警示色)
- **Title**: 2025 年 400 万辆增量中,中国贡献一半,美国转负,中美欧之外的市场首次超过欧洲
- **Core message**: 增量地图与存量地图不一样
- **Content**: 图 2「全球电动车销量按地区,2020–2025」(堆叠:中国、欧洲、美国、其他) · 2025 年占比:中国 62%、欧洲 20%、美国 7%、其他 11% · 增量拆分:中国 +200 万、欧洲 +100 万、美国 −10 万、其他 +110 万 · "其他"=全球减中美欧(计算值) · 来源行
- **Visualization**: `regional-mix` = 2020–2025 堆叠柱(百万辆,四个系列,面板 A);`increment-2025` = 2025 年增量横向条形(四地区,含负值,面板 B);存量 vs 增量占比小表为普通文字;Native-ready: regional-mix=yes; increment-2025=yes
- **Motion suggestion**: P03 的全球柱在翻页时承接为 P04 的堆叠柱(同一物体拆成四层),让读者看到"总量被拆开"

### Part 3: 诊断

#### Slide 05 - 成熟市场见顶

- **Audience move**: 认为美国只是"慢一点" → 看到美国渗透率 2024、2025 两年停在 10%、销量转负,日本 3%,与欧洲 28% 形成对照
- **Relationships**: contrast — 美国/日本的停滞与欧洲的抬升;order — 2019–2025
- **Composition**: 左 2/3 图 3 三条折线(欧洲、美国、日本),美国线用警示色并在 2025 点标注"−10 万辆";右 1/3 两个要点
- **Title**: 美国渗透率连续两年停在 10%、销量首次下滑,日本仍在 3%——成熟市场不再提供确定的增量
- **Core message**: 把美国当作确定增量来源的假设已经失效
- **Content**: 图 3「渗透率走势:欧洲、美国、日本,2019–2025」 · 美国:销量 160 万→150 万(−6%),渗透率 10%→10% · 日本:销量 10 万持平,渗透率 3% · 欧洲:21%→28% · 推论:美国在 2026–2028 只能按守势规划 · 来源行
- **Visualization**: `mature-share` = 三条渗透率折线(2019–2025,%,面板 A);`mature-sales` = 美国/日本/韩国 2023–2025 销量分组柱(万辆,面板 B);Native-ready: mature-share=yes; mature-sales=yes; mature-overview=yes

#### Slide 06 - 欧洲分化

- **Audience move**: 把欧洲当一个市场 → 知道欧洲 100 万辆增量集中在英国和德国,法国零增长,选点比铺开更重要
- **Relationships**: contrast — 英国/德国的跃升 vs 法国持平;membership — 五国同属欧洲;order — 按 2025 渗透率排序
- **Composition**: 左 2/3 图 4 横向条形(2025 渗透率,附 2023→2025 变化);右 1/3 三个要点
- **Title**: 欧洲反弹到 28% 靠英国(35%)和德国(30%)拉动,法国两年零增长——进入欧洲要选国家而不是选大区
- **Core message**: 欧洲是一组分化的国家市场
- **Content**: 图 4「欧洲主要市场渗透率,2025 年,及较 2023 年变化」:挪威 97%(+7pt)、英国 35%(+12pt)、德国 30%(+6pt)、法国 26%(+1pt)、欧洲整体 28%(+6pt) · 销量:英国 46 万→70 万、德国 70 万→86 万、法国 47 万→45 万 · 推论:英德优先,法国观望 · 来源行
- **Visualization**: `europe-share` = 五行横向条形(2025 渗透率 %,条尾标注百分点变化,面板 A);`europe-sales` = 英国/德国/法国/挪威 2023 vs 2025 销量分组柱(万辆,面板 B);Native-ready: europe-share=yes; europe-sales=yes; europe-overview=yes

#### Slide 07 - 新兴市场加速

- **Audience move**: 认为新兴市场"还早" → 看到东南亚两年渗透率翻两倍、四个新兴市场合计销量 98 万辆是 2023 年的 3.2 倍
- **Relationships**: contrast — 2023 与 2025 两期对比;membership — 五个市场同属"新兴";order — 按 2025 渗透率排序
- **Composition**: 左 2/3 图 5 分组柱(每市场两根:2023、2025),2025 柱用电蓝;右 1/3 三个要点
- **Title**: 东南亚渗透率两年从 8.4% 升到 18%、泰国达 23%,巴西、墨西哥、印度同步起量——新兴市场进入加速段
- **Core message**: 新兴市场已从"早"变成"正在发生"
- **Content**: 图 5「新兴市场渗透率:2023 vs 2025」:东南亚 5.2%→18%、泰国 11%→23%、巴西 3%→9%、墨西哥 1.5%→7%、印度 2.1%→4% · 销量:东南亚 16 万→54 万(3.4 倍)、巴西 5.2 万→18 万(3.5 倍)、墨西哥 1.7 万→9 万(5.3 倍)、印度 8.2 万→17 万(2.1 倍) · 四市场(东南亚、印度、巴西、墨西哥)合计 31 万→98 万 · 来源行
- **Visualization**: `emerging-share` = 五组分组柱(2023、2025 渗透率 %,面板 A);`emerging-sales` = 2025 年销量横向条形(万辆,条尾标注两年倍数,面板 B);Native-ready: emerging-share=yes; emerging-sales=yes; emerging-overview=yes

#### Slide 08 - PHEV 的角色

- **Audience move**: 把 PHEV 当过渡产品 → 看到 PHEV 占全球电动车销量 34%,中国 2022 年以来 PHEV 增 3.4 倍而 BEV 只增 1.8 倍
- **Relationships**: membership — 电动车销量由 BEV 与 PHEV 构成;contrast — 两者增速不同;order — 2019–2025
- **Composition**: 左 2/3 图 6 堆叠面积(全球 BEV、PHEV);右 1/3 一个小表(2025 年 PHEV 占比:全球 34%、中国 38%、欧洲 33%、美国 22%)
- **Title**: PHEV 已占全球电动车销量的 34%,在中国三年增长 3.4 倍——它是低渗透市场的破冰产品,不是过渡产品
- **Core message**: 产品组合决定能否进入低渗透市场
- **Content**: 图 6「全球 BEV 与 PHEV 销量,2019–2025」(百万辆) · 2025:BEV 1,400 万、PHEV 720 万 · 中国 PHEV 150 万(2022)→510 万(2025),BEV 450 万→820 万 · PHEV 占比表 · 推论:进入渗透率 <10% 的市场以 PHEV 先行 · 来源行
- **Visualization**: `powertrain-mix` = 两层堆叠面积(2019–2025,百万辆,面板 A);`phev-share-region` = 2025 年 PHEV 占比横向条形(四地区,%,面板 B);`china-powertrain` = 中国 2022–2025 BEV/PHEV 分组柱(百万辆,面板 C);Native-ready: powertrain-mix=yes; phev-share-region=yes; china-powertrain=yes

### Part 4: 前瞻与建议

#### Slide 09 - 2035 情景

- **Audience move**: 只看当下 → 看到 IEA 既定政策情景下 2025→2035 的 3,400 万辆增量里美国只占 5%,印度与东南亚合计 12%
- **Relationships**: order — 从 2025 起点到 2035 终点的逐项累加;membership — 各地区增量构成总增量;contrast — 美国份额与其体量不匹配
- **Composition**: 图 7 瀑布图占满宽度,起点 2,100 万,终点 5,500 万,美国一级用警示色,印度/东南亚用电蓝;下方一行说明"IEA 既定政策情景,非本报告预测"
- **Title**: 到 2035 年的 3,400 万辆增量中,中国占 38%、欧洲 29%、印度与东南亚合计 12%,美国仅 5%——增量地图与今天的存量地图不同
- **Core message**: 用增量而不是存量来排优先级
- **Content**: 图 7「2025→2035 电动车年销量增量分解(IEA STEPS)」:2025 起点 2,100 万 · 中国 +1,300 万 · 欧洲 +980 万 · 东南亚 +216 万 · 印度 +193 万 · 美国 +160 万 · 韩国 +66 万 · 日本 +60 万 · 其他 +425 万(计算值=总增量减各项) · 2035 终点 5,500 万 · 说明:情景值仅供参照 · 来源行
- **Visualization**: `steps-waterfall` = 瀑布图(起点、八项增量、终点,百万辆);Native-ready: steps-waterfall=yes; steps-top5=yes

#### Slide 10 - 市场优先级分级

- **Audience move**: 面对十几个市场无从排序 → 拿到一张三级优先级表,每级有进入方式和判断依据
- **Relationships**: parent — 三个优先级层级各包含若干市场;membership — 各市场归入其层级;link — 每个市场的判断依据指向前文页码
- **Composition**: 一张占满宽度的原生表(市场 / 2025 销量 / 2025 渗透率 / 2035 情景 / 优先级 / 进入方式),优先级列用三个层级标签,一级市场行用电蓝标注
- **Title**: 建议按三级优先级分配 2026–2028 增量投入:中国深耕、欧洲选点、东南亚与拉美抢滩,美国转为守势
- **Core message**: 分级投入而不是平均铺开
- **Content**: 表「市场优先级分级」:一级(增量主战场)——中国(1,300 万 / 53% / 2,600 万)深耕,东南亚(54 万 / 18% / 270 万)以 PHEV 抢滩,英国(70 万 / 35%)与德国(86 万 / 30%)重点投入;二级(择机)——巴西(18 万 / 9%)、墨西哥(9 万 / 7%)、印度(17 万 / 4% / 210 万)、韩国(22 万 / 11% / 88 万)以 PHEV 试点;三级(守势)——美国(150 万 / 10% / 310 万)、日本(10 万 / 3% / 70 万)、法国(45 万 / 26%)维持现有布局 · 依据列写"见第 N 页" · 来源行
- **Visualization**: `market-tiers` = 12 行 × 8 列文本表(含 2023→2025 倍数与依据页码列);Native-ready: market-tiers=yes
- **Motion suggestion**: P07 的电蓝柱在翻页时承接到本页表格的一级市场行,表示"上一页的证据变成这一页的决定"

#### Slide 11 - 产品与节奏

- **Audience move**: 同意分级但不知道先做什么 → 看到 2026、2027、2028 三段各自的动作与 PHEV/BEV 节奏
- **Relationships**: order — 2026 → 2027 → 2028 三个阶段;parent — 每阶段下按三个层级列动作;link — 阶段之间有前置关系(试点结果决定下一阶段投放)
- **Composition**: 横向三段时间带占满宽度,每段下方三行(一级/二级/三级市场的动作),阶段之间用箭头式细线相连;底部一行"决策门:2026 年底复盘试点数据"
- **Title**: 2026 年以 PHEV 进入东南亚与拉美试点,2027 年按试点结果放量并在英德补齐 BEV,2028 年再决定是否加码美国
- **Core message**: 先试点、再放量、最后决定守势市场是否加码
- **Content**: 2026:东南亚 PHEV 试点上市 · 巴西/墨西哥渠道搭建 · 英德 BEV 车型补齐 · 中国维持 BEV+PHEV 双线 // 2027:按试点渗透率数据在东南亚放量 · 印度 PHEV 试点 · 美国不新增产能 // 2028:复盘美国渗透率是否突破 10%,决定是否加码 · 印度按试点放量 // 决策门:每年底以 IEA 同口径数据复盘 · 无来源引用(建议)

#### Slide 12 - 风险与应对

- **Audience move**: 担心建议过于乐观 → 看到三项主要风险各自的触发指标、影响与应对
- **Relationships**: link — 每项风险对应一个触发指标和一个应对;membership — 三项风险同属"分级投入"方案的风险
- **Composition**: 左侧五列原生表(风险 / 触发指标 / 影响 / 应对 / 监测数据),右侧「监测节奏」窄栏,底部推论带
- **Title**: 三项风险各有可监测的触发指标:新兴市场增速回落、欧洲政策反复、PHEV 需求提前见顶
- **Core message**: 风险可监测、可应对,不构成不行动的理由
- **Content**: 风险 1「新兴市场增速回落」触发:东南亚 2026 渗透率低于 18%;影响:二级市场放量推迟;应对:2026 试点规模控制、2027 复盘 · 风险 2「欧洲政策反复」触发:德国渗透率回落到 25% 以下(2024 曾从 24% 降到 20%);影响:英德投入回报期拉长;应对:英国优先、德国按季度评估 · 风险 3「PHEV 需求提前见顶」触发:中国 PHEV 占比连续两季下降(2025 为 38%);影响:破冰产品失效;应对:二级市场同步准备 BEV 版本 · 来源行(触发值来自工作簿,阈值为建议)

### Part 5: 决策与附录

#### Slide 13 - 决策请求

- **Audience move**: 认同分析 → 明确本季度要决定的三件事和 90 天内的动作
- **Relationships**: order — 三项决策按紧迫度排列;link — 每项决策对应一个 90 天动作和一个负责角色
- **Composition**: 页面左侧三个编号决策(大号序号),右侧对应的 90 天动作与负责角色;底部一行"下一次复盘:2026 年 12 月,使用 IEA 同口径数据"
- **Title**: 请管理层本季度决定三件事:批准三级优先级、批准 PHEV 先行节奏、指定东南亚试点负责人
- **Core message**: 决策请求
- **Content**: 决策 1「批准三级市场优先级」→ 90 天:海外业务部按层级重排 2026 预算 · 决策 2「批准 PHEV 先行的产品节奏」→ 90 天:产品部提交东南亚 PHEV 车型清单 · 决策 3「指定东南亚试点负责人」→ 90 天:成立试点小组、确定泰国首发 · 复盘节点一行
- **Closing impact**: 结尾要点=「三件事、90 天、一个复盘节点」(binding);构图为参考

#### Slide 14 - 附录:数据与口径

- **Audience move**: 想核对数字 → 找到完整数据表、口径说明和可点击的来源链接
- **Relationships**: membership — 各地区 × 各年份的销量与渗透率构成一张矩阵;link — 来源链接指向 IEA 数据浏览器
- **Composition**: 左 2/3 原生表(地区 × 2020–2025 销量与渗透率),右 1/3 口径说明与来源链接
- **Title**: 附录:本报告全部数字来自 IEA Global EV Outlook 2025 数据浏览器,口径为乘用车 BEV+PHEV
- **Core message**: 数字可追溯
- **Content**: 表「各地区电动车销量(万辆)与渗透率(%),2020–2025」:全球、中国、欧洲、美国、德国、英国、法国、日本、韩国、印度、东南亚、巴西、墨西哥 · 口径:EV=BEV+PHEV,乘用车,2025 为 IEA 全年估计,STEPS 为既定政策情景 · 链接:IEA Global EV Data Explorer(https://www.iea.org/data-and-statistics/data-tools/global-ev-data-explorer) · 数据许可 CC BY 4.0 · 整理日期 2026-09-05
- **Visualization**: `appendix-data` = 13 行 × 8 列数值表(面板 A);`steps-2035` = 8 行 × 3 列 2035 情景表(面板 B);Native-ready: appendix-data=yes; steps-2035=yes
- **Hyperlinks**: 「IEA Global EV Data Explorer」→ https://www.iea.org/data-and-statistics/data-tools/global-ev-data-explorer

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 每页备注写三段:这页要读者记住的一句话;页面上每个计算值的公式与源表位置(sheet/行/列);讲解时的过渡语。事实只引用工作簿,不补充外部信息
- **Total duration**: 20 分钟(14 页,证据页各 1.5 分钟,结论与建议页各 2 分钟)
- **Notes style**: formal
- **Presentation purpose**: 先给出判断再逐条证明,最后请管理层对 2026–2028 的市场优先级与产品组合节奏做出决定
