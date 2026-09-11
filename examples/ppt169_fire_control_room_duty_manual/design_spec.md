<!-- ppt-master-schema: design-spec/v1 -->
# 消防控制室值班手册 - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | 消防控制室值班手册 |
| Canvas Format | PPT 16:9 (1280×720) |
| Page Count | 16 |
| Primary Language | zh-CN |
| Target Audience | 新上岗的消防控制室值班员(已取得或正在取得消防设施操作员证的监控操作方向人员);受过设备按键层面的基础培训,但没有把散落在国家标准、法规和统计里的值班规则串成一条可推导的判断轴 |
| Communication Intent | 以教学为主、留档交接为辅:先建立"报警信号 → 处于哪一级 → 下一步做什么"的判断轴,再把每一级的规则回溯到它依赖的机制,最后交付可当班携带的检查表与人员配置表 |
| Desired Audience Outcome | 值班员在接到报警后不翻手册即可说出自己处于哪一级、该级唯一正确的动作是什么,并能正确填写值班与交接记录 |
| Core Message / Ask / Action | 值班不是盯屏幕,是把每一个报警信号推进到一个明确的级别,并在该级别上执行唯一正确的动作 |
| Delivery Context | 讲师主导的内部上岗培训课,约 35 分钟;课后作为电子手册留存,供当班随时翻阅 |
| Artifact Afterlife | 上岗前自查与班组复训;检查表页与人员配置表页需要能被单独打印或导出编辑 |
| Reading Mode | balanced |
| Content Strategy | 把 GB 25506-2010、《消防法》、国家职业标准与年度火灾统计中的值班规则重组为一条四级判断轴;事实一律不外扩,凡自建的分级、框架与推论在页面上标注"整理",引自条文的标注条号 |
| Design Style | Duty Manual(勤务手册)Style:判断句标题、机制先于规则、规则回溯机制页;深底硬网格、零圆角细线容器、左缘进度指示条、两种强调色分工固定 |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 最终 Stage-2 主动建议值(默认 true) |
| Custom Animations | enabled — 用户在本次运行指令中明确要求自定义动画 |
| Narration Audio | disabled — 最终 Stage-2 主动建议值(默认 false) |
| Created Date | 2026-09-11 |

- **Template Application**: 采用 duty-manual Style 的全部方法层与视觉默认值:标题写成可判断的句子,机制页先于规则页,每条规则标出它回溯的机制页;深底、零圆角细线容器、左缘进度指示条(当前节亮强调色、反例页整条转警示色)、两种强调色分工固定(黄绿承载关键量与正确做法,橙红承载危险、禁止与最高级别)。Style 未提供原型与结构,页面为自由设计的 flat 结构;Style 的回退配色与字体表在本项目没有 Brand/Deck 身份可覆盖的前提下整套采用。Style §VII 的 Review Focus 仅作为自检清单,不触发 visual-review 阶段。

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 上 56 / 下 56 / 左 96(含左缘指示条 24 + 间距)/ 右 64 |
| Content Area | x 96–1216,y 56–664 |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: instructional, pyramid
- **Mode Behavior**: 每节以一句可判断的结论开场,再按"拆开—展开—应用"三拍讲机制:先讲对象是什么与它的代价,再讲什么条件下会变化,最后讲它要求的配置与动作。全 deck 只保留一条纵向判断轴,任何一页都能回答"现在在第几级、第几步"。标题写成判断句而不是名词短语。
- **Visual style**: custom
- **Visual Style References**: swiss-minimal, blueprint, dark-tech
- **Visual Style Behavior**: 深底之上的严格网格手册。swiss-minimal 负责基线栏、硬左对齐边与大留白;blueprint 负责细线网格、引出线注解与剖面式图解排布;dark-tech 负责深底上的荧光级强调与几何精度。容器一律为零圆角的细线方框,无投影无辉光。左缘固定一条分节进度指示条,当前节以强调色点亮,离轴内容整条转为警示色。
- **Theme**: 一本挂在值班台上的技术手册:线是信息,不是装饰;判断轴贯穿全书,读者随时知道自己在哪一格
- **Tone**: 克制、准确、可执行;不煽情,不用"务必""切记"一类空词,用条款号与代价说话

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #0E1B2E | 全 deck 深色场地 |
| Secondary background | #1A2C46 | 面板、表头、图解衬底 |
| Primary | #4A9FD8 | 结构线、次级标题、图表主系列 |
| Accent | #D8F04A | 关键量、当前级别、正确做法 |
| Secondary accent | #E85D2B | 危险、禁止、最高风险级别与离轴内容 |
| Body text | #DCE6F0 | 正文与主要标签 |
| Secondary text | #8FA3BC | 注解、脚注、来源行 |
| Divider | #2A3F5C | 分隔线与容器描边 |
| Surface | #16273D | 表格奇偶行与次级面板底,比 Secondary background 更沉 |
| Grid | #1C2E49 | 细线网格背景,永远比 Divider 更弱 |
| Scrim | #0A1422 | 压在实景图上的定向遮罩底色(配透明度使用) |

### AI Image Strategy

- **Image Rendering**: custom
- **Visual**: 两个互补的登记册共享同一深底与同一组强调色——其一是白色等线宽技术线图(无填充、正交连线、端点圆点、引出线注解),其二是冷光深色的实景画面(值班台、报警控制器面板、状态旋钮),画面内一律无文字
- **Mood**: 像一份工程图册和一组夜班现场记录被装订在同一本手册里;前者的参照是工程蓝图,后者的参照是夜间值班室里只有屏幕发光的那种冷静
- **Image Rendering Behavior**: blueprint 负责单一线宽、引出线与剖面式取景;vector-illustration 负责干净的平面主体与无渐变填充;digital-dashboard 负责荧光注解色与刻度式数值显示的观感。线图主体一律用均匀细线勾勒不填充,流向用平行流线与箭头表示,只使用两种强调色——黄绿标关键量、橙红标危险——无渐变、无阴影、无景深、图内无任何文字。实景画面保持同一深底与同一冷光方向,硬边直角嵌入,不做羽化、圆角与倾斜;需要压字处使用定向 scrim 而非整幅压暗。
- **Image Rendering References**: blueprint, vector-illustration, digital-dashboard

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 中性无衬线,方正精确;力量由判断句本身给出 | Microsoft YaHei | Arial | sans-serif |
| Body | 与标题同族;长机制段落久读不累 | Microsoft YaHei | Arial | sans-serif |
| Display | 极重无衬线,用于章节号、级别标记与冲击数字 | Arial Black | Arial Black | sans-serif |
| Data | 等宽等高数字,表格与图表数值对齐 | Arial | Arial | sans-serif |
| Annotation | 与正文同族的小号注解与引出线标签 | Microsoft YaHei | Arial | sans-serif |
| Footnote | 与正文同族的来源行与页码 | Microsoft YaHei | Arial | sans-serif |

- **Title stack**: `'Microsoft YaHei', Arial, sans-serif`
- **Body stack**: `'Microsoft YaHei', Arial, sans-serif`
- **Display stack**: `'Arial Black', 'Microsoft YaHei', sans-serif`
- **Data stack**: `Arial, 'Microsoft YaHei', sans-serif`
- **Annotation stack**: `'Microsoft YaHei', Arial, sans-serif`
- **Footnote stack**: `'Microsoft YaHei', Arial, sans-serif`
- **Role rationale**: Display 与 Data 各自换族——Display 用 Arial Black 取得与正文的重量对比,承载章节号、级别标记与冲击数字;Data 用 Arial 取等高数字,保证原生表格与图表数值右对齐后仍然列齐。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 40 |
| Subtitle | 30 |
| Lead | 28 |
| Display | 96 |
| Data | 22 |
| Annotation | 18 |
| Footnote | 16 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 左缘指示条先回答"在哪一节",标题横贯顶部给出判断句,证据与图解向右下展开,页面以底部一行可执行结论收口
- **Composition tendency**: 硬左对齐的两栏或不对称分割;图与文在相邻页之间左右互换以形成阅读节奏;机制页图解约占半页
- **Cross-page continuity**: 左缘进度指示条每页都在,分四段对应四节;判断轴的四级标记在第 7 页建立后,在每个层级页以同一形状与位置复现;来源行固定在页脚同一基线
- **Spacing posture**: 机制页与表格页密,分隔页与技术要点页留白;每节至少一页明显低密度作为休息
- **Spacing anchors**: 页边距 56px · 块间距 28px · 栏间距 32px · 圆角 0px · 正文行高 1.55

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2

| Icon Path | Suitable Scenarios |
| --- | --- |
| icons/tabler-outline/bell.svg | 报警信号、警报到达 |
| icons/tabler-outline/alert-triangle.svg | 风险提示、离轴内容 |
| icons/tabler-outline/phone.svg | 拨打 119、对外报警 |
| icons/tabler-outline/clipboard-check.svg | 交接班逐项检查 |
| icons/tabler-outline/users.svg | 每班人数与岗位 |
| icons/tabler-outline/clock.svg | 时限、时段 |
| icons/tabler-outline/flame.svg | 火灾确认、着火部位 |
| icons/tabler-outline/device-desktop.svg | 图形显示装置 |
| icons/tabler-outline/toggle-right.svg | 自动/手动状态 |
| icons/tabler-outline/door-exit.svg | 疏散与安全出口 |
| icons/tabler-outline/certificate.svg | 职业资格证书 |
| icons/tabler-outline/file-text.svg | 记录与档案资料 |
| icons/tabler-outline/link.svg | 规则回溯与来源链接 |
| icons/tabler-outline/ban.svg | 禁止做法 |
| icons/tabler-outline/droplet.svg | 消防储水设施与水位 |
| icons/tabler-outline/wind.svg | 防排烟风机 |
| icons/tabler-outline/eye.svg | 核实、观察 |
| icons/tabler-outline/checklist.svg | 清单项与巡查记录 |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P03 | chart | grouped_bar_chart | 同一年度内,两个时段的火灾起数占比与亡人数占比并排对比 |
| P13 | table | record_table | 交接班逐项检查记录:检查项、合格判据、依据条款、挡住的风险 |
| P14 | table | record_table | 每班岗位设置:人数、资格要求、主要职责与依据 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cover_control_room_night.png | 2752x1536 | 16:9 | 封面场景的原始生成件,仅用于派生 | Source | 原始生成件不上页,派生件承担全出血 | adaptive | ai | Generated | 夜间消防控制室内景:一排火灾报警控制器与一面图形显示装置屏幕低亮发光,冷蓝夜色,值班台在前景,无人物面部,画面左半安静、右半承载设备 | none | hero_page |
| cover_control_room_night_fit.jpg | 1280x714 | 16:9 | 封面全出血场景(Slide 01) | 实景 | 全出血铺满整页,配自右向左减弱的定向 scrim,把判断句标题留在左半安静区 | adaptive | ai | Generated | Derived from cover_control_room_night.png; treatment=fit 1280x720; 降到计划上屏尺寸 | none | hero_page |
| divider_alarm_panel.png | 2752x1536 | 16:9 | 第一节分隔页底图的原始生成件,仅用于派生 | Source | 原始生成件不上页,派生件承担全出血 | adaptive | ai | Generated | 火灾报警控制器面板特写:指示灯阵列与按键行,斜向取景,深色背景,冷光,左侧留黑 | none | hero_page |
| divider_alarm_panel_fit.jpg | 1280x714 | 16:9 | 第一节分隔页底图(Slide 04) | 实景 | 全出血底图,巨大章节号与判断句压在左侧安静区,右侧留给面板本身 | adaptive | ai | Generated | Derived from divider_alarm_panel.png; treatment=fit 1280x720; 降到计划上屏尺寸 | none | hero_page |
| divider_duty_log.png | 2752x1536 | 16:9 | 第二节分隔页底图的原始生成件,仅用于派生 | Source | 原始生成件不上页,派生件承担全出血 | adaptive | ai | Generated | 值班台面俯视:摊开的空白值班记录本、手电与对讲机聚在左半幅,右半幅留空,冷光 | none | hero_page |
| divider_duty_log_fit.jpg | 1280x714 | 16:9 | 第二节分隔页底图(Slide 12) | 实景 | 全出血底图,章节号与判断句压在右侧安静区 | adaptive | ai | Generated | Derived from divider_duty_log.png; treatment=fit 1280x720; 降到计划上屏尺寸 | none | hero_page |
| diagram_signal_chain.png | 2528x1696 | 3:2 | 信号链路线图的原始生成件,仅用于派生 | Source | 原始生成件不上页,派生件承担半页线图 | no-crop | ai | Generated | 白色等线宽技术线图:探测器与手动报警按钮经正交连线汇入火灾报警控制器,再到消防联动控制器与受控设备,另有一条支路指向远程监控中心;端点小圆点,箭头示流向,无填充、无文字 | none | local |
| diagram_signal_chain_fit.png | 715x480 | 3:2 | 信号从探测器到监控中心的链路线图(Slide 06) | 线图 | 半页线图置于页面右侧,左侧承载时限判断句与引出线注解 | no-crop | ai | Generated | Derived from diagram_signal_chain.png; treatment=fit 720x480; 降到计划上屏尺寸 | none | local |
| counter_auto_manual_switch.png | 2048x2048 | 1:1 | 反例页主视觉的原始生成件,仅用于派生 | Source | 原始生成件不上页,派生件承担方形主视觉 | adaptive | ai | Generated | 联动控制器面板上旋转状态选择旋钮的近景,指针明显偏离正上方位置,旁边两枚状态指示灯,冷光,无文字 | none | local |
| counter_auto_manual_switch_fit.jpg | 720x720 | 1:1 | 反例页主视觉:自动/手动状态旋钮(Slide 15) | 实景 | 单一主视觉居右成方形硬边嵌入,禁止标记叠在其上,左侧留给机制与罚则 | adaptive | ai | Generated | Derived from counter_auto_manual_switch.png; treatment=fit 720x720; 降到计划上屏尺寸 | none | local |

## IX. Content Outline

### Part 1: 为什么这本手册值得重讲

#### Slide 01 - 封面:接到信号那一刻

- **Audience move**: 把"值班就是盯屏幕、别睡着"的模糊印象 → 意识到每个信号都要被推进到一个明确的级别
- **Relationships**: 判断句主标题与副标题、依据行之间是 parent(主标题统领);依据行三项为 membership(本课的三个权威出处)
- **Composition**: 全出血实景图打底,定向 scrim 从左下向右上减弱;判断句标题压在左下三分之一,左缘进度指示条已经出现但四段都未点亮
- **Cover impact**: hook = "接到信号那一刻,你已经在某一级上";构图为 Reference
- **Title**: 接到信号那一刻,你已经在某一级上
- **Core message**: 值班的全部动作,由"当前处于哪一级"决定
- **Content**: · 主标题判断句 · 副标题:消防控制室值班手册 · 新上岗培训 · 依据行:GB 25506-2010 / 《中华人民共和国消防法》/ 国家职业标准《消防设施操作员》(2026 年版) · 页脚:内部培训材料 · 2026
- **Images**: cover_control_room_night_fit.jpg
- **Motion suggestion**: 主标题与副标题作为主角依次进场;左缘指示条、页脚与底图不动
- **page_rhythm**: anchor

#### Slide 02 - 一年 90.8 万起火灾,最危险的六小时在夜里

- **Audience move**: 知道"火灾很多" → 知道夜班时段的每一次确认,权重与白班不同
- **Relationships**: 三个规模数字为 membership(同一年度同一次发布);夜间两项占比与白天两项占比为 contrast
- **Composition**: 三个超大数字横排占据主区,其余大面积留白;底部一行翻转结论
- **Title**: 一年 90.8 万起火灾,最危险的六小时在夜里
- **Core message**: 火灾总量说明这门课值得重讲,时段结构说明夜班值班员的判断代价最高
- **Content**: · 三个冲击数字:90.8 万起 / 亡 2001 人 / 直接财产损失 77.4 亿元 · 数字下的来源行:2024 年全国火灾情况,国家消防救援局 2025 年 1 月发布 · 翻转结论:0 时至 6 时的火灾只占全年起数的 10.3%,亡人数却占 31.3% · 收口句:夜班的一次确认,不等于白班的一次确认
- **Fact IDs**: F022, F024
- **Motion suggestion**: 三个数字依次进场,翻转结论最后出现;来源行与页面框架不动
- **page_rhythm**: anchor

#### Slide 03 - 夜里六小时,起数最少、死亡最多

- **Audience move**: 只记住"夜里危险" → 看清危险来自"起数占比"与"亡人占比"的背离
- **Relationships**: 两个时段为 contrast;每个时段内起数占比与亡人占比为 overlap(同一时段的两种口径)
- **Composition**: 左侧原生图表占约六成宽,右侧为一段机制说明与一句整理结论
- **Title**: 夜里六小时,起数最少、死亡最多
- **Core message**: 同一口径下起数与亡人占比背离,说明夜间的失败不在"有没有报警",而在"报警之后多久被处理"
- **Content**: · 原生分组柱图:类别为 0—6 时与 10—20 时,系列为火灾起数占比与亡人数占比 · 数值:0—6 时 10.3% / 31.3%;10—20 时 61.4% / 37.4% · 机制说明(整理):占比背离指向报警到处置之间的时间差,而不是探测器更容易失灵 · 收口句:夜班值班员压缩的正是这段时间差
- **Visualization**: `night-vs-day-share` — 原生分组柱图,纵轴为占全年总量的百分比,两系列分别为火灾起数占比与亡人数占比;百分比数据标签使用 number_format
- **Native-ready**: night-vs-day-share=yes
- **Fact IDs**: F024
- **page_rhythm**: dense

### Part 2: 信号从哪里来,走多快

#### Slide 04 - 第一节:先弄清信号从哪里来

- **Audience move**: 准备接受规则清单 → 接受"先讲机制,再讲规则"的顺序
- **Relationships**: 本节两个条目为 order(先设备构成,后时限机制)
- **Composition**: 全出血底图,巨大章节号 01 与判断句压在左侧安静区,本节条目竖排其下
- **Title**: 先弄清信号从哪里来,再谈接到信号怎么办
- **Core message**: 值班动作的合理性来自设备关系与时限,不来自背诵条文
- **Content**: · 章节号 01 · 本节条目:消防控制室里有哪七类设备 · 信息在 10 秒与 100 秒之间怎么走
- **Images**: divider_alarm_panel_fit.jpg
- **Motion suggestion**: 章节号与判断句作为主角进场;左缘指示条第一段在此页点亮,底图不动
- **page_rhythm**: breathing

#### Slide 05 - 消防控制室不是一间房,是七类设备的汇聚点

- **Audience move**: 把消防控制室当作"有屏幕的房间" → 看成一个状态信息必须汇聚并可外传的节点
- **Relationships**: 七类设备为 membership(同一条款列举);七类设备与图形显示装置为 link(状态信息汇聚);汇聚点与城市远程监控中心为 order(先汇聚后外传)
- **Composition**: 原生几何图解占主区,七个零圆角方框经连接线汇入中央的图形显示装置,再向右上一条线指向监控中心;左下为一段判断句说明
- **Title**: 七类设备把状态汇进一块屏,这块屏才是你的工作面
- **Core message**: 值班员操作的不是单台设备,而是一个必须保持状态可见、可控、可外传的汇聚点
- **Content**: · 七类设备(GB 25506-2010 第 3.1 条):火灾报警控制器 / 消防联动控制器 / 消防控制室图形显示装置 / 消防电话总机 / 消防应急广播控制装置 / 消防应急照明和疏散指示系统控制装置 / 消防电源监控器 · 第 3.2 条:设备应能监控并显示建筑消防设施运行状态,并应具有向城市消防远程监控中心传输这些信息的功能 · 第 3.3 条:控制室内应保存第 4.1 条规定的资料与附录 B 的消防安全管理信息 · 收口句:任何一类设备离线,你的工作面就少一块
- **Fact IDs**: F015, F014
- **Motion suggestion**: 七个设备框先在位,连接线随后从外向内生长,最后中央屏与外传链路出现;网格与标题不动
- **page_rhythm**: dense

#### Slide 06 - 火警信息有优先权:10 秒显示,10 秒上传

- **Audience move**: 以为"报警了就会有人知道" → 知道显示、传输各有上限,且火警优先于其他信息
- **Relationships**: 显示时限与传输时限为 overlap(同一信号的两段路径);10 秒与 100 秒为 contrast;火警信息与其他信息为 order(优先级)
- **Composition**: 左侧为时限判断句与两组数字,右侧为信号链路线图,引出线把线图的两个节点与左侧时限对上
- **Title**: 火警信号只有 10 秒的显示与上传额度,其他信号是 100 秒
- **Core message**: 标准把时限写死在设备侧,值班员要做的是不让人为环节把这几十秒吃掉
- **Content**: · 第 5.1 条 e):图形显示装置应在 10 s 内显示输入的火灾报警信号和反馈信号,100 s 内显示其他输入信号 · 第 7.1 / 7.2 条:接收到火灾报警或联动信号后 10 s 内、接收到运行状态信息后 100 s 内传送给监控中心 · 第 7.6 条:火灾报警信息应优先于其他信息传输 · 第 6.1—6.3 条:三类记录容量均不应少于 10 000 条,记录备份后方可被覆盖;第 6.4 条要求历史记录可打印或刻录归档 · 收口句(整理):设备侧的几十秒是给出来的,人为侧的几分钟是自己丢的
- **Images**: diagram_signal_chain_fit.png
- **Fact IDs**: F008, F012, F013, F010, F011
- **page_rhythm**: dense

### Part 3: 一条判断轴

#### Slide 07 - 四级判断轴:先定级,再动作

- **Audience move**: 把值班规则记成一串并列条文 → 把它们挂到一条单向升级的轴上
- **Relationships**: 四个级别为 order(单向升级,不可跳级回退);每个级别与其依据条款为 link;两项代价与级别为 overlap(随级别同步上升)
- **Composition**: 左侧为纵向四级轴的主视觉,右侧为级别索引与对应条款;当前位置标记在此页建立形状
- **Title**: 四级判断轴:你在哪一级,决定你下一步做什么
- **Core message**: 把散落的值班条款收到一条单向升级的轴上,任何时刻只需回答"现在第几级"
- **Content**: · 分级为整理,不是条文原文;条文只区分"接到警报—确认—确认为火灾后" · L0 待确认:信号已到,性质未定;代价:时间压力开始计时,动作可撤销 · L1 非火警:核实为误报或非火灾报警;代价:时间压力解除,记录义务不解除 · L2 确认火警:代价最高,动作不可撤销,三项动作同时启动 · L3 移交与记录:指挥权移交到场力量,记录与归档义务收尾 · 两项随级别上升的代价:可用时间收紧 / 动作的不可撤销性上升
- **Fact IDs**: F003, F004, F005
- **Motion suggestion**: 四级轴自上而下依次建立,当前位置标记最后落到 L0;右侧条款索引与页面框架不动。与下一页构成同一视觉映射的状态推进
- **page_rhythm**: anchor

#### Slide 08 - L0 待确认:唯一正确的动作是立刻去核实

- **Audience move**: 遇到报警先看是不是常报的那个点位 → 先以最快方式确认,再谈判断
- **Relationships**: 条文动作与整理出的执行细则为 parent(细则挂在条文之下);核实与复位为 contrast
- **Composition**: 判断轴缩为左缘的小标记停在 L0,主区为"该做什么/不该做什么"的两栏对照
- **Title**: L0 待确认:标准只给了一个动作——立即以最快方式确认
- **Core message**: 在性质未定之前,任何解释都不能替代到现场看一眼
- **Content**: · 条文(第 4.2.2 条 a 款):接到火灾警报后,值班人员应立即以最快方式确认 · 整理:最快方式的含义由建筑规模决定,标准未规定具体时限,单位应在制度中写死自己的上限 · 整理:每班不少于 2 人的编制,正是为了让一人核实、一人留守工作面 · 不该做的:先消音、先复位、先查历史记录再决定去不去 · 回溯:本页依赖的机制页是 Slide 06(时限)与 Slide 05(工作面)
- **Fact IDs**: F003, F001
- **Motion suggestion**: 与上一页共用判断轴的视觉映射,轴上的当前标记从总览位置推进到 L0;两栏对照随后进场
- **page_rhythm**: dense

#### Slide 09 - L1 非火警:误报不是"没事",是一条必须留痕的记录

- **Audience move**: 把误报当作"虚惊一场,复位即可" → 把误报当作一条要归档、要统计、要复盘的记录
- **Relationships**: 记录义务的四个来源为 membership;复位与留痕为 contrast;误报记录与设备检修为 link
- **Composition**: 主区为一条从"核实为非火警"出发的分支线,分出记录、归档、复盘三条;右下为条款出处
- **Title**: L1 非火警:可以复位,不可以不留痕
- **Core message**: 降级只解除时间压力,不解除记录义务;误报的价值全在记录里
- **Content**: · 第 4.1 条 e):值班情况、消防安全检查情况及巡查情况的记录应保存在控制室 · 第 4.1 条 h):设备运行状况、接报警记录、火灾处理情况、设备检修检测报告等资料应能定期保存和归档 · 《消防法》第十七条:消防安全重点单位应实行每日防火巡查,并建立巡查记录 · 国家职业标准把"能填写消防控制室值班记录表"列为五级/初级工技能 1.1.14 · 整理:同一点位重复误报,应转为检修申报而不是继续复位 · 回溯:本页依赖的机制页是 Slide 05(资料与工作面)
- **Fact IDs**: F014, F020, F017
- **page_rhythm**: dense

#### Slide 10 - L2 确认火警:三个动作同时开始,没有先后可挑

- **Audience move**: 以为"先打 119 还是先启动预案"是个可以商量的顺序 → 知道三项动作在条文里是并列启动,不是排队
- **Relationships**: 三项动作为 membership(同一条款的三款)且为 order(在同一时刻同时开始);与 L1 为 contrast
- **Composition**: 三步竖排堆叠,每步一行核心动作加一行"为什么它不能往后放";右缘为级别标记 L2
- **Title**: L2 确认火警:确认自动、拨打 119、启动预案,三件事同时开始
- **Core message**: 条文把三项动作写成"立即"与"同时",任何一项被排到后面,损失的都是不可逆的时间
- **Content**: · 第一步:立即确认火灾报警联动控制开关处于自动状态——晚一步,联动就要靠人手补 · 第二步:同时拨打 119 报警——晚一步,到场时间整体后移 · 第三步:立即启动单位内部应急疏散和灭火预案,并同时报告单位负责人——晚一步,疏散从最有利的时段开始不了 · 条文出处:第 4.2.2 条 b)、c)款 · 回溯:本页依赖的机制页是 Slide 06(优先级与时限)
- **Fact IDs**: F004, F005
- **Motion suggestion**: 三步自上而下依次进场;级别标记与左缘指示条不动。与下一页构成同一视觉映射的展开
- **page_rhythm**: dense

#### Slide 11 - 报警电话里必须说满五件事

- **Audience move**: 打 119 时凭现场感觉描述 → 按固定五项把信息说满
- **Relationships**: 五个要素为 membership(同一条款的并列要求);与上一页第二步为 parent(本页是该步的展开)
- **Composition**: 五个编号方块横向两行排布,大量留白;底部一行提示为什么最后一项最常被漏
- **Title**: 报警时说满五件事,少一件就要再问一轮
- **Core message**: 五个要素是条文写死的,不是话术建议;补问一轮就是多花一轮时间
- **Content**: · 一 着火单位地址 · 二 起火部位 · 三 着火物种类 · 四 火势大小 · 五 报警人姓名和联系电话 · 条文出处:第 4.2.2 条 b)款 · 整理:第五项最常被漏,而它决定接警方能否回拨核实
- **Fact IDs**: F004
- **Motion suggestion**: 从上一页第二步的位置展开为五个编号块;页面框架与左缘指示条不动
- **page_rhythm**: breathing

### Part 4: 把规则变成当班动作

#### Slide 12 - 第二节:把规则变成当班能执行的动作

- **Audience move**: 理解了判断轴 → 准备接受可逐项核对的当班清单
- **Relationships**: 本节三个条目为 order(先清单,后编制,再反例)
- **Composition**: 全出血底图,章节号 02 与判断句压在右侧安静区,本节条目竖排其下
- **Title**: 判断轴要落到两张能签字的表上
- **Core message**: 判断轴的价值不在记住,而在交接班时能被逐项核对
- **Content**: · 章节号 02 · 本节条目:交接班检查表 · 每班岗位与人数 · 一个反例
- **Images**: divider_duty_log_fit.jpg
- **Motion suggestion**: 章节号与判断句作为主角进场;左缘指示条第二段在此页点亮,底图不动
- **page_rhythm**: breathing

#### Slide 13 - 交接班清单:每一项都挡住一个已知的失败

- **Audience move**: 交接班签个字 → 按项核对,并知道每一项挡住的是哪一种失败
- **Relationships**: 七个检查项为 membership;每个检查项与其依据条款为 link;检查项与它挡住的风险为 link
- **Composition**: 原生表格占据主区,前置条件行以底色区分;右缘留一列放风险图标
- **Title**: 交接班清单:每一项都挡住一个已知的失败
- **Core message**: 清单不是流程留痕,每一行都对应一条会在夜里付出代价的条款
- **Content**: · 原生表格:检查项 / 合格判据 / 依据条款 / 挡住的风险 · 值班人数与证件:在岗 2 人且均持证(第 4.2.1 条 a 款) · 联动控制开关状态:应处于自动状态的设备无一被置于手动(第 4.2.1 条 c 款) · 消防储水设施:高位水箱、水池、气压水罐水量充足(第 4.2.1 条 d 款) · 阀门状态:消防泵出水管阀门、自动喷水系统管道阀门常开(第 4.2.1 条 d 款) · 配电柜启动开关:消防水泵、防排烟风机、防火卷帘的启动开关在自动位置且通电(第 4.2.1 条 d 款) · 图形显示装置:中文界面正常,记录容量与备份可用(第 5.1 条 f、第 6.1—6.3 条) · 上一班未闭环事项:重复报警点位、检修申报、未归档记录(第 4.1 条 h) · 页脚来源行:GB 25506-2010,2010 年发布
- **Visualization**: `handover-checklist` — 原生表格,四列七行,表头以填充与字重区分,关键行以文字颜色而非填充强调,依据条款列右对齐
- **Native-ready**: handover-checklist=yes
- **Fact IDs**: F001, F006, F007, F009, F010, F014
- **page_rhythm**: dense

#### Slide 14 - 每班两人是下限,不是编制建议

- **Audience move**: 以为人数排班由单位自定 → 知道 2 人是标准写死的下限,且两个岗位的职责不同
- **Relationships**: 两个岗位为 contrast(留守与外出核实);岗位与资格要求为 link;人数与条款为 link
- **Composition**: 原生表格居主区,人数列以数字徽标形式加重;左下一行说明资格证书的等级来源
- **Title**: 每班两人是标准写死的下限,且两人不做同一件事
- **Core message**: 2 人不是冗余,是把"留守工作面"与"外出核实"拆成两个不能合并的岗位
- **Content**: · 原生表格:岗位 / 每班人数 / 资格要求 / 主要职责 / 依据 · 值班长(留守):1 人,持消防控制室操作职业资格证书,守住工作面、按值班应急程序处置火警信息、对外报警与报告 · 值班员(核实):1 人,同上资格,接到警报后以最快方式到现场核实,回传结果并配合启动预案 · 合计每班不应少于 2 人(第 4.2.1 条 a 款) · 资格来源:国家职业标准《消防设施操作员》,职业编码 4-07-05-03,设五级/初级工至一级/高级技师五个等级;"能按照消防控制室值班应急程序处置火警信息"是五级/初级工的核心技能 1.1.12 · 整理:岗位名称与分工为本手册整理,标准只规定人数与资格
- **Visualization**: `shift-staffing` — 原生表格,五列三行(含合计行),数字列右对齐,单位统一为"人"
- **Native-ready**: shift-staffing=yes
- **Fact IDs**: F001, F016, F017, F018
- **page_rhythm**: dense

#### Slide 15 - 反例:把该自动的设成手动,等于把整套联动关掉

- **Audience move**: 觉得"怕误动作,先打到手动"是稳妥做法 → 知道这一步同时触发条文禁止与法律责任
- **Relationships**: 错误做法与两条机制为 link(它同时废掉时限机制与联动机制);错误做法与替代做法为 contrast;错误做法与罚则为 order(因果)
- **Composition**: 单一主视觉居右并叠加禁止标记,左侧自上而下为"错误做法—两条机制—罚则—替代做法";左缘指示条整条转为警示色
- **Title**: 把该自动的设成手动,等于把整套联动关掉
- **Core message**: 为了少一次误动作而关掉自动,换来的是在最需要联动的那一刻没有联动
- **Content**: · 错误做法:为避免误喷、误动作,把应处于自动状态的联动控制设备长期置于手动 · 条文禁止(第 4.2.1 条 c 款):不得将应处于自动状态的设备设在手动状态 · 机制一:Slide 06 的时限只覆盖信号侧;手动状态下受控设备的启动完全落在人身上 · 机制二:Slide 02 的时段数据显示 0—6 时亡人占比 31.3%,而这正是人手最少的时段 · 法律后果(《消防法》第六十条):消防设施未保持完好有效,或者损坏、挪用、擅自拆除、停用的,责令改正,处五千元以上五万元以下罚款 · 替代做法(整理):临时转手动必须在值班记录中写明原因、时间与恢复人,并在本班内恢复自动;交接班逐项确认自动位
- **Images**: counter_auto_manual_switch_fit.jpg
- **Fact IDs**: F006, F021, F024
- **page_rhythm**: dense

#### Slide 16 - 每一条规则,都能走回它依赖的那一页

- **Audience move**: 把课程当作听过的一堆条款 → 带走一张能双向查的对照表与四个可核验的出处
- **Relationships**: 每条规则与其机制页为 link(双向可查);被反复回溯的机制页与其余为 contrast;四个来源为 membership
- **Composition**: 密排多列:左两列为"规则 → 机制页"对照,右列为四个来源的可点击链接;被反复回溯的两页以强调色标出
- **Title**: 每一条规则,都能走回它依赖的那一页
- **Closing impact**: 判断轴不是记忆材料,是当班时的定位器;构图为 Reference
- **Core message**: 手册可以合上,轴不能丢:任何一条规则都能在两步内走回它的机制页
- **Content**: · 规则回溯对照:每班 2 人持证 → Slide 14;接警后立即核实 → Slide 08 / Slide 06;误报必须留痕 → Slide 09 / Slide 05;确认火警三动作 → Slide 10;报警说满五要素 → Slide 11;禁止把自动设为手动 → Slide 15 / Slide 06 · 被反复回溯的两页:Slide 06(时限)与 Slide 05(工作面) · 来源与链接:GB 25506-2010《消防控制室通用技术要求》全文(江苏省消防救援总队公开 PDF)· 国家职业标准《消防设施操作员》(2026 年版,国家消防救援局)· 《中华人民共和国消防法》(中国人大网)· 2024 年全国火灾情况(国家消防救援局 2025 年 1 月发布,央视网) · 收口句:接到信号那一刻,先定级,再动作
- **Hyperlinks**: "GB 25506-2010《消防控制室通用技术要求》全文" → https://js.119.gov.cn/group1/M00/00/86/rBPe7WOQFC-ADUCxACEPrA_OX9w654.pdf ; "国家职业标准《消防设施操作员》(2026 年版)" → https://www.119.gov.cn/images/zfxxgk/fdzdgknr/zcfg/2026/05/10/1778399688277005154.pdf ; "《中华人民共和国消防法》" → http://www.npc.gov.cn/npc/c2/c183/c198/201905/t20190522_73607.html ; "2024 年全国火灾情况" → https://news.cctv.com/2025/01/24/ARTIzxLWxFYy5ewOGCrrZPKV250124.shtml
- **Fact IDs**: F001, F003, F004, F006, F014, F021, F024
- **page_rhythm**: dense

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 每页备注承接该页的判断句,先给结论再给支撑;条文一律注明条款号,整理出的分级、岗位分工与推论明确说明是本手册整理;不引入页面上没有的新事实,不复述页面文字
- **Total duration**: 约 35 分钟,单页 1.5—3 分钟,表格页与反例页偏长
- **Notes style**: 讲师口语但克制,先结论后支撑;过渡句用因果关系连接,不用"接下来我们看"一类填充句
- **Presentation purpose**: 以教学为主、留档交接为辅,建立"报警信号 → 处于哪一级 → 下一步做什么"的判断轴
