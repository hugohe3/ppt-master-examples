<!-- ppt-master-schema: design-spec/v1 -->
# apollo_photo_essay - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | apollo_photo_essay |
| Canvas Format | PPT 16:9 (1280×720) |
| Page Count | 13 |
| Primary Language | zh-CN |
| Target Audience | 对太空史有兴趣但不是专业读者的中文观众；知道"阿波罗登月"这个名字，记得一两张照片，但说不清这四年里到底发生了几件事 |
| Communication Intent | 先让照片建立在场感，再用少量精确的数字把四年串成一条能复述的时间线；优先顺序是"看见"在前、"记住"在后、"理解技术细节"不在本卷范围内 |
| Desired Audience Outcome | 看完后能说出这四年的四个关键时刻（1968 绕月、1969 落月、1970 事故、1972 收尾），知道卷中每张照片是谁在什么时候拍的，并且意识到"最后一次离开月面"已经过去半个多世纪 |
| Core Message / Ask / Action | 从 1968 年 12 月 21 日到 1972 年 12 月 19 日，1,459 天，人类九次抵达月球、六次落上去、十二个人走过月面——然后再没有回去 |
| Delivery Context | 主要为有主讲人的图片随笔式放映，约十分钟；次要为会后独立翻阅的图文留存 |
| Artifact Afterlife | 作为 photo-editorial 风格示例卷入库，可被再次放映、引用与拆用 |
| Reading Mode | presentation |
| Content Strategy | 题目型输入，全部可外部核验的事实来自本轮 topic-research；结构由本卷自建（四段弧线），但每个数字与日期都必须挂得上 fact_id。来源之间口径冲突时二选一并在页面上注明口径，绝不把两个口径并列或相加；本卷自行推算出的数字（如 1,459 天）标注"本卷推算"，不挂 fact_id |
| Design Style | photo-editorial × narrative：满版照片主导，文字只做指认与计数；暗色安静的文字侧，一个锈橙强调色只用在编号、细线和关键词上 |
| AI Image Acquisition Path | not applicable |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 工作流默认 `true`，无相反的显式指令 |
| Custom Animations | enabled — 用户显式要求"自定义动画必须做，Morph ≥ 2 组且有承接物" |
| Narration Audio | disabled — 工作流默认 `false`，用户未要求旁白音频 |
| Created Date | 2026-09-04 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 72 px 四边 |
| Content Area | 1136 × 576（x 72–1208, y 72–648）；满版出血页的照片与 scrim 不受此限 |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Visual style**: custom
- **Theme**: 一本关于四年的月度画报。照片是版面的脊椎，文字只在照片让出来的暗部里说话。整卷共用一枚"任务章标"——一条细线加一行 `1968 · APOLLO 8` 这样的编号，它在每一页的同一个位置出现，并在相邻页之间移动、改写，成为把十三页缝起来的那根线
- **Tone**: 克制、具体、有重量。不抒情，不惊叹；靠确切的时刻（`02:56:15 UTC`）、确切的编号（`AS11-40-5903`）和确切的距离（`400,171 公里`）产生分量

- **Mode References**: narrative
- **Mode Behavior**: 以 narrative 的 situation → tension → resolution 走四年：1968 设赌注（先离开地球轨道）、1969 兑现（落脚与那 2 小时 31 分）、1970 崩塌（氧罐与回家的弧线）、1971–72 收束（开车、地质学家、最后一步）。页标题写成推进故事的句子而非标签（"他们本来是去看月球的"、"原话是过去完成时"）；张力与呼吸交替，不做机械的密度轮转；人物、时刻、器材是抓手，抽象的"人类壮举"不作为论据。
- **Visual Style References**: photo-editorial
- **Visual Style Behavior**: 满版出血照片是页面脊椎，文字只做指认、计数与图注；页面装饰只有发丝细线、编号章标和小字图注，任何卡片、图标、阴影都不与照片争夺注意力。构图在四种之间轮换——L 形文字区、标题跨压照片明暗交界、破边的浮动图注卡、以及无照片时退回 editorial 的多栏文字页。留白给文字，出血给照片；文字侧永远是安静的中性暗色，锈橙只出现在编号、细线和一两个关键词上。整卷平面，唯一允许的渐变是压字用的方向性 scrim。

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #0B0E11 | 深空底色；照片未覆盖处、无照片文字页的整页底 |
| Secondary background | #161A20 | 安静的文字侧场、浮动图注卡与表格底 |
| Primary | #E9E4D9 | 骨白：标题、主要文字、章标的主体 |
| Accent | #D2622B | 锈橙：编号、发丝线、每页一两个关键词；不做面 |
| Secondary accent | #6E7B8A | 冷灰蓝：次级标记、表头、非关键的分组线 |
| Body text | #DAD5CA | 正文与引句 |
| Secondary text | #98A0A9 | 图注、口径说明、注解 |
| Divider | #39414A | 分隔发丝线、表格横线 |
| Scrim | #06080B | 压在照片上的方向性渐变基色，保证骨白文字在照片上仍可读 |
| Surface | #1E242B | 表格斑马行与图注卡的抬升面 |

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 编辑衬线：横细竖粗，出版物标题的骨架 | SimSun | Times New Roman | — |
| Display | 同 Title 的衬线骨架，放大到封面与英雄数字的尺度 | SimSun | Times New Roman | — |
| Body | 干净无衬线：中性、不抢戏、小字仍可读 | Microsoft YaHei | Arial | — |

- **Title stack**: `Times New Roman, SimSun`
- **Body stack**: `Arial, Microsoft YaHei`
- **Display stack**: `Times New Roman, SimSun`
- **Role rationale**: 只新增一个字族角色 `display`——封面标题与英雄数字（1,459）需要与页标题同一套衬线骨架，若继承 Body 栈会变成无衬线，与整卷的编辑衬线标题体系断开；`annotation` / `footnote`（图注、编号、署名、口径说明）继承 Body 栈，不另立字族。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 30 |
| Title | 54 |
| Subtitle | 40 |
| Annotation | 22 |
| Display | 78 |
| Footnote | 18 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 照片先被看见，再是压在它明暗交界上的标题，再是一段不超过两句的正文，最后才是小字图注与署名。每页只有一个视觉主角
- **Composition tendency**: 四种构图轮换——L 形文字区（沿左缘与下缘）、标题跨压照片明暗交界、破边的浮动图注卡、无照片时退回 editorial 多栏文字页；不重复相邻两页的同一种
- **Cross-page continuity**: 任务章标（`1968 · APOLLO 8` 这样的一行小字加一条锈橙发丝线）在每一页的同一位置出现，是整卷的框架元素；相邻页之间它承接、移动并改写编号，成为 Morph 的承接物
- **Spacing posture**: 变化：满版照片页极度呼吸（文字只占一角），文字页与表格页可以密
- **Spacing anchors**: 页边距 72 / 块间距 32 / 栏间距 40 / 圆角 4 / 正文行距 48

## VI. Icon Usage Specification

- **Primary bundled library**: none

| Icon Path | Suitable Scenarios |
| --- | --- |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P11 | table | record_table | 六次成功着陆各自的发射时间、着陆点与带回样品，一行一次任务 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 01_launch.jpg | 1280x720 | 16:9 | 封面：土星五号在夜里离开地面 | Photography | 满版出血做封面场，暗侧留在左边给 L 形文字区；#P1-01 + #M2-01 方向性 scrim 压字 | adaptive | web | Sourced | 阿波罗17号 1972-12-07 凌晨的夜间发射：土星五号的火焰把发射场和云层照亮，倒影落在水面上，横幅取景，画面左侧与上方是可压字的夜色暗区；要求是升空瞬间而非静态塔架照 | — | — |
| 02_earthrise.jpg | 1280x720 | 16:9 | 阿波罗8号《地出》，本卷的第一个转折 | Photography | 满版出血；标题跨压在月平线的明暗交界上；#P1-01 + #M2-01 | adaptive | web | Sourced | NASA AS08-14-2383《地出》：地球半明半暗悬在月球地平线之上，月面占下半幅，横幅取景，右侧或下方为月面暗区可压字；须是这一帧本身，不要后期重绘或艺术再创作版本 | — | — |
| 03_ladder.jpg | 760x720 | 19:18 | 阿波罗11号：Aldrin 沿登月舱梯子下降 | Photography | 竖幅裁形放在右侧，左缘与下缘留 L 形文字区；#M1-01 几何裁形 + #P1-02 | adaptive | web | Sourced | NASA AS11-40-5868：Buzz Aldrin 背对镜头、双手扶梯从登月舱下降，登月舱腿部与梯子完整在画面内；竖向构图，主体居中偏右 | — | — |
| 04_visor.jpg | 1280x720 | 16:9 | 阿波罗11号：Aldrin 面罩肖像，面罩里映着 Armstrong | Photography | 满版出血，人物居中偏左，右侧 scrim 压字；破边的浮动图注卡压在下缘；#P1-01 + #M2-01 | adaptive | web | Sourced | NASA AS11-40-5903：Buzz Aldrin 站在月面正对镜头，面罩反射里能看到登月舱、国旗与拍摄者 Armstrong；须是这张著名的 "Visor" 全身或半身正面像，反射细节清楚 | — | — |
| 05_bootprint.jpg | 1280x720 | 16:9 | 阿波罗11号：月壤中的鞋印特写 | Photography | 满版出血做总览，右下角一枚同源圆形放大窗对准印痕边缘（#P2-04 同源放大 + 嵌套裁切），细线牵到浮动图注 | adaptive | web | Sourced | NASA AS11-40-5878：月壤上一枚清晰的靴印特写，纹路完整、光比强，画面基本被月壤填满，没有其他主体 | — | — |
| 06_apollo13_sm.jpg | 1280x720 | 16:9 | 阿波罗13号受损服务舱（仅作单色派生的母本，不上页） | Source | 仅作派生母本；本身不放置 | adaptive | web | Sourced | NASA AS13-59-8500：抛弃后的阿波罗13号服务舱漂在黑色太空中，2 号氧罐爆炸掀掉的整块面板缺口清晰可见 | — | — |
| 06_apollo13_sm_mono.jpg | 1280x720 | 16:9 | 阿波罗13号事故页的主视觉 | Photography | 满版出血铺开，主体偏右，左缘与下缘的黑色太空直接承字，不再加 scrim | adaptive | web | Sourced | Derived from 06_apollo13_sm.jpg; treatment=desaturate+contrast; 去掉残余色偏、压成近单色的冷灰，让缺口的边界更硬，事故页与其他彩色页拉开距离 | — | — |
| 07_irwin_rover.jpg | 1280x720 | 16:9 | 阿波罗15号：Irwin 向国旗行军礼，身后是登月舱与月球车 | Photography | 满版出血；标题横跨照片上缘的明暗交界；#P1-01 + #M2-01 | adaptive | web | Sourced | NASA AS15-88-11866：James Irwin 在哈德利—亚平宁着陆点向展开的美国国旗行军礼，背后是登月舱 Falcon 与 Hadley Delta 山体，月球车在画面内；横幅取景 | — | — |
| 08_schmitt_boulder.jpg | 1280x720 | 16:9 | 阿波罗17号：Schmitt 与 6 号站巨砾 | Photography | 满版出血，巨砾在中偏左、人在左下；破边的浮动图注卡压在下缘；#P1-01 + #M2-01 | adaptive | web | Sourced | NASA S73-22871：6 号站那块巨大的裂开岩块（Tracy's Rock / Split Rock）占据画面，Harrison Schmitt 站在它旁边显出尺度，黑色月空占上半可压标题；横幅取景 | — | — |
| 09_blue_marble.jpg | 1280x720 | 16:9 | 阿波罗17号《蓝色弹珠》，本卷的收束 | Photography | 满版出血，地球居中偏右，左缘 L 形文字区落在太空的黑里；#P1-01 + #M2-01 | adaptive | web | Sourced | NASA AS17-148-22727《蓝色弹珠》：整颗地球满照，非洲与南极冰盖清楚可见，四周是黑色太空；须是这一原始帧，不要后期合成的"蓝色弹珠"系列再制版 | — | — |
| 10_apollo11_liftoff.jpg | 620x620 | 1:1 | 来源页的视觉收束：阿波罗11号的土星五号升空 | Photography | 圆形裁形放在右侧做视觉句号，左侧是来源清单；#M1-01 几何裁形 | adaptive | web | Sourced | NASA：1969-07-16 阿波罗11号的土星五号点火升空，箭体与火焰在画面中轴，可裁入圆形而不丢失箭体与火焰 | — | — |

## IX. Content Outline

### Part 1: 1968 — 先离开地球轨道

#### Slide 01 - 封面

- **Audience move**: 只知道"阿波罗登月"是个名字 → 知道它是一段有确切起点、终点和长度的完整故事，并愿意跟着看下去
- **Relationships**: 起点（1968-12-21 阿波罗8号发射）与终点（1972-12-19 阿波罗17号溅落）构成一段闭合区间；主标题为 parent，区间与长度是它的两个说明子项
- **Composition**: 满版出血的发射照，暗侧留在左边；L 形文字区沿左缘向下、再沿下缘向右展开，标题压在照片的暗部
- **Cover impact**: hook（binding 语义）= 1,459 天——从第一次离开地球轨道到最后一次离开月面，人类总共只用了这么久；composition 为 Reference
- **Title**: 阿波罗：人类离开地球的四年
- **Core message**: 1968 年 12 月 21 日到 1972 年 12 月 19 日，1,459 天，人类九次抵达月球、六次落上去、十二个人走过月面
- **Content**:
  - 主标题「阿波罗：人类离开地球的四年」，衬线，压在照片暗部
  - 副题：1968.12.21 阿波罗8号发射 — 1972.12.19 阿波罗17号溅落
  - 英雄数字 1,459 天，旁边小字「本卷推算」
  - 图注与署名：阿波罗17号 · 土星五号夜间发射 1972.12.07 / NASA（Public Domain）——封面用的是最后一次离开，正文从第一次开始
- **Images**: 01_launch.jpg 满版出血，方向性 scrim 压在左侧
- **Fact IDs**: F001, F061, F076
- **Motion suggestion**: 照片先在场并稳住，随后任务章标落位，标题与副题按阅读路径依次进入；这一页不承接上一页

#### Slide 02 - 他们本来是去看月球的

- **Audience move**: 以为阿波罗8号是一次"去看月球"的任务 → 明白它真正留下的是一张回望地球的照片
- **Relationships**: "去看月球"与"拍下地球"构成 contrast；照片、拍摄者、拍摄时刻三者构成 link
- **Composition**: 满版出血的《地出》，地球在上方；标题跨压在月平线的明暗交界上，正文落在月面的暗部
- **Title**: 他们本来是去看月球的
- **Core message**: 1968 年 12 月 24 日 16:39 UTC，William Anders 在绕月途中拍下 AS08-14-2383，人类第一次从外面看见自己的家
- **Content**:
  - 一句起：绕月途中地球升起在月平线上，Anders 先拍了一张黑白，随即要来彩色胶片才拍下这一张
  - 器材：大幅改装的电动 Hasselblad 500 EL，250 mm 镜头，柯达定制 Ektachrome
  - 破边浮动图注卡：AS08-14-2383 / 1968-12-24 16:39:39.3 UTC / 摄影 William Anders
  - NASA 的说法：这张照片"给了人类看待自己家园的新视角"
- **Images**: 02_earthrise.jpg 满版出血，方向性 scrim 压在下缘
- **Fact IDs**: F007, F008, F009
- **Motion suggestion**: 照片作为主角先进场，任务章标 `1968 · APOLLO 8` 随后落位；这枚章标是承接物，应能在下一页继续存在并改换位置

#### Slide 03 - 十圈，二十小时，四分之一的人类在听

- **Audience move**: 只知道"绕了一圈" → 知道这一圈的量级：十圈、二十小时、全球四分之一的人在看或在听
- **Relationships**: 圈数、时长、听众规模三个量级构成 membership（同属这一次任务）；平安夜广播与这三个数字构成 link；乘组三人为并列 membership
- **Composition**: 本页没有可用照片，退回 editorial 的多栏文字版式：左栏三个并置的量级数字，右栏是广播与返回的叙述，锈橙发丝线分栏
- **Title**: 十圈，二十小时，四分之一的人类在听
- **Core message**: 阿波罗8号是人类第一次抵达并环绕另一个天体，也是当时收听规模最大的一次广播
- **Content**:
  - 三个并置量级：绕月 10 圈 · 约 20 小时 · 全球约四分之一的人看到或听到
  - 乘组：Frank Borman、James Lovell（洛弗尔）、William Anders
  - 平安夜：1968-12-24 第九圈绕月中三人轮流朗读《创世记》前十节；NASA 说乘组刻意挑了适合全球不同信仰听众的内容
  - 返回：1968-12-27 15:51 UTC 溅落北太平洋，全程 6 天 3 小时
- **Fact IDs**: F002, F003, F004, F005, F007, F010, F011
- **Motion suggestion**: 承接上一页的任务章标，让它从照片角落移到本页栏头并放大；三个量级数字按阅读路径依次进入

### Part 2: 1969 — 落脚

#### Slide 04 - 从落地到落脚，中间隔了六个小时

- **Audience move**: 把"登月"记成一个笼统的日期 → 记住着陆与第一步是两个不同的时刻，中间隔着六个多小时
- **Relationships**: 着陆时刻与第一步时刻构成 order；把呼号从 Eagle 改成 Tranquility Base 与"宣告着陆成功"构成 link
- **Composition**: 竖幅裁形的下梯照放在右侧，左缘与下缘围成 L 形文字区；裁形轮廓沿用整卷的直角语言
- **Title**: 从落地到落脚，中间隔了六个小时
- **Core message**: 1969 年 7 月 20 日 20:17 UTC 鹰号落在静海，六个多小时后的 02:56 UTC，Armstrong 才踩上月面
- **Content**:
  - 着陆 1969-07-20 20:17:40 UTC；Armstrong 主动把呼号从 Eagle 改成 Tranquility Base，以此宣告落成
  - 第一步 1969-07-21 02:56:15 UTC（美东 7 月 20 日晚 10:56）
  - 原话 "That's one small step for [a] man, one giant leap for mankind"；录音里听不清那个不定冠词 "a"，Armstrong 后来承认自己大概是漏掉了
  - 小字图注：AS11-40-5868 / Aldrin 沿登月舱梯子下降 / 摄影 Neil Armstrong
- **Images**: 03_ladder.jpg 竖幅几何裁形，不做 scrim
- **Fact IDs**: F015, F016, F017, F018, F088
- **Motion suggestion**: 任务章标改写为 `1969 · APOLLO 11` 并在此页首次出现，随后连续三页承接同一枚章标

#### Slide 05 - 面罩里的那个人，就是按快门的人

- **Audience move**: 记得这张照片但说不清拍的是谁、谁拍的 → 知道照片里是 Aldrin，面罩反射里那个小小的身影是 Armstrong
- **Relationships**: 被摄者与拍摄者构成 link（面罩把拍摄者收进画面）；这张照片与"两人一共 2 小时 31 分"的时长构成 parent/子项
- **Composition**: 满版出血的面罩肖像，人物居中偏左；方向性 scrim 压在右侧承字；一张破边的浮动图注卡从照片下缘探出
- **Title**: 面罩里的那个人，就是按快门的人
- **Core message**: AS11-40-5903 里 Aldrin 的面罩映出登月舱、国旗和正在拍照的 Armstrong；两人在月面一共只待了 2 小时 31 分 40 秒
- **Content**:
  - 面罩反射里能看到登月舱、国旗与拍摄者 Armstrong
  - 两人的舱外活动全程 2 小时 31 分 40 秒
  - 破边浮动图注卡：AS11-40-5903 / 1969-07-20 / 摄影 Neil Armstrong / NASA
- **Images**: 04_visor.jpg 满版出血，方向性 scrim 压在右侧
- **Fact IDs**: F019, F085
- **Motion suggestion**: 承接上一页的 `1969 · APOLLO 11` 章标；照片进场后图注卡跟随

#### Slide 06 - 那不是纪念照，是一次土壤力学试验

- **Audience move**: 把鞋印当成一个纯粹的符号 → 知道它原本是一组土壤力学取样序列里的一帧
- **Relationships**: 试验记录与后来的符号意义构成 contrast；样品质量与电视观众规模是两个并列的量级 membership
- **Composition**: 满版出血的鞋印做总览，右下角一枚同源的圆形放大窗对准印痕边缘，一条锈橙细线从放大窗牵到浮动图注；总览与放大窗共用同一张源图与同一套坐标
- **Title**: 那不是纪念照，是一次土壤力学试验
- **Core message**: AS11-40-5878 属于一组土壤力学序列；这次任务带回 21.5 公斤月球样品，全球约六亿到六亿五千万人在看
- **Content**:
  - 这枚鞋印属于同一组土壤力学取样序列，同序列的 AS11-40-5877 是靴子与印痕同框的那张
  - 带回月球样品 21.5 公斤（47.5 磅）；1969-07-24 溅落
  - 全球电视观众约 6 亿到 6.5 亿（两个估算并存，本卷取区间）
  - 放大窗图注：印痕边缘的月壤（同源放大，非另一张照片）
- **Images**: 05_bootprint.jpg 满版出血做总览，同一文件再做一枚圆形同源放大窗
- **Fact IDs**: F020, F021, F022, F023, F086, F087
- **Motion suggestion**: 承接 `1969 · APOLLO 11` 章标；总览先在场，放大窗与牵引细线随后出现

### Part 3: 1970 — 崩塌

#### Slide 07 - 原话是过去完成时

- **Audience move**: 记得电影里那句台词 → 知道飞行中的原话是什么，以及爆的到底是哪一个罐
- **Relationships**: 电影台词与飞行原话构成 contrast；导线绝缘破损 → 按地面要求打开风扇 → 短路起火 构成 order（因果链）
- **Composition**: 单色派生的受损服务舱满版铺开，主体偏右；左缘与下缘的黑色太空直接承字，构成 L 形文字区，不另加 scrim
- **Title**: 原话是过去完成时
- **Core message**: 1970 年 4 月 14 日 03:08 UTC，2 号氧罐内搅拌风扇导线的绝缘层破损导致短路起火；Swigert 说的是 "Okay, Houston, we've had a problem here"
- **Content**:
  - 事故时刻：任务经过时间 55:54:53，即 1970-04-14 03:08 UTC
  - 原因：2 号氧罐内搅拌风扇导线的特氟龙绝缘层受损，Swigert 依地面要求打开风扇时短路起火
  - 原话：Swigert "Okay, Houston, we've had a problem here"；随后 Lovell "Houston, we've had a problem. We've had a Main B Bus undervolt."
  - 一行小字注：通行的 "Houston, we have a problem" 出自电影，不是飞行原话
  - 图注：AS13-59-8500 / 抛弃服务舱后拍摄，整块面板被 2 号氧罐爆炸掀掉 / NASA
- **Images**: 06_apollo13_sm_mono.jpg 满版出血，本页唯一处理层是单色派生，不再叠加 scrim
- **Fact IDs**: F033, F034, F035, F040, F041
- **Motion suggestion**: 章标改写为 `1970 · APOLLO 13`；照片先在场，引句作为本页重量最大的一块随后进入

#### Slide 08 - 回家的路，是绕着月球再走一圈

- **Audience move**: 只知道"他们最后回来了" → 知道回来的路是绕月一圈，也知道这一圈顺带创下了什么纪录、这个纪录什么时候被打破
- **Relationships**: 临阵换人、自由返回轨道、距离纪录三件事同属这次任务的 membership；纪录的创下与 2026 年被打破构成 order
- **Composition**: 本页没有可用照片，退回 editorial：一条贯穿版面的绕月弧线把"去"与"回"分在两侧，文字沿弧线内外分块；弧线是本卷唯一一处几何叙事
- **Title**: 回家的路，是绕着月球再走一圈
- **Core message**: 阿波罗13号把登月舱当救生艇，沿自由返回轨道绕月一圈；过近月点时距地球 400,171 公里，这个纪录保持了半个多世纪
- **Content**:
  - 发射前两天临阵换人：备份乘组的 Charles Duke 感染风疹，同批训练的五人中只有 Mattingly 没有免疫力，于是 Swigert 顶替 Mattingly
  - 放弃登月，登月舱 Aquarius 当作救生艇，沿自由返回轨道绕月一圈再回地球
  - 1970-04-14 过近月点时距地球 400,171 公里（248,655 英里）
  - 这个纪录保持了半个多世纪：2026 年 4 月 6 日被 Artemis II 乘组以 252,756 英里打破
  - 1970-04-17 溅落南太平洋，全程 5 天 22 小时 54 分 41 秒
- **Fact IDs**: F032, F036, F037, F038, F039

### Part 4: 1971–1972 — 收束

#### Slide 09 - 1971年，他们开始开车

- **Audience move**: 以为登月就是在着陆点附近走几步 → 知道 1971 年起他们开着车在月面跑了几十公里
- **Relationships**: 步行时代与驾车时代构成 contrast；月球车的规格与它跑出的距离构成 link
- **Composition**: 满版出血的 Irwin 敬礼照；标题横跨照片上缘的明暗交界，一半压在天空的黑上、一半压在山体上；右下角小字图注
- **Title**: 1971年，他们开始开车
- **Core message**: 阿波罗15号第一次把月球车带上月面，在哈德利—亚平宁一共开了 27.9 公里
- **Content**:
  - 1971-07-26 发射；乘组 大卫·斯科特、阿尔弗莱德·沃尔登、詹姆斯·艾尔文
  - 首次使用月球车（Lunar Roving Vehicle），着陆点 Hadley–Apennine
  - 行驶 27.9 公里；空车 210 公斤，设计最高时速 10 公里
  - 收尾时 Scott 当着电视镜头同时松手，放下一根猎鹰羽毛和一把地质锤，验证落体速率与质量无关
  - 图注：AS15-88-11866 / Irwin 向国旗行军礼，身后是登月舱 Falcon 与 Hadley Delta / 摄影 David R. Scott
- **Images**: 07_irwin_rover.jpg 满版出血，方向性 scrim 压在上缘
- **Fact IDs**: F046, F047, F048, F049, F051, F052, F056, F092
- **Motion suggestion**: 章标改写为 `1971 · APOLLO 15` 并作为承接物传给下一页

#### Slide 10 - 最后一次去的人里，有一个地质学家

- **Audience move**: 以为登月的都是试飞员 → 知道最后一次去的人里有一位职业地质学家，而且他在那里找到了橙色的土
- **Relationships**: 试飞员与地质学家构成 contrast；橙色土壤这一发现与"35 亿年前的火山玻璃珠"这一解释构成 parent/子项
- **Composition**: 满版出血的 Schmitt 与巨砾，人在左下、岩块在右；破边的浮动图注卡压在下缘，把人与岩块的尺度关系点出来
- **Title**: 最后一次去的人里，有一个地质学家
- **Core message**: 阿波罗17号是载人土星五号唯一一次夜间发射；Harrison Schmitt 是唯一登上月球的职业地质学家，他在 Shorty 陨石坑发现了橙色土壤
- **Content**:
  - 1972-12-07 凌晨 0:33 发射，这是载人土星五号唯一一次夜间发射
  - 着陆 Taurus–Littrow；三次月面行走合计 22 小时 3 分 57 秒；月球车穿越 30.5 公里（NASA 任务页口径）
  - Schmitt 在 Shorty 陨石坑发现橙色土壤——成分是 35 亿年前形成的极细火山玻璃珠
  - 破边浮动图注卡：S73-22871 / Harrison Schmitt 与 6 号站巨砾（Tracy's Rock）/ NASA
  - 一行小字注：岩面上那个 "Tracy" 字样出自 1984 年的一幅画，原照片里没有
- **Images**: 08_schmitt_boulder.jpg 满版出血，方向性 scrim 压在下缘
- **Fact IDs**: F061, F063, F064, F065, F066, F068, F089
- **Motion suggestion**: 承接上一页的章标并改写为 `1972 · APOLLO 17`

#### Slide 11 - 四年的账：六次落下去

- **Audience move**: 记住了几个片段 → 能把六次成功着陆放进同一张表里对比，并看见整个计划的总量
- **Relationships**: 六次着陆构成 membership，按发射时间 order 排列；六次着陆与另外三次"抵达但没落下去"构成 contrast
- **Composition**: 本页没有可用照片，退回 editorial：一张横贯版面的原生表格是页面主体，只用横向发丝线不做全网格；表格上方一行是总量，右下角是 1,459 天
- **Title**: 四年的账：六次落下去
- **Core message**: 九次载人任务飞抵月球，六次成功着陆，十二个人走过月面，带回 382 公斤岩石与土壤
- **Content**:
  - 原生表格（任务 / 发射 / 着陆点 / 带回样品）：Apollo 11 · 1969-07-16 · Tranquility Base（静海）· 21.5 kg；Apollo 12 · 1969-11-14 · Surveyor 3 旁 163 米 · 33.45 kg；Apollo 14 · 1971-01-31 · Fra Mauro · 42.80 kg；Apollo 15 · 1971-07-26 · Hadley–Apennine · 77 kg；Apollo 16 · 1972-04-16 · Descartes 高地 · 95.71 kg；Apollo 17 · 1972-12-07 · Taurus–Littrow · 110.4 kg
  - 表下一行：另有三次抵达月球而未着陆——阿波罗8号、10号、13号
  - 总量：24 人到过月球，其中 12 人踩上月面；全计划带回 382 公斤岩石与土壤
  - 代价：254 亿美元（1973 年美元），按 2020 年美元约 2,570 亿；峰值雇用 40 万人
  - 右下角英雄数字 1,459 天，小字「本卷推算：1968-12-21 发射至 1972-12-19 溅落」
- **Visualization**: `mission-ledger` 六次成功着陆的任务 × 字段记录表；表下的三次未着陆说明与总量、代价均为普通文字，不入表
- **Native-ready**: mission-ledger=yes
- **Fact IDs**: F012, F020, F024, F027, F029, F042, F045, F046, F057, F058, F059, F060, F061, F064, F070, F077, F078, F079, F080, F081
- **Motion suggestion**: 1,459 天这个数字是承接物，应能在下一页继续存在并重新落位

#### Slide 12 - 走的时候，他说我们还会回来

- **Audience move**: 把阿波罗当成一段已经过去的历史 → 意识到最后一步已经过去半个多世纪，而那张最著名的地球照就拍在这次任务出发的路上
- **Relationships**: 出发五小时后拍下的地球与结束时离开月面的最后一步构成 order（同一次任务的首尾）；"离开"与"还会回来"构成 contrast
- **Composition**: 满版出血的《蓝色弹珠》，地球居中偏右；左缘的黑色太空承 L 形文字区，引句是全页重量最大的一块
- **Closing impact**: 最后一个离开月面的人是 Eugene Cernan，时间是 1972 年 12 月 14 日 5:40:56 UTC；此后没有第十三个人。composition 为 Reference
- **Title**: 走的时候，他说我们还会回来
- **Core message**: 阿波罗17号出发五小时后拍下《蓝色弹珠》；1972 年 12 月 14 日 Eugene Cernan 成为最后一个离开月面的人，至今没有人回去
- **Content**:
  - AS17-148-22727：1972-12-07 10:39 UTC 拍摄，距发射约 5 小时 6 分，距地表约 29,400 公里
  - 器材 70 mm Hasselblad 500 EL 配 80 mm Zeiss Planar，柯达 SO-368 Ektachrome，f/2.8、1/250 秒；NASA 把版权归属整个乘组，证据与后来的访谈指向实际按快门的是 Harrison Schmitt
  - 1972-12-14 5:40:56 UTC，第三次舱外活动结束，Eugene Cernan 最后一个离开月面
  - 引句："we leave as we came and, God willing, as we shall return, with peace and hope for all mankind."
  - 收束一行：十二个人走过月面，此后没有第十三个
- **Images**: 09_blue_marble.jpg 满版出血，方向性 scrim 压在左侧
- **Fact IDs**: F072, F073, F074, F075, F078
- **Motion suggestion**: 承接上一页的 1,459 天数字，让它在本页重新落位后再让引句进入

#### Slide 13 - 来源与图片版权

- **Audience move**: 看完了但不知道这些数字从哪来 → 知道每个数字都可追溯，并且能点开链接自己去查
- **Relationships**: 事实来源与照片版权是两组并列的 membership；每条来源与它的链接构成 link
- **Composition**: 左侧两栏来源清单（可点的链接用锈橙下划线标出），右侧一枚圆形裁形的夜间发射照做视觉句号；一条锈橙发丝线分开两侧
- **Title**: 来源与图片版权
- **Core message**: 全卷事实来自 NASA 官方站点与英文维基百科，照片全部是 NASA 拍摄的美国公有领域作品
- **Content**:
  - 事实来源（可点击）：NASA · The Apollo Program，链接 https://www.nasa.gov/the-apollo-program/ ；NASA · Apollo 17 Mission Details，链接 https://www.nasa.gov/missions/apollo/apollo-17-mission-details/ ；NASA JSC 照片数据库，链接 https://eol.jsc.nasa.gov/SearchPhotos/ ；NASA · Images and Media（版权说明），链接 https://www.nasa.gov/nasa-brand-center/images-and-media/
  - 版权：NASA 声明其影像内容在美国境内一般不受版权保护，使用时希望注明来源为 NASA；徽标、可辨识人物的商业使用与第三方版权素材另需许可
  - 本卷用到的编号：AS08-14-2383、AS11-40-5868、AS11-40-5878、AS11-40-5903、AS13-59-8500、AS15-88-11866、S73-22871、AS17-148-22727，以及阿波罗17号夜间发射（GPN-2000-001150）与阿波罗11号升空两张发射照
  - 一行小字：全卷共 100 条外部事实，逐条对应 `sources/apollo_photo_essay_research.facts.json` 中的 fact_id
- **Images**: 10_apollo11_liftoff.jpg 圆形几何裁形放在右侧
- **Fact IDs**: F093

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 每页的讲述从这一页最终 SVG 上真实可见的内容出发：照片是谁在什么时候拍的、页面上那几个数字各自意味着什么、这一页把故事推到了哪里。数字读法按中文口语展开（"两小时三十一分"而不是 "2:31:40"），编号照读英文原样。口径冲突处按 §I Content Strategy 已裁决的取值讲，不在讲稿里复述被弃用的另一个口径。图片署名与许可只在页面上出现，不进讲稿。
- **Total duration**: 约 10 分钟，13 页平均每页 40–50 秒；照片页短、文字页与表格页长
- **Notes style**: 对话式叙述，页与页之间用一句过渡承接，不用列表和标记
- **Presentation purpose**: 先让照片建立在场感，再用少量精确的数字把四年串成一条能复述的时间线
