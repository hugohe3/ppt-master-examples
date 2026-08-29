<!-- ppt-master-schema: design-spec/v1 -->
# 什么是 PPT - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | 什么是 PPT |
| Canvas Format | PPT 16:9 (1280×720) |
| Page Count | 17 |
| Target Audience | 需要制作或评审演示文稿的知识工作者、学生与职场人——他们会用 PowerPoint，但大多把 PPT 只当成"做几页幻灯片"，缺少对这一媒介本质的系统认知 |
| Communication Intent | 系统性地讲清"PPT 到底是什么"：它同时是沟通媒介、可编辑文档、传递载体和原生文件结构；解释人们为什么做演示、何时该用/不该用 PowerPoint、什么是好 PPT，并纠正"PPT=漂亮几页图"的常见误解 |
| Desired Audience Outcome | 看完后能区分"PPT"的几种含义、理解 PowerPoint 原生对象模型、判断某个任务是否真的适合用演示文稿，并在下次做 PPT 前先问对关键问题 |
| Core Message / Ask / Action | PPT 不是一叠静态页面，而是有顺序、模块化、可编辑并需要持续流转的沟通产物——先想清楚受众要完成什么任务，工具才服务沟通 |
| Delivery Context | 既可作为讲解式科普演示（有主讲），也适合独立阅读；单次约 15-20 分钟 |
| Artifact Afterlife | 作为理解 PPT 本质的参考资料、培训讲义与团队入门读物长期复用 |
| Reading Mode | balanced |
| Content Strategy | balanced 默认：在忠实源文档全部事实与关系的前提下，将十节内容重构为"解构→重构→方法"三幕叙事，可重组、提炼、补足过渡，但不引入源材料之外的新事实 |
| Design Style | 自定义"蓝图×编辑"：editorial 杂志栅格与层级为底，讲结构/对象模型的页面叠加 blueprint 示意线稿与标注语汇；墨蓝暖纸浅色场，红色作单一强调 |
| Formula Policy | text-only |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Created Date | 2026-07-24 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 上下左右安全边距 40px |
| Content Area | 1200 × 640（安全区，起点 40,40） |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Visual style**: custom
- **Theme**: 技术编辑体——把"PPT 是有结构的原生包"这一核心隐喻贯穿版式：正文区是清晰的杂志栅格，结构区是精细的工程蓝图示意
- **Tone**: 清晰、理性、可信，有工程质感而不冰冷；克制的编辑红只标记结构与强调
- **Mode References**: instructional, pyramid
- **Mode Behavior**: 三幕结构。第一幕"解构"先拆解"PPT"被混用的多重含义、制造认知张力（原来我们一直在说不同的东西）；第二幕"重构"逐层重建——从沟通媒介到对象模型到模板，用 instructional 的概念分解逐页只讲一个概念、平行展开可比；每个关键页用 pyramid 的结论先行，标题即断言。第三幕"方法"落到"每次做 PPT 该问的问题"，把认知转成可执行的方法闭环。
- **Visual Style References**: editorial, blueprint
- **Visual Style Behavior**: 在 editorial 的杂志栅格、细分隔线、眉题（kicker）→标题→引言→正文的强纵向层级基础上，为讲"结构/对象模型"的页面叠加 blueprint 的示意线稿与标注语汇——细单色线框、等距/等轴示意、尺寸标注线、引线箭头、坐标/代号标签、极低透明度网格背景。正文区保持编辑体清晰留白；结构图区让线稿在浅场上呼吸。单一编辑红作强调色，遵循工程图"一个高亮色"的惯例。

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #FFFFFF | 主页面底色，杂志白场 |
| Secondary background | #F4F1EA | 暖纸副底：侧栏、面板、结构图衬底、引用块 |
| Primary | #1A2B4A | 墨蓝：标题、蓝图线稿主色、主要文字结构、边框 |
| Accent | #C8102E | 编辑红：单一强调、关键路径、当前项、分隔强调标记 |
| Secondary accent | #5E7089 | 次级蓝灰：眉题、次要标注、辅助线、图注 |
| Body text | #22262B | 正文近黑，长文可读 |

### AI Image Strategy

- **Image Rendering**: custom
- **Visual**: 技术蓝图线稿融合杂志信息图：细的示意线条+等距结构+少量实色块与标注
- **Mood**: 清晰、理性、有工程质感，像一份被精心排版的技术说明
- **Image Rendering Behavior**: 以 blueprint 的示意线稿、网格与标注为骨架，叠加 editorial 信息图的实色区块与层级排版；crisp 单一线宽（约 1.5px 观感）、直角与精确曲线，元素简化为示意形态（框、连接线、锚点、代号标记），可选极低透明度（5-8%）网格衬底；线条精细、无照片、无渐变噪点、无材质阴影。图像色彩全部继承演示色板：墨蓝 #1A2B4A 作线稿主色，编辑红 #C8102E 作单一高亮，白/暖纸 #F4F1EA 作场，蓝灰 #5E7089 作次级线。用于把抽象概念画成"可读的结构图"。
- **Image Rendering References**: blueprint, editorial

## IV. Typography System

### Font Plan

| Role | Chinese | English | Fallback tail |
| --- | --- | --- | --- |
| Title | Microsoft YaHei | Arial | sans-serif |
| Body | Microsoft YaHei | Consolas | monospace |

- **Title stack**: `"Microsoft YaHei", Arial, sans-serif`
- **Body stack**: `"Microsoft YaHei", Consolas, monospace`

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 42 |
| Subtitle | 32 |
| Annotation | 18 |
| Footnote | 16 |

## V. Layout Principles

### Page Structure

- **Header area**: 顶部 40-96px 区，眉题（kicker，蓝灰小字/代号）+ 主标题（断言式）；标题下可选一条墨蓝细分隔线或半幅规则线
- **Content area**: 杂志栅格，优先非对称 2:1 / 3:7 分栏与竖向规则线悬挂内容；结构页让蓝图示意图作骨架，正文/标注挂在引线与栅格上
- **Footer area**: 底部左侧页码代号（如 `P07 / 17`），右侧来源行（Footnote，蓝灰）；两者用 Footnote 尺寸

### Spacing Specification

| Element | Current Project |
| --- | --- |
| Safe margin | 40px |
| Content block gap | 24-32px |
| Icon-text gap | 12px |

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Brand-logo library**: none

| Purpose | Icon Path | Page |
| --- | --- | --- |
| 软件/应用 | icons/tabler-outline/app-window.svg | P02 |
| 演示活动 | icons/tabler-outline/presentation.svg | P02, P08 |
| 有序文档/Deck | icons/tabler-outline/stack-2.svg | P02 |
| 幻灯片放映 | icons/tabler-outline/player-play.svg | P02 |
| 数字文件包 | icons/tabler-outline/file-zip.svg | P02, P11 |
| 转化/意图 | icons/tabler-outline/transform.svg | P04 |
| 目标结果 | icons/tabler-outline/target.svg | P04, P16 |
| 告知 | icons/tabler-outline/info-circle.svg | P05 |
| 解释 | icons/tabler-outline/bulb.svg | P05, P08 |
| 说服 | icons/tabler-outline/speakerphone.svg | P05 |
| 决策 | icons/tabler-outline/checkbox.svg | P05 |
| 对齐 | icons/tabler-outline/users-group.svg | P05 |
| 教学 | icons/tabler-outline/school.svg | P05 |
| 汇报问责 | icons/tabler-outline/report.svg | P05 |
| 动员 | icons/tabler-outline/flag.svg | P05 |
| 留档交接 | icons/tabler-outline/archive.svg | P05 |
| 顺序 | icons/tabler-outline/list-numbers.svg | P06 |
| 模块化 | icons/tabler-outline/layout-grid.svg | P06 |
| 多媒体组合 | icons/tabler-outline/photo.svg | P06 |
| 演讲支持 | icons/tabler-outline/microphone.svg | P06, P09 |
| 阅读支持 | icons/tabler-outline/book.svg | P06, P09 |
| 可编辑 | icons/tabler-outline/edit.svg | P06, P16 |
| 组织可移植 | icons/tabler-outline/transfer.svg | P06 |
| 文档/报告 | icons/tabler-outline/file-text.svg | P07 |
| 电子表格 | icons/tabler-outline/table.svg | P07 |
| 白板画布 | icons/tabler-outline/layout-board.svg | P07 |
| 视频 | icons/tabler-outline/movie.svg | P07, P09 |
| Web 应用 | icons/tabler-outline/browser.svg | P07 |
| 混合场景 | icons/tabler-outline/arrows-shuffle.svg | P09 |
| Theme 主题 | icons/tabler-outline/palette.svg | P11, P12 |
| Slide Master 母版 | icons/tabler-outline/template.svg | P11, P12 |
| Slide Layout 版式 | icons/tabler-outline/layout.svg | P11, P12 |
| Placeholder 占位符 | icons/tabler-outline/rectangle.svg | P11 |
| Slide 幻灯片 | icons/tabler-outline/square.svg | P11 |
| Notes 备注 | icons/tabler-outline/notes.svg | P11 |
| 包关系 | icons/tabler-outline/link.svg | P11 |
| 事实层 | icons/tabler-outline/checklist.svg | P13 |
| 沟通层 | icons/tabler-outline/message-2.svg | P13, P16 |
| 叙事层 | icons/tabler-outline/route.svg | P13 |
| 认知层 | icons/tabler-outline/brain.svg | P13, P14 |
| 视觉层 | icons/tabler-outline/eye.svg | P13, P16 |
| 原生运行层 | icons/tabler-outline/settings.svg | P13 |
| 提问 | icons/tabler-outline/help-circle.svg | P16 |
| 受众 | icons/tabler-outline/users.svg | P16 |
| 核心信息 | icons/tabler-outline/bulb.svg | P16 |
| 复用重复 | icons/tabler-outline/refresh.svg | P16 |

## VII. Visualization Reference List

（无 catalog 图表引用；本演示的可视化均为自定义结构图与信息版式，见 §IX 各页 Layout。）

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Layout pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cover_identities.jpg | 1280×720 | 16:9 | 封面主视觉：把"PPT 的多重身份"做成概念隐喻 | AI Illustration | #73 Full-bleed poster image + side title stack | adaptive | ai | Generated | 一个中心的演示页/文档对象，向外裂解并展开为多个等距示意面板与线框，隐喻同一件东西同时是软件、活动、文档、放映与文件包；蓝图线稿+少量实色块，构图右侧留出安置标题的平静区 | none | hero_page |
| five_meanings.jpg | 960×720 | 4:3 | "PPT 的五种含义"概念插图 | AI Illustration | #3 Right-third image + left text body | adaptive | ai | Generated | 一个"PPT"符号向右侧散射为五片各异的示意面板（应用窗口、演讲台、有序页堆、播放三角、文件包），每片风格统一但形态不同，蓝图信息图质感 | none | local |
| object_model.jpg | 1280×720 | 16:9 | PowerPoint 原生对象模型：包结构等距爆炸图 | AI Illustration | #41 Background image + measurement lines and module tags (engineering overlay) | adaptive | ai | Generated | 一个演示文稿包的等距（isometric）爆炸分层示意：自上而下 Theme、Slide Master、Slide Layout、Slide 等薄平面依次错落堆叠，用引线连接层与层；纯蓝图线稿、等距投影、极低透明度网格底，一处编辑红高亮当前层，无任何文字 | none | hero_page |
| quality_layers.jpg | 720×900 | 4:5 | "什么是好的 PPT"的六层质量剖面 | AI Illustration | #3 Right-third image + left text body | adaptive | ai | Generated | 一个纵向分层的剖面/堆叠示意：自下而上六个薄层依次收窄（事实→沟通→叙事→认知→视觉→原生运行），像一份工程剖面图，蓝图线稿+每层一个细实色块，无文字 | none | local |
| ppt_is_not.jpg | 800×800 | 1:1 | "PPT 不是什么"对照概念图 | AI Illustration | #2 Left-third image + right text body | adaptive | ai | Generated | 对照示意：左边一叠装饰化、互不相连的扁平页面被一条编辑红斜线否定；右边同样的内容被组织成有引线连接的结构化包，形成"扁平图片 vs 有结构的产物"的对比，蓝图线稿风格，无文字 | none | local |

## IX. Content Outline

### Part 1: 解构——我们说的"PPT"其实不是一回事

#### Slide 01 - 封面：什么是 PPT？

- **Audience move**: 从"PPT 不就是做几页幻灯片吗"→ 被"它其实同时是四五种不同的东西"这一悬念抓住，愿意重新认识
- **Cover impact**: 钩子＝把日常最熟悉却最被低估的对象陌生化——"PPT" 三个字母同时指代软件、活动、文档、放映与文件包；构图策略＝#73 全幅蓝图主视觉（同一演示对象裂解展开为多个等距面板）+ 右/左侧悬浮标题栈
- **Layout**: 全幅 AI 主视觉作场（cover_identities.jpg），左下或右侧安置标题栈：眉题 `WHAT IS PPT · 演示文稿本质` + 巨号主标题"什么是 PPT？" + 一行副题；必要处加两段式 scrim 保证标题可读；底部一行来源/署名小字
- **Title**: 什么是 PPT？
- **Core message**: PPT 远不止一叠静态页面——先看清它到底是什么
- **Content**: 主标题"什么是 PPT？"；副题"它同时是沟通媒介、可编辑文档、传递载体和原生文件结构——不只是几页图"；眉题 `WHAT IS PPT`；底部小字"面向理解演示文稿本质 · 基于 Microsoft、ECMA-376 与沟通/认知研究"
- **Images**: cover_identities.jpg（#73 + 两段式 scrim/#29，标题作 SVG #65）

#### Slide 02 - "PPT"同时指五种不同对象

- **Audience move**: 从把"PPT"当一个词混用 → 能清楚区分它至少五种含义，意识到讨论前需要先对齐指代
- **Layout**: #3 右侧 four:three 概念插图（five_meanings.jpg，约占右 38%），左侧竖向规则线悬挂五行含义清单；每行＝tabler-outline 图标 + 含义名（PowerPoint / Presentation / Deck / Slide show / PPT/PPTX 文件）+ 一句定义；顶部眉题 `01 · 一个混合概念`
- **Title**: 说"PPT"时，我们其实在说五种不同的东西
- **Core message**: 日常语境里的"PPT"是混合概念，至少要区分软件、活动、文档、放映与文件包五层含义
- **Content**: 五行含义（逐字自源表）：PowerPoint＝Microsoft 提供的创作、编辑、演示与协作软件；Presentation＝一次包含信息、受众、传递场景和预期结果的沟通活动；Deck＝在活动前中后使用的有序、可编辑演示文档；Slide show＝被现场演示或自动播放的页面序列，可含转场、动画、旁白、视频与计时；PPT/PPTX 文件＝保存页面、可复用结构、媒体、备注、批注、关系与演示行为的数字包。底部一句提示"本演示中，PPT 指 PowerPoint 这一类演示文稿产物及其沟通用途，不只是旧版 .ppt 扩展名"。来源：Microsoft PowerPoint 简介
- **Images**: five_meanings.jpg（#3，图标与文字为 SVG）

#### Slide 03 - 常见文件类型与背后的标准

- **Audience move**: 从"只知道 .ppt/.pptx" → 能分清五种扩展名各自用途，并知道现代 .pptx 是有标准的 OOXML 包
- **Layout**: 左侧 3:7 主区做一个五行扩展名表（等宽代号列 + 用途列，编辑体细分隔线）；右侧窄栏做一个"标准"侧注卡（暖纸底）：OOXML / ECMA-376 / ISO/IEC 29500；顶部眉题 `01 · 文件类型`
- **Title**: 五种扩展名，一个现代标准
- **Core message**: 现代 .pptx 不是一块二进制黑箱，而是标准化的 Office Open XML 包
- **Content**: 表：`.ppt`＝PowerPoint 97–2003 旧版二进制演示文稿；`.pptx`＝当前无宏演示文稿包，现代主要可编辑格式；`.pptm`＝含宏演示文稿；`.potx`＝可复用模板；`.ppsx`＝打开即进入放映视图的放映文件。侧注：现代 `.pptx` 是 Office Open XML 包，其词汇与打包方式由 ECMA-376 / ISO/IEC 29500 标准化。来源：Microsoft 文件格式说明、ECMA International

### Part 2: 重构——把 PPT 建成一个完整的心智模型

#### Slide 04 - 人们为什么做演示

- **Audience move**: 从"做 PPT＝产出几页" → 理解真正目的是改变受众所知/所信/所决/所行，并留下可复用记录
- **Layout**: 上部横向"转化链"流程带（源材料+意图 →有顺序的论证 →共同视觉体验 →受众结果 ＋可编辑可传播记录），用蓝图引线箭头串联的四/五个节点；下部一行结论句；#8 或流程节点样式，节点用 SVG 绘制；眉题 `02 · 目的`
- **Title**: 人们要的不是"几页"，是受众身上发生的改变
- **Core message**: 演示的终点是受众结果加一份组织可继续使用的记录，页面只是手段
- **Content**: 转化链（逐字自源 code 块）：源材料 + 意图 → 有顺序的论证或解释 → 共同的视觉体验 → 受众结果 ＋ 可编辑、可传播的记录。一句话点题："人们通常不以'得到一些页面'为最终目的，而是希望改变受众所知道、理解、相信、决定或采取的行动。"
- **Images**: 无（纯 SVG 流程）

#### Slide 05 - 演示要完成的沟通任务

- **Audience move**: 从"演示就是讲一讲" → 能说出九类具体沟通任务，并理解一份 deck 可同时承担多种、需分清主导结果与顺序
- **Layout**: 3×3 平行卡片网格（instructional 平行展开），每卡＝tabler-outline 图标 + 任务名 + "演示结束后希望发生的变化"一句；网格下一条窄结论带；眉题 `02 · 沟通任务`
- **Title**: 一份演示，可能同时在完成九种任务
- **Core message**: 告知/解释/说服/决策/对齐/教学/汇报/动员/留档——真正要澄清的不是哪个标签胜出，而是它们的主次与顺序
- **Content**: 九卡（逐字自源表）：告知＝受众知道此前不知道的事实；解释＝理解某种机制、关系或原因；说服＝接受或认真考虑某个立场；决策＝群体从多个选项走向明确选择；对齐＝形成共同优先级、语言和下一步；教学＝学习者能理解、记忆或执行；汇报与问责＝评价进展、证据、风险和责任；动员＝从意识到问题转向采取行动；留档与交接＝获得可审批、可审计、可复用的正式成果。结论带："一份 deck 可同时承担多种任务；关键是它们如何互相支撑、按什么顺序发生。"来源：Yates & Orlikowski《组织沟通类型》
- **Images**: 无

#### Slide 06 - 为什么用 PowerPoint，而不是别的媒介

- **Audience move**: 从"习惯性打开 PowerPoint" → 理解它在七项属性同时被需要时才有独特价值
- **Layout**: 七项属性做非对称清单/小卡（左窄图标列 + 右属性名 + 价值句），或 2 列×3-4 行；每项 tabler-outline 图标；顶部一句"当一项任务同时需要下列属性时，PowerPoint 具有独特价值"；眉题 `02 · 媒介价值`
- **Title**: 顺序 × 模块化 × 多媒体 × 演讲 × 阅读 × 可编辑 × 可移植
- **Core message**: PowerPoint 的独特价值来自这七项属性的叠加，而非任何单一属性
- **Content**: 七项（逐字自源表）：顺序＝控制或建议注意力展开顺序；模块化＝页面可重排、隐藏、复制、替换、复用；多媒体组合＝文字/图示/数据/图片/音频/视频在页内组合，动画呈现变化、转场连接页面；演讲支持＝备注、演讲者视图、计时、导航支持现场传递；阅读支持＝阅读视图、批注、备注页、讲义、共享支持异步审阅；可编辑性＝可修改、本地化、扩展、改作他用；组织可移植性＝同一产物穿过会议、评审、审批、归档、复用环节
- **Images**: 无

#### Slide 07 - 何时不该用 PowerPoint

- **Audience move**: 从"什么都做成 PPT" → 能按首要需求判断某任务更适合文档、表格、白板、视频还是 Web 应用
- **Layout**: 对照表：左列"首要需求"、右列"通常更适合的主要媒介"，共六行；每行右侧配对应媒介的 tabler-outline 图标；末行"有顺序、可视化、可编辑并需继续流转的沟通 → PowerPoint"用编辑红高亮；眉题 `02 · 媒介边界`
- **Title**: PowerPoint 不该是所有信息任务的默认选择
- **Core message**: 媒介选择由场景决定——问"这个任务是否需要一份有顺序、模块化、可编辑的演示文稿产物"，而不是"能不能做成几页 PPT"
- **Content**: 对照（逐字自源表）：很长、线性、可独立阅读的完整论证→文档或报告；动态数据的实时探索→电子表格/Notebook/仪表盘；开放式群体探索→白板或协作画布；不需编辑的固定重复播放→视频；交互导航和丰富用户输入→Web 应用；有顺序、可视化、可编辑并需继续流转的沟通→PowerPoint（高亮）
- **Images**: 无

#### Slide 08 - 一份 PPT 有不止一种生命

- **Audience move**: 从"deck＝开会那一刻用的东西" → 理解它在活动前/中/后及无现场活动时承担不同作用
- **Layout**: 四阶段时间带/四栏（活动前 →活动中 →活动后 →没有现场活动），每栏＝阶段名 + deck 的作用一句 + 图标；下方一句 PowerPoint 提供多种视图的说明；眉题 `02 · 生命周期`
- **Title**: 同一份 deck，在不同阶段扮演不同角色
- **Core message**: deck 会在生命周期里从思考工具变成共同界面、再变成记录与复用来源，设计要为主要角色服务
- **Content**: 四阶段（逐字自源表）：活动前＝思考、综合、评审、排练工具；活动中＝协调注意力与节奏的共同视觉界面；活动后＝阅读副本、决策记录、讲义、审批材料或复用来源；没有现场活动＝异步阅读、录制、旁白或自动播放的演示内容。补充："PowerPoint 提供编辑、放映、演讲者、阅读、备注、讲义、母版等不同视图——现场用带私有备注的演讲者视图，无讲者时用阅读视图。"来源：Microsoft 选择正确视图
- **Images**: 无

#### Slide 09 - 传递场景会改变设计

- **Audience move**: 从"同一页能应付所有场合" → 理解演讲主导/读者主导/混合/录制四种场景要优化的东西不同，必须先定主要场景
- **Layout**: 四卡或 2×2：演讲者主导 / 读者主导 / 混合场景 / 录制或自动播放，每卡＝图标 + 场景名 + "应优化的内容"；卡下一句强约束提示；眉题 `02 · 传递场景`
- **Title**: 一页无法同时最优地服务四种传递场景
- **Core message**: 必须先明确主要传递场景，再决定信息密度与字体——稀疏的演讲页当不了决策记录，密集的董事会页在大屏上讲不动
- **Content**: 四场景（逐字自源表）：演讲者主导＝远距离可读性、节奏、视觉锚点、对口头表达的补充；读者主导＝自解释逻辑、明确上下文、更完整证据、可导航性；混合场景＝明确主要模式，用备注/附录/补充细节服务次要模式；录制或自动播放＝旁白、计时、转场、播放可靠性、不依赖现场讲者。提示："不能假设同一页面可同时最优服务四种场景。"来源：Microsoft 备注与讲义、旁白与计时、共享与共同创作
- **Images**: 无

#### Slide 10 - PowerPoint 原生对象模型

- **Audience move**: 从"每页是一张图片" → 建立"pptx 是相互关联部件组成的包"的结构直觉，看懂 Theme→Master→Layout→Slide 的层级
- **Layout**: #41 全幅蓝图爆炸图（object_model.jpg）作骨架，SVG 叠加尺寸标注线、引线与模块代号标签，标出 Theme / Slide Master / Slide Layout / Slide / Notes·Media 各层；左上眉题 `03 · 原生结构` + 标题；一处编辑红高亮"当前层"。text_policy none，全部标签为 SVG
- **Title**: .pptx 是相互关联部件组成的包，不是每页一张位图
- **Core message**: 演示文稿有清晰层级：Theme 下有 Slide Master，其下有 Slide Layout，具体 Slide 绑定某个 Layout——外加备注、媒体、关系与演示行为
- **Content**: 结构树（逐字自源 code 块，作为 SVG 标注/侧注）：Presentation package ├ Theme ├ Slide Master A（├ Slide Layout A1 → Slide 1/Slide 4；└ Layout A2 → Slide 2）├ Slide Master B（Layout B1 → Slide 7）├ Notes/Handouts/Comments └ Media/Charts/Tables/Transitions/Animation/Audio。一句引题："pptx 不是每页一张位图，也不是一个巨大的单体 XML。"来源：Microsoft PresentationML 结构指南
- **Images**: object_model.jpg（#41 工程叠加，标注为 SVG #65；adaptive）

#### Slide 11 - 对象模型里各部件的职责

- **Audience move**: 从"看到漂亮截图就以为是好文件" → 能说出各部件职责，并接受"视觉正确≠结构良好"
- **Layout**: 左 7 / 右 5：左侧八行职责清单（图标 + 对象名 + 职责一句），右侧暖纸卡放"视觉正确≠结构良好"的关键警句 + 真正可用 deck 还需要的要素；眉题 `03 · 部件职责`
- **Title**: 视觉上正确的截图，仍可能是一份结构很差的 PowerPoint
- **Core message**: 真正可用的 deck 还需要合理的对象边界、继承关系、可编辑性、包关系与演示行为
- **Content**: 八职责（逐字自源表）：Theme＝可复用的颜色、字体与效果；Slide Master＝一组 Layout 共同继承的格式与对象；Slide Layout＝某类页面的默认外观、位置与占位符；Placeholder＝Layout 上预格式化、带类型的内容容器；Slide＝绑定某个 Layout 的一次具体内容实例；Notes 与 Handouts＝可见页面之外的演讲者与受众通道；Package relationships＝连接页面/Layout/Master/媒体/备注/批注及其他部件；Presentation behavior＝顺序、转场、动画、旁白与计时。右卡警句＝标题句 + "Microsoft 明确把 Slide Layout 置于 Slide Master 之下"。来源：Microsoft 什么是 Slide Layout
- **Images**: 无

#### Slide 12 - 什么是 PowerPoint 模板

- **Audience move**: 从"复制一份好看的 deck 就是模板" → 理解模板是把稳定可复用的决策与一次性内容分开，且 Theme≠Template
- **Layout**: 上部一条"Theme vs Template"对比条（Theme：颜色/字体/效果；Template：在 Theme 之上加面向用途的内容与结构）；下部四层堆叠（Theme → Slide Master → Slide Layout → 预置内容与示例），蓝图分层示意；中间放引用块金句；眉题 `03 · 模板`
- **Title**: 模板存在，是因为某种身份、结构或场景预计会重复出现
- **Core message**: 视觉相似不会自动形成模板；有效模板把稳定、可复用的决策与只属于某一次演示的内容分开
- **Content**: 区分（逐字自源）：Theme 提供协调的颜色、字体与效果；Template 在 Theme 之上增加面向特定用途的内容与结构。四层次（逐字自源表）：Theme＝协调一致的颜色/字体/效果；Slide Master＝一组 Layout 共同使用的格式与固定对象；Slide Layout＝某类重复页面的占位符结构与默认构图；预置内容与示例＝面向特定用途的起始页面、固定措辞、示例与使用指引。引用块金句："模板之所以存在，是因为某种演示身份、结构或沟通场景预计会重复出现。"来源：Microsoft Theme 与 Template 的区别
- **Images**: 无

#### Slide 13 - 什么是好的 PPT

- **Audience move**: 从"好 PPT＝好看" → 理解质量至少有六个层次，视觉只是其一
- **Layout**: #3 右侧竖向六层剖面插图（quality_layers.jpg，约占右 36%），左侧六行质量层次（图标 + 层次名 + 核心问题）自下而上对应插图分层；底部一句由场景决定的质量原则；眉题 `03 · 质量`
- **Title**: 好的 deck，不能只用"视觉精美"来定义
- **Core message**: 质量至少含事实、沟通、叙事、认知、视觉、原生与运行六层——每个元素都应帮目标受众在目标场景完成目标任务
- **Content**: 六层（逐字自源表）：事实＝论断、数值、来源、概念区分是否正确；沟通＝受众、结果、核心信息、行动要求是否明确；叙事＝页面顺序是否形成预期的理解/判断/决策；认知＝能否不过载地感知、处理并连接信息；视觉＝层级/字体/留白/图像/数据图形是否服务含义；原生与运行＝能否可靠地演示、编辑、评审、复用与交付。原则句："每个元素都应该帮助目标受众，在目标传递场景中完成目标认知或组织任务。"
- **Images**: quality_layers.jpg（#3，文字为 SVG）

#### Slide 14 - 研究怎么说：不是"图片越多越好"

- **Audience move**: 从"多加图和动效更好" → 知道有实证研究表明无关图片与声音会损害学习，设计要克制
- **Layout**: 三栏研究卡（Mayer / Bartsch & Cobern / Kosslyn 等），每卡＝研究者 + 一句发现 + 来源；上方一句反常识提要；认知图标点缀；眉题 `03 · 证据`
- **Title**: 研究并不支持"图片越多越好"这样的普遍规则
- **Core message**: 设计良好的文字与图形组合能改善理解，但无关的图片与声音会损害记忆与学习——人的信息处理容量有限
- **Content**: 三项（逐字自源）：Mayer《多媒体学习》＝设计良好的文字与图形组合可改善理解，同时人的信息处理容量有限；Bartsch & Cobern＝即使 PowerPoint 本身可能有帮助，不相关的图片和声音仍会损害记忆与学习；Kosslyn 等＝真实演示常违反可辨别性、有限容量与信息变化原则，且未经训练的观察者常无法识别这些问题。提要："结论不是建立万能页面公式，而是一条由场景决定的质量原则。"来源：三篇文献
- **Images**: 无

#### Slide 15 - PPT 不是什么

- **Audience move**: 从若干关于 PPT 的错误默认 → 能逐条识别并否定它们，理解工具应服务沟通模型
- **Layout**: #2 左侧对照概念图（ppt_is_not.jpg，约占左 34%），右侧八条否定清单，每条前置编辑红否定标记（✕/斜杠）；底部一句"工具应服务沟通模型，而不是根据按钮倒推沟通模型"；眉题 `03 · 澄清`
- **Title**: PPT 并不天然等于这八件事
- **Core message**: 若从软件默认的页面形式出发、而非从受众要完成的任务出发，PowerPoint 的惯例会反过来扭曲沟通
- **Content**: 八否定（逐字自源）：把文档分页后加装饰；一组漂亮但互不相关的画布；演讲者逐字稿；视觉效果展示；没有后续生命的一次性放映；只是带 .pptx 扩展名的扁平图片；因页面看起来一致就自动成为模板；所有沟通任务的正确媒介。结句："工具应该服务沟通模型，而不是根据工具按钮倒推沟通模型。"
- **Images**: ppt_is_not.jpg（#2，文字为 SVG）

### Part 3: 方法——把认知变成可执行的问题清单

#### Slide 16 - 每个 PPT 请求都该回答的问题

- **Audience move**: 从"上来就选风格/模板/动画" → 拿到一张先于制作的八问清单，知道要先回答任务与边界
- **Layout**: 2×4 或 4×2 问题清单卡，每卡＝tabler-outline 图标 + 问题 + "为什么重要"一句；卡阵下一条结论带"这些问题应先于风格、版式、模板、动画或制作方式的详细决定"；眉题 `04 · 方法清单`
- **Title**: 做 PPT 之前，先回答这八个问题
- **Core message**: 受众、期望改变、传递场景、核心信息、可见证据、编辑边界、原生要求、复用性——这些先于一切风格决定
- **Content**: 八问（逐字自源表）：受众是谁？→决定语言、默认知识、证据、语气；看完后必须发生什么变化？→定义沟通任务与成功条件；主要是现场讲/独立读/录制/混合？→决定密度、字体、备注、演示行为；核心信息是什么？→防止无论证就生产页面；哪些证据必须可见或可追溯？→保护事实完整与决策价值；什么可以改变、什么必须保留？→明确编辑边界与评审预期；哪些内容必须可编辑或保持原生？→定义对象模型与交付要求；什么会反复出现？→决定是否需要 Theme/Master/Layout/预置内容，或根本不需要模板
- **Images**: 无

#### Slide 17 - 收尾：先想清任务，工具才服务沟通

- **Audience move**: 从被动接受一堆概念 → 带走一个可执行的心智闭环：任务→媒介→结构→质量，并把核心信息内化
- **Closing impact**: 带走的一件事＝核心信息"PPT 不是一叠静态页面，而是有顺序、模块化、可编辑并需持续流转的沟通产物；先想清受众要完成什么任务，工具才服务沟通"；构图＝把三幕收成一个闭环示意（解构→重构→方法 回到"任务"），巨号核心句 + 环形/箭头闭环，非"谢谢"页
- **Layout**: 中心巨号核心信息句（primary，跨栏），下方一条方法闭环带：任务 → 选媒介 → 建结构 → 保质量 →（回到）任务，用蓝图引线箭头串成环；底部一行长期用途/致读者小字；#12 或负空间主导 + 环形示意
- **Title**: 先想清任务，工具才服务沟通
- **Core message**: PPT 不是一叠静态页面，而是有顺序、模块化、可编辑并需要持续流转的沟通产物
- **Content**: 巨号句"先想清楚受众要完成什么任务，工具才服务沟通"；闭环带：明确任务与受众结果 → 判断是否该用演示文稿 → 搭建有顺序、可编辑的原生结构 → 用六层质量自检 →（回到）下一次的任务。收束小字"把它当作理解 PPT 本质的参考，随团队与场景反复复用。"
- **Images**: 无

## X. Speaker Notes Requirements

- **Filename**: 与各 SVG 文件同名，置于 `notes/`（如 `01_cover.svg` → `notes/01_cover.md`）
- **Content**: 讲解式、耐心解释的语气（instructional 底 + pyramid 每页先给结论句）；先给这一页的断言，再补 2-3 点支撑与过渡；忠实源文档事实，不引入源外新事实；外部来源（Microsoft、ECMA-376、Yates & Orlikowski、Mayer、Bartsch & Cobern、Kosslyn 等）在备注中点名
- **Total duration**: 约 15-20 分钟
- **Notes style**: conversational
- **Presentation purpose**: instruct（讲清概念）为主，兼 inform 与 report（澄清误解、给出方法）
