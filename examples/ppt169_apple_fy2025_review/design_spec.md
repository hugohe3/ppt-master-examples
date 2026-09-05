<!-- ppt-master-schema: design-spec/v1 -->
# Apple FY2025 经营复盘 - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | apple_fy2025_review |
| Canvas Format | ppt169 (1280×720) |
| Page Count | 14 |
| Primary Language | zh-CN |
| Target Audience | 苹果管理层与机构投资者;已经熟悉业务与分部口径,不需要重新介绍公司 |
| Communication Intent | 先给出 FY2025 的整体结论,再逐项解释每一处重大变化的来源;把两处结构性收缩放在与增长同等的位置上暴露出来;最后交出三个必须由管理层回答的问题。报告与暴露风险优先,决策请求排在最后 |
| Desired Audience Outcome | 读完能说出 FY2025 增长的真实来源(服务贡献了 51.7% 的收入增量、77.6% 的毛利增量)、能指出净利润 +19.5% 中的基数效应、能定位大中华区与可穿戴两处收缩,并对三个未决问题各自有判断 |
| Core Message / Ask / Action | FY2025 总量健康(收入 416,161 百万美元,+6.43%),质量确有提升(毛利率 46.91%),但增长与毛利同时向服务集中,而风险集中在大中华区与可穿戴两个可定位的地方;净利润 +19.5% 中相当部分是 FY24 一次性税项造成的基数效应,剔除后为 +7.72% |
| Delivery Context | 管理层经营复盘会,主讲人带读为主;会后作为可离线阅读的留存文档分发 |
| Artifact Afterlife | 审阅、存档,并作为后续季度复盘沿用同一页面形状的基线 |
| Reading Mode | balanced |
| Content Strategy | 忠实于两个源文件,不引入外部事实;所有比率、增速、占比均由源表数字两三步算出并在 notes 中写明公式;源表未覆盖的因果一律标注"现有口径无法判定" |
| Design Style | 账页式数据复盘:中性纸白场、发丝细线栅格、等宽表格数字、状态色只编码状态 |
| AI Image Acquisition Path | not applicable |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 工作流默认(final Stage-2 proactive policy 保持默认 true) |
| Custom Animations | enabled — 用户明确要求 animations.json 必写、Morph ≥2 对 |
| Narration Audio | disabled — 工作流默认;用户未要求配音 |
| Created Date | 2026-09-05 |

- **Template Application**: 挂用 operating-review Style 方法模板,只取其 Direction / method 段:采用"结果 → 偏差 → 原因 → 承诺"的复盘骨架、按位置阅读的固定区域(状态区 / 数字区 / 说明区)、变化量优先于原值的页面纪律、以及"漏项与达成同等醒目、口径不可追溯就写明未定"的措辞纪律;表格采用固定列契约(本期 / 上期 / 变化 / 变化率),图表在变化是重点处画出比较基线。身份层(色彩、字体、图标)由本项目自行决定,模板的 Fallback 配色仅作为状态映射的起点并按 WCAG AA 收紧。本项目没有"计划值",一律以上年同期为比较基准并在每页标明;模板要求的责任人与日期在源数据中不存在,因此"纠正行动"页降级为"待回答问题"页,不虚构 owner 与 date。

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | ppt169 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 上下左右 64px |
| Content Area | x 64–1216,y 64–656(1152 × 592) |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: briefing, pyramid
- **Mode Behavior**: 用简报的方式开场——直接给出本期结果,不复述受众已有的背景;随后对每一处重大变化用金字塔方式收口:偏差是什么、哪一个原因解释了它的大部分、证据在哪、还剩什么没定论。深度跟随重要性而非版面对称:平稳的指标一行带过,移动了的指标给完整链条。页面形状跨期保持稳定,让返场受众直接比较而不是重新认路。
- **Visual style**: custom
- **Visual Style References**: data-journalism, swiss-minimal
- **Visual Style Behavior**: 账页式栅格。纸白场上用发丝细线(而非卡片与阴影)划分区域,分栏与基线严格对齐,页面像一张可以逐格审计的账页;每页固定三个区域——顶部断言句、中部数字/图表主体、底部来源与口径行——位置跨页不变。装饰为零:没有渐变、发光、圆角 KPI 卡与仪表盘外壳,状态只由色 + 形/标签双重编码。数字全部走等宽字族并右对齐,列与列之间靠对齐而不是容器分组。留白用于把"结果"与"解释"分开,而不是用于稀释密度。
- **Theme**: 一份可审计的年度账页——每一个数字都能指回源表的某一行某一列
- **Tone**: 克制、直述、不软化坏数字

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #FFFFFF | 全部页面的中性纸白场 |
| Secondary background | #F4F6F8 | 表格分组带、记分卡单元格、区域底衬 |
| Primary | #1E293B | 主文字、标题、发丝线与主数字 |
| Accent | #2B6CB0 | 当前讨论中的指标或驱动因子(焦点色) |
| Secondary accent | #2E7D5B | 达成/改善状态(on plan) |
| Body text | #1E293B | 正文 |
| Secondary text | #64748B | 注释、脚注、来源行、坐标轴标签 |
| Divider | #D8DEE6 | 区域分隔发丝线与表格横线 |

补充的复用语义角色(与上表同为 deck 级锚点,投影进 spec_lock):

| Role | HEX | Purpose |
| --- | --- | --- |
| Surface | #F4F6F8 | 与 Secondary background 同值,用作面板抬升 |
| Grid | #E8EDF2 | 图表网格线,比 Divider 更浅 |
| Positive | #2E7D5B | 改善/增长(与 Secondary accent 同值) |
| Warning | #8A5A12 | 观察项;由模板 Fallback 的 #B7791F 压暗到白底 5.76:1 以满足 AA |
| Negative | #B4342C | 收缩/下滑;固定映射到大中华区与可穿戴两条收缩序列 |
| Series alt | #7BA7D4 | 分类编码用的第二蓝,由 Accent 派生,仅用于多序列图表 |

状态映射全卷固定:改善 = Positive + 向上三角 + `+` 号;观察 = Warning + 空心方块;收缩 = Negative + 向下三角 + `−` 号。色永远与形状或符号成对出现,灰度打印仍可读。

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 紧凑中性无衬线,靠字重与对齐拉层级 | Microsoft YaHei | Microsoft YaHei | 无 |
| Body | 同族,正文中性 | Microsoft YaHei | Microsoft YaHei | 无 |
| Data | 真等宽,表格数字等宽等高,列可逐位对齐 | Consolas | Consolas | 无 |
| KPI hero | 大号数字,与 Data 同族以保证与表内数字一致 | Consolas | Consolas | 无 |

- **Title stack**: `Microsoft YaHei`
- **Body stack**: `Microsoft YaHei`
- **Data stack**: `Consolas`
- **KPI hero stack**: `Consolas`
- **Role rationale**: 标题与正文同族是 operating-review §V Typography Character 的明确要求(用一套紧凑中性无衬线,层级由字重和对齐产生而非容器);第二个族 `Data` 单独存在,是因为本卷有 9 个原生数据对象、上百个需要逐位对齐的数字,`Consolas` 提供真正的等宽表格数字。中文标签一律走 Body 族,`Data` 族只承载数字、百分号、货币符号与拉丁缩写。两个族均写单一具体名,不写逗号栈。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 44 |
| Subtitle | 30 |
| Annotation | 18 |
| Cover title | 72 |
| Lead | 28 |
| KPI hero | 64 |
| Data | 24 |
| Footnote | 16 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 自上而下——顶部断言句先落地结论,中部把支撑它的那个数字放到最大,底部给口径与来源;横向上把"变化量"放在比"原值"更靠左或更大的位置。
- **Composition tendency**: 每页一个主导事实 + 一组可审计的支撑数字;图表占据中部主区并自带比较基线,说明文字沿右侧或下方成窄栏。
- **Cross-page continuity**: 顶部断言句带、底部来源行、状态色映射三者跨页不变;大中华区色块与"416,161"这两个承接物在相邻页之间保持同一形状与颜色。
- **Spacing posture**: variable by page rhythm——记分卡与问题页 breathing,图表与明细页 dense,封面与结论页 anchor。
- **Spacing anchors**: 页边距 64px;区块间距 32px;分栏栏距 24px;圆角半径 0px;正文行高 1.55。

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2
- **Brand-logo library**: simple-icons(仅用于 Apple 自身的品牌标记)

| Icon Path | Suitable Scenarios |
| --- | --- |
| tabler-outline/trending-up | 改善方向标记 |
| tabler-outline/trending-down | 收缩方向标记 |
| tabler-outline/chart-bar | 数据/图表区域的类目提示 |
| tabler-outline/world | 地区分部相关页 |
| tabler-outline/device-mobile | 硬件品类相关页 |
| tabler-outline/cloud | 服务业务相关页 |
| tabler-outline/coin | 盈利与税项相关页 |
| tabler-outline/alert-triangle | 观察项与待回答问题 |
| tabler-outline/target | 结论与行动含义 |
| tabler-outline/file-text | 来源与口径 |
| tabler-outline/link | 外部链接标记 |
| tabler-outline/calendar-stats | 季度节奏与季节性 |
| simple-icons/apple | 封面与页脚的公司标记 |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P02 | table | metric_table | 用固定列契约(FY2025 / FY2024 / 变化 / 变化率)一次给出全年九项核心指标的本期standing |
| P03 | chart | waterfall_chart | 把收入总增量分解为产品与服务两项贡献,并让首尾值合拢到源表合计 |
| P04 | chart | column_chart | 展示八个季度净销售额的绝对水平与 Q1 峰值节奏 |
| P05 | chart | column_chart | 服务净销售额八个季度柱序列,FY25 柱标同比,证明增长连续而非一次性 |
| P05 | chart | line_chart | 服务与产品季度毛利率双线,量级差距一眼可见 |
| P05 | chart | stacked_bar_chart | 收入增量与毛利增量两条 100% 条,给出服务在增量中的占比 |
| P06 | chart | grouped_bar_chart | 五个品类 FY2025 与 FY2024 并置比较,暴露唯一收缩项 |
| P07 | chart | stacked_bar_chart | 八个季度五地区的构成与总量同时可读 |
| P08 | chart | line_chart | 大中华区八个季度的走向,判断是方向还是波动 |
| P09 | table | comparison_matrix | 指标 × 八个季度的损益摘要,让率值跨期逐列对比 |
| P11 | chart | line_chart | 研发与销管两条费率线跨八个季度的相对走向 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

本卷 `image_usage: none`。用户明确要求不做 AI 生图、不搜网图;证据全部是数字,没有任何页面把一个真实主体、场地、产品或现场状态当作证据来呈现,因此没有一行图像资源需要准备。装饰性题字候选同样为零——用户的"不做 AI 生图"是显式禁止,该规则不激活。

## IX. Content Outline

### Part 1: 结论

#### Slide 01 - 封面

- **Audience move**: 打开文件 → 立刻知道这份复盘的中心结论是"增长的一半来自服务",并准备好按结构而非按总量来读
- **Relationships**: 三个单元——全年收入总量、收入增量、增量中的服务份额;后两者是前者的分解(parent),服务份额与产品份额构成 contrast
- **Cover impact**: hook 是"25,126 百万美元的收入增量里,服务拿走 51.7%"这一个数字对比;构图为 Reference——超大主数字压左、副标题与期间口径成窄栏靠下
- **Composition**: 单焦点。主数字占左侧三分之二,右侧留白只放公司标记与期间标签;底部一条发丝线与来源行
- **Title**: FY2025:收入创新高,增长的一半来自服务
- **Core message**: 全年收入 416,161 百万美元、同比 +6.43%,而 25,126 百万美元的增量中服务贡献 51.7%,超过全部产品之和
- **Content**:
  - 主数字块:416,161 百万美元 · 同比 +6.43%
  - 副行:服务贡献增量 12,989 / 25,126 = 51.7%
  - 期间口径:苹果财年,FY2025 截止 2025-09-27
  - 页脚:数据来自 Apple 各季度 Condensed Consolidated Financial Statements
- **Motion suggestion**: 主数字先落位,增量分解的两段随后从主数字下方展开——顺序即"总量 → 分解"

#### Slide 02 - 全年记分卡

- **Audience move**: 知道有一个中心结论 → 看到全部九项核心指标的本期 standing,确认"总量没有问题"
- **Relationships**: 九个指标行是并列的 membership;每行内部 FY2025 与 FY2024 构成 contrast,变化与变化率是该 contrast 的派生
- **Composition**: 单一主表占据中部主区,顶部断言句,右侧窄栏放三条读法提示
- **Title**: 全年九项核心指标全部改善,问题不在总量而在结构
- **Core message**: FY2025 相对 FY2024,收入、毛利、营业利润、净利润、每股收益等九项全部为正;需要解释的是这些改善的构成,不是它们的方向
- **Content**:
  - 固定列契约:项目 / FY2025 / FY2024 / 变化 / 变化率(本项目无计划值,比较基准统一为上年同期)
  - 九行:净销售额合计 · 产品净销售额 · 服务净销售额 · 毛利 · 研发费用 · 销售及管理费用 · 营业利润 · 净利润 · 稀释每股收益
  - 读法提示:服务增速是收入增速的两倍多 / 净利润增速远高于营业利润增速,原因在 P10 / 研发增速快于收入,原因在 P11
  - 单位行:百万美元;每股收益为美元
- **Visualization**: `annual-scorecard` = 九项指标 × 四列的固定契约表(table/metric_table)
- **Native-ready**: annual-scorecard=yes
- **Motion suggestion**: 表格整体入场后,净销售额一行的 FY2025 值单独抬升——它是下一页的承接物

#### Slide 03 - 增量归因

- **Audience move**: 知道总量改善 → 知道这 25,126 百万美元增量是谁带来的,并接受"服务已经是主要引擎"
- **Relationships**: FY2024 收入 → 产品贡献 → 服务贡献 → FY2025 收入 是一条 order;两项贡献对总增量是 parent-分解关系,彼此 contrast
- **Composition**: 瀑布占中部主区并横贯全宽,首尾柱与源表合计对齐;右下角一句结论行
- **Title**: 25,126 百万美元增量里,服务贡献 51.7%,超过全部产品之和
- **Core message**: 收入增量的过半来自服务,产品四个品类合计只贡献 48.3%
- **Content**:
  - 桥式分解:391,035 → +12,137(产品)→ +12,989(服务)→ 416,161
  - 份额行:服务 51.7% / 产品 48.3%
  - 一句限定:产品内部并非齐涨,细节见 P06
- **Visualization**: `revenue-bridge` = 四段收入桥(chart/waterfall_chart),数值标签带千分位
- **Native-ready**: revenue-bridge=yes
- **Motion suggestion**: 起点柱由上一页的净销售额数字承接,两段贡献依次生长,终点柱最后合拢

### Part 2: 节奏与结构

#### Slide 04 - 季度节奏

- **Audience move**: 只看到年度合计 → 看到八个季度的实际节奏,知道 Q1 峰值是常态而不是异常
- **Relationships**: 八个季度是时间 order;FY25 每个季度与 FY24 同季构成 contrast
- **Composition**: 柱列横贯中部,FY24 与 FY25 用同一基线;同比标签贴在 FY25 四根柱顶
- **Title**: FY25 四个季度收入同比全部为正,Q1 峰值节奏保持不变
- **Core message**: 增长不是靠某一个季度拉起来的,四个季度同比在 +3.95% 到 +9.63% 之间,而 Q1 仍占全年近三成
- **Content**:
  - 八根柱:119,575 / 90,753 / 85,777 / 94,930 / 124,300 / 95,359 / 94,036 / 102,466
  - 同比标签:Q1 +3.95% · Q2 +5.08% · Q3 +9.63% · Q4 +7.94%
  - 季节性一行:FY25 Q1 占全年 29.87%,FY24 Q1 占 30.58%
- **Visualization**: `quarterly-revenue` = 八季度净销售额柱列(chart/column_chart),y 轴自零起,不截断
- **Native-ready**: quarterly-revenue=yes

#### Slide 05 - 服务

- **Audience move**: 知道服务贡献大 → 知道服务的增长是连续的而非一次性,并知道它的毛利率量级
- **Relationships**: 八个季度服务收入是 order 且单调递增;服务毛利率与产品毛利率构成 contrast
- **Composition**: 三个编号面板:左侧 A 八季柱图(FY25 柱下标同比),右上 B 服务/产品季度毛利率双线,右下 C 收入增量与毛利增量的 100% 条;底部一句结论行
- **Title**: 服务是唯一八个季度连续增长的业务,毛利率 75.41%
- **Core message**: 服务净销售额八个季度逐季走高、无一次回落,且其毛利率是产品的两倍以上——它同时解释了收入增量和毛利增量
- **Content**:
  - 八季序列:23,117 → 23,867 → 24,213 → 24,972 → 26,340 → 26,645 → 27,423 → 28,750
  - 全年:109,158,同比 +13.51%
  - 毛利率对照:服务 75.41% vs 产品 36.77%(FY25 四季合计口径)
  - FY25 各季同比:+13.9% / +11.6% / +13.3% / +15.1%
  - 季度毛利率:服务 72.8%→75.3%,产品 39.4%→36.2%
  - 增量占比:收入增量 25,126 中服务 51.7%;毛利增量 14,518 中服务 77.6%
  - 一句结论:服务已占全年收入 26.23%(FY24 为 24.59%)
- **Visualization**: `services-trend` = 服务八季度净销售额柱序列(chart/column_chart);`services-margin-lines` = 服务与产品季度毛利率双线(chart/line_chart);`increment-share` = 服务在收入/毛利增量中的占比(chart/stacked_bar_chart)
- **Native-ready**: services-trend=yes; services-margin-lines=yes; increment-share=yes

#### Slide 06 - 产品结构

- **Audience move**: 把产品当成一个整体 → 看到产品内部分化,并锁定唯一收缩的品类
- **Relationships**: 五个品类是 membership;每个品类 FY2025 与 FY2024 构成 contrast;可穿戴与其余四项构成方向上的 contrast
- **Composition**: 成对横条占中部,按 FY2025 规模降序;唯一收缩项用 Negative 色 + 向下三角单独标出
- **Title**: iPhone 依赖度降至 50.36%,可穿戴是唯一收缩的品类
- **Core message**: iPhone 仍是半壁江山但依赖度较 FY24 下降 1.09 个百分点;真正需要解释的是可穿戴的 -3.56%
- **Content**:
  - 五品类 FY2025 / FY2024:iPhone 209,586 / 201,183 · Mac 33,708 / 29,984 · iPad 28,023 / 26,694 · 可穿戴、家居及配件 35,686 / 37,005 · 服务 109,158 / 96,169
  - 同比:+4.18% · +12.42% · +4.98% · −3.56% · +13.51%
  - iPhone 占收入:FY25 50.36%,FY24 51.45%
  - 可穿戴逐季同比:−1.72% / −4.94% / −8.56% / −0.32%
- **Visualization**: `category-compare` = 五品类两期并置横条(chart/grouped_bar_chart)
- **Native-ready**: category-compare=yes

#### Slide 07 - 地区结构

- **Audience move**: 认为增长是全面的 → 看到四个地区在长、一个地区在缩
- **Relationships**: 五个地区是 membership 且合计等于净销售额合计;大中华区与其余四个地区构成方向 contrast;八个季度是 order
- **Composition**: 堆叠柱横贯中部,总量与构成同时可读;右侧窄栏列出五个地区的全年同比
- **Title**: 四个地区增长,大中华区是唯一下滑地区
- **Core message**: 日本 +14.57%、欧洲 +9.58%、亚太其他 +9.91%、美洲 +6.77%,只有大中华区 −3.85%,并把该区占收入比重从 17.12% 拉到 15.47%
- **Content**:
  - 五地区全年 FY2025 / FY2024:美洲 178,353 / 167,045 · 欧洲 111,032 / 101,328 · 大中华区 64,377 / 66,952 · 日本 28,703 / 25,052 · 亚太其他 33,696 / 30,658
  - 同比:+6.77% · +9.58% · −3.85% · +14.57% · +9.91%
  - 占比迁移:大中华区 17.12% → 15.47%
  - 校验行:五地区合计 = 净销售额合计
- **Visualization**: `region-stack` = 八季度五地区堆叠柱(chart/stacked_bar_chart),大中华区固定用 Negative 色
- **Native-ready**: region-stack=yes
- **Motion suggestion**: 大中华区色块最后落位并短暂高亮——它是下一页的承接物

#### Slide 08 - 大中华区

- **Audience move**: 知道大中华区在缩 → 知道它是趋势不是噪声,并知道现有口径解释不了原因
- **Relationships**: 八个季度是 order;FY25 三个连续下降的环比构成一条子 order;与其余四个地区的走向构成 contrast
- **Composition**: 折线占中部主区并压满宽度,最低点单独标注;下方一句"原因未定"的口径声明
- **Title**: 大中华区在 FY25 连降三个季度,Q4 是八个季度最低点
- **Core message**: FY25 Q1 之后连续三个季度环比走低(−13.6% / −4.0% / −5.7%),14,493 百万美元是八个季度中的最低值;同比口径下四个季度中有三个为负
- **Content**:
  - 八季序列:20,819 / 16,372 / 14,728 / 15,033 / 18,513 / 16,002 / 15,369 / 14,493
  - FY25 逐季同比:−11.1% / −2.3% / +4.4% / −3.6%
  - FY25 逐季环比:Q1→Q2 −13.6% · Q2→Q3 −4.0% · Q3→Q4 −5.7%
  - 口径声明:源表只到地区合计,没有地区 × 品类交叉,因此下滑归因于哪一类产品——现有口径无法判定
- **Visualization**: `greater-china-trend` = 大中华区八季度折线(chart/line_chart),标注最低点
- **Native-ready**: greater-china-trend=yes

### Part 3: 盈利质量与费用

#### Slide 09 - 盈利质量

- **Audience move**: 认为毛利率上升是普遍改善 → 知道产品毛利率其实在降,毛利率的提升全部来自服务占比
- **Relationships**: 五个损益指标行 × 八个季度是 membership × order 的网格;产品毛利率与服务毛利率构成 contrast
- **Composition**: 矩阵表占中部主区,率值行与金额行用发丝线分隔;顶部断言句下方一行三个关键率值
- **Title**: 毛利率升至 46.91%,提升全部来自服务占比而非产品本身
- **Core message**: FY25 产品毛利率反而由 37.18% 降到 36.77%,毛利率仍上升,是因为高毛利的服务从 24.59% 的收入占比升到 26.23%;毛利增量的 77.6% 来自服务
- **Content**:
  - 表:净销售额 / 毛利 / 毛利率 / 营业利润 / 营业利润率,五行 × 八个季度
  - 年度率值:毛利率 46.91%(FY24 46.21%)· 营业利润率 31.97%(FY24 31.51%)· 净利率 26.92%(FY24 23.97%)
  - 结构证据:服务毛利 82,314(FY24 71,050),占全部毛利 42.17%(FY24 39.32%)
  - 增量归因:毛利增量 14,518 中服务贡献 11,264,占 77.6%
- **Visualization**: `quarterly-pl-matrix` = 五项指标 × 八季度的损益摘要矩阵(table/comparison_matrix)
- **Native-ready**: quarterly-pl-matrix=yes

#### Slide 10 - 一次性税项

- **Audience move**: 把净利润 +19.5% 当作经营改善 → 知道其中相当部分是 FY24 基数造成的,并知道可比口径下的真实数字
- **Relationships**: 报告口径与还原口径构成 contrast;一次性税项是 FY24 Q4 所得税的 parent-分解项
- **Composition**: 左右两栏对照——左栏报告口径、右栏剔除一次性事项后的可比口径,中间一条竖发丝线;下方一行给出该事项的源表出处
- **Title**: 净利润 +19.50% 里有基数效应,剔除 FY24 一次性税项后为 +7.72%
- **Core message**: FY24 Q4 所得税费用 14,874 中含欧盟 State Aid 一次性税项 10,246,把当季净利润压到 14,736;以可比口径重算,FY2025 净利润同比是 +7.72% 而非 +19.50%
- **Content**:
  - 报告口径:FY2025 净利润 112,010 vs FY2024 93,736,+19.50%
  - 可比口径:FY2024 还原为 103,982(93,736 + 10,246),FY2025 同比 +7.72%
  - 季度证据:FY24 Q4 有效税率 50.23%,剔除后 15.63%;同期其余七个季度均在 14.7%–16.4%
  - 出处:该事项写在源表「来源与口径」sheet 的"特殊事项"行
- **Visualization**: 无原生对象;用两栏数字与一条桥接标注构成的页面几何承载对照
- **Motion suggestion**: 报告口径先出,可比口径随后从其右侧推出——顺序即"看到的 → 可比的"

#### Slide 11 - 费用纪律

- **Audience move**: 担心费用随收入膨胀 → 知道研发在主动加码而销管在被动收敛
- **Relationships**: 研发费率与销管费率是两条并列 order;两者与收入增速构成 contrast
- **Composition**: 双线占中部,两条线同轴同刻度;右侧窄栏放两组年度费率与一句判断
- **Title**: 研发增速快于收入,销管占比反而下降:费用纪律仍在
- **Core message**: 研发 +10.14% 快于收入 +6.43%,费率升 0.28 个百分点;销管 +5.76% 慢于收入,费率降 0.04 个百分点;营业费用合计仅升 0.23 个百分点,营业利润率仍从 31.51% 升到 31.97%
- **Content**:
  - 研发费率八季:6.4% / 8.7% / 9.3% / 8.2% / 6.7% / 9.0% / 9.4% / 8.7%
  - 销管费率八季:5.7% / 7.1% / 7.4% / 6.9% / 5.8% / 7.1% / 7.1% / 6.9%
  - 年度:研发 34,550(8.30%,FY24 8.02%)· 销管 27,601(6.63%,FY24 6.67%)
  - 判断:费率的季度波动主要跟随收入的季节性,而不是费用本身的跳动
- **Visualization**: `opex-ratio-lines` = 研发与销管费率八季度双线(chart/line_chart),y 轴百分比
- **Native-ready**: opex-ratio-lines=yes

### Part 4: 未决与收口

#### Slide 12 - 三个待回答的问题

- **Audience move**: 已经看完全部证据 → 拿到三个必须由管理层回答、且每一个都指明了现有口径缺什么的问题
- **Relationships**: 三个问题是并列 membership;每个问题与前面某一页的证据构成 link
- **Composition**: 三行等宽横条,每行左侧问题、中部支撑数字、右侧"现有口径缺什么";行间发丝线分隔
- **Title**: 三个必须回答的问题:大中华、可穿戴、毛利对服务的依赖
- **Core message**: 三个问题都由本卷数字推出,且都在现有口径下无法自行收口——需要补的数据在每一行右侧写明
- **Content**:
  - 问题一(承接 P08):大中华区连降三季、Q4 为八季最低,而同期日本 +14.57%、亚太其他 +9.91%——这是区域需求问题还是产品组合问题?缺:地区 × 品类交叉数据
  - 问题二(承接 P06):可穿戴全年 −3.56%,降幅在 FY25 Q3 最深(−8.56%)而 Q4 几乎持平(−0.32%)——是产品周期还是趋势性下行?缺:品类内部的单品与出货口径
  - 问题三(承接 P09):毛利增量的 77.6% 来自服务,服务毛利已占全部毛利 42.17%——这一集中度的敞口有多大?缺:服务收入的构成拆分
  - 措辞纪律:三条都不给责任人与日期,源数据不含 owner 与 due date,不虚构
- **Motion suggestion**: 三行依次出现,每行的支撑数字由其来源页的对应元素承接

#### Slide 13 - 结论

- **Audience move**: 手里有零散结论 → 能用三句话向别人复述这份复盘
- **Relationships**: 三条收口结论是并列 membership,分别 link 回总量、质量、风险三条主线
- **Closing impact**: 绑定的收口是"总量健康、质量提升、风险集中在两个可定位的地方";构图为 Reference——三段等重横排,每段一个数字加一行判断
- **Composition**: 三段等重横排,每段顶部一个数字、下方一行判断;底部一行给出下一期复盘应带的三项数据
- **Title**: 总量健康,质量提升,风险集中在两个可定位的地方
- **Core message**: FY2025 可以用三个数字复述:收入 +6.43%、毛利率 46.91%、可比口径净利润 +7.72%;而下一期需要带来的是三项目前缺失的交叉数据
- **Content**:
  - 总量:416,161,+6.43%,四个季度同比全为正
  - 质量:毛利率 46.91%,但产品毛利率下降,提升全部来自服务占比
  - 风险:大中华区 −3.85%、可穿戴 −3.56%,是仅有的两条收缩序列
  - 下一期带来:地区 × 品类交叉 / 可穿戴单品口径 / 服务收入构成
- **Motion suggestion**: 三段依次落位,风险段最后并保持 Negative 色

#### Slide 14 - 数据来源与口径

- **Audience move**: 想核对任意一个数字 → 知道每个数字出自哪一份公开报表,并能直接点开
- **Relationships**: 四份季度报表与四个季度是 link;口径说明与全部数字是 parent 关系
- **Composition**: 上半部四行链接列表,下半部三行口径说明;整页低密度
- **Title**: 数据来源与口径
- **Core message**: 全部数字取自 Apple Newsroom 公开的四份季度合并财务报表,FY24 各季取自对应 FY25 季度报表的上年同期列
- **Content**:
  - 四条原生超链接:FY25 Q1(季度截止 2024-12-28)/ FY25 Q2(2025-03-29)/ FY25 Q3(2025-06-28)/ FY25 Q4(2025-09-27,含 FY2025 与 FY2024 十二个月合计)
  - 口径:单位百万美元,每股收益为美元;财年为苹果财年,9 月底截止
  - 口径:FY24 各季度取自对应 FY25 季度报表的上年同期列
  - 特殊事项:FY24 Q4 所得税费用 14,874 含欧盟 State Aid 一次性税项 10,246
  - 整理:2026-09-05 由 PPT Master 维护者从上述 PDF 逐项抄录并校验各分部/品类合计等于净销售额合计
- **Hyperlinks**:
  - "FY25 Q1 合并财务报表" → https://www.apple.com/newsroom/pdfs/fy2025-q1/FY25_Q1_Consolidated_Financial_Statements.pdf
  - "FY25 Q2 合并财务报表" → https://www.apple.com/newsroom/pdfs/fy2025-q2/FY25_Q2_Consolidated_Financial_Statements.pdf
  - "FY25 Q3 合并财务报表" → https://www.apple.com/newsroom/pdfs/fy2025-q3/FY25_Q3_Consolidated_Financial_Statements.pdf
  - "FY25 Q4 合并财务报表" → https://www.apple.com/newsroom/pdfs/fy2025-q4/FY25_Q4_Consolidated_Financial_Statements.pdf

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 每页 notes 交代三件事——这一页确立了什么、页面上每个计算值的公式与中间数(例如"服务占增量 = 12,989 ÷ 25,126 = 51.7%")、以及这一页的数字取自哪个 sheet 的哪一行。凡是源表无法支撑的因果,notes 里明确写"现有口径无法判定"。不复述页面文字。
- **Total duration**: 约 18–22 分钟(14 页,平均每页 80–95 秒)
- **Notes style**: formal
- **Presentation purpose**: 先给出 FY2025 的整体结论,再逐项解释每一处重大变化的来源;把两处结构性收缩暴露出来;最后交出三个必须由管理层回答的问题
