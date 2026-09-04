<!-- ppt-master-schema: design-spec/v1 -->
# nbs_2025_communique_briefing - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | nbs_2025_communique_briefing |
| Canvas Format | ppt169 (1280 × 720) |
| Page Count | 17 |
| Primary Language | zh-CN |
| Target Audience | 没有统计学背景、希望在 15 分钟内看懂"2025 年中国经济长什么样"的普通读者；他们熟悉新闻里的 GDP、就业、房价等词，但不清楚这些数字的量级、口径和相互关系 |
| Communication Intent | 先报告与说明：把《2025 年国民经济和社会发展统计公报》的官方数字按"总量与结构 → 人口与人 → 需求三面 → 外部与能源 → 创新与民生"的顺序摊开，让读者建立坐标系；再让读者自己判断走向，不代替读者下结论 |
| Desired Audience Outcome | 读完后能说出 2025 年中国经济的 5 个关键数字（GDP 总量与增速、人口总量与变动、城镇化率、居民收入、进出口规模）和 3 条主要走向（增长逐季回落但全年达 5.0%、人口继续负增长而城镇化仍在推进、投资收缩而消费与外贸顶住） |
| Core Message / Ask / Action | 2025 年中国经济总量 1401879 亿元、比上年增长 5.0%；在人口减少 339 万人、固定资产投资下降 3.8% 的同时，消费、外贸和新质生产力共同支撑了这个增速 |
| Delivery Context | 读者主导的自读简报，屏幕阅读为主；可在会议前作为快速铺垫材料被人翻阅，无现场讲解人 |
| Artifact Afterlife | 存档与转发；每个数字都要能回溯到公报原文，最后一页给出官方来源链接 |
| Reading Mode | balanced |
| Content Strategy | 贴近源：所有数值、口径、单位与公报完全一致，不改写、不换算、不推算；公报没有的数字标注 NO DATA。页面结构可自由重组，把公报的十二个章节重排为读者视角的叙述顺序 |
| Design Style | 数据新闻简报：出版级信息密度 + 中性陈述语气；宋体标题承担权威感，无衬线正文与衬线数字承担精度，图表是版面的脊椎 |
| AI Image Acquisition Path | not applicable |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — final Stage-2 proactive policy |
| Custom Animations | enabled — explicit user instruction (至少 2 对 Morph + entrance 家族入场) |
| Narration Audio | disabled — final Stage-2 proactive policy |
| Created Date | 2026-09-04 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | ppt169 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 上 56 / 下 52 / 左右 64 |
| Content Area | x 64–1216，y 56–668（可用宽 1152，可用高 612） |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: briefing
- **Mode Behavior**: 中性、完整、可扫读。页标题写主题而不写论断（"三次产业：结构与贡献"，不是"服务业撑起了增长"）；每页 core message 说这一页铺开了什么，而不是证明了什么。同级事实等权呈现，只有公报本身把某个数字单列时才让它变大。章节按读者视角分组并给出组标签，顺序可预期。全篇不制造转折、不设悬念、不替读者下结论；唯一的例外是封面钩子和结尾要点，它们复述而非新增判断。
- **Visual style**: custom
- **Visual Style References**: data-journalism
- **Visual Style Behavior**: 出版级密度。多栏栅格承载图表与数据表，图表是页面的脊椎——版面绕着可视化排，而不是把图表装进卡片盒子里；发丝分隔线代替重卡片，整幅横贯的规则线落进统计带；侧栏切进栅格承载口径与注释；小倍数条带代替单个大图。装饰只有一条强调规则线和克制的标注。数字按含义着色（升 / 降 / 焦点），图表用同族色阶而非彩虹。整体平面，无发光、无装饰阴影。
- **Theme**: 官方统计公报的纸面出版感——暖白纸底、深墨蓝正文、砖红标记关键与下行、深绿标记上行；每页右下角一条细的来源脚注线构成跨页母题。
- **Tone**: 冷静、克制、可核查。

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #F4F1EA | 暖白出版纸底，全页大面积场 |
| Secondary background | #FFFFFF | 数据表、侧栏、统计带的抬起面 |
| Primary | #123B57 | 深墨蓝：标题、图表主系列、正文强调 |
| Accent | #C0392B | 砖红：关键数字、下行与收缩值、单一强调规则线 |
| Secondary accent | #2E6F4E | 深绿：上行值、第二数据系列 |
| Body text | #1F2A30 | 正文与表格文字 |
| Secondary text | #5F6B72 | 说明、坐标轴标签、图注 |
| Divider | #CFC7B8 | 发丝分隔线、表格行线、页面规则线 |
| Surface | #FFFFFF | 面板抬起（与 Secondary background 同值，语义不同：surface 用于图表底板） |
| Grid | #E4DED0 | 图表网格线，比分隔线更淡 |
| Positive | #2E6F4E | 增长、改善方向的语义色 |
| Warning | #C98B2E | 中性偏关注的量（持平、口径调整） |
| Negative | #C0392B | 下降、收缩方向的语义色 |

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 衬线 / 出版权威 | SimSun | Times New Roman | 无 |
| Body | 无衬线 / 屏幕精度 | Microsoft YaHei | Segoe UI | 无 |
| Display | 衬线等高数字 / 统计刊物的英雄数 | Times New Roman | Times New Roman | 无 |
| Data | 无衬线等高数字 / 表格与坐标轴数值对齐 | Arial | Arial | 无 |
| Annotation | 无衬线 / 小字说明 | Microsoft YaHei | Segoe UI | 无 |
| Footnote | 无衬线 / 来源行 | Microsoft YaHei | Segoe UI | 无 |

- **Title stack**: SimSun
- **Body stack**: Microsoft YaHei
- **Display stack**: Times New Roman
- **Data stack**: Arial
- **Annotation stack**: Microsoft YaHei
- **Footnote stack**: Microsoft YaHei
- **Role rationale**: Display 与 Data 离开正文族，因为全篇 10 张图表 + 3 张数据表 + 每页英雄数都是纯数字串：英雄数用 Times New Roman 保留衬线权威感，表格与坐标轴用 Arial；两者都是等高（lining）数字，Georgia 的旧式数字高低不齐、读数费劲，已弃用；两者尺寸差 3 倍以上，各自需要独立锚点。Data 角色只承载纯数字与拉丁标签，含中文的标签走 Annotation。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 42 |
| Subtitle | 32 |
| Annotation | 18 |
| Cover title | 84 |
| Display (hero number) | 72 |
| Lead | 30 |
| Data | 20 |
| Footnote | 16 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 左上角标题与主题标签先落地，视线沿栅格向右下走到可视化主体，末端收在右下角来源脚注行。
- **Composition tendency**: 图表作脊椎——先定可视化占据的主栏，再让文字沿它的边缘排；英雄数按整栏尺度放；横贯规则线把页面切成上部叙述带与下部统计带；侧栏切进栅格承载口径。
- **Cross-page continuity**: 右下角来源脚注线每页复现；左上角主题标签（一产/人口/消费…）保持同一位置与字号；深墨蓝主系列、砖红关键值在全篇稳定。
- **Spacing posture**: 偏密，但由栅格约束；导读页与要点页给出呼吸。
- **Spacing anchors**: 页边距 64px、块间距 32px、栏间距 24px、圆角 0px、正文行高 36px。

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2

| Icon Path | Suitable Scenarios |
| --- | --- |
| icons/tabler-outline/chart-bar.svg | |
| icons/tabler-outline/chart-line.svg | |
| icons/tabler-outline/chart-pie.svg | |
| icons/tabler-outline/building-factory-2.svg | |
| icons/tabler-outline/plant-2.svg | |
| icons/tabler-outline/building-store.svg | |
| icons/tabler-outline/users.svg | |
| icons/tabler-outline/home.svg | |
| icons/tabler-outline/briefcase.svg | |
| icons/tabler-outline/coin.svg | |
| icons/tabler-outline/shopping-cart.svg | |
| icons/tabler-outline/building-bridge-2.svg | |
| icons/tabler-outline/ship.svg | |
| icons/tabler-outline/world.svg | |
| icons/tabler-outline/bolt.svg | |
| icons/tabler-outline/leaf.svg | |
| icons/tabler-outline/bulb.svg | |
| icons/tabler-outline/cpu.svg | |
| icons/tabler-outline/school.svg | |
| icons/tabler-outline/heartbeat.svg | |
| icons/tabler-outline/shield-check.svg | |
| icons/tabler-outline/file-text.svg | |
| icons/tabler-outline/link.svg | |
| icons/tabler-outline/trending-up.svg | |
| icons/tabler-outline/trending-down.svg | |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P03 | chart | line_chart | 四个季度 GDP 同比增速沿时间轴的走向 |
| P04 | chart | donut_chart | 三次产业增加值占国内生产总值的份额 |
| P05 | chart | waterfall_chart | 三大需求各自拉动的百分点如何累加成 5.0% |
| P06 | table | hierarchical_table | 年末人口总量按城乡、性别、年龄逐层分解 |
| P07 | chart | column_chart | 出生人口与死亡人口的绝对量对比 |
| P08 | chart | horizontal_bar_chart | 全国居民五等份收入分组的人均可支配收入排序 |
| P09 | chart | stacked_bar_chart | 社会消费品零售总额按消费类型与经营地的两种拆分 |
| P10 | chart | horizontal_bar_chart | 分行业固定资产投资增速的正负分布 |
| P11 | chart | grouped_bar_chart | 出口额与进口额在四类贸易口径上的并置 |
| P12 | table | metric_table | 主要国家和地区的出口额、进口额及其增速与比重 |
| P13 | chart | pie_chart | 全年发电量按电源类型的构成 |
| P14 | chart | column_chart | 新质生产力相关行业与产品的增速排序 |
| P15 | table | metric_table | 五项社会保险年末参保人数及其比上年增量 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

## IX. Content Outline

### Part 1: 坐标

#### Slide 01 - 封面

- **Audience move**: 只知道"中国经济 2025 年不错" → 手里握住一个具体量级：140 万亿元、5.0%
- **Relationships**: 总量 1401879 亿元 与 增速 5.0% 是同一事实的两个面（link）；发布机构与发布日期是它们的来源（parent）
- **Composition**: 英雄数占据整栏尺度，标题在其上方作衬线大字，发布机构与日期落在右下来源线上
- **Title**: 2025 年中国经济数据简报
- **Core message**: 本简报铺开国家统计局 2025 年统计公报的核心数字
- **Content**:
  - 主标题「2025 年中国经济数据简报」/ 副标题「读《中华人民共和国 2025 年国民经济和社会发展统计公报》」
  - 英雄数：国内生产总值 1401879 亿元 · 比上年增长 5.0%
  - 来源行：国家统计局 · 2026 年 2 月 28 日发布
- **Cover impact**: 钩子（binding）= 用"1401879 亿元 / +5.0%"这一组公报开篇数字直接作为封面主体，不用任何抽象口号；构图为 Reference
- **Motion suggestion**: 英雄数块先立住，标题与来源行随后进入；该数字块在下一页仍以同一身份出现
- **Fact IDs**: 公报一、综合
- **Native-ready**: none

#### Slide 02 - 六个数字读懂 2025

- **Audience move**: 没有坐标系 → 一眼拿到六个量级各不相同的锚点
- **Relationships**: 六个指标是并列的观察面（membership）；每个指标的绝对量与增速成对（link）；人口的变动方向与其余五项相反（contrast）
- **Composition**: 三列两行的统计带，每格一个绝对量 + 一条增速行；格与格之间只用发丝线分隔，不用卡片
- **Title**: 六个数字读懂 2025
- **Core message**: 本页铺开总量、人口、城镇化、收入、外贸、消费六个面的年度量级
- **Content**:
  - 国内生产总值 1401879 亿元 / 比上年增长 5.0%
  - 年末全国人口 140489 万人 / 比上年末减少 339 万人
  - 常住人口城镇化率 67.89% / 比上年末提高 0.89 个百分点
  - 全国居民人均可支配收入 43377 元 / 比上年增长 5.0%
  - 货物进出口总额 454685 亿元 / 比上年增长 3.8%
  - 社会消费品零售总额 501202 亿元 / 比上年增长 3.7%
- **Visualization**: 六格统计带为非图表表达（等权数字格 + 增减方向标记），不是独立数据图
- **Motion suggestion**: 六格按阅读顺序依次进入；其中 GDP 一格与上一页的英雄数是同一单元的两个状态
- **Fact IDs**: 公报一、综合；五、国内贸易；七、对外经济；九、居民收入消费和社会保障
- **Native-ready**: none

#### Slide 03 - 总量与增速：全年 5.0%，逐季回落

- **Audience move**: 只记得"全年 5.0%" → 看到这个年度数字内部是逐季走低的
- **Relationships**: 四个季度增速沿时间有序（order）；全年 5.0% 是四季的汇总口径（parent）；人均 GDP、国民总收入、劳动生产率是同一年度的伴随指标（membership）
- **Composition**: 折线占据右侧主栏作页面脊椎，左栏是英雄数与三条伴随指标
- **Title**: 总量与增速
- **Core message**: 本页铺开 2025 年 GDP 总量、全年增速与分季度增速，以及人均和效率指标
- **Content**:
  - 英雄数：国内生产总值 1401879 亿元，比上年增长 5.0%
  - 分季度同比增速：一季度 5.4% / 二季度 5.2% / 三季度 4.8% / 四季度 4.5%
  - 全年人均国内生产总值 99665 元，比上年增长 5.1%
  - 国民总收入 1393700 亿元，比上年增长 5.1%
  - 全员劳动生产率 184413 元/人，比上年提高 6.1%
- **Visualization**: `quarterly-gdp-growth` 折线，x = 四个季度，y = 同比增速（%），另叠一条全年 5.0% 的参考水平线
- **Motion suggestion**: 左栏英雄数由上一页同一数字块延续；折线自左向右生成
- **Fact IDs**: 公报一、综合
- **Native-ready**: quarterly-gdp-growth=yes

#### Slide 04 - 三次产业：结构与贡献

- **Audience move**: 模糊地知道"服务业占大头" → 拿到 6.7 / 35.6 / 57.7 的确切结构与各自增速
- **Relationships**: 三次产业增加值是国内生产总值的组成部分（parent）；三者占比互斥且合计（membership）；各自增速可横向比较（contrast）
- **Composition**: 环形图占左栏，右栏三行分别给出绝对量与增速，行首用同族色块与环形扇区对应
- **Title**: 三次产业：结构与贡献
- **Core message**: 本页铺开三次产业的增加值规模、占比与增速
- **Content**:
  - 第一产业增加值 93347 亿元，比上年增长 3.9%，占 6.7%
  - 第二产业增加值 499653 亿元，增长 4.5%，占 35.6%
  - 第三产业增加值 808879 亿元，增长 5.4%，占 57.7%
  - 口径说明：绝对数按现价计算，增长速度按不变价格计算
- **Visualization**: `industry-share` 环形图，三扇区为三次产业占 GDP 比重（%）
- **Motion suggestion**: 环形按产业顺序展开，右栏三行随对应扇区进入
- **Fact IDs**: 公报一、综合；注释[2]
- **Native-ready**: industry-share=yes

#### Slide 05 - 增长从哪里来：三大需求的拉动

- **Audience move**: 把 5.0% 当成一个整块 → 看到它由消费 2.6、资本形成 0.8、净出口 1.6 三段累加而成
- **Relationships**: 三个拉动百分点顺序累加为 5.0%（order + parent）；净出口的拉动大于资本形成（contrast）
- **Composition**: 瀑布图横贯整页作脊椎，起点为 0、终点为 5.0；下方一条侧栏写口径与 NO DATA 说明
- **Title**: 增长从哪里来
- **Core message**: 本页铺开最终消费、资本形成、净出口三项对 GDP 增长的拉动百分点
- **Content**:
  - 最终消费支出拉动国内生产总值增长 2.6 个百分点
  - 资本形成总额拉动 0.8 个百分点
  - 货物和服务净出口拉动 1.6 个百分点
  - 合计即全年 5.0% 的增速
  - NO DATA：公报只给出三大需求各自的拉动百分点，未给出三者各自的绝对规模，本页不作推算
- **Visualization**: `gdp-contribution` 瀑布图，三个正向贡献段加一个合计段
- **Motion suggestion**: 三段按累加顺序依次落位，合计段最后出现
- **Fact IDs**: 公报一、综合
- **Native-ready**: gdp-contribution=yes

### Part 2: 人

#### Slide 06 - 人口：总量与结构

- **Audience move**: 只听说"人口在减少" → 拿到城乡、性别、年龄三层的确切构成
- **Relationships**: 全国人口逐层分解为城乡、男女、年龄三组（parent）；每组内部互斥合计 100%（membership）；60 周岁及以上与 65 周岁及以上是包含关系（overlap）
- **Composition**: 分层数据表占据整页主体，层级用缩进与发丝线表达；左上角保留人口总量的英雄数
- **Title**: 人口：总量与结构
- **Core message**: 本页铺开 2025 年末全国人口数及其城乡、性别、年龄构成
- **Content**:
  - 英雄数：年末全国人口 140489 万人
  - 表：全国人口 140489 万人 / 100.0%
  - 城镇 95380 / 67.9%；乡村 45109 / 32.1%
  - 男性 71685 / 51.0%；女性 68804 / 49.0%
  - 0–15 岁（含不满 16 周岁）23015 / 16.4%；16–59 岁（含不满 60 周岁）85136 / 60.6%；60 周岁及以上 32338 / 23.0%；其中 65 周岁及以上 22365 / 15.9%
  - 口径注：全国人口指大陆 31 个省、自治区、直辖市和现役军人的人口
- **Visualization**: `population-structure-table` 分层数据表，行 = 人口分组，列 = 年末数（万人）、比重（%）
- **Motion suggestion**: 表头先立，分组按城乡 → 性别 → 年龄的顺序逐组进入；人口总量英雄数在下一页继续存在
- **Fact IDs**: 公报一、综合 表1；注释[5]
- **Native-ready**: population-structure-table=yes

#### Slide 07 - 人口变动：出生、死亡与城镇化

- **Audience move**: 知道人口在减少 → 看到减少来自 792 万出生对 1131 万死亡，同时城镇化仍在上行
- **Relationships**: 出生人口与死亡人口的差构成自然增长率（link）；两者方向相反（contrast）；城镇化率与人口总量是同一年末时点的两个面（membership）
- **Composition**: 左侧柱形对比出生与死亡，右侧竖排三条：自然增长率、城镇化率进度条、城镇常住人口
- **Title**: 人口变动
- **Core message**: 本页铺开 2025 年出生、死亡、自然增长率与常住人口城镇化率
- **Content**:
  - 全年出生人口 792 万人，出生率 5.63‰
  - 死亡人口 1131 万人，死亡率 8.04‰
  - 自然增长率 −2.41‰
  - 年末全国人口 140489 万人，比上年末减少 339 万人
  - 年末常住人口城镇化率 67.89%，比上年末提高 0.89 个百分点；年末城镇常住人口 95380 万人
- **Visualization**: `births-deaths` 柱形图，两根柱分别为出生人口与死亡人口（万人）；城镇化率 67.89% 另用非图表的进度条表达，不作独立数据图
- **Motion suggestion**: 出生柱与死亡柱同时升起以便比较，随后自然增长率与城镇化进度条进入
- **Fact IDs**: 公报一、综合
- **Native-ready**: births-deaths=yes

#### Slide 08 - 就业与居民收入

- **Audience move**: 只有"人均收入 4 万多"的印象 → 看到五等份分组内部从 1.0 万到 10.4 万的实际跨度
- **Relationships**: 五等份收入组沿收入水平有序（order）；全国人均可支配收入与中位数是同一分布的两个统计量（link）；城镇与农村收入形成对照（contrast）；就业规模与收入是同一民生面的两个单元（membership）
- **Composition**: 横条按收入组从低到高排列占右侧主栏，左栏是就业规模与收入总量的四条统计
- **Title**: 就业与居民收入
- **Core message**: 本页铺开就业规模、失业率与居民可支配收入的水平与分布
- **Content**:
  - 年末全国就业人员 72504 万人，其中城镇就业人员 47535 万人，占 65.6%
  - 全年城镇新增就业 1267 万人，比上年多增 11 万人；全年城镇调查失业率平均值 5.2%，年末 5.1%
  - 全国居民人均可支配收入 43377 元，比上年增长 5.0%；中位数 36231 元，增长 4.4%
  - 城镇居民 56502 元，农村居民 24456 元；城乡居民人均可支配收入比值 2.31，比上年缩小 0.03
  - 五等份分组人均可支配收入：低收入组 10150 元 / 中间偏下 22702 元 / 中间 35536 元 / 中间偏上 55586 元 / 高收入组 103778 元
- **Visualization**: `income-quintiles` 横条图，五条为五等份收入组的人均可支配收入（元）
- **Motion suggestion**: 五条横条自低到高依次延伸，左栏统计随后进入
- **Fact IDs**: 公报一、综合；九、居民收入消费和社会保障；注释[64]
- **Native-ready**: income-quintiles=yes

### Part 3: 需求三面

#### Slide 09 - 消费：社零总额与结构

- **Audience move**: 只知道"消费还行" → 拿到 50 万亿元的量级和商品 / 餐饮、城镇 / 乡村两种拆法
- **Relationships**: 社零总额按消费类型与按经营地是同一总量的两种互斥拆分（parent + membership）；乡村增速高于城镇（contrast）；网上零售是其中一部分（overlap）
- **Composition**: 两条堆叠横条上下并置作页面脊椎，一条按消费类型、一条按经营地；下方统计带放网上零售与人均消费
- **Title**: 消费：社零总额与结构
- **Core message**: 本页铺开社会消费品零售总额的规模与两种口径下的结构
- **Content**:
  - 社会消费品零售总额 501202 亿元，比上年增长 3.7%
  - 按消费类型：商品零售额 443220 亿元，增长 3.8%；餐饮收入 57982 亿元，增长 3.2%
  - 按经营地：城镇消费品零售额 432972 亿元，增长 3.6%；乡村消费品零售额 68230 亿元，增长 4.1%
  - 服务零售额比上年增长 5.5%
  - 实物商品网上零售额 130923 亿元，增长 5.2%，占社会消费品零售总额比重 26.1%
  - 全国居民人均消费支出 29476 元，增长 4.4%；恩格尔系数 29.3%
- **Visualization**: `retail-composition` 堆叠条图，两组各自把 501202 亿元拆成两段（商品/餐饮、城镇/乡村）；网上零售 26.1% 另用非图表的占比条表达
- **Motion suggestion**: 两条堆叠条先出总长再分段着色，下方统计带随后进入
- **Fact IDs**: 公报五、国内贸易；九、居民收入消费和社会保障
- **Native-ready**: retail-composition=yes

#### Slide 10 - 投资：全面收缩

- **Audience move**: 不清楚投资的方向 → 看到总量下降 3.8%，且下行集中在房地产与建筑业
- **Relationships**: 分行业增速围绕总计 −3.8% 分布在正负两侧（contrast）；房地产开发投资是第三产业投资的一部分（parent）；三次产业投资构成总量（membership）
- **Composition**: 分行业横条按增速排序、以 0 为轴左右分列，占页面主体；左上侧栏放总量与三次产业三条
- **Title**: 投资：全面收缩
- **Core message**: 本页铺开固定资产投资的总量、三次产业分布与分行业增速
- **Content**:
  - 全社会固定资产投资 491109 亿元，比上年下降 3.9%；固定资产投资（不含农户）485186 亿元，下降 3.8%
  - 第一产业投资 9570 亿元，增长 2.3%；第二产业投资 177368 亿元，增长 2.5%；第三产业投资 298248 亿元，下降 7.4%
  - 基础设施投资下降 2.2%；民间投资下降 6.4%
  - 房地产开发投资 82788 亿元，比上年下降 17.2%，其中住宅投资 63514 亿元，下降 16.3%
  - 分行业增速（表 7 节选，10 项，覆盖正负两端与总计）：电力、热力、燃气及水生产和供应业 +9.1、信息传输、软件和信息技术服务业 +8.8、金融业 +7.2、批发和零售业 +5.6、制造业 +0.6、总计 −3.8、水利、环境和公共设施管理业 −8.4、卫生和社会工作 −12.3、房地产业 −17.5、建筑业 −22.2
- **Visualization**: `investment-by-industry` 横条图，以 0 为基线的正负增速条，正向用深绿、负向用砖红
- **Motion suggestion**: 零轴先落，正负两侧的条同时从轴向外延伸
- **Fact IDs**: 公报六、固定资产投资 表7；注释[20]
- **Native-ready**: investment-by-industry=yes

#### Slide 11 - 对外贸易：进出口的规模与口径

- **Audience move**: 只知道"外贸不错" → 拿到 45 万亿元的规模，以及出口涨 6.1%、进口涨 0.5% 的分化
- **Relationships**: 出口额与进口额在四类口径上成对（link）；两者之差为顺差（parent）；一般贸易进口与加工贸易进口方向相反（contrast）
- **Composition**: 分组条图占据整页主体，四组口径横排，每组两根（出口 / 进口）；上方统计带写总额、顺差与两条占比
- **Title**: 对外贸易：规模与口径
- **Core message**: 本页铺开货物进出口的总额、顺差与四类口径下的出口进口对比
- **Content**:
  - 货物进出口总额 454685 亿元，比上年增长 3.8%；出口 269890 亿元，增长 6.1%；进口 184795 亿元，增长 0.5%
  - 货物进出口顺差 85094 亿元，比上年增长 20.4%
  - 一般贸易：出口 176411 亿元（+6.0%）/ 进口 110650 亿元（−3.7%）
  - 加工贸易：出口 52633 亿元（+4.9%）/ 进口 32527 亿元（+12.7%）
  - 机电产品：出口 164683 亿元（+8.9%）/ 进口 74069 亿元（+5.7%）
  - 高新技术产品：出口 67806 亿元（+8.0%）/ 进口 58844 亿元（+9.9%）
  - 对共建"一带一路"国家进出口额 236018 亿元，增长 6.3%，占进出口总额比重 51.9%
  - 民营企业进出口额 260403 亿元，增长 7.1%，占比 57.3%
- **Visualization**: `trade-composition` 分组条图，四组口径 × 出口/进口两系列（亿元）
- **Motion suggestion**: 出口系列先整体进入，进口系列随后并置，便于逐组比较
- **Fact IDs**: 公报七、对外经济 表10
- **Native-ready**: trade-composition=yes

#### Slide 12 - 主要贸易伙伴

- **Audience move**: 只记得"美国下降了" → 看到东盟、欧盟、美国三者规模与方向的确切排序
- **Relationships**: 各伙伴按出口额有序（order）；每个伙伴的出口与进口成对（link）；美国与东盟的方向相反（contrast）；各伙伴比重同属出口/进口总额（membership）
- **Composition**: 指标数据表占据整页，六列，增速列按正负着色；右下侧栏一行口径注
- **Title**: 主要贸易伙伴
- **Core message**: 本页铺开对主要国家和地区的货物出口额、进口额及其增速与比重
- **Content**:
  - 表列：国家和地区 / 出口额（亿元）/ 出口增速（%）/ 占全部出口比重（%）/ 进口额（亿元）/ 进口增速（%）
  - 东盟 47596 / +14.0 / 17.6 / 27861 / −1.0
  - 欧盟 40071 / +9.0 / 14.8 / 19182 / +0.1
  - 美国 30067 / −19.5 / 11.1 / 10000 / −14.1
  - 中国香港 24001 / +16.1 / 8.9 / 2266 / +73.4
  - 日本 11261 / +4.1 / 4.2 / 11792 / +6.1
  - 韩国 10319 / −0.6 / 3.8 / 13379 / +3.6
  - 印度 9723 / +13.4 / 3.6 / 1412 / +10.3
  - 俄罗斯 7384 / −9.9 / 2.7 / 8924 / −3.4
  - 中国台湾 5982 / +11.8 / 2.2 / 16509 / +6.5
  - 口径注：各项统计数据均未包括香港特别行政区、澳门特别行政区和台湾省
- **Visualization**: `trade-partners-table` 指标数据表，行 = 国家和地区，列 = 出口额 / 出口增速 / 出口比重 / 进口额 / 进口增速
- **Motion suggestion**: 表头先立，数据行按出口额从大到小依次进入
- **Fact IDs**: 公报七、对外经济 表13；注释[1]
- **Native-ready**: trade-partners-table=yes

### Part 4: 能源、创新与民生

#### Slide 13 - 能源与绿色转型

- **Audience move**: 只听说"新能源在涨" → 看到火电仍占 6 成、而太阳能发电增长 39.8% 的同时结构
- **Relationships**: 五类电源构成全年发电量（parent + membership）；火电下降与太阳能大幅增长方向相反（contrast）；装机增速与发电量增速对应（link）
- **Composition**: 饼图占左栏作脊椎，右栏是发电量增速与装机三条，下方统计带放能耗与环境四项
- **Title**: 能源与绿色转型
- **Core message**: 本页铺开发电量结构、清洁能源规模与单位 GDP 能耗、排放及环境质量指标
- **Content**:
  - 全年发电量 105752.5 亿千瓦时，比上年增长 4.8%
  - 构成：火电 63271.5（−0.7%）/ 水电 14616.7（+2.5%）/ 核电 4852.3（+7.6%）/ 风电 11279.2（+13.1%）/ 太阳能发电 11732.4（+39.8%）
  - 水电、核电、风电、太阳能发电等清洁能源发电量 42481 亿千瓦时，比上年增长 14.4%
  - 年末全国发电装机容量 389134 万千瓦，增长 16.1%；其中太阳能发电装机 120173 万千瓦，增长 35.4%；风电装机 64001 万千瓦，增长 22.9%
  - 全年能源消费总量 61.7 亿吨标准煤，增长 3.5%；煤炭消费量占比 51.4%，比上年下降 1.8 个百分点；清洁能源消费量占比 30.4%，上升 1.8 个百分点
  - 万元国内生产总值二氧化碳排放比上年下降 5.0%；万元国内生产总值能耗下降 5.1%
  - 监测的 339 个地级及以上城市中，空气质量达标城市占 72.6%；PM2.5 年平均浓度 28.0 微克/立方米，下降 4.4%
  - NO DATA：公报分别给出清洁能源发电量与全年发电量，但未给出清洁能源占总发电量的比重，本页不作推算
- **Visualization**: `power-generation-mix` 饼图，五个扇区为五类电源的发电量（亿千瓦时）；煤炭与清洁能源消费占比另用非图表的对比条表达
- **Motion suggestion**: 饼图按电源顺序展开，右栏与下方统计带随后进入
- **Fact IDs**: 公报三、工业和建筑业 表4；一、综合；十二、资源环境和应急管理；注释[22][88]
- **Native-ready**: power-generation-mix=yes

#### Slide 14 - 创新与数字经济

- **Audience move**: 对"新质生产力"只有词感 → 拿到 R&D 2.80%、3D 打印设备 +52.5% 这类可核查的量
- **Relationships**: 各行业与产品增速可横向比较（contrast）；R&D 经费与基础研究经费是包含关系（parent）；数字经济各项同属一个观察面（membership）
- **Composition**: 柱形按增速降序占页面主体，左上侧栏放 R&D 三条，右下统计带放数字经济四条
- **Title**: 创新与数字经济
- **Core message**: 本页铺开研发投入、专利存量与新质生产力相关行业、产品的增速
- **Content**:
  - 研究与试验发展（R&D）经费支出 39262 亿元，比上年增长 8.1%，与国内生产总值之比为 2.80%
  - 其中基础研究经费 2778 亿元，增长 11.1%，占 R&D 经费支出比重 7.08%
  - 年末有效发明专利 631.8 万件，比上年末增长 11.1%；每万人口高价值发明专利拥有量 16 件
  - 技术合同成交金额 75734 亿元，比上年增长 10.8%
  - 增速排序：3D 打印设备 +52.5% / 工业机器人 +28.0% / 新能源汽车 +25.1% / 服务机器人 +16.1% / 集成电路 +10.9% / 高技术制造业增加值 +9.4% / 数字产品制造业增加值 +9.3% / 装备制造业增加值 +9.2%
  - 占规模以上工业增加值比重：装备制造业 36.8%、高技术制造业 17.1%、数字产品制造业 12.5%
  - 电子商务交易额 467339 亿元，增长 2.5%；网上零售额 159722 亿元，增长 8.6%；软件业务收入 154831 亿元，增长 13.2%
  - 年末 5G 基站 484 万个；互联网普及率 80.1%
  - NO DATA：公报未给出"数字经济总规模"这一口径的数值，本页不作估算
- **Visualization**: `innovation-growth` 柱形图，八根柱为新质生产力相关行业与产品的比上年增速（%）
- **Motion suggestion**: 柱按降序依次升起，侧栏与统计带随后进入
- **Fact IDs**: 公报一、综合；三、工业和建筑业 表3；四、服务业；十、科学技术和教育；注释[12][13][14]
- **Native-ready**: innovation-growth=yes

#### Slide 15 - 民生：社保、医疗与教育

- **Audience move**: 对社保覆盖没有量级概念 → 看到基本医保 13.3 亿人参保的规模
- **Relationships**: 五项保险并列且各自有年度增量（membership + link）；医疗与教育是同一民生面的另外两组（membership）
- **Composition**: 指标数据表占左栏放五项社保，右栏上下两块分别放医疗与教育的英雄数与统计行
- **Title**: 民生：社保、医疗与教育
- **Core message**: 本页铺开五项社会保险参保规模、医疗卫生资源与教育普及指标
- **Content**:
  - 表列：险种 / 年末参保人数（万人）/ 比上年末增加（万人）
  - 基本养老保险 107599 / +316（其中城镇职工 54680、城乡居民 52919）
  - 基本医疗保险 133068 / +406（其中职工 38856、城乡居民 94212）
  - 工伤保险 30500 / +102
  - 生育保险 25966 / +666
  - 失业保险 24918 / +329
  - 医疗：年末医疗卫生机构 110.7 万个，床位 1009 万张，卫生技术人员 1340 万人；全年总诊疗 105.8 亿人次，出院 3.0 亿人次
  - 教育：九年义务教育巩固率 96.1%，高中阶段毛入学率 92.0%；16—59 岁人口平均受教育年限 11.3 年，比上年提高 0.1 年；在学研究生 430.0 万人
  - 兜底：年末 595 万人享受城市最低生活保障，3340 万人享受农村最低生活保障
- **Visualization**: `social-insurance-table` 指标数据表，行 = 五项保险，列 = 年末参保人数、比上年末增加
- **Motion suggestion**: 表按参保人数从大到小逐行进入，右栏两块随后
- **Fact IDs**: 公报九、居民收入消费和社会保障；十、科学技术和教育；十一、文化旅游卫生健康和体育
- **Native-ready**: social-insurance-table=yes

### Part 5: 收束

#### Slide 16 - 关键要点回顾

- **Audience move**: 读完十五页信息 → 手里留下五条可复述的走向
- **Relationships**: 五条要点分别对应前文五个部分（parent）；每条要点由一个数字支撑（link）
- **Composition**: 五条编号横行，每行左侧一个衬线大数字、右侧一句陈述；行间发丝线；顶部一条横贯规则线
- **Title**: 关键要点回顾
- **Core message**: 本页把前十五页的量级收束为五条可复述的事实
- **Content**:
  - 一 · 总量与增速：国内生产总值 1401879 亿元，比上年增长 5.0%；分季度增速由 5.4% 回落至 4.5%
  - 二 · 结构：第三产业增加值占比 57.7%；最终消费支出拉动增长 2.6 个百分点，是三大需求中最大的一项
  - 三 · 人口：年末全国人口 140489 万人，比上年末减少 339 万人；常住人口城镇化率 67.89%，提高 0.89 个百分点
  - 四 · 需求三面：社会消费品零售总额 501202 亿元增长 3.7%，货物进出口 454685 亿元增长 3.8%，固定资产投资（不含农户）下降 3.8%
  - 五 · 新与绿：太阳能发电量增长 39.8%，新能源汽车产量 1652.4 万辆增长 25.1%；万元国内生产总值二氧化碳排放下降 5.0%
- **Closing impact**: 收束（binding）= 五条要点必须各自带一个公报原文数字，不新增判断、不加号召；构图为 Reference
- **Motion suggestion**: 五行自上而下依次进入；顶部规则线在下一页保持同一身份
- **Fact IDs**: 公报一、综合；三、工业和建筑业；五、国内贸易；六、固定资产投资；七、对外经济；十二、资源环境和应急管理
- **Native-ready**: none

#### Slide 17 - 数据来源与口径

- **Audience move**: 想核对某个数字 → 拿到可点击的公报原文地址与三条口径提醒
- **Relationships**: 来源、发布方与发布日期同属一条出处（membership）；三条口径说明限定全篇数字的读法（link）
- **Composition**: 顶部横贯规则线延续上一页；中部是来源块与可点击链接；下部三行口径说明
- **Title**: 数据来源与口径
- **Core message**: 本页给出本简报全部数字的唯一出处与三条读数提醒
- **Content**:
  - 来源：《中华人民共和国 2025 年国民经济和社会发展统计公报》
  - 发布：国家统计局，2026 年 2 月 28 日
  - 原文链接（可点击）：https://www.stats.gov.cn/sj/zxfbhjd/202602/t20260228_1962662.html
  - 口径一：本公报中数据均为初步统计数
  - 口径二：各项统计数据均未包括香港特别行政区、澳门特别行政区和台湾省
  - 口径三：部分数据因四舍五入的原因，存在总计与分项合计不等的情况
  - 说明：本简报只引用公报原文数值，不作换算与推算；公报未给出的量已在相应页面标注 NO DATA
- **Motion suggestion**: 顶部规则线由上一页延续，来源块与口径行随后进入
- **Fact IDs**: 公报注释[1]；资料来源
- **Native-ready**: none

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 每页一段平实读出：先说这一页摊开了什么，再把页面上的数字按顺序念一遍，最后交代口径限制。数字与页面完全一致，不得四舍五入、不得换算、不得补充公报以外的事实；标注 NO DATA 的页面在注释里说明为什么不给这个数。
- **Total duration**: 约 15 分钟（17 页，平均每页 50 秒左右）
- **Notes style**: formal
- **Presentation purpose**: 先报告与说明公报的官方数字，让读者建立坐标系并自行判断走向
