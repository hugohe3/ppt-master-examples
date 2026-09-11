<!-- ppt-master-schema: design-spec/v1 -->
# 北斗卫星导航系统:从一颗星到全球组网 - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | 北斗卫星导航系统:从一颗星到全球组网 |
| Canvas Format | ppt169 (1280 × 720) |
| Page Count | 14 |
| Primary Language | zh-CN |
| Target Audience | 科普展厅循环播放区的公众观众,含中小学生与陪同家长。他们每天用手机地图,但不知道手机里就有北斗,不了解卫星导航的原理、北斗的建设历程,也说不清"为什么中国要自己建一套"。停留时间短,随时可能中途加入观看。 |
| Communication Intent | 先讲清楚"这是什么、为什么必须自己建",再用一条清晰的时间线讲"三步走怎么走完",然后把"三种轨道各自在做什么""定位原理""短报文为什么是北斗独有"三件事讲透,最后落到"它已经在你身边"和"下一步"。优先级:可信 > 易懂 > 自豪感;不喊口号,只用能标出处的事实说话。 |
| Desired Audience Outcome | 观众离开时能用自己的话说出三件事:北斗走了三步、用三种轨道、能发短报文;并且知道自己手机里就有北斗。 |
| Core Message / Ask / Action | 北斗不是"中国版GPS",而是一套按自己的路线走出来的时空基础设施——三步走完、三轨混合、导航与通信合一,而这条独创的路从第一颗星就已经定下。 |
| Delivery Context | 录播/自动播放(recorded, self-running):科普展厅常设循环播放的讲解片,无现场讲解员,配逐字旁白音频、字幕与自动换页,全片5–7分钟;观众可能中途加入,因此每一场景自身要能读懂。次要用途:线上短视频与课堂播放。 |
| Artifact Afterlife | 长期归档与复用:作为展厅常设素材反复播放,并可交付学校做课堂材料;需保留逐字旁白脚本与来源标注以备核查。 |
| Reading Mode | presentation |
| Content Strategy | 无现成文章可贴近,全部事实来自 topic-research 的权威事实卡片,因此叙事线由本方案自由重组;但每一个数字、每一个日期都必须回到 `sources/beidou_navigation_research.facts.json` 的某一条 fact_id,页面上标出来源名与年份。没有可追溯出处的数字一律不用。 |
| Design Style | 深空仪表台(custom mode + custom visual style):近黑深蓝的太空场作底,信号蓝画轨道与结构,暖金只留给关键数字;页面像一台精密仪器的读数面板,而不是一叠卡片。 |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 启用的 Narration Audio 依赖项;同时本片的逐字旁白就是备注内容 |
| Custom Animations | enabled — 录播/自动播放交付,动效需与旁白 cue 对齐(video-design §4 的 narration-governed motion 分支) |
| Narration Audio | enabled — 用户明确要求 MiniMax 逐字旁白全链路 |
| Created Date | 2026-09-11 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | ppt169 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 72 px 四边安全边 |
| Content Area | x 72–1208, y 72–648(可用宽 1136,可用高 576);背景场、轨道弧线与整幅图像允许出血至画布边缘 |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Visual style**: custom
- **Theme**: 一台观测仪的读数面。全片共用一个"深空观测"心智地图:近黑深蓝的天场恒定不变,地球与轨道是反复出现的锚点,每一页只改变这台仪器正在读的那一个量。跨页母题是**一条贯穿页面的细水平基线**(y 固定),时间轴、轨道剖面、精度刻度、报文长度条都挂在这同一条线上——它是本片的"仪器横梁",让 14 个场景看起来是同一台设备的连续读数,而不是 14 张各自为政的幻灯片。
- **Tone**: 克制、精确、有分量。解说的语气是"我把事实摆给你看",不是"你看我们多厉害"。
- **Mode References**: instructional, narrative
- **Mode Behavior**: 骨架用 instructional 的概念分解与分步推进(每一场景只推进一个理解台阶,前一台阶的结论是下一台阶的前提);但历史那一段(三步走)按 narrative 的张力走——起点是"只有一颗试验星、用户还得自己发信号",转折是"从有源到无源",收束是"提前半年,18箭30星"。两者的分工固定:凡是讲"怎么回事"的页用分解,凡是讲"怎么走过来"的页用故事推进。标题一律写成陈述句而非话题词,让中途加入的观众读标题就拿到该页的主张。
- **Visual Style References**: dark-tech, blueprint, data-journalism
- **Visual Style Behavior**: 近黑深蓝的连续天场(dark-tech 的暗场与发光强调),其上用 blueprint 的示意线语言——细实线、细虚线、刻度、引出线与标注,几何一律用原生形状画(圆、椭圆弧、连接线、预设形状),不用卡片网格承载概念;面板只在需要把读数与天场分开时出现,直角无圆角,靠一条 1px 分隔线而不是阴影抬起。数据页借 data-journalism 的纪律:每个数字下面必须有一条极小的来源行(来源名 + 年份),来源行是本片的视觉签名,出现在每一个有外部事实的页面。装饰密度低——除轨道弧线、刻度与那条仪器横梁外不加任何纯装饰元素;留白大面积留给天场本身,让发光的少数元素成为焦点。排版性格:标题用钝头黑体的方正力量对住天场,数字用等宽体排成仪表读数,两者的对比就是本片的字体戏剧。

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #060B1A | 全片恒定的深空天场,所有页面的底 |
| Secondary background | #0E1730 | 读数面板、表格底、图表绘图区的抬高层 |
| Primary | #4EA8FF | 信号蓝:轨道线、结构线、连接线、图表主序列、页面主强调 |
| Accent | #FFC24B | 暖金:关键数字、当前焦点标记、时间轴上的"现在"点;全片最稀缺的颜色,每页至多一处主用 |
| Secondary accent | #35D0A5 | 青绿:第三类编码(MEO/全球服务/对照序列),只在需要三类并置时出现 |
| Body text | #D8E0F0 | 正文与标题的单色实心字 |
| Secondary text | #8FA0C0 | 说明、标签、坐标轴文字 |
| Divider | #1E2B4A | 分隔线、面板描边、刻度细线 |
| Surface | #111C38 | 图表/表格面板的实底(比 secondary background 再抬一层) |
| Grid | #1A2747 | 网格与刻度发丝线,永远比 divider 更浅 |
| Scrim | #060B1A | 图像之上的压暗层(以 alpha 施加),保证叠字对比 |

### AI Image Strategy

- **Image Rendering**: custom
- **Visual**: 电影级夜景摄影的光与景深。极低照度,单一冷蓝主光,画面里只允许一处暖金点光源;真实大气、真实噪点、真实镜头景深,不是插画也不是三维渲染。每张图都必须留出一块大面积近黑的安静区供叠字,主体推到画面一侧。画面内不得出现任何文字、界面、标注、logo 或可识别的真实人物面孔。
- **Mood**: 安静、辽阔、有人在值守的感觉。参照物是纪录片里的夜间观测镜头——不是宣传片的高饱和英雄镜头。
- **Image Rendering Behavior**: 以真实摄影的线与质地为唯一基底:自然的镜头虚化、可见但克制的暗部噪点、冷蓝到近黑的连续影调过渡,材质靠光而不是靠描边表达;深度来自景深与大气透视,不来自投影或高光贴图;情绪是低照度纪录片的克制,不加任何风格化滤镜、渐变叠加或发光特效。
- **Image Rendering References**: corporate-photo

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 钝头黑体 / 方正、等宽感强、笔画末端平切,对住天场有分量 | SimHei | Arial | sans-serif |
| Body | 人文黑体 / 字面大、开口开,投影距离下可读 | Microsoft YaHei | Arial | sans-serif |
| Display | 钝头黑体放大 / 封面主词与章节大字,与 Title 同族但自成尺寸锚点 | SimHei | Arial | sans-serif |
| Year | 等宽定宽数字放大 / 时间轴与对比表上的年份标记,与 Data 同族但自成尺寸锚点 | Consolas | Consolas | monospace |
| Data | 等宽 / 定宽数字、等高衬线数码,排成仪表读数;所有外部事实数字、坐标轴、刻度、来源行都走这一族 | Consolas | Consolas | monospace |

- **Title stack**: `SimHei, Arial, sans-serif`
- **Body stack**: `Microsoft YaHei, Arial, sans-serif`
- **Display stack**: `SimHei, Arial, sans-serif`
- **Data stack**: `Consolas, Microsoft YaHei, monospace`
- **Year stack**: `Consolas, Microsoft YaHei, monospace`
- **Role rationale**: 增设 Data 一族是因为本片每一页都有外部事实数字、刻度或来源行(37 条 fact 全部带数字或日期),等宽定宽数字让跨页的读数纵向对齐、位数不跳动;这正是"仪表读数"这一身份的承重点,不是一次性装饰。另设 Year 40 是因为年份在 P03/P04/P05/P13/P14 五页反复出现且必须比普通数据标签更重,属于结构性复现角色,不能靠 Executor 的稀疏 display 例外承载。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Display(封面主词、章节大字) | 96 |
| Hero number(关键数字,Data 族) | 88 |
| Title(页面标题) | 52 |
| Subtitle | 40 |
| Year(时间轴/对比表年份,Data 族) | 40 |
| Lead(导入句) | 36 |
| Body | 30 |
| Annotation(标注、标签,Data 或 Body 族) | 22 |
| Data(坐标轴、刻度,Data 族) | 22 |
| Footnote(来源行,Data 族) | 18 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 先读标题(陈述句,一眼拿到主张)→ 再读页面上那一个被暖金标出的读数或焦点 → 最后读挂在仪器横梁上的结构与标注。中途加入的观众在两秒内应当拿到前两级。
- **Composition tendency**: 每页只允许一个主体占据画面主导,其余元素退成结构与标注。避免把要点平均分进等宽格子——这是本片最需要躲开的失败模式。天场是连续的,构图靠"在这片天上把东西放在哪儿"决定,而不是靠给内容加边框。
- **Cross-page continuity**: 那条仪器横梁(单条细水平基线)在需要挂载结构的页面上保持同一 y;地球与轨道环在 P06/P07/P09/P10 之间保持可辨认的同一身份与朝向,只改变被强调的那一层;来源行的位置与字号全片不变。封面、章节与收束页可以放掉横梁。
- **Spacing posture**: variable by page rhythm——anchor 页大幅留白让天场说话,dense 页把结构收紧到横梁附近,breathing 页只放一个对象加一行字。
- **Spacing anchors**: 页边距 72 px;块间距 32 px;分栏槽 40 px;圆角半径 0 px(直角,示意图与仪表台的语言);正文行高 1.6。

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 3
- **Brand-logo library**: 不使用(本片内容不涉及任何公司或产品品牌标识)

| Icon Path | Suitable Scenarios |
| --- | --- |
| `icons/tabler-outline/satellite.svg` | 卫星、星座、在轨对象 |
| `icons/tabler-outline/world.svg` | 全球服务、覆盖范围 |
| `icons/tabler-outline/clock.svg` | 授时、时延、时间基准 |
| `icons/tabler-outline/broadcast.svg` | 信号播发、无源接收 |
| `icons/tabler-outline/map-pin.svg` | 定位、位置解算结果 |
| `icons/tabler-outline/message.svg` | 短报文通信 |
| `icons/tabler-outline/ship.svg` | 渔业、海上应用 |
| `icons/tabler-outline/plane.svg` | 航空应用 |
| `icons/tabler-outline/tractor.svg` | 农业应用 |
| `icons/tabler-outline/bolt.svg` | 电力调度应用 |
| `icons/tabler-outline/device-mobile.svg` | 大众手机应用 |
| `icons/tabler-outline/route.svg` | 交通运输、导航路径 |
| `icons/tabler-outline/rocket.svg` | 发射、组网节点 |
| `icons/tabler-outline/target.svg` | 精度、指标 |
| `icons/tabler-outline/lifebuoy.svg` | 国际搜救、救灾减灾 |
| `icons/tabler-outline/link.svg` | 星间链路 |
| `icons/tabler-outline/antenna.svg` | 地面站、用户终端 |
| `icons/tabler-outline/radar.svg` | 监测、测控 |
| `icons/tabler-outline/mountain.svg` | 遮挡、低仰角环境 |
| `icons/tabler-outline/map.svg` | 服务区、区域覆盖 |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P05 | table | comparison_matrix | 三代北斗按同一组判据横向对比,让"每一步解决了上一步的什么问题"成为可读的网格 |
| P08 | chart | donut_chart | 30 颗卫星按三种轨道的构成比,中心承载总数 |
| P12 | chart | horizontal_bar_chart | 区域短报文与全球短报文的单次容量对比,长度差本身就是论据 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cover_orbit_earth.png | 2752x1536 | 16:9 | 封面主视觉的生成原片,仅用于派生,不直接上页 | Source | 原片保留完整画幅,不做任何页面构图承诺 | no-crop | ai | Generated | 从中地球轨道高度俯瞰的地球夜面弧线,大气层边缘一道极细冷蓝辉光,弧线上方是深空;左上大面积近黑安静区;画面右下一处极小暖金光点作为唯一暖色;无文字无界面无地名标注 | none | hero_page |
| cover_orbit_earth_fit.jpg | 1280x714 | 16:9 | 封面实际置入件:把观众直接放到"从轨道上看地球"的位置,给全片定下深空场 | Background | 整幅出血作底,地球弧线压在画面下缘偏右,上方三分之二留作近黑安静区承载主词与副题;不做卡片式插入 | adaptive | ai | Generated | Derived from cover_orbit_earth.png; treatment=fit 1280x720; | none | hero_page |
| scene_night_sea.png | 2752x1536 | 16:9 | P11 短报文场景的生成原片,仅用于派生,不直接上页 | Source | 原片保留完整画幅,不做任何页面构图承诺 | no-crop | ai | Generated | 夜间开阔海面上一艘小型渔船的远景剪影,驾驶舱一盏暖金小灯是画面唯一暖光源,海面反射极弱;天空占三分之二为深蓝到近黑;镜头远、景深浅、大气感强;无文字无船名无可辨认人脸 | none | local |
| scene_night_sea_fit.jpg | 1280x714 | 16:9 | P11 实际置入件:让"没有信号的地方还能发出一句话"这件事有真实的重量 | Illustration | 主体推到画面右侧下三分之一,左半保持近黑海面与夜空供叠标题与指标;与页面横梁在同一水平带上交接 | adaptive | ai | Generated | Derived from scene_night_sea.png; treatment=fit 1280x720; | none | local |
| app_scene_base.png | 2752x1536 | 16:9 | P13 应用场景的原始摄影底片,仅用于派生,不直接上页 | Source | 原片保留完整画幅,不做任何页面构图承诺 | no-crop | ai | Generated | 破晓前的沿海平原横向全景:远处港口塔吊与近处规整农田同处一个画面,几点冷白作业灯散布;天色是深蓝转灰的过渡;极低对比、极安静;无文字无品牌无可辨认人脸 | none | local |
| app_scene_muted.jpg | 1280x714 | 16:9 | P13 实际置入件:压暗去饱和后作为页面下缘的标签带底,让应用领域标签能直接叠在图上而不失可读性 | Illustration | 作为页面下缘的整幅横带(在 SVG 里原生裁出下半带),应用标签沿横带排布并与图中元素位置呼应;图本身退为质地,不与文字争 | adaptive | ai | Generated | Derived from app_scene_base.png; treatment=desaturate 0.7 + brightness 0.72 + fit 1280x720; | none | local |

## IX. Content Outline

### Part 1: 为什么是北斗

#### Slide 01 - 封面:从一颗星到全球组网

- **Audience move**: 刚走到屏幕前、不知道要看什么 → 知道这是关于北斗的片子,并被"一颗 → 30 颗"这个落差钩住。
- **Relationships**: 两个数量状态(2000 年的 1 颗试验星 / 2020 年的 30 颗组网星)构成时间上的 order 与量级上的 contrast;标题与副题是 parent-child。
- **Cover impact**: 钩子(binding)——"2000年10月31日,中国只有一颗试验星。二十年后,30颗。"这两个可核验的数字本身就是全片的悬念。
- **Composition**: 整幅深空图出血作底,主词占据左上大面积安静区;两个数字以 Data 族排成一行低位读数,中间用一道细线连接,暗示这是一条要走二十年的路。
- **Title**: 北斗:从一颗星到全球组网
- **Core message**: 二十年,从 1 颗到 30 颗——这条路是怎么走完的。
- **Content**: 主词"从一颗星到全球组网" · 副题"北斗卫星导航系统" · 低位读数行"2000-10-31 · 1颗试验星 → 2020-07-31 · 30颗全球组网"
- **Images**: cover_orbit_earth_fit.jpg 整幅作底
- **Fact IDs**: F003, F007, F008
- **Motion suggestion**: 主词先到位,随后那行低位读数自左向右显现,最后暖金落在"30颗"上——对应旁白说到"二十年后"的那一刻。
- **page_rhythm**: anchor

#### Slide 02 - 为什么必须自己建

- **Audience move**: 默认"有GPS就够了" → 理解卫星导航是基础设施,而基础设施必须自己能开、自己能关。
- **Relationships**: 定位/导航/授时三项能力是 membership(同属"时空基础设施"这一整体);四条建设原则(自主·开放·兼容·渐进)是并列 membership;"自主"与其余三条是 contrast(其余三条讲对外,自主讲对内)。
- **Composition**: 左侧一句官方定性作为 lead,右侧"自主 开放 兼容 渐进"八个字排成一列大字阵,暖金只落在"自主"上;定位/导航/授时三项以三个小图标加标签挂在页面横梁上。
- **Title**: 导航是基础设施,基础设施要自己能开
- **Core message**: 北斗的官方定性只有一句——着眼于国家安全和经济社会发展需要,自主建设运行;八字原则里,"自主"是其余三条的前提。
- **Content**: 定性引文(F001) · 定位/导航/授时三项能力 · 八字原则"自主 开放 兼容 渐进",自主=独立提供服务的能力(F026)
- **Fact IDs**: F001, F026
- **Motion suggestion**: 三项能力先挂上横梁,随后八字原则逐字落位,"自主"最后变暖金——与旁白念到"自主"同步。
- **page_rhythm**: dense

### Part 2: 三步走

#### Slide 03 - 三步走:路线定在三十年前

- **Audience move**: 以为北斗是最近几年才有的 → 知道这是1994年就定下的三阶段路线,每一步都有明确的服务范围。
- **Relationships**: 三步之间是严格的 order(一号→二号→三号)与 parent(同属一条"三步走"路线);三步的服务范围是逐级扩大的 link(中国→亚太→全球)。
- **Composition**: 建立本片的仪器横梁——一条贯穿页宽的细水平时间轴,三个节点等距落在轴上,每个节点上方是年份(Data 族),下方是服务范围;地球缩略图在轴的右端待命,此刻只画中国那一小段弧。这是 Morph 组 A 的起始状态。
- **Title**: 一条路线,三十年,分三步走
- **Core message**: 2000年底到中国、2012年底到亚太、2020年到全球——这不是走一步看一步,是1994年就定下的路线。
- **Content**: 三步走官方表述(F002) · 1994年北斗一号建设正式启动(F031) · 三个节点年份与服务范围
- **Fact IDs**: F002, F031
- **Motion suggestion**: 时间轴先画出,三个节点自左向右依次落位,与旁白逐个念出"第一步、第二步、第三步"同步;地球上的覆盖弧保持在"中国"这一段不动,留给下一页展开。
- **page_rhythm**: anchor

#### Slide 04 - 三步走:每一步解决了上一步的什么问题

- **Audience move**: 知道有三步 → 理解每一步的技术转折(从无到有 → 从有源到无源 → 全球组网靠星间链路),并记住收官那一天。
- **Relationships**: 三步之间是 order 与因果 link(前一步的限制是后一步要解决的问题);三个技术转折与三步是一一对应的 parent;五个精确日期挂在同一条轴上是 order。
- **Composition**: 承接 P03 的同一条时间轴(Morph 组 A 的终止状态):节点保持原位,但每个节点下方展开一行技术转折,地球上的覆盖弧从中国扩到亚太再扩到全球;轴的右端落一个暖金读数"18箭30星 / 两年半"。
- **Title**: 从有源到无源,再到全球组网
- **Core message**: 第一步解决"有没有",第二步解决"用户得自己发信号"这个限制,第三步用星间链路解决"全球组网要在全球布站"这个限制。
- **Content**: 2000-10-31首星、2003-05-25一号建成、2012-12-27区域服务(14星:5GEO+5IGSO+4MEO)、2020-06-23 09:43第55星提前半年、2020-07-31正式开通 · 有源→无源→双体制+星间链路 · 18箭30星两年半
- **Fact IDs**: F003, F004, F005, F006, F007, F019, F027, F032, F034, F035
- **Motion suggestion**: 与 P03 同一条轴做 Morph;覆盖弧分三段扩张,每一段对应旁白讲到的那一步;"18箭30星"最后落位,对应旁白的收束句。
- **page_rhythm**: dense

#### Slide 05 - 三代同框:同一组判据看下来

- **Audience move**: 三步的印象还是线性的时间 → 能在一张网格里横向比出三代在体制、星座、服务范围上的真实差别。
- **Relationships**: 三代系统是 comparison 的列,四条判据是行,交点是事实;"定位体制"一行三代之间是 order 与 contrast(有源 → 有源+无源 → 继承两种)。
- **Composition**: 页面主体让给一张三列四行的读数表,直角、无圆角、靠一条 1px 分隔线分栏;表底用 surface 抬起一层与天场分开;"定位体制"那一行用暖金标出,因为它是本页真正的论点。
- **Title**: 三代北斗,差别不在多了几颗星
- **Core message**: 三代之间最本质的差别是定位体制——有源、增加无源、两种都继承,星座规模只是这个差别的结果。
- **Content**: 表格行=建成时间/服务范围/定位体制/星座构成;列=北斗一号(2000年底·中国·有源·3颗GEO)、北斗二号(2012年底·亚太·兼容有源并增加无源·14颗=5GEO+5IGSO+4MEO)、北斗三号(2020·全球·继承两种体制+星间链路·30颗=3GEO+3IGSO+24MEO)
- **Visualization**: `three-generation-comparison` — 三代 × 四判据的纯文字网格表,使用 `table/comparison_matrix`。`Native-ready`: three-generation-comparison=yes
- **Fact IDs**: F002, F008, F031, F032, F034, F035
- **page_rhythm**: dense

### Part 3: 它怎么工作

#### Slide 06 - 三种轨道:为什么不是一种就够

- **Audience move**: 以为卫星都在"天上同一个地方" → 建立三层轨道的空间直觉,知道高轨与中轨的高度差是 14000 多公里。
- **Relationships**: 三类轨道是 membership(同属一个混合星座)且在高度上是 order(GEO/IGSO 同高 → MEO 更低);三类与"混合星座"是 parent。
- **Composition**: 全片的几何锚点在这里建立——地球置于画面左侧偏下,三条轨道以原生椭圆弧分层环绕,GEO 一条定点弧、IGSO 一条倾斜8字弧、MEO 一条更低更密的环;右侧以引出线标注三组高度与倾角(Data 族)。这是 Morph 组 B 的起始状态,地球与三条弧的位置、朝向在下一页保持不变。
- **Title**: 三种轨道,一个星座
- **Core message**: 北斗把三种轨道混在一个星座里,高轨卫星比别人多,所以在城市峡谷和低纬度这些最容易被挡住的地方反而更稳。
- **Content**: GEO 35786km、定点东经80/110.5/140度 · IGSO 35786km、倾角55度 · MEO 21528km、倾角55度、Walker24/3/1 · 高轨多=抗遮挡强、低纬优势明显(F020)
- **Fact IDs**: F008, F009, F020
- **Motion suggestion**: 地球先在位,三条轨道弧由外向内依次画出,与旁白逐条介绍同步;标注随对应的弧出现。
- **page_rhythm**: dense

#### Slide 07 - 每一层轨道在替你做什么

- **Audience move**: 知道有三层 → 知道每一层各自承担哪些服务,理解"轨道分工"不是几何趣味而是服务设计。
- **Relationships**: 每类轨道与其承担的服务是 parent-child;GEO 的三项服务之间是 membership;搜救的6颗 MEO 与 24 颗 MEO 是 overlap(子集关系);全球服务与区域服务是 contrast(覆盖范围不同)。
- **Composition**: 承接 P06 的同一张几何图(Morph 组 B 的终止状态):地球与三条弧保持原位,三条引出线从各自的弧延伸到右侧,展开成三组服务清单;当前被讲到的那一层用暖金点亮,其余两层退为 divider 色。
- **Title**: 每一层轨道都在替你做一件具体的事
- **Core message**: 三颗 GEO 管中国周边的高精度与区域短报文,MEO 管全球定位并有6颗带搜救载荷,IGSO 和 MEO 一起用星间链路把搜救回执送回来。
- **Content**: GEO×3 → 星基增强、精密单点定位(PPP-B2b)、区域短报文 · MEO×24 → 全球定位导航授时,其中6颗带搜救载荷 · IGSO×3+MEO×24 → 搜救返向链路(星间链路支持) · 区域服务区=东经75–135度、北纬10–55度
- **Fact IDs**: F016, F017, F018, F036
- **Motion suggestion**: 与 P06 同一组几何做 Morph;三组服务清单按旁白讲述顺序依次接入,同时对应的轨道弧变暖金、上一层熄灭——一次只亮一层。
- **page_rhythm**: dense

#### Slide 08 - 30颗怎么分

- **Audience move**: 对三层轨道有了功能理解 → 拿到确切的数量分配,把"30颗"这个封面数字落实。
- **Relationships**: 三类卫星数量是 part-to-whole(同属30颗总数),三者之间是数量 contrast(24 与 3、3 的悬殊)。
- **Composition**: 页面中央一个大环形图,中心留空承载暖金的"30";三段弧按 24/3/3 分配,MEO 那段用 primary,GEO 与 IGSO 用 secondary accent 与 divider 区分;右侧一列极简图例带数量。整页只做这一件事,是 P06/P07 密集之后的呼吸页。
- **Title**: 30颗,24颗在中圆轨道上
- **Core message**: 全球定位的活主要由 24 颗 MEO 干,GEO 和 IGSO 各 3 颗,负责的是中国周边那些别人没有的服务。
- **Content**: MEO 24颗 · GEO 3颗 · IGSO 3颗 · 合计30颗 · 两年半18箭30星完成部署
- **Visualization**: `constellation-composition` — 30颗按轨道类型的构成环形图,使用 `chart/donut_chart`。`Native-ready`: constellation-composition=yes
- **Fact IDs**: F008, F019
- **page_rhythm**: breathing

#### Slide 09 - 它是怎么知道你在哪儿的

- **Audience move**: 把定位当黑箱 → 理解定位就是"量距离 + 交会",并知道为什么需要不止三颗星。
- **Relationships**: 卫星、距离、交会点三者是因果 link(测距 → 球面 → 交会);三颗星与第四颗星是 contrast(前者定位置,后者定时间);无源体制与有源体制是 contrast(是否需要用户发信号)。
- **Composition**: 页面中央一个地面接收点,四颗卫星分布在上方不同方位,每颗向接收点画一条细实线(测距)并带一段圆弧(等距球面的剖面);交会区域此刻还是一片较大的模糊区。这是 Morph 组 C 的起始状态。注:本页讲的是通用卫星导航原理,官方文本中未检索到可直接引用的整句,因此**本页不设来源行**,也不放任何需要出处的数字。
- **Title**: 量四个距离,解四个未知数
- **Core message**: 卫星报时间,你算距离;三个距离定住位置,第四个距离用来消掉你手表的误差——而你什么都不用发。
- **Content**: 信号里带发射时刻 → 接收端算传播时间 → 得到距离 · 三个距离交会出位置、第四个解算钟差 · 无源:用户不用发射信号,只靠接收就能定位(这正是北斗二号那一步的意义)
- **Mathematical content**: (x-x_i)^2+(y-y_i)^2+(z-z_i)^2=(c\,(t_r-t_i)-c\,\delta t)^2,\quad i=1,2,3,4
- **Fact IDs**: F028, F034
- **Motion suggestion**: 卫星与测距线逐颗接入(一、二、三、四),每接入一颗交会区收缩一点——与旁白数到第几颗严格对齐。
- **page_rhythm**: dense

#### Slide 10 - 能准到什么程度

- **Audience move**: 知道原理 → 拿到官方公开的量化指标,并理解"9米"是全球平均的95%统计值而不是营销数字。
- **Relationships**: 四项指标(定位/测速/授时/可用性)是 membership(同属公开服务性能规范);全球平均与最差位置是 contrast;每项指标与其约束条件(95%置信度)是 parent-child。
- **Composition**: 承接 P09 的几何(Morph 组 C 的终止状态):四条测距线收束,交会区坍缩成一个明确的点,并在该点旁拉出一把刻度尺;四项指标以 Data 族大号读数横排在仪器横梁上,每个读数下方一行极小的来源行。
- **Title**: 水平9米,授时20纳秒——而且写在公开规范里
- **Core message**: 这些不是宣传口径,是《公开服务性能规范(3.0版)》里带约束条件的指标,任何人都可以去核。
- **Content**: 水平定位≤9米、垂直≤10米(全球平均,95%) · 测速≤0.2米/秒 · 授时≤20纳秒 · 定位服务可用性全球平均≥99% · 最差位置水平≤15米、垂直≤22米 · 空间信号精度SISRE≤2米
- **Fact IDs**: F010, F011, F012, F013, F025
- **Motion suggestion**: 与 P09 同一组几何做 Morph,交会区坍缩为点;四项读数随旁白逐项点亮,数字用暖金。
- **page_rhythm**: dense

### Part 4: 它独有的一件事

#### Slide 11 - 短报文:能回话的导航

- **Audience move**: 认为导航就是"告诉我在哪儿" → 知道北斗还能把一句话发出去,而且这是第一步就设计好的独创。
- **Relationships**: "定位"与"通信"是本页的核心 contrast,又在北斗里被 link 成一体;北斗一号的双向短报文与北斗三号的短报文服务是 order(继承关系)。
- **Composition**: 夜海渔船图占据页面下三分之二并向右出血,左上近黑区承载标题与主张;一条自船向上的极细信号线穿过标题区,把图与文缝在一起;右下角一行小指标读数。
- **Title**: 没有信号的地方,它还能替你发出一句话
- **Core message**: 别的导航系统只告诉你"你在哪儿";北斗从第一颗星起就把通信和导航做成了一体——官方原话:这是北斗的独创。
- **Content**: 北斗一号即设计双向短报文,通信与导航一体化是北斗独创(F033) · 成功率≥95%、时延平均优于2秒、频度平均1次/30秒 · 无源定位导航授时免费,短报文需经运营商注册
- **Images**: scene_night_sea_fit.jpg 作为本页主体图
- **Fact IDs**: F014, F029, F033
- **Motion suggestion**: 图先在位,标题落下,最后那条信号线自船体向上生长——与旁白说到"发出一句话"同步。
- **page_rhythm**: dense

#### Slide 12 - 一次能发多少字

- **Audience move**: 知道能发消息 → 拿到确切容量,并理解区域与全球两种短报文是不同量级的两件事。
- **Relationships**: 区域短报文与全球短报文是 contrast(容量差 25 倍)且是 membership(同属短报文服务);比特与汉字是同一事实的两种口径(link)。
- **Composition**: 两条横向长条,长度严格按 14000 : 560 的真实比例画——差距本身就是论据,不做任何压缩或断轴;上条区域、下条全球,条末各接一个汉字数读数;下方一行注明区域服务区范围。
- **Title**: 区域1000个汉字,全球40个
- **Core message**: 在中国及周边,一次能发1000个汉字;在全球任意位置,一次40个汉字——都够把一件事说清楚。
- **Content**: 区域短报文单次≤14000比特(1000个汉字) · 全球短报文单次560比特(40个汉字) · 区域服务区=东经75–135度、北纬10–55度 · 两者比例约25:1
- **Visualization**: `short-message-capacity` — 区域与全球单次报文容量的横向条形对比(单位比特),使用 `chart/horizontal_bar_chart`。`Native-ready`: short-message-capacity=yes
- **Fact IDs**: F014, F015, F017
- **page_rhythm**: breathing

### Part 5: 今天与明天

#### Slide 13 - 它已经在你身边

- **Audience move**: 觉得北斗是"国家的事" → 知道自己口袋里的手机就在用北斗,并看到它已经是一个近六千亿的产业。
- **Relationships**: 八个应用领域是 membership;"你的手机"与"国家基础设施"是 contrast 但被同一系统 link;产业总产值与核心/关联产值是 part-to-whole。
- **Composition**: 页面下缘一条压暗去饱和的破晓平原横带作为质地,八个领域以图标加标签沿横带排布并与图中元素位置呼应;上方留给一个暖金 hero number——98%,以及那句"你手机里就有"。
- **Title**: 98%的国产手机里,已经有北斗
- **Core message**: 北斗不是遥远的国家工程——2024年国内约2.88亿部智能手机支持北斗定位,占比98%,你今天用地图的时候大概率就在用它。
- **Content**: 交通运输/农林渔业/水文监测/气象测报/通信授时/电力调度/救灾减灾/公共安全八大领域(F021) · 2.88亿部手机支持北斗、占比98%(F023) · 2024年产业总产值5758亿元,同比增长7.39%;核心产值1699亿元、关联产值4059亿元(F022)
- **Images**: app_scene_muted.jpg 作为页面下缘横带质地
- **Fact IDs**: F021, F022, F023
- **Motion suggestion**: 八个领域图标沿横带自左向右依次出现,与旁白逐项带过;"98%"最后落位并变暖金。
- **page_rhythm**: dense

#### Slide 14 - 下一步:2035

- **Audience move**: 拿到了完整的过去与现在 → 知道这条路还在往前走,并且拿到可以自己去核对的来源。
- **Relationships**: 三步走与"下一步"是 order(第四阶段);2035 目标的三个定语(更加泛在/更加融合/更加智能)是 membership;四个来源与全片事实是 parent-child(出处关系)。
- **Closing impact**: 收束句(binding)——"从一颗试验星到30颗组网星用了二十年;下一个二十年,这台仪器要变成一整套时空体系。"
- **Composition**: 天场恢复到封面的空旷,P03 建立的那条时间轴最后一次出现并向右延伸出画面,末端标 2035;下方一条极细的来源带,四个来源名各自带原生超链接。
- **Title**: 下一步,到2035年
- **Core message**: 计划是到2035年建设完善更加泛在、更加融合、更加智能的国家综合时空体系——北斗从"一个导航系统"走向"一套时空体系"。
- **Content**: 2035年国家综合时空体系,三个定语(F037/F024) · 收束句 · 来源带:中国卫星导航系统管理办公室官网、《北斗卫星导航系统公开服务性能规范(3.0版)》2021、国务院新闻办《新时代的中国北斗》白皮书2022、《2025中国卫星导航与位置服务产业发展白皮书》(经新华网)
- **Hyperlinks**: "中国卫星导航系统管理办公室官网" → `http://www.beidou.gov.cn/xt/xtjs/`;"公开服务性能规范(3.0版)" → `http://www.beidou.gov.cn/xt/gfxz/202105/P020210526215541444683.pdf`;"《新时代的中国北斗》白皮书" → `https://www.gov.cn/zhengce/2022-11/04/content_5724523.htm`;"2024年产业产值(新华网)" → `http://www.news.cn/politics/20250518/c81eaecabddd4ca79ffcfb1cb1ade4a7/c.html`
- **Fact IDs**: F024, F037
- **Motion suggestion**: 时间轴自 P03 的三个节点延伸出第四段并淡出画面右缘;来源带最后整体淡入,不参与强调。
- **page_rhythm**: anchor

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 备注即本片的逐字旁白脚本,由本方案在页面 roster 定稿并通过 Gate 2 之后、SVG 动笔之前一次性写入 `notes/total.md`(`# Slide N` + `---`),作为页面设计的输入而不是事后补写的解说。脚本按场景切分,一场景一段,每段只讲这一页能看见的东西;页面上出现而脚本没讲的主张,改页面或回到规划,不许事后改脚本凑画面(video-design §4)。脚本为本方案自撰(非用户提供的 final/literal script),因此允许在终检后、合成音频之前做一次基于最终 SVG 的校订。每个外部事实在旁白中口语化复述时,页面上必须有对应的来源行。
- **Total duration**: 全片 5–7 分钟;14 个场景,平均每段约 90–130 字(按中文播音约 4.5 字/秒估算),封面与收束段偏短。
- **Notes style**: 讲解式口语,陈述句为主,不用"大家好""让我们一起"这类主持腔;数字念完整(如"三万五千七百八十六公里"),年份念"二〇二〇年七月三十一日";每段最后一句留一个向下一场景的推进,但不说"下一页"。
- **Presentation purpose**: 见 §I Communication Intent——先讲清为什么必须自己建,再用时间线讲三步走,然后讲透三种轨道、定位原理与短报文,最后落到身边应用与2035。
