<!-- ppt-master-schema: design-spec/v1 -->
# 粉笔写下的节日 · 教师节黑板报 - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | 粉笔写下的节日 · 教师节黑板报 |
| Canvas Format | PPT 16:9 (1280×720) |
| Page Count | 13 |
| Primary Language | zh-Hans-CN |
| Target Audience | 中小学师生与到校家长,以及负责出黑板报的宣传委员和班主任;他们知道教师节是 9 月 10 日,但基本说不出这个日期怎么定下来的,也没见过教师队伍的整体数字 |
| Communication Intent | 先把教师节的来历讲清楚(四次改期与 1985 年设节的动议链条),再用官方数据让"老师"这个群体有具体体量感,最后落到今天就能做出的尊师表达;顺序上"讲清来历"优先于"讲数据",数据服务于情感落点 |
| Desired Audience Outcome | 看完能说出教师节为什么定在 9 月 10 日、能举出至少一个尊师典故,并愿意在今天对老师说一句具体的话 |
| Core Message / Ask / Action | 教师节不是凭空定下来的——它被提了四次、改了四次日期,才在 1985 年落到 9 月 10 日;今天全国有 1870.10 万名专任教师站在讲台后面 |
| Delivery Context | 主:教室投影,班会课上由老师或宣传委员逐页讲;次:导出后作为校园公众号推文素材与打印板报底稿留存 |
| Artifact Afterlife | 存档复用——明年教师节换一组数据可再用;也可拆页作为黑板报版式参考 |
| Reading Mode | balanced |
| Content Strategy | 自采事实为唯一数字与史实来源,官方共识与出处不确的传闻分开写并标注;版式上按黑板报栏目自由重组,不受源文件段落顺序约束 |
| Design Style | 黑板报:深板面 + 干涩粉笔笔触 + 粉质彩粉点缀;每页一块板报版面(报头 + 主栏 + 小栏目 + 粉笔花边) |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 最终 Stage-2 proactive 默认值 `true`,用户未作相反指示 |
| Custom Animations | enabled — 用户在任务书中明确要求 `animations.json` 与自定义入场/承接动画 |
| Narration Audio | disabled — 最终 Stage-2 proactive 默认值 `false` |
| Created Date | 2026-09-10 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 上下左右各 56px;板面木框内侧再留 20px 粉笔留白 |
| Content Area | x 56–1224, y 56–664(可用 1168 × 608) |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: narrative, instructional
- **Mode Behavior**: 全卷主轴用 narrative 的 situation → tension → resolution 走"教师节被提了四次、改了四次日期,才落到 9 月 10 日"这条曲折;每一页内部改用 instructional 的分块并列——一个主栏把这一段讲透,两到三个小栏目(数字角/小知识角/名言角)平行承载可扫读的碎片,像真实黑板报那样一版多栏。转场页用板擦擦过的动作完成幕的切换。
- **Visual style**: chalkboard
- **Theme**: 教室后墙的一整排黑板报——深板面、木框、粉笔槽;报头是手写粉笔艺术字,主栏用手绘粉笔框圈住,小栏目用非对齐点的粉笔线框,页脚有粉笔灰与半截粉笔头
- **Tone**: 怀旧、亲切、课堂气;不端着,也不卖萌

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #1E2B27 | 黑板板面主色(深墨绿石板) |
| Secondary background | #26352F | 栏目底板、板面分区、木框内侧的稍亮区块 |
| Primary | #F4F1E8 | 主粉笔白——报头、主标题、主栏正文的主要笔迹 |
| Accent | #F3C969 | 粉质暖黄——重点圈画、关键数字、当前节点 |
| Secondary accent | #9FD0C0 | 粉质薄荷绿——次级强调、图表第二序列、时间轴刻度 |
| Body text | #E8E4D8 | 正文粉笔字 |
| Secondary text | #B4AE9E | 注释、栏目落款、图注、来源行 |
| Divider | #46564F | 粉笔分栏线、表格格线、栏目边框 |
| Chalk rose | #E8A0A8 | 粉质胭脂——图表第三序列与引文标记 |
| Surface | #2B3A34 | 小栏目卡片抬起一档的底 |
| Grid | #38473F | 图表网格发丝线(比 divider 更淡) |
| Block shade | #24322C | 手绘框的错位投影块(平涂,非阴影) |

### AI Image Strategy

- **Image Rendering**: chalkboard
- **Visual**: 粉笔画在深色石板上——干涩起毛的白色主线、粉质彩色点染、笔画末端有断续与粉尘,没有渐变与高光,没有描边外框
- **Mood**: 课间刚被人画完的那块黑板报,粉笔灰还浮在空气里;像小学教室后墙拍下来的一角

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 手写楷体,粉笔书写的顿挫感 | KaiTi | Trebuchet MS | serif |
| Body | 清晰黑体,投影可读 | Microsoft YaHei | Arial | sans-serif |
| Quote | 古文引句,竖排感的楷书 | KaiTi | Times New Roman | serif |
| Data | 等高数字,图表与数字角专用 | Trebuchet MS | Trebuchet MS | sans-serif |
| Annotation | 小字注释与图注 | Microsoft YaHei | Arial | sans-serif |
| Emphasis | 等高数字,比率强调 | Trebuchet MS | Trebuchet MS | sans-serif |

- **Typography upgrade (Reference)**: 若目标机安装了「华文行楷」或「方正粉笔体」,可将 Title 与 Quote 角色替换为其一,粉笔手写感更强;未安装时保持 KaiTi
- **Title stack**: `KaiTi, "Trebuchet MS", serif`
- **Body stack**: `"Microsoft YaHei", Arial, sans-serif`
- **Quote stack**: `KaiTi, "Times New Roman", serif`
- **Data stack**: `"Trebuchet MS", "Microsoft YaHei", sans-serif`
- **Annotation stack**: `"Microsoft YaHei", Arial, sans-serif`
- **Emphasis stack**: `"Trebuchet MS", "Microsoft YaHei", sans-serif`
- **Role rationale**: Emphasis 是 P09 三个生师比数字反复出现的比率显示档,低于 Data 的 64 而高于 Subtitle,须单独命名;Quote 与 Data 各自需要不同族——古文引句要楷体的书写体势,而 KaiTi 的数字不等高,图表与数字角必须换成等高数字的 Trebuchet MS

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 44 |
| Subtitle | 32 |
| Cover title | 84 |
| Column head | 28 |
| Lead | 30 |
| Quote | 30 |
| Data | 64 |
| Annotation | 18 |
| Emphasis | 40 |
| Footnote | 16 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 视线从左上角报头(艺术字 + 原生标题)进入,沿主栏向右下读完,再被粉笔花边引到右侧或下方的小栏目;每页只有一个主栏
- **Composition tendency**: 一版多栏的板报式分区——主栏占约三分之二,小栏目沿一条边排开;分区靠粉笔线与留白,不靠卡片堆叠
- **Cross-page continuity**: 木框与粉笔槽每页复现且位置不变;报头永远在左上;页脚右下角永远有半截粉笔与粉笔灰;时间轴弧线在 P03–P05 连续推移
- **Spacing posture**: variable by page rhythm——anchor 页放空,dense 页栏目排满但每栏内部保持行距宽松
- **Spacing anchors**: 页边距 56px;区块间距 32px;分栏槽 40px;圆角 12px;正文行高 38px

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2

| Icon Path | Suitable Scenarios |
| --- | --- |
| icons/tabler-outline/chalkboard-teacher.svg | 教师、讲台、课堂角色 |
| icons/tabler-outline/school.svg | 学校、学段、校园场景 |
| icons/tabler-outline/pencil.svg | 书写、提议、起草 |
| icons/tabler-outline/book-2.svg | 典籍、课文、引文出处 |
| icons/tabler-outline/calendar-event.svg | 日期、节点、改期 |
| icons/tabler-outline/quote.svg | 名言角、引句标记 |
| icons/tabler-outline/award.svg | 表彰、优秀教师 |
| icons/tabler-outline/users-group.svg | 教师队伍、人数规模 |
| icons/tabler-outline/star.svg | 粉笔星点缀、重点标记 |
| icons/tabler-outline/bulb.svg | 小知识角、提示 |
| icons/tabler-outline/ruler-2.svg | 度量、比例、生师比 |
| icons/tabler-outline/world.svg | 各国教师节 |
| icons/tabler-outline/snowflake.svg | 程门立雪 |
| icons/tabler-outline/mail-heart.svg | 慰问信、给老师的话 |
| icons/tabler-outline/link.svg | 来源链接栏 |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P08 | chart | column_chart | 按学段比较 2025 年专任教师人数,让"1870 万"落成七根可读的柱子 |
| P09 | chart | horizontal_bar_chart | 比较四个学段专任教师中本科及以上学历的比例,呈现学历结构的台阶 |
| P10 | table | record_table | 六个国家/国际组织各占一行,列出教师节日期与它的来历 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cover_lettering.png | 1760×627 | 2.81:1 | 封面刊头艺术字「粉笔写下的节日」 | Illustration | 横贯封面上半的手写粉笔大字,原生副标题在其正下方另起一行 | no-crop | slice | Generated | Derived from cover_head_sheet.png; grid cell 1 | embedded | local |
| head_p02.png | 800×158 | 5.06:1 | P02 刊头字 | Illustration | 报头左上角,原生小标题在其右下 | no-crop | slice | Generated | Derived from head_sheet_a.png; grid cell 1 | embedded | local |
| head_p03.png | 800×124 | 6.46:1 | P03 刊头字 | Illustration | 报头左上角 | no-crop | slice | Generated | Derived from head_sheet_a.png; grid cell 2 | embedded | local |
| head_p04.png | 800×139 | 5.75:1 | P04 刊头字 | Illustration | 报头左上角,与 P03 同位承接 | no-crop | slice | Generated | Derived from head_sheet_a.png; grid cell 3 | embedded | local |
| head_p05.png | 800×170 | 4.7:1 | P05 刊头字 | Illustration | 报头左上角 | no-crop | slice | Generated | Derived from head_sheet_a.png; grid cell 4 | embedded | local |
| head_p06.png | 800×174 | 4.61:1 | P06 刊头字 | Illustration | 报头左上角 | no-crop | slice | Generated | Derived from head_sheet_a.png; grid cell 5 | embedded | local |
| head_p07.png | 1400×255 | 5.49:1 | P07 转场页刊头字 | Illustration | 居中放大,作为幕间大字 | no-crop | slice | Generated | Derived from head_sheet_a.png; grid cell 6 | embedded | local |
| head_p08.png | 800×148 | 5.4:1 | P08 刊头字 | Illustration | 报头左上角 | no-crop | slice | Generated | Derived from head_sheet_b.png; grid cell 1 | embedded | local |
| head_p09.png | 800×143 | 5.58:1 | P09 刊头字 | Illustration | 报头左上角 | no-crop | slice | Generated | Derived from head_sheet_b.png; grid cell 2 | embedded | local |
| head_p10.png | 800×201 | 3.99:1 | P10 刊头字 | Illustration | 报头左上角 | no-crop | slice | Generated | Derived from head_sheet_b.png; grid cell 3 | embedded | local |
| head_p11.png | 800×234 | 3.42:1 | P11 刊头字 | Illustration | 报头左上角 | no-crop | slice | Generated | Derived from head_sheet_b.png; grid cell 4 | embedded | local |
| head_p12.png | 800×251 | 3.18:1 | P12 刊头字 | Illustration | 报头左上角 | no-crop | slice | Generated | Derived from head_sheet_b.png; grid cell 5 | embedded | local |
| head_p13.png | 800×201 | 3.98:1 | P13 刊头字 | Illustration | 报头左上角 | no-crop | slice | Generated | Derived from head_sheet_b.png; grid cell 6 | embedded | local |
| art_chalk_stub.png | 694×483 | 1.44:1 | 半截粉笔与板擦——页脚复现物与承接件 | Illustration | 页脚右下角小尺寸复现;P07 放大为主角 | no-crop | slice | Generated | Derived from chalk_sheet.png; grid cell 1 | none | local |
| art_podium.png | 765×593 | 1.29:1 | 讲台与黑板一角——封面与数字页的场景锚 | Illustration | 封面右下角压住木框;P08 缩小为栏目角标 | no-crop | slice | Generated | Derived from chalk_sheet.png; grid cell 2 | none | local |
| art_book_brush.png | 792×519 | 1.53:1 | 线装书与毛笔——典故与引文栏的插图 | Illustration | P11 主栏右侧 | no-crop | slice | Generated | Derived from chalk_sheet.png; grid cell 3 | none | local |
| art_snow_gate.png | 800×604 | 1.32:1 | 程门立雪——雪中门前两个身影 | Illustration | P11 主栏主视觉,与引文左右并置 | no-crop | slice | Generated | Derived from chalk_sheet.png; grid cell 4 | none | local |
| art_globe_caps.png | 800×511 | 1.56:1 | 地球与不同学士帽——各国教师节栏插图 | Illustration | P10 表格右上角留白处 | no-crop | slice | Generated | Derived from chalk_sheet.png; grid cell 5 | none | local |
| art_flower_card.png | 771×469 | 1.64:1 | 粉笔花与贺卡——收尾页尾花 | Illustration | P13 右下尾花 | no-crop | slice | Generated | Derived from chalk_sheet.png; grid cell 6 | none | local |

## IX. Content Outline

### Part 1: 这个日子是怎么来的

#### Slide 01 - 封面 · 粉笔写下的节日

- **Audience move**: 知道今天是教师节 → 意识到这个日期本身有故事,愿意读下去
- **Relationships**: 三个单元——刊头(节日名)、当届标记(第 42 个、2026-09-10)、今年主题;当届标记与主题是刊头的从属说明(parent)
- **Cover impact**: 钩子(binding)——「今天是第 42 个教师节。这个日子,改了四次才定下来。」;构图 Reference:艺术字横贯上半,原生副标题压在其下,右下角讲台插图咬住木框
- **Composition**: 单焦点——报头艺术字独大,其余全部让位
- **Title**: 粉笔写下的节日
- **Core message**: 教师节的日期改过四次,今天是它定型后的第 42 个年头
- **Content**: 副标题「教师节黑板报 · 2026 年 9 月 10 日 · 第 42 个教师节」· 今年主题「大力弘扬教育家精神,共筑尊师重教风尚」· 落款「班级板报组 编」
- **Images**: cover_lettering.png 作显示层,原生标题另起一行;art_podium.png 压右下木框
- **Motion suggestion**: 刊头字按笔顺逐笔写出,副标题随后浮现;粉笔插图最后落位
- **Fact IDs**: F001
- **page_rhythm**: anchor

#### Slide 02 - 为什么是九月十日

- **Audience move**: 只知道日期 → 能说出选 9 月 10 日的两条官方理由,并记住 1985-01-21 这个决定日
- **Relationships**: 两个单元——"哪一天作的决定"与"为什么选这一天";后者是前者的理由(link),两条理由之间是并列(membership)
- **Composition**: 左侧一个大日期块作焦点,右侧两条理由平行排开
- **Title**: 为什么是九月十日
- **Core message**: 1985 年 1 月 21 日,第六届全国人大常委会第九次会议决定,每年 9 月 10 日为教师节
- **Content**: 决定日「1985.01.21」与会议全称 · 理由一:新生入学伊始即开始尊师重教,给"教师教好、学生学好"创造气氛 · 理由二:9 月份全国性节日少,便于集中组织活动和宣传报道 · 数字角「9·10」
- **Visualization**: 无独立数据对象;日期块为原生 SVG 排版
- **Motion suggestion**: 日期块先立住,两条理由依次从粉笔线上滑入
- **Fact IDs**: F008, F009
- **page_rhythm**: breathing

#### Slide 03 - 改了四次的日子(上)

- **Audience move**: 以为教师节一直是 9 月 10 日 → 知道 1931 年和 1939 年各有过一个不同的教师节
- **Relationships**: 一条时间序列(order)上的两个节点;两个节点之间是对比(contrast)——一个由教师自发、政府未承认,一个由政府另立、未能推行
- **Composition**: 一条手绘粉笔弧线横贯页面,两个节点挂在弧线上,弧线右端留白指向下一页
- **Title**: 改了四次的日子(上)
- **Core message**: 头两个教师节,一个不被承认,一个推不下去
- **Content**: 1931「六·六」:邰爽秋、程其保等发起,拟定每年 6 月 6 日,发表《教师节宣言》,提出改善教师待遇、保障教师工作、增进教师修养三项目标;教师自发设立,当时的国民党政府没有承认,但在各地产生了一定影响 · 1939「八·二七」:决定另立孔子诞辰日 8 月 27 日为教师节,颁发《教师节纪念暂行办法》,当时未能在全国推行 · 小知识角:自 1931 年以来共有过 4 种不同日期和性质的教师节
- **Motion suggestion**: 弧线先画出,两个节点按年份先后点亮;弧线右端保持未完成
- **Fact IDs**: F002, F003, F004, F012
- **page_rhythm**: dense

#### Slide 04 - 从五一到九一〇(下)

- **Audience move**: 知道前两次改期 → 补齐后两次,能完整复述四次变迁
- **Relationships**: 承接上一页的同一条时间序列(order),补上第三、第四个节点;第三个节点与第四个节点之间是转折(contrast)
- **Composition**: 同一条粉笔弧线从上一页推移过来,左端两个旧节点淡去,右端两个新节点点亮
- **Title**: 从五一到九一〇
- **Core message**: 并进"五一"的教师节缺少教师的特点,直到 1985 年才有了自己的日子
- **Content**: 1951「五·一」:4 月 19 日,教育部长和中国教育工会全国委员会主席发表书面谈话,宣布"五一国际劳动节"同时为教师节;由于这一天缺少教师的特点,执行的结果并不理想 · 1985「九·一〇」:1 月 11 日国务院提出议案,1 月 21 日第六届全国人大常委会第九次会议作出决议 · 数字角:四次改期,历时 54 年
- **Motion suggestion**: 弧线与前两个节点保持位置不动,后两个节点依次点亮,第四个节点用暖黄圈住
- **Fact IDs**: F005, F007, F008
- **page_rhythm**: dense

#### Slide 05 - 一个早上的念头

- **Audience move**: 以为设节是一纸公文 → 知道它起于一个人某天早上的念头,经过报纸、联名、议案四步才落地
- **Relationships**: 四个事件构成严格的时间因果链(order + link):念头 → 见报 → 联名提议 → 议案与决议
- **Composition**: 四格粉笔链条自左向右,每格一日期一动作,末格放大
- **Title**: 一个早上的念头
- **Core message**: 从一个人的念头到全国性的节日,只用了 43 天
- **Content**: 1984.12.09 王梓坤教授当天把想法告诉《北京晚报》 · 次日该报刊出《王梓坤校长建议开展尊师重教月活动》 · 1984.12.15 北师大钟敬文、启功、王梓坤、陶大镛、朱智贤、黄济、赵擎寰联名正式提议设立教师节 · 1985.01.11 国务院提出议案,01.21 全国人大常委会作出决议 · 引语角:"我也不知道为什么,那天早上一起床就忽然想到老师应该有自己的节日。"——王梓坤
- **Motion suggestion**: 四格按时间依次出现,末格放大后与下一页的日期章对齐
- **Fact IDs**: F006, F007, F008
- **page_rhythm**: dense

#### Slide 06 - 第一个教师节

- **Audience move**: 知道日期定了 → 知道 1985 年 9 月 10 日那天真实发生了什么
- **Relationships**: 一个日期下挂三件同日发生的事(parent + membership);另有一条与节日属性有关的小知识,与主栏无从属关系(none)
- **Composition**: 中央一枚放大的日期章作焦点,三件事绕章排开,右下角小知识角独立成框
- **Title**: 第一个教师节
- **Core message**: 1985 年 9 月 10 日,中国恢复建立的第一个教师节
- **Content**: 国家主席李先念向全国教师发出慰问信祝贺节日 · 首都召开万人庆祝大会 · 教师节期间 20 个省市共表彰 11871 个省级优秀教师集体和个人 · 数字角「11871」 · 小知识角:教师节是我国仅有的三个行业性节日之一(另两个是护士节、记者节);按《全国年节及纪念日放假办法》第五条,教师节不放假
- **Motion suggestion**: 日期章先落下,三件事依次浮现,数字 11871 最后跳出
- **Fact IDs**: F010, F011, F012
- **page_rhythm**: breathing

### Part 2: 讲台后面有多少人

#### Slide 07 - 擦一擦,换一版

- **Audience move**: 读完来历 → 意识到叙述要换一个方向,从历史转向今天的教师队伍
- **Relationships**: none
- **Composition**: 幕间大字居中,一块板擦从左向右擦出一道干净板面,右侧露出下一版的起头
- **Title**: 擦一擦,换一版
- **Core message**: 日子讲完了,该讲讲今天站在讲台后面的人
- **Content**: 幕间大字「擦一擦,换一版」 · 一行引导句:今天全国有多少位专任教师?
- **Images**: art_chalk_stub.png 放大为主角,板擦与粉笔头并置
- **Motion suggestion**: 板擦横向扫过,擦过之处旧笔迹消失、新板面露出;粉笔头随后落在粉笔槽上
- **page_rhythm**: anchor

#### Slide 08 - 讲台后面有多少人

- **Audience move**: 对"很多老师"没有量感 → 能说出全国专任教师总数,并知道人最多的是小学
- **Relationships**: 七个学段构成一个整体的分项(parent + membership),彼此之间按人数可比(contrast)
- **Composition**: 上方一行总量数字,下方一幅按学段排开的柱状图占据主栏
- **Title**: 讲台后面有多少人
- **Core message**: 2025 年,全国专任教师 1870.10 万人
- **Content**: 总量「1870.10 万人」,同年各级各类学校 44.07 万所、在校生 28040.43 万人 · 分学段柱状:学前 261.26、小学 645.82、初中 423.95、普通高中 237.20、中职 70.32、特殊教育 8.51、高等教育 222.36(单位:万人) · 口径注:七个学段合计 1869.42 万人,与总数的差额来自公报另计的其他学校教师,不可写成"等于总数" · 数字角「1870.10 万」
- **Visualization**: teacher-count-by-stage = 按学段的专任教师人数柱状图(chart/column_chart);`Native-ready` teacher-count-by-stage=yes
- **Fact IDs**: F013, F014, F015, F016, F017, F018, F019, F020
- **page_rhythm**: dense

#### Slide 09 - 他们是怎样一群人

- **Audience move**: 只有总数概念 → 知道教师队伍的学历结构与生师比这两个侧面
- **Relationships**: 四个学段在同一把学历标尺上比较(contrast);生师比是另一组独立指标,与学历无从属关系(none)
- **Composition**: 左侧横向条形图占主栏,右侧一列生师比小栏目
- **Title**: 他们是怎样一群人
- **Core message**: 学段越高,本科及以上学历的比例越高;而生师比在初中与普通高中最低
- **Content**: 本科及以上学历比例:小学 85.30%、初中 95.51%、中职 97.59%、普通高中 99.47% · 生师比小栏:小学 15.76:1、初中 13.00:1、普通高中 12.81:1 · 口径注:学前教育用的是"专科及以上"96.05%,与上面四行口径不同,单独放在注释里,不进同一组比较 · 义务教育阶段专任教师合计 1069.76 万人
- **Visualization**: teacher-degree-share = 四学段本科及以上学历比例横向条形图(chart/horizontal_bar_chart);`Native-ready` teacher-degree-share=yes
- **Fact IDs**: F015, F016, F017, F021, F022, F023, F034, F035, F036
- **page_rhythm**: dense

#### Slide 10 - 世界的教师节

- **Audience move**: 以为教师节是中国独有 → 知道各国日期不同,且每个日期背后都有一个来由
- **Relationships**: 六行并列记录(membership),每行"日期"与"由来"之间是解释关系(link)
- **Composition**: 一张占据主栏的原生表格,右上留白处放一枚粉笔插图
- **Title**: 世界的教师节
- **Core message**: 每个国家的教师节都挂在一个具体的人或一份具体的文件上
- **Content**: 表格三列(国家/地区、日期、由来):中国 9 月 10 日 / 1985 年全国人大常委会决议;世界教师日 10 月 5 日 / 1994 年设立,纪念 1966 年 ILO-UNESCO《关于教师地位的建议》通过;印度 9 月 5 日 / 纪念学者、第二任总统拉达克里希南生日,自 1962 年起;美国 5 月第一个整周的星期二 / 1985 年起由全国教育协会确定;泰国 1 月 16 日 / 源于 1945 年 1 月 16 日《教师法》公布,1957 年首次举办;韩国 5 月 15 日 / 1965 年起定于世宗大王诞辰
- **Visualization**: world-teacher-days = 各国教师节日期与来历记录表(table/record_table);`Native-ready` world-teacher-days=yes
- **Images**: art_globe_caps.png 置于表格右上留白
- **Fact IDs**: F008, F024, F025, F026, F027, F028
- **page_rhythm**: dense

### Part 3: 尊师是一件具体的事

#### Slide 11 - 程门立雪

- **Audience move**: 听过"程门立雪"这个成语 → 能说出它的原文出处与两个当事人,并读到《师说》里对"师"的定义
- **Relationships**: 两个单元——典故与经典定义;二者并列(membership),共同支撑"尊师"这一主题(parent)
- **Composition**: 左侧典故插图与原文竖排引句,右侧《师说》两句引文,中间一道粉笔分栏线
- **Title**: 程门立雪
- **Core message**: 尊师在古人那里是站在雪里等一个人醒来
- **Content**: 典故原文(《宋史·杨时传》):"又见程颐于洛,时盖年四十矣。一日见颐,颐偶瞑坐,时与游酢侍立不去。颐既觉,则门外雪深一尺矣。" · 一句白话释义与人物说明(杨时、游酢、程颐) · 韩愈《师说》:"古之学者必有师。师者,所以传道、受业、解惑也。" · "是故无贵无贱,无长无少,道之所存,师之所存也。" · 引用注:两段引文的权威底本为繁体,此处转写为简体,原字词未改;"受业"不写作"授业"
- **Images**: art_snow_gate.png 主视觉;art_book_brush.png 作《师说》栏角标
- **Fact IDs**: F031, F032, F033
- **page_rhythm**: dense

#### Slide 12 - 板报角

- **Audience move**: 读完主线 → 在三个小栏目里各带走一件可复述或可动手的小东西
- **Relationships**: 三个小栏目并列(membership),彼此无先后
- **Composition**: 三栏等宽的小栏目并排,每栏一个手绘粉笔框,框的错位投影块用平涂
- **Title**: 板报角
- **Core message**: 名言、谜语、画法——黑板报该有的三个小栏目
- **Content**: 名言角:"三人行,必有我师焉。择其善者而从之,其不善者而改之。"(《论语·述而》);"温故而知新,可以为师矣。"(《论语·为政》) · 谜语角(编者出题,非古籍典故):"一身白衣不怕脏,越写越短越漂亮,黑板上面留下字,自己却是无声响。"——打一文具 · 粉笔技法角:握笔要平推不要立着戳,粉笔侧面拖出来的宽笔画适合写报头;先用点定四角再连线,框才不歪;写完用手指抹一下笔画外缘,粉笔字才有毛边
- **Motion suggestion**: 三栏依次浮现,谜语的答案在框内保持隐藏,由讲述者口头揭晓
- **Fact IDs**: F029, F030
- **page_rhythm**: breathing

#### Slide 13 - 说给老师听

- **Audience move**: 读完全篇 → 带走一句可以今天就说出口的话,并知道去哪里核对本卷的每一个数字
- **Relationships**: 两个单元——行动建议与来源清单;二者并列(membership),来源清单是全卷事实的凭据(link)
- **Closing impact**: 落点(binding)——「与其说'老师辛苦了',不如说出一件具体的事:哪一节课、哪一句话、哪一次你被拉了一把。」;构图 Reference:落点句独占左侧主栏,来源清单收在右侧窄栏,尾花在右下
- **Composition**: 左重右轻——一句大字落点,右侧一列可点击的来源行
- **Title**: 说给老师听
- **Core message**: 把感谢说具体,把数字留下出处
- **Content**: 落点大字 · 三条可照着说的句式提示 · 想自己查:教育部《我国教师节简介》《教师节的由来》《2025 年全国教育事业发展统计公报》、教育部《关于做好庆祝第 42 个教师节有关工作的通知》、UNESCO 世界教师日 · 落款「资料截至 2026 年 9 月 10 日」
- **Images**: art_flower_card.png 作右下尾花
- **Motion suggestion**: 落点句先出,来源行随后逐条浮现;粉笔头从上一页的位置移到本页落款处
- **Fact IDs**: F001, F013, F024
- **page_rhythm**: anchor

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 每页写给站在班上讲这块板报的老师或宣传委员——先一句把本页的板报版面指给听众看,再按主栏、小栏目的顺序讲;所有数字与史实只复述页面上已有的内容,不引入页面外的新事实;古文引句先读原文再给一句白话;涉及出处不确的传闻一律不讲
- **Total duration**: 全卷约 11–13 分钟,平均每页 50–60 秒,P07 转场页约 20 秒
- **Notes style**: conversational——课堂口语,可以直接对学生发问
- **Presentation purpose**: 先把教师节的来历讲清楚,再用官方数据让教师群体有体量感,最后落到今天就能做出的尊师表达
