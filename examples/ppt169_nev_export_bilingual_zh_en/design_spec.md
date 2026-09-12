<!-- ppt-master-schema: design-spec/v1 -->
# nev_export_bilingual_zh_en - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | nev_export_bilingual_zh_en |
| Canvas Format | PPT 16:9 (1280×720) |
| Page Count | 15 |
| Primary Language | zh-CN |
| Target Audience | 一半中国同事(产业研究、销售与战略)、一半海外合作伙伴(经销商与合资方);双方都熟悉汽车行业,但对中国统计口径、企业口径与政策细节的掌握程度不同 |
| Communication Intent | 先用公开数据说明 2025 年中国新能源汽车出海的规模与结构;再解释关税与本地化如何改变出海方式;最后对齐 2026 年双方可共同判断的方向。报告与解释优先,不做投资建议 |
| Desired Audience Outcome | 中外双方能用同一套口径明确的数字描述 2025 年出海格局,能说出关税与海外建厂之间的因果关系,并对"增量重心从整车出口转向海外生产"形成共识 |
| Core Message / Ask / Action | 2025 年中国新能源汽车出口翻倍至 261.5 万辆(中汽协口径),但增长方式已从"卖整车"转向"在当地造车、建网络";2026 年的增量要靠海外产能与价格承诺机制 |
| Delivery Context | 主要为有主讲人的 30 分钟双语行业例会现场讲解(投影);次要为会后中外双方各自独立阅读的简报材料 |
| Artifact Afterlife | 作为双方共享的事实基线与后续合作讨论的引用材料,需要可追溯到来源机构与年份 |
| Reading Mode | balanced |
| Content Strategy | 平衡默认(用户未声明素材取舍偏好):按本简报的沟通目标重新组织调研补充中的事实,保留全部实质内容与口径限定,不引入调研之外的事实 |
| Design Style | 方向一「双语公报 / Bilingual Gazette」——数据新闻式栅格公报,中文主行与英文副行成对分层 |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 工作流默认值(Stage 2 proactive notes 取默认 true,用户未反对) |
| Custom Animations | enabled — 用户显式要求"要有自定义动画和 Morph"(对象级动画 + 页间 Morph 转场) |
| Narration Audio | disabled — 工作流默认值(用户未要求旁白音频) |
| Created Date | 2026-09-12 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 上 56 / 下 64 / 左右 72;底部 64 含常驻来源条 |
| Content Area | x 72–1208(宽 1136),y 56–656(高 600) |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: briefing, pyramid
- **Mode Behavior**: 每一部分的首页先给一句可引用的判断句(pyramid 的结论先行),部分内的页面按 briefing 的等权可扫读方式铺开事实与口径,标题写成判断而非话题词;结尾把四个部分的判断收束为双方可共同使用的议题,不做投资建议。
- **Visual style**: custom
- **Visual Style References**: data-journalism, swiss-minimal, editorial
- **Visual Style Behavior**: 以 data-journalism 负责多栏证据密度、微型图注与常驻来源条;swiss-minimal 负责 12 栏硬栅格、大留白与近零装饰,使同页双语不靠色块分区而靠栅格与细规则线分层;editorial 负责中文衬线标题与拉丁衬线副标题的层级互文、细规则线与边注。中文主行与英文副行永远上下成对,英文行以更小字号、次级文字色与 0.5px 细线左缘标记为副层,不另起色块。
- **Theme**: 出海年鉴——用公报式栅格承载两种语言,同一栏里中文在上、英文在下,数字与来源常驻可引用
- **Tone**: 克制、可核查、供双方引用;不渲染胜利叙事,也不淡化壁垒

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #FFFFFF | 页面主底,公报纸感 |
| Secondary background | #F2F4F7 | 数据面板、表格与口径框的底 |
| Primary | #0E3A66 | 中文标题、栅格主线、结构性文字 |
| Accent | #D4541E | 关键数字、增长方向与当页焦点(每页仅一处主焦点) |
| Secondary accent | #2E7D8F | 第二数据序列、海外产能与网络类信息 |
| Body text | #1B2430 | 中文正文 |
| Secondary text | #5C6673 | 英文副行、注释、图注 |
| Divider | #D8DEE6 | 分栏细线、表格边线 |
| Surface | #FAFBFC | 面板抬升层,比 secondary background 更浅 |
| Grid | #E8ECF1 | 图表网格与发丝线,比 divider 更浅 |
| Positive | #2E7D32 | 同比增长、正向变化 |
| Negative | #C62828 | 同比下降、税率与壁垒 |
| Warning | #F57C00 | 未生效、待确认的机制(价格承诺) |

### AI Image Strategy

- **Image Rendering**: custom
- **Image Rendering References**: editorial, minimalist-swiss
- **Visual**: 扁平矢量编辑插画——只用简化的几何体块与 1.5px 轮廓表现滚装码头、厂房与充电阵列,平面无渐变,单一光源方向的浅色块面,不含任何真实品牌标识、车标与文字
- **Mood**: 克制的行业年鉴插图,像《经济学人》图表页旁的说明插画,而非广告主视觉
- **Image Rendering Behavior**: 由 editorial 负责杂志信息图的体块归纳与说明性构图,由 minimalist-swiss 负责大留白、硬边缘与近零装饰;线条为等宽 1.5px 深蓝轮廓,质感为纯平色块与 8% 主色薄阴影,深度靠体块重叠而非渐变,材质统一为哑光纸面,情绪安静、可引用。

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 衬线/公报权威 | SimSun | Cambria | serif |
| Body | 无衬线/屏幕可读 | Microsoft YaHei | Cambria | sans-serif |
| En title | 衬线/拉丁副标题 | Cambria | Cambria | serif |
| En body | 衬线/拉丁副行与全部数字 | Cambria | Cambria | serif |
| Display | 衬线/封面与章节大字 | SimSun | Cambria | serif |

- **Typography upgrade (Reference)**: 若目标机确认安装思源宋体 Source Han Serif,可将中文标题由 SimSun 升级为 Source Han Serif SC;未确认前保持 SimSun。
- **Title stack**: SimSun
- **Body stack**: Microsoft YaHei
- **En title stack**: Cambria
- **En body stack**: Cambria
- **Display stack**: SimSun
- **Role rationale**: 双语同页使两条拉丁文本行成为结构性角色(每页标题副行 + 每个要点的英文行),故把拉丁面单独声明为 `en_title` / `en_body` 两个复现角色,并让全卷数字统一走该拉丁面(Cambria 为 lining figures),避免中文面渲染西文数字造成的字宽与基线漂移;三个字族到顶,不再引入第四族。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 22 |
| Title | 40 |
| Subtitle | 28 |
| Annotation | 17 |
| Display | 64 |
| Lead | 26 |
| Footnote | 14 |
| En title | 24 |
| En body | 18 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 左上判断句 → 右侧或下方证据(图/表/数字)→ 底部来源条;同一栏内永远中文在上、英文在下,读者选定语言后只需垂直扫一列
- **Composition tendency**: 12 栏硬栅格上的双语成对分层;每页一个焦点数字或一个证据对象,其余为支撑栏;部分首页在右上角标出部分序号与双语部分名
- **Cross-page continuity**: 常驻元素为页眉细规则线、右上角部分索引、底部来源条(机构 + 年份);Morph 页对之间保留同一数据对象的位置与命名,仅改变其状态
- **Spacing posture**: variable by page rhythm——dense 页用双栏或三栏并列,breathing 页只留一条中央论证轴
- **Spacing anchors**: 页边距 72px;块间距 28px;栏间距 32px;圆角 0px(公报硬边);正文行距 34px

## VI. Icon Usage Specification

- **Primary bundled library**: chunk-filled

| Icon Path | Suitable Scenarios |
| --- | --- |
| icons/chunk-filled/ship.svg | 整车出口、滚装运输、出海总量 |
| icons/chunk-filled/factory.svg | 海外工厂、本地生产、产能 |
| icons/chunk-filled/truck.svg | 商用车与物流、交付 |
| icons/chunk-filled/plug.svg | 充电与补能网络 |
| icons/chunk-filled/globe.svg | 目的市场、区域分布 |
| icons/chunk-filled/map-pin.svg | 具体国家与工厂所在地 |
| icons/chunk-filled/chart-bar.svg | 数量对比与排名 |
| icons/chunk-filled/chart-line.svg | 年度序列与增速 |
| icons/chunk-filled/table.svg | 口径对照与企业对照 |
| icons/chunk-filled/percent.svg | 税率、占比、同比 |
| icons/chunk-filled/shield-check.svg | 合规、价格承诺、准入 |
| icons/chunk-filled/circle-exclamation.svg | 壁垒、风险与未生效事项 |
| icons/chunk-filled/circle-checkmark.svg | 已落地事实与已投产 |
| icons/chunk-filled/calendar.svg | 生效日期与时间表 |
| icons/chunk-filled/coin.svg | 投资额与均价 |
| icons/chunk-filled/building.svg | 企业主体与机构 |
| icons/chunk-filled/target.svg | 2026 目标与展望 |
| icons/chunk-filled/arrow-trend-up.svg | 增长方向 |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P04 | chart | donut_chart | 2025 年汽车出口总量中新能源与传统燃料的构成比例 |
| P05 | chart | column_chart | 2022–2025 年新能源汽车出口量的逐年台阶式变化 |
| P07 | chart | horizontal_bar_chart | 2025 年前三大出口目的国的出口量对比 |
| P08 | table | metric_table | 五家代表企业 2025 年出口量、同比与主要落点的对照 |
| P10 | table | record_table | 四个海外基地的国别、时间、产能与投资额记录 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cover_port_roro.jpg | 2048×2048 | 1:1 | 封面主视觉:出海的实体场景锚点 | Illustration | 右侧竖幅满高图版,与左侧双语标题栏以一条竖向细规则线相接,图像只占右 45% 宽 | adaptive | ai | Generated | 简化几何体块的滚装码头:一艘侧视滚装船、三层车辆甲板轮廓、岸边两台岸桥与整齐排列的无标识乘用车块;深蓝主色体块 + 暖橙单点强调;无任何品牌标识、车标、文字与人物 | none | hero_page |
| local_plant.jpg | 1264×848 | 1.49:1 | 本地化部分首页:说明"在当地造车"的场景 | Illustration | 右栏说明性插画,与左栏三步框架并列,底边与框架末行对齐 | adaptive | ai | Generated | 简化几何体块的整车工厂:长条厂房轮廓、两座焊装车间体块、屋顶光伏条纹、厂前三辆无标识整车与一列集装箱;深蓝轮廓 + 青蓝屋面;无品牌标识与文字 | none | local |
| charging_array.jpg | 1376×768 | 1.79:1 | 充电与售后网络页:补能网络的视觉锚点 | Illustration | 页面下半幅横向带状插画,上方为三地闪充站数字,插画作为数字的底座 | adaptive | ai | Generated | 简化几何体块的公共快充站阵列:六根等距充电桩剪影、顶棚横板、两辆无标识车辆侧视轮廓、地面标线;深蓝轮廓 + 暖橙充电指示点;无品牌标识与文字 | none | local |

## IX. Content Outline

### Part 0: 开篇 Opening

#### Slide 01 - 封面 Cover

- **Audience move**: 从"又一份出口数据汇报"→ 立刻知道本场要讲的是出海方式的变化,而不只是数量
- **Relationships**: 标题与副标题为 parent(主题与年度范围);中文标题行与英文标题行为 link(同一内容的两种语言);钩子判断句与副标题为 contrast(翻倍 vs 方式改变)
- **Cover impact**: 钩子为"出口翻倍,但增长方式变了 / Exports doubled — the growth model changed"(binding 的是这句判断,构图可改)
- **Composition**: 左栏双语标题与钩子,右侧竖幅插画满高,二者以一条竖向细规则线相接;左下角放机构与年份的来源条
- **Title**: 中国新能源汽车出海 2025 / China's NEV Exports 2025
- **Core message**: 2025 年出口翻倍,但真正的变化是从卖整车转向在当地造车
- **Content**: 主标题中英双语并置 · 钩子判断句(中英各一行)· 副标题"公开数据行业简报 · 中汽协/海关口径标注 / An industry briefing on public data" · 日期与页数说明
- **Images**: cover_port_roro.jpg
- **Motion suggestion**: 标题对(中英)作为一个单元先进场,钩子判断句随后,插画最后以位置轻移到位;来源条不动
- **Fact IDs**: F001, F002

#### Slide 02 - 本次简报的四个部分 Agenda

- **Audience move**: 从不知道信息顺序 → 知道四个部分各回答什么问题,并能挑自己关心的部分
- **Relationships**: 四个部分为 order(规模 → 市场 → 本地化 → 壁垒与展望);每个部分名与其问句为 parent
- **Composition**: 四栏等宽并列,每栏一个部分序号、双语部分名与一行双语问句;栏间细规则线
- **Title**: 本次简报的四个部分 / Four Parts of This Briefing
- **Core message**: 从规模到方式再到规则,四个部分回答四个问题
- **Content**: 一 规模与口径 Scale & Calibres:出口了多少,按谁的口径 · 二 市场与企业 Markets & Players:卖到哪里,谁在卖 · 三 本地化 Localization:为什么开始在当地造车 · 四 壁垒与展望 Barriers & Outlook:规则怎么变,2026 怎么看
- **Motion suggestion**: 四栏按部分顺序依次进场,每栏的中英部分名同时出现,问句紧随该栏之后

### Part 1: 规模与口径 Scale & Calibres

#### Slide 03 - 先说口径:本简报怎么读 How to Read the Numbers

- **Audience move**: 从"中国的出口数字总是对不上"→ 知道本简报每个数字属于哪个口径、来自哪个机构与年份
- **Relationships**: 三个机构口径为 contrast(中汽协 / 乘联分会 / 海关与整车均价);口径说明与后续各页数字为 parent(本页规则管全卷)
- **Composition**: 中央一条论证轴:上方一句双语判断,下方三个并列口径卡,每卡一行机构、一行覆盖范围、一行本简报如何使用
- **Title**: 先说口径:同一年有两个"新能源出口"数字 / Two Calibres, One Year
- **Core message**: 本简报以中汽协口径为主,乘联分会口径并列标注,不做相加与折中
- **Content**: 本页为整理页(编者按调研来源整理,非单一来源原文)· 中汽协口径:2025 年新能源汽车出口 261.5 万辆,本简报主口径 · 乘联分会口径:同年 343 万辆,统计范围更宽,并列标注 · 出口均价与目的国排名采用乘联分会整车统计,含燃油车 · 每页底部常驻来源条:机构 + 年份
- **Fact IDs**: F002, F009, F006
- **Motion suggestion**: 判断句先进场,三张口径卡依次进场,"本简报如何使用"这一行始终排在该卡其余两行之后

#### Slide 04 - 2025 年出口总量与构成 2025 Volumes

- **Audience move**: 从模糊的"中国出口很多车"→ 记住 709.8 万辆总量里新能源占 261.5 万辆,且只有新能源在增长
- **Relationships**: 总量与两个分项为 parent(709.8 = 261.5 + 448.3);新能源与传统燃料的增速为 contrast(+103.7% vs -2%)
- **Composition**: 左侧环形构成图与中心总量数字,右侧两行双语要点各配一个增速标记;右上角部分索引"一 / Part 1"
- **Title**: 总量 709.8 万辆,增量全部来自新能源 / All Growth Came from NEVs
- **Core message**: 2025 年汽车出口 709.8 万辆中新能源 261.5 万辆,传统燃料同比下降
- **Content**: 汽车出口 709.8 万辆,同比 +21.1%(中汽协,2026 年 1 月发布)· 新能源汽车 261.5 万辆,同比 +103.7% · 传统燃料汽车 448.3 万辆,同比 -2% · 新能源占出口总量约 36.8%(由前两项计算)
- **Visualization**: 环形构成图 `export-mix-donut`,两段为新能源 261.5 万辆与传统燃料 448.3 万辆,中心标注总量 709.8 万辆;Native-ready `export-mix-donut=yes`
- **Fact IDs**: F001, F002, F003
- **Motion suggestion**: 环形两段按"新能源先、传统燃料后"进场,中心总量随后,右侧两行要点对应各自扇段依次进场

#### Slide 05 - 四年台阶 Four-Year Step Change

- **Audience move**: 从"出口在增长"→ 看出 2024 年几乎走平、2025 年才翻倍,增长不是匀速
- **Relationships**: 四个年度值为 order(2022→2025);2024 与 2025 为 contrast(走平 vs 翻倍)
- **Composition**: 下方四根年度柱列占页宽三分之二,2025 柱用强调色并引出一条注记线;上方一句双语判断,右侧留白放"台阶"注记
- **Title**: 不是匀速,是两级台阶 / Not Steady Growth, but Two Steps
- **Core message**: 新能源出口从 2022 年 67.9 万辆到 2025 年 261.5 万辆,2024 年几乎走平后在 2025 年翻倍
- **Content**: 2022 年 67.9 万辆 · 2023 年 120.3 万辆 · 2024 年 128.4 万辆 · 2025 年 261.5 万辆 · 2024→2025 增幅 +103.7%,2023→2024 仅约 +6.7%(由年度值计算)
- **Visualization**: 年度柱列 `nev-export-series`,类别为 2022/2023/2024/2025,值为万辆;Native-ready `nev-export-series=yes`
- **Fact IDs**: F005, F004, F002
- **Motion suggestion**: 四根柱按年份顺序升起,2025 柱到位后其"翻倍"注记再出现;2025 柱及其数值标签同时是本页与下一页之间保留身份的视觉端点

#### Slide 06 - 同一年,两个数字 Same Year, Two Numbers

- **Audience move**: 从"你们的数字和我看到的不一样"→ 能自己判断对方引用的是哪一套口径
- **Relationships**: 两个口径值为 contrast(261.5 万辆 vs 343 万辆);均价下降与量增为 overlap(同一批出口的两个侧面)
- **Composition**: 中央论证轴:P05 的 2025 柱留在原位,右侧升起第二根更高的口径柱,两柱之间用一条双语说明线连接;下方一行均价注记
- **Title**: 261.5 还是 343 万辆,取决于谁在统计 / It Depends Who Is Counting
- **Core message**: 口径差异来自统计范围,不是数据打架,引用时必须带机构名
- **Content**: 中汽协:新能源汽车出口 261.5 万辆,同比 +103.7% · 乘联分会:新能源汽车出口 343 万辆,同比 +70%,范围更宽 · 两者不相加、不折中,本简报主口径为中汽协 · 同期整车出口均价 1.6 万美元,低于 2024 年的 1.8 万美元:量增价减
- **Fact IDs**: F002, F009, F008
- **Motion suggestion**: 由 P05 的 2025 柱原地保留,第二根口径柱随后升起,连接两柱的说明线最后出现;均价注记作为整页最后一个单元

### Part 2: 市场与企业 Markets & Players

#### Slide 07 - 目的地换位 The Map Has Shifted

- **Audience move**: 从"中国车主要卖去俄罗斯"→ 知道 2025 年第一目的国已换成墨西哥,且前三名接近
- **Relationships**: 三个目的国为 order(按出口量排序);墨西哥与俄罗斯为 contrast(首次易位);第四至第六名为 membership(同一梯队但本简报无确切值)
- **Composition**: 左侧三条横向长条按量排序并在条内标注国别与区域,右侧一栏双语判断与一行口径提示;右上角部分索引"二 / Part 2"
- **Title**: 第一目的国换成了墨西哥 / Mexico Took the Top Spot
- **Core message**: 2025 年墨西哥以 62.52 万辆首次超过俄罗斯成为第一目的国,前三名差距不到 6 万辆
- **Content**: 墨西哥 62.52 万辆,北美 · 俄罗斯 58.27 万辆,独联体 · 阿联酋 57.2 万辆,中东 · 第四至第六位为英国、巴西、沙特(本简报无确切数值,不作图)· 口径提示:本页为乘联分会整车出口统计,含燃油车
- **Visualization**: 横向条列 `destination-top3`,类别为三个目的国(双语标签),值为万辆;Native-ready `destination-top3=yes`
- **Fact IDs**: F006, F007
- **Motion suggestion**: 三条横条按排名依次伸出,国别与区域标签随各自条出现;口径提示行放在全部条之后

#### Slide 08 - 谁在卖:五家企业 Who Is Exporting

- **Audience move**: 从只记得一两个品牌 → 知道出口第一与增速最快不是同一家,并看到各家的量级差
- **Relationships**: 五家企业为 order(按出口量排序);出口量与同比为 contrast(奇瑞量第一、比亚迪增速第一);企业与集团总销量为 parent
- **Composition**: 整页一张五行对照表,表头双语上下两行,量与同比右对齐;表下一行双语判断句
- **Title**: 量第一与增速第一不是同一家 / Largest Is Not Fastest
- **Core message**: 奇瑞以 134.4 万辆保持出口第一,比亚迪以 +145% 的增速首破百万辆
- **Content**: 奇瑞 134.4 万辆,同比 +17.4%,集团总销量 280.6 万辆 · 上汽 107.1 万辆,MG 品牌欧洲销量 30 万辆以上(同比接近 +30%),集团总销量 450.7 万辆 · 比亚迪 104.96 万辆,同比 +145%,出口约占其总销量 23% · 长安 63.7 万辆,同比 +18.9% · 长城 50.6 万辆,同比 +11.7% · 另:上汽通用五菱出口 26.7 万辆,同比 +128.6%
- **Visualization**: 五行对照表 `exporter-metrics`,行为企业,列为 2025 出口量 / 同比 / 集团总销量或落点(列头中英双行);Native-ready `exporter-metrics=yes`
- **Fact IDs**: F010, F011, F012, F013
- **Motion suggestion**: 表头先出现,五行按排名依次进场,表下判断句最后

### Part 3: 本地化 Localization

#### Slide 09 - 从卖整车到当地造车 From Shipping to Building

- **Audience move**: 从把建厂看作扩张动作 → 理解建厂同时回答关税、交付与服务三个问题
- **Relationships**: 三步为 order(出口整车 → 当地组装/生产 → 当地网络);关税压力与建厂为 link(因果);三步与本部分后两页为parent
- **Composition**: 左栏三步纵向框架,每步一行中英标签与一行说明;右栏工厂插画;右上角部分索引"三 / Part 3"
- **Title**: 建厂不是扩张动作,是回答三个问题 / Local Plants Answer Three Questions
- **Core message**: 本地化同时回答关税、交付与服务三个问题,所以它是 2026 年增量的载体
- **Content**: 本页为整理页(框架由编者按调研事实整理)· 第一步 出口整车:受关税与运输成本直接约束 · 第二步 当地生产:东南亚与拉美服务本地与区域市场,欧洲直接对冲关税并满足当地投资要求 · 第三步 当地网络:充电与售后决定复购,基础设施投入大、回报周期长 · 判断:2026 年的增量更多来自海外产能,而非整车出口
- **Images**: local_plant.jpg
- **Motion suggestion**: 三步按顺序进场,每步的中英标签同时出现、说明行紧随该步之后;插画在第三步后到位;"当地生产"节点是与下一页保留身份的视觉端点

#### Slide 10 - 四个海外基地 Four Overseas Bases

- **Audience move**: 从"中国车企在海外建厂"这一泛化印象 → 记住四个具体基地的地点、时间、产能与投资额
- **Relationships**: 四条记录为 membership(同一类本地化动作);时间与投产状态为 order;欧洲两例与亚洲/拉美两例为 contrast(对冲关税 vs 服务本地市场)
- **Composition**: 整页一张四行记录表,列头双语上下两行;表右侧留一栏放各基地的一句双语用途注记
- **Title**: 四个已落地的海外基地 / Four Bases on the Ground
- **Core message**: 泰国、巴西、匈牙利、西班牙四个基地覆盖了服务本地市场与对冲关税两种目的
- **Content**: 泰国罗勇府:2024 年 7 月 4 日竣工投产,年产能约 15 万辆,同日下线第 800 万辆新能源汽车 · 巴西卡马萨里:2025 年 7 月 1 日首车下线,规划产能 15 万辆,投资 55 亿雷亚尔(约 71 亿元人民币),预计 2 万个就业岗位 · 匈牙利塞格德:投资 40 亿欧元(约 350 亿元人民币),最大年产能 30 万辆、初期约 15 万辆,2026 年一季度试生产、二季度量产 · 西班牙巴塞罗那:合资工厂 2024 年 11 月 23 日投产首款车型,有望带来 1250 个当地就业岗位
- **Visualization**: 四行记录表 `overseas-plants`,行为基地,列为国家与城市 / 时间节点 / 产能 / 投资与就业(列头中英双行);Native-ready `overseas-plants=yes`
- **Fact IDs**: F014, F015, F016, F017
- **Motion suggestion**: 列头先出现,四行按时间顺序进场,右栏用途注记跟在对应行之后

#### Slide 11 - 卖车之后:补能与售后 After the Sale

- **Audience move**: 从"卖出去就完成了"→ 知道网络投入的具体量级与它为什么慢
- **Relationships**: 三地闪充站数为 membership(同一计划的区域拆分);计划量与落地难点为 contrast(投入意愿 vs 推进速度)
- **Composition**: 上半幅三个区域数字并列(欧洲/美洲/亚太),下半幅横向充电站插画作为数字底座;右下角放难点注记
- **Title**: 6000 座闪充站,和它为什么慢 / 6,000 Fast-Charging Sites, and Why It Is Slow
- **Core message**: 海外补能网络已有明确量级计划,但售后与基建的推进速度受审批与协作制约
- **Content**: 计划自 2026 年 3 月至 2027 年 3 月底在海外建成 6000 座闪充站 · 欧洲 3000 座 · 美洲 2000 座 · 亚太 1000 座(比亚迪集团品牌及公关处总经理李云飞,2026 年 7 月)· 难点:充电难与维修难需要售后服务中心、零件仓库与充换电设施配套 · 基础设施投入大、回报周期长,用地审批与跨行业协作使进度常不及预期
- **Images**: charging_array.jpg
- **Motion suggestion**: 三个区域数字按欧洲、美洲、亚太依次进场,总数 6000 在三者之后出现,插画随后到位,难点注记作为整页最后一个单元

### Part 4: 壁垒与展望 Barriers & Outlook

#### Slide 12 - 两道关税墙 Two Tariff Walls

- **Audience move**: 从"听说欧美加了关税"→ 能说出欧盟的分企业税率如何叠加,以及美国税率与生效日
- **Relationships**: 欧盟与美国为 contrast(分企业叠加 vs 统一提高);欧盟各企业税率为 order(7.8%→35.3%);反补贴税与 10% 进口关税为 overlap(叠加)
- **Composition**: 左右两栏各一道"墙":左栏欧盟分企业税率阶梯并标出叠加后的综合税负,右栏美国 100% 与同批其他税率;右上角部分索引"四 / Part 4"
- **Title**: 一道按企业分级,一道一刀切 / One Tiered, One Flat
- **Core message**: 欧盟自 2024 年 10 月 31 日起按企业征收 7.8%–35.3% 反补贴税并叠加 10% 进口关税,美国自 2024 年 9 月 27 日起将电动汽车关税提高到 100%
- **Content**: 欧盟确定性反补贴税自 2024 年 10 月 31 日起生效,叠加在 10% 汽车进口关税之上 · 个别税率:特斯拉 7.8% · 比亚迪 17.0% · 吉利 18.8% · 上汽 35.3% · 配合调查未抽样企业加权平均 20.3% · 美国 301 条款:电动汽车关税自 2024 年 9 月 27 日起提高至 100%,同批还包括光伏电池 50%、动力电池与关键矿产 25%(USTR)
- **Fact IDs**: F018, F019
- **Motion suggestion**: 欧盟税率阶梯自低到高依次出现,叠加后的综合税负在阶梯完成后出现,右栏美国一侧随后;每条税率的企业名与数值同时进场;综合税负条是与下一页保留身份的视觉端点

#### Slide 13 - 2026 年:价格承诺替代关税 Price Undertaking Instead of Duties

- **Audience move**: 从"关税就是终局"→ 知道 2026 年出现了可替代机制,但它还没有明确生效日
- **Relationships**: 原税负与 MIP 机制为 contrast(替代关系);MIP 与在欧建厂承诺为 link(附加条件);机制状态与生效日为 overlap(框架已达成但未生效)
- **Composition**: 中央论证轴:P12 的综合税负条留在原位并转为 MIP 机制条,右侧三行双语条件说明,底部一行状态提示
- **Title**: 框架已达成,生效日还没有 / Framework Agreed, Date Unset
- **Core message**: 最低进口价格机制可替代 17%–35.3% 的反补贴税,但报道只称进入"软着陆"阶段,未明确生效日期
- **Content**: 2026 年 1 月,欧盟发布《关于提交价格承诺申请的指导文件》,中国商务部同日通报 · 最低进口价格(MIP)可替代 17%–35.3% 反补贴税,原综合税负最高 45.3% · MIP 依调查期到岸价加反补贴税额、对标欧盟同类非补贴纯电车售价确定 · 附加条件:企业需承诺在欧建厂的投资规模与时间表 · 状态:框架已达成、进入"软着陆"阶段,未明确生效日期——本页按未生效处理
- **Fact IDs**: F020, F018
- **Motion suggestion**: 由 P12 的综合税负条原地转为 MIP 条,三行条件说明依次跟在该条之后,"未明确生效日期"的状态提示作为整页最后一个单元

#### Slide 14 - 2026 与 2030 Outlook

- **Audience move**: 从只看 2025 的高增速 → 接受总量增速回落,并把注意力转到海外生产占比
- **Relationships**: 两个 2026 预测为 contrast(中汽协 740 万 vs 车百会 800 万);2026 与 2030 为 order;总量与海外生产占比为 parent
- **Composition**: 左栏两个 2026 预测并列,右栏 2030 的海外产销与占比判断;中间一条细规则线,底部一行"增速回落"注记
- **Title**: 总量增速回落,重心转向海外生产 / Slower Volume, Local Production Leads
- **Core message**: 2026 年出口增速预测回落至个位数,增长重心从整车出口转向海外生产
- **Content**: 中汽协 2026 年 1 月 14 日预测:2026 年汽车出口 740 万辆,同比 +4.3% · 车百会理事长张永伟预测冲击 800 万辆 · 车百会预计到 2030 年中国汽车含出口在内的海外产销达 1000 万辆,海外生产销售占比有望冲击 50% · 对比 2025 年实际 +21.1%,总量增速明显回落
- **Fact IDs**: F023, F024, F001
- **Motion suggestion**: 两个 2026 预测同时进场以体现并列,2030 判断随后,"增速回落"注记最后

#### Slide 15 - 结论与共同议题 Takeaway & Shared Agenda

- **Audience move**: 从各自记住若干数字 → 拿到一句可共同引用的判断和三个双方都能推进的议题
- **Relationships**: 结论与三个议题为 parent;三个议题为 membership(同一合作清单);议题与前四部分为 link(各自对应)
- **Closing impact**: 绑定的收束是"下一阶段比的不是出口量,而是本地产能、网络与规则适配"(构图可改)
- **Composition**: 上方一句双语结论占整页宽度,下方三栏议题并列,每栏一行中英标签与一行动作;底部来源条保留
- **Title**: 下一阶段比什么 / What the Next Stage Is About
- **Core message**: 出口量已翻倍,下一阶段比的是本地产能、网络与规则适配
- **Content**: 结论:2025 年出口翻倍(261.5 万辆,中汽协),但 2026 年的增量要靠海外产能与价格承诺机制 · 议题一 口径对齐:双方引用数字时标注机构与年份 · 议题二 本地化配套:按基地时间表对齐产能与零部件、售后计划 · 议题三 规则跟踪:共同跟踪 MIP 生效进展与各市场准入变化
- **Fact IDs**: F002, F020, F024
- **Motion suggestion**: 结论句先进场,三栏议题依次跟随,每栏中英标签同时出现

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 每页备注先中文段后英文段,英文段为中文段的对应表述而非逐字直译;内容只使用本页已在页面上出现的事实与 `sources/nev_export_2025_research.facts.json` 中的事实,数字一律带机构与年份;主讲人换语言时的过渡句写在中文段末尾;不加入页面上没有的新数据,不做投资建议
- **Total duration**: 约 30 分钟(15 页,平均每页约 2 分钟,含中英两次表述)
- **Notes style**: formal
- **Presentation purpose**: 先用公开数据说明 2025 年规模与结构,再解释关税与本地化的因果,最后对齐 2026 年的共同判断
