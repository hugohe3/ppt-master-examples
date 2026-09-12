<!-- ppt-master-schema: design-spec/v1 -->
# 中国铁路2024:数据与现场 - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | china_rail_2024_zh_sonnet |
| Canvas Format | PPT 16:9 (1280×720) |
| Page Count | 15 |
| Primary Language | zh-CN |
| Target Audience | 来访的省交通部门代表团(专业但非铁路系统内部人员,关心宏观数据、建设成效与安全绿色治理) |
| Communication Intent | 汇报2024年全国铁路运输生产、建设、装备、科技与治理成效(report and account);建立对铁路行业发展态势的整体认知(inform);在结尾获得对铁路与地方协同发展的认同(align) |
| Desired Audience Outcome | 代表团清楚记住2024年铁路核心增长数字(客运/货运/换算周转量/投资)与安全绿色底线,并认可铁路在路网、装备、科技上的进展 |
| Core Message / Ask / Action | 2024年铁路运输生产量质齐升、建设与装备持续扩能、安全绿色底线守住,支撑经济回升向好 |
| Delivery Context | 现场汇报为主(presenter-led),投影展示,会后可留存为书面材料 |
| Artifact Afterlife | 会后留存作为存档与对外汇报材料(archive, hand-off) |
| Reading Mode | balanced |
| Content Strategy | balanced——在公报与Excel事实基础上按"总览→客运→货运→建设→装备→现场→国际→科技→绿色→结语"重新组织叙事顺序,不逐段照抄公报原文段落,但每个数字与结论严格来自附件 |
| Design Style | Mode: pyramid(结论与数据支撑的汇报体);Visual style: data-journalism(多栏微图表+来源线+密集但克制的编辑排版) |
| AI Image Acquisition Path | 不适用——本项目不使用AI生成图片,全部图片来自用户附件照片 |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 委托确认:任务书要求全卷讲者备注(目标语言) |
| Custom Animations | enabled — 委托确认:任务书硬性要求自定义动画,含Morph转场≥2处 |
| Narration Audio | disabled — 任务书未要求旁白/视频,工作流默认关闭 |
| Created Date | 2026-09-12 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 64px 四边安全边距 |
| Content Area | 约 1152 × 592 可用区域(扣除页眉/来源条后局部收窄) |

## III. Visual Theme

### Theme Style

- **Mode**: pyramid(preset)——每个板块先给结论性标题与关键数字,再用图表/表格支撑;结尾回到全年判断
- **Visual style**: data-journalism(preset)——多栏网格、细分隔线、来源脚注、密集但对齐克制的数据版式;与照片现场页交替形成呼吸感
- **Theme**: "数据与现场"——统计数字的严谨版式与铁路现场影像的真实感并置,体现"汇报有据、现场可信"
- **Tone**: 正式、克制、专业,面向政府部门的工作汇报语气

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #F6F7FA | 页面主底色,纸感浅灰白 |
| Secondary background | #E7EAF1 | 卡片/面板底色,与主底形成弱对比层次 |
| Primary | #14335C | 标题、图表主色、结构性色块,铁路行业稳重蓝 |
| Accent | #C81E3A | 关键数字、强调色块、"国铁集团"识别红 |
| Secondary accent | #1D7A8C | 图表次要系列、辅助强调,与红色区分正负语义 |
| Body text | #232B36 | 正文文字 |
| Secondary text | #5B6472 | 说明文字、图注、来源脚注 |
| Divider | #D7DBE3 | 分隔线、表格网格线 |
| Positive | #2E7D32 | 增长(+%)标记 |
| Negative | #C62828 | 下降(−%)标记 |

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 衬线宋体承载编辑出版式权威感(呼应data-journalism"serif headline"性格) | SimSun (Bold) | SimSun (Bold) | FangSong |
| Body | 中性易读黑体,与标题衬线形成对比配对 | Microsoft YaHei | Microsoft YaHei | SimHei |

- **Typography upgrade (Reference)**: 若目标机安装"思源宋体 Heavy"可用于标题以增强对比,现阶段保持 SimSun 保证跨机一致
- **Title stack**: SimSun, FangSong
- **Body stack**: Microsoft YaHei, SimHei
- **Data stack**: Consolas, Courier New(用于表格数字、KPI 大数字,等宽对齐、数位清晰,呼应data-journalism"precise mono data"性格)

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 40 |
| Subtitle | 30 |
| Lead | 28 |
| Hero (KPI大数字, Data字体) | 64 |
| Cover Display (封面钩子数字, Title字体) | 88 |
| Annotation | 18 |
| Footnote (来源/署名) | 16 |

- **Role rationale**: 新增 `Data` 字重用于所有表格数字与 KPI 大数字,保证跨页数字对齐一致;`Hero` 与 `Cover Display` 为重复出现的超大号数字角色,单独锚定避免逐页临时取值。

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 左上标题起势,数字/图表居中或右侧承重,来源脚注固定于页面底部
- **Composition tendency**: 数据页倾向"标题+KPI卡/图表+来源条"三段式;现场页倾向"大幅照片+说明浮层+署名条"
- **Cross-page continuity**: 页眉小型路徽记号(线条图形,非品牌LOGO)、页码、来源条在每页固定位置;KPI卡片语言跨页统一;两组同图不同页的照片(复兴号、丹昆特大桥)构成相邻页视觉延续
- **Spacing posture**: dense(数据页)与 breathing(现场页)交替
- **Spacing anchors**: page margin 64px;block gap 32px;column gutter 24px;corner radius 12px;body leading 34px

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2

| Icon Path | Suitable Scenarios |
| --- | --- |
| tabler-outline/users | 客运、旅客相关指标 |
| tabler-outline/train | 铁路装备、动车组 |
| tabler-outline/truck | 货运相关指标 |
| tabler-outline/route | 路网、营业里程 |
| tabler-outline/building-skyscraper | 建设、车站 |
| tabler-outline/coin | 固定资产投资 |
| tabler-outline/bolt | 电化率、能源消耗 |
| tabler-outline/leaf | 绿色低碳、污染物减排 |
| tabler-outline/shield-check | 运输安全 |
| tabler-outline/award | 科技奖项、标准 |
| tabler-outline/gavel | 行业监管、行政许可 |
| tabler-outline/target | 结语、目标达成 |
| tabler-outline/globe | 国际对照 |
| tabler-outline/map-2 | 路网/国际里程地图类场景 |
| tabler-outline/flag-2 | 目录/开篇导览 |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P04 | table | metric_table | 全国铁路旅客运输量(公报表格直转) |
| P05 | table | metric_table | 全国铁路货物运输量(公报表格直转) |
| P06 | chart | column_chart | 主要品类运量对比(煤/冶炼物资/石油/粮食/化肥及农药/集装箱) |
| P08 | chart | progress_bar_chart | 复线率、电化率占比 |
| P10 | table | metric_table | 机车/客车/动车组/货车拥有量 |
| P12 | chart | line_chart | 8国铁路营业里程 2000–2021 |
| P14 | chart | column_chart | 综合能耗、化学需氧量、二氧化硫各自的本年/上年对比(三个独立小图,单位不同不合并单一坐标轴) |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| fuxing_train.jpg | 3840×2560 | 1.50 | 复兴号动车组原始素材,供封面与内页派生 | Source | 全幅动车组侧view,适合裁切出封面英雄图与内页展示图 | adaptive | user | Existing | Wikimedia Commons, CC BY-SA 4.0, 摄影 N509FZ | overlay-safe | cover-hero-and-device |
| fuxing_train_cover.jpg | 3840×2560 | 1.50 | 封面英雄图(藏青双色调,压暗右侧供标题落版) | — | 全幅裁切,右侧渐变压暗承载标题与钩子数字 | adaptive | user | Existing | Derived from fuxing_train.jpg; treatment=duotone(#0B1B32→#8FB0D8)+contrast1.08 | overlay-safe | P01 cover |
| fuxing_train_device.jpg | 3840×2560 | 1.50 | 装备页动车组实景;P11缩小复用形成Morph配对 | — | 圆角卡片裁切,自然色调 | adaptive | user | Existing | Derived from fuxing_train.jpg; treatment=brightness1.04+contrast1.06 | caption-below | P10/P11 morph pair |
| danyang_kunshan_bridge.jpg | 3840×2158 | 1.78 | 丹昆特大桥原始素材,供建设页与现场页派生 | Source | 全幅高铁桥梁远景,适合裁出通版大图与细节特写 | adaptive | user | Existing | Wikimedia Commons, CC BY-SA 4.0, 摄影 MNXANL | overlay-safe | bridge-hero-and-detail |
| bridge_hero.jpg | 3840×2158 | 1.78 | 建设/路网页通版大图(藏青-灰绿双色调) | — | 全幅裁切,底部渐变承载数据卡 | adaptive | user | Existing | Derived from danyang_kunshan_bridge.jpg; treatment=duotone(#0A2A3D→#BFD9CE)+contrast1.05 | overlay-safe | P08 hero |
| bridge_detail.jpg | 3840×2158 | 1.78 | 现场影像页桥梁结构特写;与P08形成Morph配对 | — | 收紧裁切至桥墩/桁架细节,自然色调 | adaptive | user | Existing | Derived from danyang_kunshan_bridge.jpg; treatment=brightness1.02+contrast1.08 | caption-below | P09 detail |
| qinghai_tibet_railway.jpg | 2400×1800 | 1.33 | 青藏铁路原始素材,供绿色低碳页派生 | Source | 车厢内望向高原窗景 | adaptive | user | Existing | Wikimedia Commons, CC BY 3.0, 摄影 Hiroki Ogawa | caption-below | qinghai-derivative |
| qinghai_green.jpg | 2400×1800 | 1.33 | 绿色低碳页配图(墨绿双色调,呼应主题) | — | 圆角裁切,置于污染物数据旁 | adaptive | user | Existing | Derived from qinghai_tibet_railway.jpg; treatment=duotone(#1B3B2E→#CFE3D5)+contrast1.03 | caption-below | P14 |
| beijing_south_station.jpg | 2560×1600 | 1.60 | 导览页站台实景,呈现路网枢纽规模感 | — | 竖向收窄的编辑式裁切,置于导览列表旁 | adaptive | user | Existing | Wikimedia Commons, CC BY-SA 4.0, 摄影 颐园新居 | caption-below | P02 |
| shanghai_hongqiao.jpg | 3840×2558 | 1.50 | 客运页候车厅实景,呼应客运量数据 | — | 宽幅裁切,置于KPI卡下方通栏 | adaptive | user | Existing | Wikimedia Commons, CC BY-SA 3.0, 摄影 Patrick Nagel | caption-below | P04 |
| fuxing_interior.jpg | 3840×2560 | 1.50 | 现场影像页复兴号商务座内饰,体现装备升级 | — | 斜切角卡片裁切,自然色调 | adaptive | user | Existing | Wikimedia Commons, CC BY-SA 4.0, 摄影 N509FZ | caption-below | P11 |

## IX. Content Outline

### Part 1: 总览与导览

#### Slide 01 - 封面:中国铁路2024,数据与现场

- **Audience move**: 代表团从"例行汇报"预期 → 被一个具体增长数字锚定,进入"有据可查"的阅读状态
- **Relationships**: none
- **Composition**: 全幅复兴号动车组英雄图右侧压暗,标题与钩子数字叠加在暗部;来源条置于右下角
- **Title**: 中国铁路2024:数据与现场
- **Core message**: 2024年全国铁路旅客发送量43.12亿人次,同比增长11.9%——运输生产量质齐升的一年
- **Content**: · 主标题"中国铁路2024" · 副标题"数据与现场——面向省交通部门的年度汇报" · 钩子数字"43.12亿人次 · 旅客发送量 +11.9%"(来源:国家铁路局《2024年铁道统计公报》第1页) · 汇报单位/日期落款
- **Cover impact**: 钩子取公报最强增长数字(旅客发送量+11.9%),用复兴号实景照片承托,不使用泛化"欢迎页"构图

#### Slide 02 - 汇报导览

- **Audience move**: 建立整场汇报的心智地图,预期将看到"生产—建设—装备—现场—国际—科技—绿色"的完整链条
- **Relationships**: order——总览→客运→货运→建设→装备→现场→国际→科技→绿色→结语,九个板块顺序排列
- **Composition**: 左侧竖排导览列表(编号+板块名),右侧北京南站实景竖幅图作为氛围支撑
- **Title**: 汇报导览
- **Content**: · 01 总览:2024年核心指标 · 02 客运:结构与增长 · 03 货运:总量与品类 · 04 换算周转量与运输安全 · 05 建设:投资与路网 · 06 现场:高铁桥梁 · 07 装备:机车车辆 · 08 现场:复兴号与车站 · 09 国际对照:8国营业里程 · 10 科技创新与技术标准 · 11 绿色低碳与行业监管 · 12 结语
- **Images**: 北京南站站台实景,竖向裁切,置于列表右侧,不与文字重叠

### Part 2: 运输生产

#### Slide 03 - 2024年铁路运输总览

- **Audience move**: 从"不了解具体规模"到"记住四个最核心的年度总量指标"
- **Relationships**: none(四个并列KPI,无先后关系)
- **Composition**: 四宫格KPI卡片,每卡大数字+同比箭头+简短说明
- **Title**: 2024年铁路运输总览
- **Core message**: 客运、货运、换算周转量、固定资产投资四项核心指标同步增长
- **Content**: · KPI1 旅客发送量 43.12亿人次 +11.9% · KPI2 货运总发送量 51.75亿吨 +2.8% · KPI3 总换算周转量 51661.00亿吨公里 +0.9% · KPI4 铁路固定资产投资 8506亿元(全年完成额,同比数据公报未披露,不臆造) · 底部小字:数据来源国家铁路局《2024年铁道统计公报》第1、3、5页
- **Data class**: 固定资产投资8506亿元的同比幅度公报未给出,页面仅呈现绝对值,不编造百分比

#### Slide 04 - 客运:结构与增长

- **Audience move**: 理解客运总量增长的内部结构(国家铁路为主体,其他铁路增速更快)
- **Relationships**: membership——国家铁路与其他铁路是"全国铁路"的两个组成部分;overlap=none
- **Composition**: 左侧原生表格(公报表格直转)承载全部数字,表格下方一条简单原生比例条呈现占比,底部通栏候车厅实景
- **Title**: 客运:结构与增长
- **Core message**: 全国铁路旅客发送量43.12亿人次,其中国家铁路占94.7%,其他铁路以34.0%的增速成为增长亮点
- **Content**: · 表格:旅客发送量(万人)431240/408516/22724;旅客周转量(亿人公里)15799.10/15776.35/22.74;比上年±%见表 · 比例条(非目录图表,普通原生形状):国家铁路占比94.7% vs 其他铁路占比5.3%(按发送量计算,标注为按表格数字换算) · 现场图:上海虹桥站候车厅
- **Visualization**: passenger-table(table/metric_table)=yes
- **Native-ready**: passenger-table=yes

#### Slide 05 - 货运:总量与结构

- **Audience move**: 理解货运总发送量增长但总周转量下降的"量升距降"反差
- **Relationships**: membership——国家铁路/其他铁路同为全国铁路货运的组成部分;contrast——货运总发送量(+2.8%)与货运总周转量(−1.6%)方向相反
- **Composition**: 原生表格承载全部数字,标题旁一句话点出"量升距降"反差
- **Title**: 货运:总量与结构
- **Core message**: 全国铁路货运总发送量51.75亿吨(+2.8%),但总周转量35861.90亿吨公里下降1.6%,平均运距缩短
- **Content**: · 表格:货运总发送量(万吨)517477/398531/118946;货运总周转量(亿吨公里)35861.90/32580.63/3281.26;比上年±%见表 · 一句话点评:总发送量增、总周转量降,反映短途运输占比上升
- **Visualization**: freight-table(table/metric_table)=yes
- **Native-ready**: freight-table=yes

#### Slide 06 - 重点物资运输与国际班列

- **Audience move**: 认识大宗商品运输结构及中欧班列/西部陆海新通道的对外通道价值
- **Relationships**: order=none(六类品类并列比较);link——中欧班列与西部陆海新通道同为国际物流通道
- **Composition**: 原生柱状图六类品类并列,右侧或下方两个通道数据卡
- **Title**: 重点物资运输与国际通道
- **Core message**: 集装箱运量以15.5%的增速领跑重点品类,中欧班列全年开行1.9万列
- **Content**: · 柱状图(亿吨,同比%):煤炭28.24(+1.5)、冶炼物资8.77(−3.6)、石油1.33(+2.1)、粮食0.56(−17.6)、化肥及农药0.48(−5.2)、集装箱9.14(+15.5) · 通道卡:中欧班列1.9万列/207万标箱(+10%/+9%);西部陆海新通道班列96万标箱(+11%)
- **Visualization**: category-freight(chart/column_chart)=yes
- **Native-ready**: category-freight=yes

#### Slide 07 - 换算周转量与运输安全

- **Audience move**: 从生产总量视角切换到"综合运输效率+安全底线"视角,建立信任
- **Relationships**: membership——国家铁路/其他铁路同为全国换算周转量组成部分
- **Composition**: 呼吸页,左侧三条KPI(换算周转量及分解),右侧安全信息卡,留白多于前几页
- **Title**: 换算周转量与运输安全
- **Core message**: 全国铁路总换算周转量51661.00亿吨公里,增长0.9%;全年未发生重特大铁路交通事故
- **Content**: · 总换算周转量51661.00亿吨公里(+0.9%),其中国家铁路48356.99(+2.1%),其他铁路3304.01(−13.8%) · 安全:未发生特别重大、重大事故;较大事故2件,与上年持平;交通事故死亡人数下降18.0%

### Part 3: 建设与装备

#### Slide 08 - 建设:投资与路网

- **Audience move**: 了解2024年建设投入规模与路网质量指标(复线率、电化率)
- **Relationships**: order=none;membership——复线率与电化率同为路网质量的两个维度
- **Composition**: 丹昆特大桥通版大图打底,底部渐变承载投资数字与两条原生进度条
- **Title**: 建设:投资与路网
- **Core message**: 全国铁路固定资产投资8506亿元,投产新线3113公里(其中高铁2457公里),路网质量同步提升
- **Content**: · 固定资产投资8506亿元;投产新线3113公里,其中高速铁路2457公里 · 营业里程16.2万公里,其中高速铁路4.8万公里;西部地区铁路营业里程6.6万公里;路网密度168.5公里/万平方公里 · 进度条:复线率60.8%;电化率76.2% · 图片:丹昆特大桥(通版,双色调)
- **Visualization**: network-quality(chart/progress_bar_chart)=no(进度条无对应PowerPoint原生图表类型,保持SVG展示形式,不激活原生替换)
- **Native-ready**: network-quality=no
- **Motion suggestion**: 丹昆特大桥通版大图是与P09细节图的延续单元,建议作为Morph候选,构图从远景通版收至桥梁结构特写

#### Slide 09 - 现场影像:高铁桥梁工程

- **Audience move**: 从数字回到具体工程现场,建立"数据背后有实物"的直觉信任
- **Relationships**: none(单一现场影像页)
- **Composition**: 呼吸页,桥梁结构特写卡片居中偏右,左侧极简说明文字,底部署名条
- **Title**: 现场:丹昆特大桥
- **Core message**: 丹昆特大桥是京沪高铁的代表性工程,象征2024年路网建设的技术积累
- **Content**: · 极简说明:"京沪高铁·丹昆特大桥,全长164.851公里的世界最长高铁桥梁之一"(背景性描述,非公报数字,标注为背景资料非统计数据) · 摄影署名:MNXANL · CC BY-SA 4.0 · Wikimedia Commons
- **Motion suggestion**: 承接P08的Morph配对,桥梁图片从通版大图收缩为居中特写卡片,位置与尺寸推移

#### Slide 10 - 装备:机车车辆

- **Audience move**: 理解铁路装备存量结构(机车/客车/动车组/货车),建立规模感
- **Relationships**: membership——内燃机车与电力机车同为机车拥有量的组成部分;membership——动车组是客车拥有量的子集
- **Composition**: 左侧原生表格列出四类装备数字,右侧复兴号实景卡片
- **Title**: 装备:机车车辆
- **Core message**: 全国铁路机车拥有量2.25万台,动车组保有量达4806标准组、38448辆
- **Content**: · 表格:机车拥有量2.25万台(内燃机车0.78万台、电力机车1.47万台);客车拥有量8.1万辆(其中动车组4806标准组、38448辆);货车拥有量101.9万辆 · 图片:复兴号动车组实景(圆角卡片)
- **Visualization**: fleet-table(table/metric_table)=yes
- **Native-ready**: fleet-table=yes
- **Motion suggestion**: 复兴号实景图是与P11的延续单元,建议Morph候选,尺寸从本页大卡片缩小为下一页角标

#### Slide 11 - 现场影像:复兴号车厢与枢纽车站

- **Audience move**: 从装备数字回到真实乘坐体验与枢纽车站现场,收束"运输生产"整体叙事
- **Relationships**: none
- **Composition**: 呼吸页,复兴号商务座内饰斜切大图为主视觉,复兴号缩小徽标图承接上一页Morph,底部署名条
- **Title**: 现场:复兴号与枢纽车站
- **Core message**: 从机车数字到车厢细节,装备升级最终体现在乘坐体验上
- **Content**: · 主图:复兴号商务座内饰(斜切角卡片) · 承接图:复兴号动车组缩小徽标(与P10同图,Morph目标) · 摄影署名:复兴号照片 N509FZ · CC BY-SA 4.0;车站段落引用北京南站/上海虹桥站已在P02/P04出现,本页不重复放置
- **Motion suggestion**: 承接P10的Morph配对,复兴号图片位置从P10大卡片推移到本页左上角小徽标

### Part 4: 国际对照与治理

#### Slide 12 - 国际对照:铁路营业里程

- **Audience move**: 从国内视角扩展到国际坐标系,理解中国铁路里程规模的国际位置
- **Relationships**: order——按2021年最新可比里程从高到低比较美国、俄罗斯、中国、印度、德国、法国、西班牙六国;link——日本数据点因样本过少单独标注,不纳入趋势线比较
- **Composition**: 原生折线图占页面主体,六国2000–2021曲线,日本作为独立标注框
- **Title**: 国际对照:铁路营业里程(2000–2021)
- **Core message**: 中国铁路营业里程从2000年5.87万公里增长到2021年10.98万公里,增速在六国中最快
- **Content**: · 折线图(公里):中国 58656→109767;美国 194077→148553;俄罗斯 86075→85544;印度 62759→68103;德国 36642→33401;法国 29330→27716;西班牙 13868→15963 · 数据来源:World Bank IS.RRS.TOTL.KM,下载于2026-09-12 · 说明性标注:日本仅2010–2011年有记录(20140.3/20087.4公里),样本不足未绘入趋势线;世界银行该指标公开数据覆盖至2021年,2022–2024年尚无发布值,标题年份区间据此标注为2000–2021而非公报要求的2000–2024
- **Visualization**: rail-km-intl(chart/line_chart)=yes
- **Native-ready**: rail-km-intl=yes
- **Data class**: 无(全部为World Bank实际记录值,缺失年份留空不编造)

#### Slide 13 - 科技创新与技术标准

- **Audience move**: 认识铁路行业标准与科研创新的深度(标准供给、重大科技奖项)
- **Relationships**: order=none;membership——国家标准/行业标准/计量规程/国际标准同为"技术标准"体系的子类
- **Composition**: 左侧标准数量清单,右侧科技奖项高亮卡(复兴号高速列车项目特等奖)
- **Title**: 科技创新与技术标准
- **Core message**: 铁路国家科学技术奖6个项目获奖,其中"复兴号高速列车"项目获国家科学技术进步奖特等奖
- **Content**: · 标准发布:国家标准20项、行业标准95项、国家计量规程规范4项、行业计量规程规范4项、我国主持制定的国际标准(ISO/UIC/IEEE)7项、外文译本21+5项 · 荣誉:2名专家获ISO"卓越贡献奖",1名专家获IEC"1906奖"(我国第6次获此奖项) · 2024年度国家科学技术奖6个项目,含"复兴号高速列车"特等奖、"永磁电涡流阻尼减振缓冲耗能新技术"技术发明一等奖等5项二等奖/一等奖 · 重大科技创新成果库2024年度入库335项(科技项目50/专利61/技术标准24/论文200)

#### Slide 14 - 绿色低碳与行业监管

- **Audience move**: 理解节能减排的量化成效与行业监管的规范化程度,建立"治理到位"的信任
- **Relationships**: contrast——综合能耗同比上升(+2.8%)与污染物排放同比下降(化学需氧量、二氧化硫均减少)方向相反,体现总量增长下的排放强度控制
- **Composition**: 左侧原生分组柱状图(本年/上年对比),右侧青藏铁路配图承托"绿色"主题,底部行业监管小卡
- **Title**: 绿色低碳与行业监管
- **Core message**: 铁路总能耗随运量增长而上升,但主要污染物排放量同比下降,行业监管持续规范
- **Content**: · 综合能耗:国家铁路能源消耗折算标准煤1801.2万吨(+2.8%);单位运输工作量综合能耗3.86吨标准煤/百万换算吨公里(+1.3%);单位运输工作量主营综合能耗3.85(+1.6%) · 污染物:化学需氧量排放量1337吨(减少130吨);二氧化硫排放量456吨(减少196吨) · 行业监管:1部规章、7件行政规范性文件公布;行政许可决定书622件;运输企业累计81家、基础设备生产企业累计116家、进口企业累计124家、无线电台站企业累计336家;机车车辆驾驶人员累计220308人;行政处罚198起,383个处罚决定 · 图片:青藏铁路车窗实景(墨绿双色调)
- **Visualization**: energy-yoy(chart/column_chart)=yes; cod-yoy(chart/column_chart)=yes; so2-yoy(chart/column_chart)=yes(三个指标单位不同,拆为三个独立单指标小图,不共用坐标轴)
- **Native-ready**: energy-yoy=yes; cod-yoy=yes; so2-yoy=yes

### Part 5: 结语

#### Slide 15 - 结语:量质齐升,支撑发展

- **Audience move**: 从"了解全年数据"转向"认可铁路对区域协同发展的支撑价值",为后续交流打开话题
- **Relationships**: none
- **Composition**: 回到封面同色系但转为亮色收束版式,三条要点+一句展望
- **Title**: 结语:量质齐升,支撑发展
- **Core message**: 2024年铁路运输生产量质齐升、建设装备持续扩能、安全绿色底线守住,为区域经济协同发展提供坚实支撑
- **Content**: · 要点1:客运货运两旺,换算周转量增长0.9% · 要点2:新线投产3113公里,路网质量稳步提升 · 要点3:未发生重特大事故,主要污染物排放同比下降 · 展望一句话:期待与省交通部门在路网规划、多式联运等领域深化协同(整理性表述,非公报原文)
- **Closing impact**: 收束到"支撑经济回升向好"的核心判断,不使用泛化致谢页

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: 与每个SVG文件名一一对应,存放于 `notes/`
- **Content**: 按每页最终SVG的可见信息撰写讲者备注,复述关键数字来源(公报页码/Excel来源说明)并给出汇报口径的过渡语;不引入附件之外的数字
- **Total duration**: 约12–15分钟(15页,每页约50–60秒)
- **Notes style**: formal(正式汇报口吻)
- **Presentation purpose**: 汇报2024年全国铁路运输生产、建设、装备、科技与治理成效,建立代表团对铁路发展态势的认知与认同
