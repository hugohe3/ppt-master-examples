<!-- ppt-master-schema: design-spec/v1 -->
# 中国铁路 2024:数据与现场 - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | 中国铁路 2024:数据与现场 |
| Canvas Format | PPT 16:9 (1280×720) |
| Page Count | 15 |
| Primary Language | zh-CN |
| Target Audience | 来访的省交通运输部门代表团(处级与业务骨干),熟悉交通运输统计口径,关心全国铁路的总量、结构与本省可对标的指标,但未系统读过《2024年铁道统计公报》 |
| Communication Intent | 先完整汇报 2024 年全国铁路的运输生产、建设、装备、路网与节能减排数据,让来访方掌握全年事实;其次通过国际对照与现场影像建立直观印象;最后给出三条可带走的判断 |
| Desired Audience Outcome | 来访方能复述 2024 年客运、货运、投资与路网的关键数值及其同比方向,知道每个数字出自公报的哪一处,并能区分公报口径与世界银行口径 |
| Core Message / Ask / Action | 2024 年全国铁路客运创历史高位(43.12 亿人,+11.9%),货运总量稳中有升而周转量小幅回落,路网与装备继续扩张,能耗强度微升而主要污染物持续下降 |
| Delivery Context | 主要为有主讲人的现场汇报(约 25 分钟,会议室投影);次要为会后留档传阅的电子文件 |
| Artifact Afterlife | 作为接待记录与数据引用底稿留档,供对方回本省后按页引用并核对出处 |
| Reading Mode | balanced |
| Content Strategy | 数值与口径严格跟随附件,一处不改;叙述结构由编者重组为汇报节奏,凡属编者归纳的框架页在页面上标注"整理" |
| Design Style | 数据新闻式的证据版面 + 瑞士栅格的克制留白 + 照片主导的现场页,构成"数据"与"现场"两种质地交替的汇报 |
| AI Image Acquisition Path | not applicable |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 工作流默认 true,用户未提出相反指示 |
| Custom Animations | enabled — 用户明确要求"要有自定义动画和 Morph" |
| Narration Audio | disabled — 用户未要求旁白,工作流默认 false |
| Created Date | 2026-09-12 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 左右 72px,上 64px,下 56px |
| Content Area | x 72–1208,y 64–664(页脚来源条占 y 664–700) |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: pyramid, briefing
- **Mode Behavior**: 开篇用 pyramid 把全年判断提到第二页,主体按 briefing 的等权板块推进(客运→货运→周转→装备→路网→国际→科技安全→绿色→监管),每个板块的标题写成一句可复述的判断句,板块内先给数字再给结构;末页回到三条判断收束。板块之间不制造悬念,也不为节奏牺牲完整性。
- **Visual style**: custom
- **Visual Style References**: data-journalism, swiss-minimal, photo-editorial
- **Visual Style Behavior**: 由 data-journalism 负责数据页的多栏证据密度、边注与每页底部的来源条;由 swiss-minimal 负责统一的左对齐栅格、直角容器、发丝分隔线与大留白,容器只用直角矩形和 1px 规则线,不用圆角卡片堆叠;由 photo-editorial 负责现场页——照片整幅出血、文字只作为压在照片安静区的点与说明,署名以极小字号贴在照片边缘。两种质地交替出现:数据页白底高密度,现场页深色照片低密度。
- **Theme**: 铁轨的水平线——每页顶部一条 2px 主色横规则线贯穿版心,页码与板块名坐在这条线下方,像时刻表的表头;数据页在这条线下展开栅格,现场页让照片穿过这条线。
- **Tone**: 克制、可核对、有现场温度

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #FFFFFF | 数据页底色 |
| Secondary background | #F2F5F9 | 表格斑马行、KPI 底板、边注区 |
| Primary | #0B3A6F | 顶部规则线、标题、图表主系列、板块名 |
| Accent | #C8102E | 当年值、需要读者先看的一个数字、图表中的当前系列 |
| Secondary accent | #1E6FB8 | 图表次系列、对照系列、链接性标注 |
| Body text | #1E2733 | 正文与表格正文 |
| Secondary text | #5A6775 | 注记、单位、照片署名、来源条 |
| Divider | #D8DEE6 | 表格横线、栅格发丝线 |
| Surface | #F8FAFC | 图表绘图区底 |
| Grid | #E6EBF1 | 图表网格线(比分隔线更浅) |
| Scrim | #0A1B2E | 照片上的压暗层与现场页文字底 |
| Positive | #2E7D32 | 同比上升的方向标注 |
| Negative | #C62828 | 同比下降的方向标注 |

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 黑体/方正的公文分量,笔画平直无修饰 | SimHei | Arial | sans-serif |
| Body | 屏幕可读的中性无衬线 | Microsoft YaHei | Arial | sans-serif |
| Display | 与标题同族的重量,承担页面上最大的数字 | SimHei | Arial | sans-serif |
| Annotation | 与正文同族,用于注记与单位 | Microsoft YaHei | Arial | sans-serif |
| Footnote | 与正文同族,用于来源条与照片署名 | Microsoft YaHei | Arial | sans-serif |

- **Title stack**: SimHei, Arial, sans-serif
- **Body stack**: Microsoft YaHei, Arial, sans-serif
- **Display stack**: SimHei, Arial, sans-serif
- **Annotation stack**: Microsoft YaHei, Arial, sans-serif
- **Footnote stack**: Microsoft YaHei, Arial, sans-serif
- **Role rationale**: Display 与 Title 同族但独立成角色,因为 15 页中有 6 页把一个数字放到 60px 以上;Annotation 与 Footnote 同族不同号,分别承担图表注记与全卷来源条/照片署名两种复现结构。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 40 |
| Subtitle | 32 |
| Cover title | 76 |
| Lead | 28 |
| Display | 64 |
| Annotation | 18 |
| Footnote | 15 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 从顶部规则线下的判断句标题开始,向下进入左侧的主证据(图/表/大数),右侧或下方接解释与结构拆分,最后落到页底来源条
- **Composition tendency**: 数据页用两栏或"主证据 + 右侧窄解释栏"的不对称分割;现场页取消栅格,照片整幅出血,文字收到一角
- **Cross-page continuity**: 顶部 2px 主色规则线、右上角板块名、页底来源条三件框架元素每页复现且不参与动画;复兴号封面照片在 P01→P02 之间以同一构件缩放推移;货运总量数字在 P06→P07 之间推移
- **Spacing posture**: 按 page_rhythm 变化——dense 页贴近栅格上限,breathing 页把内容压到半幅以下
- **Spacing anchors**: 页边距 72px;块间距 32px;栏间距 40px;圆角半径 0px;正文行高 1.7em(≈41px)

## VI. Icon Usage Specification

- **Primary bundled library**: chunk-filled

| Icon Path | Suitable Scenarios |
| --- | --- |
| icons/chunk-filled/train.svg | 客运、列车、动车组 |
| icons/chunk-filled/users.svg | 旅客发送量、人次 |
| icons/chunk-filled/truck.svg | 货运总量 |
| icons/chunk-filled/box.svg | 集装箱、班列标箱 |
| icons/chunk-filled/fire.svg | 煤炭等燃料品类 |
| icons/chunk-filled/factory.svg | 冶炼物资、工业品类 |
| icons/chunk-filled/droplet.svg | 石油品类 |
| icons/chunk-filled/seedling.svg | 粮食、化肥及农药品类 |
| icons/chunk-filled/leaf.svg | 节能减排、绿色 |
| icons/chunk-filled/recycle.svg | 排放下降、循环 |
| icons/chunk-filled/bridge.svg | 桥梁、工程 |
| icons/chunk-filled/route.svg | 路网、营业里程 |
| icons/chunk-filled/coin.svg | 固定资产投资 |
| icons/chunk-filled/shield-check.svg | 运输安全 |
| icons/chunk-filled/badge-check.svg | 技术标准 |
| icons/chunk-filled/trophy.svg | 科技奖项 |
| icons/chunk-filled/lightbulb.svg | 科技创新 |
| icons/chunk-filled/globe.svg | 国际对照、国际标准 |
| icons/chunk-filled/gauge-high.svg | 综合能耗强度 |
| icons/chunk-filled/file.svg | 规章与行政规范性文件 |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P03 | chart | column_chart | 六年旅客发送量的逐年变化与 2024 年的位置 |
| P04 | table | hierarchical_table | 公报原表:全国铁路旅客运输量的分项与同比 |
| P06 | chart | column_chart | 六年货运总发送量的逐年变化 |
| P07 | chart | horizontal_bar_chart | 2024 年六大品类运量的量级排序 |
| P08 | chart | area_chart | 六年总换算周转量的总量走势 |
| P09 | table | record_table | 机车/客车/货车三类装备的拥有量与构成 |
| P11 | chart | line_chart | 八国铁路营业里程 2000–2021 的长期对照 |
| P13 | chart | line_chart | 化学需氧量与二氧化硫排放量的六年下降 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| fuxing_train.jpg | 3840x2560 | 1.50 | 封面主视觉,并在总览页以同一张照片的窄立幅延续 | Photography | 封面整幅铺底,车头偏右、左侧天空作安静区承接标题;总览页把同一张收成右侧窄立幅,只留车头 | adaptive | user | Existing | CR400AF-2007 复兴号动车组(N509FZ,CC BY-SA 4.0);同一文件在 P01 与 P02 用不同裁切复用,构成尺寸与位置推移 | — | — |
| beijing_south_station.jpg | 2560x1600 | 1.60 | 客运结构页的现场佐证 | Photography | 沿站台纵深裁成横条压在表格上方,人流方向朝向表格 | adaptive | user | Existing | 北京南站站台(颐园新居,CC BY-SA 4.0) | — | — |
| shanghai_hongqiao.jpg | 3840x2558 | 1.50 | 现场页主图,承担"现场"一侧的质地 | Photography | 候车大厅整幅出血,顶部结构线留白、底部压暗后承接文字 | adaptive | user | Existing | 上海虹桥站候车大厅(Patrick Nagel,CC BY-SA 3.0) | — | — |
| fuxing_interior.jpg | 3840x2560 | 1.50 | 装备页的车内实景,与装备表并置 | Photography | 竖切放右侧半幅,与左侧装备表齐顶 | adaptive | user | Existing | CR400AF-AE-2399 商务座车厢内景(N509FZ,CC BY-SA 4.0) | — | — |
| danyang_kunshan_bridge.jpg | 3840x2158 | 1.78 | 路网页的工程实景 | Photography | 桥体水平线横切成半幅横条压在页面上半,下方接里程数字 | adaptive | user | Existing | 丹昆特大桥(无锡段)(MNXANL,CC BY-SA 4.0) | — | — |
| qinghai_tibet_railway.jpg | 2400x1800 | 1.33 | 绿色低碳页的线路实景,给排放曲线一个现场落点 | Photography | 方形小幅裁切放页面右下,与曲线末端呼应 | adaptive | user | Existing | 青藏铁路车厢(Hiroki Ogawa,CC BY 3.0) | — | — |
| fuxing_train_wash.jpg | 1920x1280 | 1.50 | 结论页的压暗收束场,与封面构成同一照片的首尾呼应 | Derived photography | 整幅压暗铺底,三条结论压在中部安静区 | adaptive | user | Existing | Derived from fuxing_train.jpg; treatment=brightness 0.55 + desaturate 0.8 + fit 1920x1280 | — | — |

## IX. Content Outline

### Part 1: 开场与全年总览

#### Slide 01 - 封面:43.12 亿人

- **Audience move**: 从"要听一份统计汇报"到"2024 年铁路最值得记住的是一个创纪录的客运量"
- **Relationships**: 标题、年度、一个统计量(旅客发送量 43.12 亿人)与封面照片之间是 link——照片是这个数字的现场载体
- **Composition**: 照片整幅出血,左侧天空区压一层渐隐暗场承接标题与大数,右下角贴署名
- **Cover impact**: binding hook —— 用 43.12 亿人这一创历史新高的客运量作钩子,与整幅复兴号照片同框;composition 为 Reference
- **Title**: 中国铁路 2024:数据与现场
- **Core message**: 2024 年全国铁路旅客发送量 43.12 亿人,比上年增长 11.9%,创历史新高
- **Content**: 主标题《中国铁路 2024:数据与现场》· 副标题"《2024年铁道统计公报》数据解读 | 汇报对象:省交通运输部门" · 大数 43.12 亿人 + 同比 +11.9% · 照片署名"复兴号动车组 摄影:N509FZ / CC BY-SA 4.0 / Wikimedia Commons" · 页底来源条"数据来源:国家铁路局《2024年铁道统计公报》"
- **Images**: fuxing_train.jpg 整幅
- **Motion suggestion**: 封面照片与 43.12 这个大数都会在下一页以更小的尺寸再次出现,二者均为 Morph 候选;标题与副标题按先后进场
- **Fact IDs**: B1

#### Slide 02 - 2024 年全年总览(整理)

- **Audience move**: 从只记住客运一个数字,到掌握客运、货运、投资、新线四个总量坐标
- **Relationships**: 四个总量指标之间是 membership(同属 2024 年全国铁路的年度总量),新线里程与其中的高速铁路里程之间是 parent
- **Composition**: 左侧四分之一保留封面照片的窄立幅,右侧四栏等宽 KPI,顶部一句判断
- **Title**: 四个数字看懂 2024 年
- **Core message**: 客运创新高、货运稳中有升、投资与新线保持高位,是 2024 年全国铁路的四个基本面
- **Content**: 旅客发送量 43.12 亿人(+11.9%) · 货运总发送量 51.75 亿吨(+2.8%) · 固定资产投资 8506 亿元 · 投产新线 3113 公里(其中高速铁路 2457 公里) · 页面标注"整理:四项总量由编者从公报正文汇总,数值未作改动"
- **Images**: fuxing_train.jpg 窄立幅(同一文件,另一裁切)
- **Motion suggestion**: 封面照片与 43.12 从上一页推移到本页的新位置与尺寸;四个 KPI 按客运→货运→投资→新线的顺序进场,判断句最后出现
- **Fact IDs**: B1, B4, B10

### Part 2: 客运

#### Slide 03 - 客运:六年回到高位

- **Audience move**: 从"客运增长了 11.9%"到看见这一年在六年曲线中的位置
- **Relationships**: 2019–2024 六个年度值之间是 order(时间顺序),2024 与 2019 之间是 contrast(已越过疫情前水平)
- **Composition**: 左侧四分之三放柱形图,右侧窄栏放两句读法
- **Title**: 43.12 亿人:客运越过 2019 年的高点
- **Core message**: 2024 年旅客发送量 431240 万人,高于 2019 年的 366002 万人,是六年来的最高值
- **Content**: 柱形图:2019 366002 / 2020 220350 / 2021 261171 / 2022 167296 / 2023 385450 / 2024 431240(万人) · 读法一:2022 年的 167296 万人是六年谷底 · 读法二:2024 年比 2019 年高出 65238 万人(编者按两项公报数据相减,标注"整理")
- **Visualization**: pax-sent-6y(柱形图,六年旅客发送量);Native-ready: pax-sent-6y=yes
- **Motion suggestion**: 柱形图整体先出,两句读法在图之后依次进场——解释必须排在被解释对象之后
- **Fact IDs**: C1, B1

#### Slide 04 - 客运结构:公报原表

- **Audience move**: 从总量到知道 43.12 亿人里国家铁路与其他铁路各占多少、周转量方向如何
- **Relationships**: 旅客发送量与旅客周转量之间是 membership(同一张公报表的两组指标);每组内国家铁路、其他铁路与合计之间是 parent
- **Composition**: 上方一条站台横条照片,下方整幅原表,右侧留一列同比方向
- **Title**: 40.85 亿人来自国家铁路
- **Core message**: 国家铁路承担了 40.85 亿人的发送量与几乎全部周转量,其他铁路增速更高但基数很小
- **Content**: 原表(指标/单位/2024年/比上年±%):旅客发送量 万人 431240 11.9;国家铁路 万人 408516 10.9;其他铁路 万人 22724 34.0;旅客周转量 亿人公里 15799.10 7.3;国家铁路 亿人公里 15776.35 7.2;其他铁路 亿人公里 22.74 85.9 · 注记:其他铁路周转量 22.74 亿人公里仅占全国的 0.14%,增速 85.9% 建立在很小的基数上
- **Visualization**: pax-volume-table(公报原表,分组行);Native-ready: pax-volume-table=yes
- **Images**: beijing_south_station.jpg 横条
- **Motion suggestion**: 表格先整体出现,右侧的同比方向标记与底部注记随后进场
- **Fact IDs**: B1, B2, B3

#### Slide 05 - 现场:候车大厅

- **Audience move**: 从表格数字回到 43.12 亿人次实际发生的地方
- **Relationships**: 现场影像与前一页的客运数字之间是 link
- **Composition**: 照片整幅出血,底部三分之一压暗承接一句话与署名,不设栅格
- **Title**: 43.12 亿人次,发生在这里
- **Core message**: 客运总量最终落在车站与候车大厅的实际承载上
- **Content**: 一句话:平均每天约 1180 万人次通过全国铁路发送(编者按 431240 万人 ÷ 366 天测算,标注"整理") · 照片署名"上海虹桥站候车大厅 摄影:Patrick Nagel / CC BY-SA 3.0 / Wikimedia Commons"
- **Images**: shanghai_hongqiao.jpg 整幅出血
- **Motion suggestion**: 照片作为场景保持不动,只有压暗层与那一句话进场
- **Fact IDs**: B1

### Part 3: 货运与周转

#### Slide 06 - 货运:总量连续六年上行

- **Audience move**: 从客运切到货运,建立"总量在涨、周转在落"的对照
- **Relationships**: 六个年度发送量之间是 order;发送量与周转量之间是 contrast(方向相反)
- **Composition**: 左侧柱形图,右侧一个大数与两行分项
- **Title**: 51.75 亿吨:总量上行,周转量回落
- **Core message**: 货运总发送量连续六年上行至 517477 万吨,而总周转量下降 1.6%
- **Content**: 柱形图:2019 441213 / 2020 455236 / 2021 477372 / 2022 498424 / 2023 503535 / 2024 517477(万吨) · 大数 51.75 亿吨(+2.8%) · 货运总周转量 35861.90 亿吨公里(-1.6%);国家铁路 32580.63(-0.2%),其他铁路 3281.26(-14.1%)
- **Visualization**: freight-sent-6y(柱形图,六年货运总发送量);Native-ready: freight-sent-6y=yes
- **Motion suggestion**: 51.75 亿吨这个大数会在下一页作为品类合计的引子再次出现,是 Morph 候选;柱形图先出,周转量的对照行随后
- **Fact IDs**: C3, B4, B5

#### Slide 07 - 货运品类:集装箱领涨,粮食领跌

- **Audience move**: 从货运总量到知道 51.75 亿吨由哪些品类构成、谁在涨谁在落
- **Relationships**: 六个品类之间是 membership(同属主要品类运量),各品类与其同比之间是 link,集装箱与粮食之间是 contrast
- **Composition**: 横条按运量降序排列,条右端接同比,顶部保留货运总量作引子
- **Title**: 煤仍占大头,集装箱增长最快
- **Core message**: 煤炭 28.24 亿吨仍是最大品类,集装箱以 +15.5% 增长最快,粮食以 -17.6% 下降最多
- **Content**: 横条图(万吨,2024,比上年):煤 282365 +1.5% · 集装箱 91371 +15.5% · 冶炼物资 87726 -3.6% · 石油 13322 +2.1% · 粮食 5640 -17.6% · 化肥及农药 4765 -5.2% · 顶部引子:货运总发送量 51.75 亿吨
- **Visualization**: freight-category-2024(横条图,六品类运量与同比);Native-ready: freight-category-2024=yes
- **Motion suggestion**: 上一页的货运总量数字推移到本页顶部作引子;横条按从多到少依次出现,同比标记在对应条之后
- **Fact IDs**: B6, B4

#### Slide 08 - 换算周转量与国际班列

- **Audience move**: 从客货分别的量到一个把两者折算在一起的总指标,并看到跨境通道的规模
- **Relationships**: 六年总换算周转量之间是 order;国家铁路与其他铁路之间是 parent;中欧班列与西部陆海新通道之间是 membership(同属跨境/跨区域班列)
- **Composition**: 上半幅面积图,下半两个并列的班列数字块
- **Title**: 51661 亿吨公里:总换算周转量小幅上行
- **Core message**: 2024 年总换算周转量 51661.00 亿吨公里,增长 0.9%,其中国家铁路增长 2.1%、其他铁路下降 13.8%
- **Content**: 面积图:2019 44924.00 / 2020 38780.65 / 2021 42805.81 / 2022 42523.22 / 2023 51189.74 / 2024 51661.00(亿吨公里) · 国家铁路 48356.99(+2.1%),其他铁路 3304.01(-13.8%) · 中欧班列开行 1.9 万列、发送 207 万标箱(分别 +10%、+9%) · 西部陆海新通道班列发送 96 万标箱(+11%)
- **Visualization**: converted-turnover-6y(面积图,六年总换算周转量);Native-ready: converted-turnover-6y=yes
- **Motion suggestion**: 面积图先出,两个班列数字块随后并列进场
- **Fact IDs**: C5, B8, B7

### Part 4: 装备与路网

#### Slide 09 - 运输装备:机车、客车与货车

- **Audience move**: 从运量到承担运量的车辆家底
- **Relationships**: 机车、客车、货车之间是 membership;内燃/电力与机车之间、动车组与客车之间是 parent
- **Composition**: 左侧装备表,右侧车厢内景竖切,两者齐顶
- **Title**: 101.9 万辆货车,4806 标准组动车组
- **Core message**: 电力机车已占机车总量的三分之二,动车组规模达到 4806 标准组
- **Content**: 表格(类别/2024年拥有量/构成):机车 2.25 万台 —— 内燃机车 0.78 万台、电力机车 1.47 万台;客车 8.1 万辆 —— 其中动车组 4806 标准组、38448 辆;货车 101.9 万辆 —— 公报未列分项 · 注记:电力机车 1.47 万台占机车总量约 65%(编者按公报两项数值计算,标注"整理")
- **Visualization**: equipment-table(装备表);Native-ready: equipment-table=yes
- **Images**: fuxing_interior.jpg 竖切
- **Motion suggestion**: 表格先出,右侧照片与底部注记随后
- **Fact IDs**: B12

#### Slide 10 - 路网:16.2 万公里与它的结构

- **Audience move**: 从车辆到线路,掌握营业里程及其电气化、复线、区域结构
- **Relationships**: 高速铁路里程、西部地区里程与全国营业里程之间是 parent;复线率与电化率之间是 membership(同属路网质量指标)
- **Composition**: 上半幅桥梁横条照片,下半左侧大数、右侧四个结构指标
- **Title**: 16.2 万公里,其中高铁 4.8 万公里
- **Core message**: 全国铁路营业里程达到 16.2 万公里,高铁占比接近三成,电化率 76.2%
- **Content**: 营业里程 16.2 万公里 · 高速铁路 4.8 万公里 · 复线率 60.8% · 电化率 76.2% · 西部地区 6.6 万公里 · 路网密度 168.5 公里/万平方公里
- **Images**: danyang_kunshan_bridge.jpg 横条
- **Motion suggestion**: 大数先出,四个结构指标随后依次进场
- **Fact IDs**: B11

#### Slide 11 - 国际对照:八国营业里程(整理)

- **Audience move**: 从本国里程到知道中国在长期对照中的位置,同时知道这组数据与公报口径不同
- **Relationships**: 八条国别曲线之间是 contrast;世界银行口径与公报口径之间是 contrast(不可直接相减)
- **Composition**: 整幅折线图,右侧末端贴国名标签,底部一条口径说明
- **Title**: 2000 年以来,只有中国的里程曲线在持续抬升
- **Core message**: 按世界银行 IS.RRS.TOTL.KM 口径,2000–2021 年中国铁路里程从 58656 公里增至 109767 公里,是八国中唯一持续上行的曲线
- **Content**: 折线图(公里,2000–2021):中国 58656→109767 · 美国 194077→148553 · 俄罗斯 86075→85544 · 印度 62759→68103 · 德国 36642→33401 · 法国 29330→27716 · 西班牙 13868→15963 · 日本仅 2010(20140.3)、2011(20087.4)两年有值,其余年份数据缺失 · 口径说明:该数据集为 route-km 口径,2022–2024 年八国均无值;其中国值 109767 公里与公报"营业里程 16.2 万公里"口径不同,不可直接比较(整理)
- **Visualization**: intl-route-km(折线图,八国营业里程);Native-ready: intl-route-km=yes
- **Motion suggestion**: 先出中国一条曲线,其余七条随后一并出现,口径说明最后进场
- **Fact IDs**: W1, B11

### Part 5: 科技、安全、绿色与监管

#### Slide 12 - 科技创新与运输安全

- **Audience move**: 从规模指标转到质量指标:标准、奖项与事故
- **Relationships**: 国家标准、行业标准、国际标准之间是 membership;科技奖项与成果库入库之间是 link;安全三项数据之间是 membership
- **Composition**: 左右两栏——左栏科技(标准与奖项),右栏安全(事故与死亡人数),中间一条竖分隔线
- **Title**: 20 项国家标准,2 件较大事故
- **Core message**: 标准与科技成果持续产出的同时,全年未发生特别重大、重大事故,死亡人数下降 18.0%
- **Content**: 铁路国家标准 20 项、行业标准 95 项 · 主持制定的国际标准 7 项 · 国家计量规程规范 4 项、行业计量规程规范 4 项 · 6 个项目获 2023 年度国家科学技术奖,"复兴号高速列车"获国家科学技术进步奖特等奖 · 重大科技创新成果库 2024 年度入库 335 项 · 新研发 BH10 冷藏车、FXD2BA 与 FXD1BA 电力机车共 3 个型号,建立中国标准新能源机车平台 · 全年未发生特别重大、重大事故;发生较大事故 2 件,与上年持平;事故死亡人数比上年下降 18.0%
- **Motion suggestion**: 左栏科技条目先出,右栏安全条目随后,分隔线随左栏一同出现
- **Fact IDs**: B13, B14, B9

#### Slide 13 - 绿色低碳:能耗微升,排放持续下降

- **Audience move**: 从"铁路更环保"的印象到两条可核对的曲线与两个能耗强度数字
- **Relationships**: 化学需氧量与二氧化硫两条曲线之间是 membership(同属主要污染物排放);能耗总量与单位能耗之间是 parent;能耗方向与排放方向之间是 contrast
- **Composition**: 左侧双系列折线,右侧两个能耗强度数字与一张小幅线路实景
- **Title**: 二氧化硫排放六年降到 456 吨
- **Core message**: 主要污染物排放连续六年下降,但单位运输工作量综合能耗比上年微升 1.3%
- **Content**: 折线图(吨):化学需氧量 2019 1732 / 2020 1623 / 2021 1606 / 2022 1427 / 2023 1466 / 2024 1337;二氧化硫 2019 5286 / 2020 3418 / 2021 2340 / 2022 1315 / 2023 652 / 2024 456 · 2024 年 COD 比上年减少 130 吨,二氧化硫减少 196 吨 · 国家铁路能源消耗折算标准煤 1801.2 万吨(+2.8%,增加 48.5 万吨) · 单位运输工作量综合能耗 3.86 吨标准煤/百万换算吨公里(+1.3%)
- **Visualization**: emission-6y(双系列折线,COD 与二氧化硫);Native-ready: emission-6y=yes
- **Images**: qinghai_tibet_railway.jpg 方形小幅
- **Motion suggestion**: 两条曲线先出,右侧能耗强度数字随后,实景小幅最后
- **Fact IDs**: C7, B16, B15

#### Slide 14 - 行业监管:许可、企业与处罚

- **Audience move**: 从运输与工程转到行业治理的年度动作量
- **Relationships**: 各类许可企业之间是 membership;新增数与累计数之间是 parent;许可与处罚之间是 contrast(准入与惩戒两侧)
- **Composition**: 低密度页——上方一行三个许可数字,下方一行三个处罚数字,大量留白
- **Title**: 622 件行政许可,198 起行政处罚
- **Core message**: 准入侧持续扩容,监管侧同时保持处罚与督办强度
- **Content**: 1 部规章、7 件行政规范性文件完成制定修订并公布 · 行政许可决定书 622 件 · 铁路运输企业新增 4 家、累计 81 家;基础设备生产企业新增 2 家、累计 116 家;机车车辆设计制造维修进口企业新增 1 家、累计 124 家 · 铁路机车车辆驾驶人员新增 10933 人、累计 220308 人 · 行政处罚 198 起、处罚决定 383 个 · 预警 262 次、通报 333 次、约谈 68 次、挂牌督办 24 次
- **Motion suggestion**: 上排许可数字先出,下排处罚数字随后
- **Fact IDs**: B17

#### Slide 15 - 结论:带走三条判断(整理)

- **Audience move**: 从十几页数据到三条可以复述、可以带回本省的判断
- **Relationships**: 三条判断之间是 order(按客运、货运、网络与绿色的汇报顺序);每条判断与其支撑数字之间是 link
- **Composition**: 压暗的封面照片铺底,三条判断纵向排列,每条右侧贴支撑数字
- **Closing impact**: binding takeaway —— 三条判断分别落在客运创高、货运结构分化、网络扩张与排放下降;composition 为 Reference
- **Title**: 三条判断
- **Core message**: 客运创历史高位、货运总量升而周转落且结构分化、路网装备继续扩张而主要污染物持续下降
- **Content**: 判断一:客运已越过疫情前水平并创历史高位——43.12 亿人(+11.9%),高于 2019 年的 36.60 亿人 · 判断二:货运总量稳中有升但周转量小幅回落,结构上集装箱 +15.5% 领涨、粮食 -17.6% 领跌 · 判断三:网络与装备继续扩张(新线 3113 公里、高铁营业里程 4.8 万公里),能耗强度 +1.3% 微升而二氧化硫排放降到 456 吨 · 页面标注"整理:三条判断由编者归纳,支撑数值全部取自公报,未作改动" · 页底"数据来源:国家铁路局《2024年铁道统计公报》;国际对照数据:World Bank IS.RRS.TOTL.KM"
- **Images**: fuxing_train_wash.jpg 整幅压暗
- **Motion suggestion**: 三条判断依次进场,支撑数字随各自判断之后出现
- **Fact IDs**: B1, C1, B4, B5, B6, B10, B11, B15, B16

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 每页备注写主讲人现场讲法:先一句本页要让来访方记住的判断,再说明页面上数字的出处(公报第几部分或世界银行表的哪一行),最后给一句过渡。凡页面标注"整理"的推算,备注必须复述其算式与依据。数字一律复述附件原值,不得引入附件之外的事实。
- **Total duration**: 约 25 分钟(15 页,平均每页 90–110 秒)
- **Notes style**: 正式、可照读,面向接待汇报场景
- **Presentation purpose**: 先完整汇报 2024 年全国铁路数据,再通过国际对照与现场影像建立印象,最后给出三条可带走的判断
