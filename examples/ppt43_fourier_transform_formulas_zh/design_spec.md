<!-- ppt-master-schema: design-spec/v1 -->
# fourier_transform_formulas_zh - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | fourier_transform_formulas_zh |
| Canvas Format | PPT 4:3 (1024×768) |
| Page Count | 15 |
| Primary Language | zh-CN |
| Target Audience | 有高中数学基础的大学新生,以及做信号/图像/通信的工程师;他们会用正弦、积分和复数记号,但没系统学过变换 |
| Communication Intent | 先教会:用一节公开课把"时域→频域"这件事讲通,顺序是直觉→级数→变换→性质→离散与快速→应用;其次是让公式可带走(课后能直接复制编辑) |
| Desired Audience Outcome | 听众能说出傅里叶变换在做什么、读懂并复述一条变换对与卷积定理、解释 FFT 为什么快,并能在自己领域指认一个傅里叶应用 |
| Core Message / Ask / Action | 傅里叶变换是一本可逆的字典:把"随时间怎么变"翻译成"由哪些频率组成",难的部分是记号,不是思想 |
| Delivery Context | 主要是有主讲人的 45 分钟公开课现场投影(传统 4:3 投影仪);次要是课后自读与公式复用 |
| Artifact Afterlife | 课后自学材料、公式取用来源、延伸阅读索引 |
| Reading Mode | balanced |
| Content Strategy | 平衡默认(用户未填写素材贴合度):事实全部取自 `sources/` 的研究对并标出处,讲授路径与类比由本卷整理 |
| Design Style | 方向二「科学期刊」— 教科书跨页式栅格,细分隔线,衬线标题配黑体正文,公式独占带状区并留边注栏 |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 工作流默认(用户未指定),公开课需要讲稿 |
| Custom Animations | enabled — 用户明确要求"要有自定义动画和 Morph" |
| Narration Audio | disabled — 工作流默认(用户未要求旁白) |
| Created Date | 2026-09-12 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 4:3 |
| Dimensions | 1024 × 768 |
| viewBox | `0 0 1024 768` |
| Margins | 上下 56 px,左右 64 px |
| Content Area | x 64–960(896 px 版面宽),y 56–712 |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: instructional, briefing
- **Mode Behavior**: 以教学阶梯为主干:每页一个可验证的理解台阶,页标题写成陈述句("求和变成积分"),上一页的结论是下一页的前提;`instructional` 负责概念分解与推导顺序,`briefing` 负责变换对表与应用页那种中性、可扫读的均权陈列。每个小节先给一句直觉,再给公式,再给一句"这条公式让你能做什么"。
- **Visual style**: custom
- **Visual Style References**: swiss-minimal, editorial, data-journalism
- **Visual Style Behavior**: 教科书跨页语言:`swiss-minimal` 定 12 栅格、硬边直角与大留白;`editorial` 提供细规则线、边注栏、小节序号与衬线/黑体互文的层级;`data-journalism` 只负责公式与图表下方的来源行与刻度注记。公式独占一条浅底带状区(secondary_bg)并以左侧 3 px 主色竖条起头,右侧留 200 px 边注栏写"读法";装饰只有细线、带状区和刻度,没有卡片阴影、没有圆角、没有渐变。
- **Theme**: 一本摊开的讲义:左页讲道理,右页留公式与边注
- **Tone**: 克制、精确、可被复制;像一份排得很好的讲义而不是发布会

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #FFFFFF | 页面底色,投影下最大对比 |
| Secondary background | #F2F4F7 | 公式带状区、表头、边注栏底 |
| Primary | #123B63 | 标题、公式竖条、坐标轴与结构线 |
| Accent | #C2452D | 频域侧的强调:重点项、谐波峰、结论标记 |
| Secondary accent | #2E7D7B | 时域侧的第二色:原始波形、对照序列 |
| Body text | #1B2027 | 正文与公式文字 |
| Secondary text | #5A6472 | 边注、刻度、来源行 |
| Divider | #D6DBE1 | 细规则线、表格线、栅格分隔 |

### AI Image Strategy

- **Image Rendering**: custom
- **Image Rendering References**: blueprint, editorial
- **Image Rendering Behavior**: 讲义插图而非海报:`blueprint` 给出等宽刻度、细网格底与描线感的技术图语言,`editorial` 给出杂志信息图那种干净留白与层级清晰的构成。线条均匀细实,无渐变、无发光、无立体投影;只用本卷的主色、时域青碧与频域朱红三色,底为纸白。
- **Visual**: 一条复合波形在左,向右逐渐分解成若干等间距的单频正弦,末端收成一排高低不同的频率竖线;浅网格与刻度暗示坐标系
- **Mood**: 冷静、可验证,像教科书扉页的示意图或科学期刊的图 1

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 衬线/教科书体,笔画有起收,承担"讲义"性格 | SimSun | Cambria | serif |
| Body | 无衬线/黑体,投影清晰,长句不糊 | Microsoft YaHei | Cambria | sans-serif |
| Formula | 数学排版体,与导出的原生公式同族 | Cambria Math | Cambria Math | serif |
| Annotation | 黑体小字,边注与刻度 | Microsoft YaHei | Cambria | sans-serif |
| Footnote | 黑体极小字,来源行与页码 | Microsoft YaHei | Cambria | sans-serif |
| Display | 衬线大字,章节序号与量级数字 | SimSun | Cambria | serif |

- **Title stack**: SimSun, Cambria, serif
- **Body stack**: Microsoft YaHei, Cambria, sans-serif
- **Formula stack**: Cambria Math, serif
- **Annotation stack**: Microsoft YaHei, Cambria, sans-serif
- **Footnote stack**: Microsoft YaHei, Cambria, sans-serif
- **Display stack**: SimSun, Cambria, serif
- **Role rationale**: 新增 `formula` 角色,让 SVG 里手写的公式回退与导出后的原生公式共用 Cambria Math,避免同一页出现两套数学字形;`display` 只用于章节序号与量级数字(N²、N log N),仍在标题族内。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 42 |
| Subtitle | 32 |
| Formula | 28 |
| Annotation | 18 |
| Footnote | 16 |
| Display | 60 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 自上而下——页标题(陈述句)→ 一句直觉 → 公式带状区 → 边注读法 / 来源行;视线先落在公式带上,再回到左侧文字
- **Composition tendency**: 主栏 + 边注栏的讲义式双区;公式页让公式带横贯主栏、边注栏写"每个符号读作什么";图表页反过来,图占上三分之二、公式与结论在下
- **Cross-page continuity**: 每页左上角有小节序号(Display 体)与小节名;公式带状区的样式(浅底 + 左侧主色竖条)全卷不变,是本卷的识别母题;时域一律青碧、频域一律朱红
- **Spacing posture**: variable by page rhythm——推导页 dense,小节入口与收束页 breathing
- **Spacing anchors**: 页边距 64 px,块间距 32 px,栏间距 24 px,圆角 0 px,正文行距 1.55

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2

| Icon Path | Suitable Scenarios |
| --- | --- |
| icons/tabler-outline/wave-sine.svg | 时域波形、单频分量 |
| icons/tabler-outline/math-function.svg | 公式、函数与变换 |
| icons/tabler-outline/chart-histogram.svg | 频谱、幅度分布 |
| icons/tabler-outline/photo.svg | 图像压缩类应用 |
| icons/tabler-outline/wifi.svg | 无线通信类应用 |
| icons/tabler-outline/activity-heartbeat.svg | 医学成像类应用 |
| icons/tabler-outline/music.svg | 音频与均衡 |
| icons/tabler-outline/clock.svg | 时间轴、时移 |
| icons/tabler-outline/repeat.svg | 周期、循环与可逆往返 |
| icons/tabler-outline/book.svg | 历史文献与延伸阅读 |
| icons/tabler-outline/bulb.svg | 直觉提示与小结 |
| icons/tabler-outline/arrows-right-left.svg | 正变换与逆变换的成对关系 |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P05 | chart | column_chart | 展示方波前若干奇次谐波的幅度按 1/k 递减 |
| P08 | table | record_table | 四对常见变换对的时域式、频域式与读法并列 |
| P13 | chart | line_chart | 对比 N² 与 N·log₂N 随 N 增长的计算量 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cover_wave_decomposition.png | 3168x1344 | 2.36:1 | 封面主视觉的生成原件,仅用于派生落位尺寸的副本 | Source | 不上页 | adaptive | ai | Generated | 抽象示意图:左侧一条复合波形,向右渐次分离出三到四条等间距单频正弦,最右收成一排高低不同的频率竖线;浅网格与刻度暗示坐标系;无文字、无人物 | none | local |
| cover_wave_band.jpg | 1024x434 | 2.36:1 | 封面主视觉:一条复合波向右分解成单频正弦并收成频率竖线 | Illustration | 横贯封面下半的通栏带状插图,标题压在其上方留白处,不要让波形穿过标题 | adaptive | ai | Generated | Derived from cover_wave_decomposition.png; treatment=fit 1024x435; 按封面落位尺寸缩小,内容不变 | none | local |

## IX. Content Outline

### Part 1: 从耳朵开始

#### Slide 01 - 封面:把信号拆成频率

- **Audience move**: 以为"傅里叶变换"是考试里的积分公式 → 愿意把它当成一次翻译练习
- **Relationships**: 标题、副标题、主视觉插图与讲授场合信息之间无源给定关系(none)
- **Cover impact**: 钩子(binding)——"一个和弦里有几个正弦波?把它数出来的那套数学,就是这节课"
- **Composition**: 上半留白放标题与副标题,下半通栏放分解插图;左上角留小节体系的起点
- **Title**: 傅里叶变换:把信号拆成频率
- **Core message**: 时域与频域是同一件事的两种写法
- **Content**: 主标题与副标题「一节课读懂级数、变换、FFT 与它们的公式」· 讲授信息:公开课 / 45 分钟 / 面向大一新生与工程师 · 底部一行:公式均为可编辑原生公式
- **Images**: 使用 §VIII 的 cover_wave_band.jpg 作为下半通栏主视觉(其生成原件 cover_wave_decomposition.png 不上页)
- **Motion suggestion**: 主标题与插图先后进场,让"一条波→若干频率"的方向被看见
- **page_rhythm**: anchor

#### Slide 02 - 一个和弦,拆成三条正弦

- **Audience move**: 觉得"波形"只是屏幕上一条抖动的线 → 接受它是若干单频波的和
- **Relationships**: 复合波形与三条单频分量之间是 parent(整体)与 membership(成分)关系;三条分量之间是 order(频率由低到高)
- **Composition**: 上方一条复合波形,下方三条错开的单频波形,右侧边注写"加起来就是上面那条"
- **Title**: 听到的是一条波,里面是好几条
- **Core message**: 叠加是听觉的常识,傅里叶只是把"有哪些分量"算出来
- **Content**: 直觉:同时按下三个琴键,耳朵听到一个和弦,空气里是三条正弦相加 · 行内写法:任何周期信号都可写成 A_n 与 φ_n 的正弦叠加 · 提问:如果只给你合成后的波形,能反推出 A_n 和 f_n 吗?这就是本节课要回答的
- **Mathematical content**: x(t) = \sum_{n=1}^{N} A_n \sin(2\pi f_n t + \varphi_n)
- **page_rhythm**: breathing

### Part 2: 傅里叶级数

#### Slide 03 - 这套级数是从热方程里逼出来的

- **Audience move**: 以为级数是信号处理的发明 → 知道它源自 1822 年的热传导研究
- **Relationships**: 1807 年提交、1811 年获奖、1822 年成书构成 order(时间顺序);历史动机与级数写法之间是 link(因果)
- **Composition**: 左侧三点时间线,右侧公式带状区放级数展开式
- **Title**: 级数不是技巧,是热方程解出来的
- **Core message**: 傅里叶的动机是物理,记号只是随之而来的工具
- **Content**: 1807 年 12 月向法兰西研究院提交热传导手稿,未获发表 · 1811 年以修订稿赢得科学院热扩散悬赏,仍被批评不够严格 · 1822 年《Théorie analytique de la chaleur》出版,级数写法由此进入数学 · 边注:他要解的是"热怎么在固体里扩散",不是"怎么压缩音频"
- **Mathematical content**: f(x) = \frac{a_0}{2} + \sum_{n=1}^{\infty} \left( a_n \cos \frac{2\pi n x}{T} + b_n \sin \frac{2\pi n x}{T} \right)
- **Fact IDs**: F001, F002
- **page_rhythm**: dense

#### Slide 04 - 系数怎么算出来:用积分把一条分量挑出来

- **Audience move**: 看到 a_n、b_n 不知从何而来 → 明白它是一次"内积筛选"
- **Relationships**: 两条系数公式之间是 contrast(余弦项与正弦项对称);系数与级数展开式之间是 parent-membership
- **Composition**: 公式带状区上下两行放 a_n 与 b_n,右侧边注逐符号给读法
- **Title**: 想知道某个频率有多少,就和它做一次积分
- **Core message**: 正交性让每个频率的分量可以被单独称重
- **Content**: 读法:把信号乘上一条已知频率的余弦,再在一个周期上积分,其他频率相互抵消,只剩这一条的量 · 两条公式互为镜像:一条量余弦成分,一条量正弦成分 · 提醒:周期 T 决定了可用的频率只能是基频的整数倍
- **Mathematical content**: a_n = \frac{2}{T} \int_{0}^{T} f(x) \cos \frac{2\pi n x}{T}\, dx \quad,\quad b_n = \frac{2}{T} \int_{0}^{T} f(x) \sin \frac{2\pi n x}{T}\, dx
- **page_rhythm**: dense

#### Slide 05 - 方波:只剩奇次谐波,幅度按 1/k 掉

- **Audience move**: 觉得级数是抽象符号 → 看到一条具体信号的频率清单
- **Relationships**: 展开式各项与幅度谱各柱是 link(同一组系数的两种呈现);柱之间是 order(谐波次数递增)
- **Composition**: 上方幅度谱柱列,下方公式带状区放方波展开式,右侧边注写"偶次项为零"
- **Title**: 一条方波的频率清单
- **Core message**: 级数把"形状"换成了一串可以逐项检查的数
- **Content**: 方波展开只含奇次谐波,第 k 项幅度正比于 1/k · 幅度谱:k = 1、3、5、7、9 的相对幅度为 1、1/3、1/5、1/7、1/9 · 边注:项数越多,拐角越方——但永远有一点过冲(吉布斯现象),本课不展开
- **Mathematical content**: f(t) = \frac{4}{\pi} \sum_{k=1,3,5,\dots} \frac{1}{k} \sin(k\omega t)
- **Visualization**: 幅度谱柱状图 `square-harmonics`,取上述 1/k 序列;`Native-ready` square-harmonics=yes
- **Data class: scenario**: 无,1/k 序列由该页展开式直接算出(整理)
- **page_rhythm**: dense

### Part 3: 从级数到变换

#### Slide 06 - 让周期变长到无穷:求和快要变成积分

- **Audience move**: 以为级数只能处理周期信号 → 预期到"周期→无穷"这一步会发生什么
- **Relationships**: 周期 T 增大与频率间隔变密之间是 link(因果);离散求和与连续积分之间是 contrast
- **Composition**: 同一条公式带状区居中,只放级数式;左右各一句"T 变大,频率越排越密"
- **Title**: 周期越长,频率排得越密
- **Core message**: 离散的频率清单在周期趋于无穷时变成连续的频谱
- **Content**: 周期 T 下可用频率是基频的整数倍,间隔为 1/T · T 变大,间隔变小,清单变长 · 下一页把 T 推到无穷:求和号换成积分号,系数换成一条连续函数
- **Mathematical content**: f(t) = \sum_{n=-\infty}^{\infty} c_n e^{i 2\pi n t / T}, \quad c_n = \frac{1}{T} \int_{-T/2}^{T/2} f(t) e^{-i 2\pi n t / T}\, dt
- **Motion suggestion**: 与下一页共用同一条公式带:级数式在两页之间变形为积分式,是本卷的推导动作
- **page_rhythm**: breathing

#### Slide 07 - 求和变积分:连续傅里叶变换对

- **Audience move**: 把变换当成新公式 → 认出它就是上一页那条式子的极限形态
- **Relationships**: 正变换与逆变换之间是 link(互逆);与上一页级数式之间是 order(推导的下一步)
- **Composition**: 公式带状区两行:正变换在上、逆变换在下,中间一个双向箭头;右侧边注写约定
- **Title**: 同一条式子,换成积分
- **Core message**: 变换与逆变换是一本可逆字典的两个方向
- **Content**: 正变换把 f(t) 读成频率分布 F(ω);逆变换把 F(ω) 读回 f(t) · 约定要先说清:1/(2π) 放在哪一侧、指数写 e^{-iωt} 还是 e^{-2πift},各教材不同,本课按 NIST DLMF §1.14 的写法 · 边注:e^{-iωt} 不是玄学,它同时量了这条频率的幅度和相位
- **Mathematical content**: F(\omega) = \int_{-\infty}^{\infty} f(t)\, e^{-i\omega t}\, dt \quad,\quad f(t) = \frac{1}{2\pi} \int_{-\infty}^{\infty} F(\omega)\, e^{i\omega t}\, d\omega
- **Fact IDs**: F010, F011
- **Motion suggestion**: 承接上一页的公式带变形,变形完成后再让逆变换那一行与双向箭头进场
- **page_rhythm**: dense

#### Slide 08 - 四对要背下来的变换对

- **Audience move**: 面对任意信号都要重算 → 手里有四对可直接套用的样板
- **Relationships**: 四行是 membership(同属"常见变换对");每行时域与频域之间是 link(一对);矩形↔sinc 与高斯↔高斯之间是 contrast(换形与不换形)
- **Composition**: 一张四行三列表格占主栏,表格单元里直接排公式,底部一行写来源
- **Title**: 四对变换,记住就能用
- **Core message**: 常见信号的频域长相是可以背下来的
- **Content**: 表格:矩形窗 → sinc;高斯 → 高斯(形状不变,只换宽度);δ(t) → 1(一瞬间含所有频率);cos(ω₀t) → 两条 δ · 每行第三列写一句读法,例如"窗越窄,频谱越宽" · 来源行:变换对与性质的系统讲法见 Stanford EE261
- **Mathematical content**: \mathrm{rect}(t) \leftrightarrow \mathrm{sinc}\!\left(\frac{\omega}{2\pi}\right), \quad e^{-\pi t^{2}} \leftrightarrow e^{-\pi \omega^{2}}, \quad \delta(t) \leftrightarrow 1, \quad \cos(\omega_0 t) \leftrightarrow \pi\left[\delta(\omega-\omega_0) + \delta(\omega+\omega_0)\right]
- **Visualization**: 变换对表 `transform-pairs`(行=信号,列=时域式/频域式/读法);`Native-ready` transform-pairs=no —— 单元格内是原生公式标记,而 `data-pptx-replace-with` 子树内禁止公式标记(native-formula §2.1),原生 `a:tbl` 单元格也承载不了 oMath;保留为 Shape-first SVG 网格以保住公式可编辑
- **Fact IDs**: F012
- **page_rhythm**: dense

### Part 4: 三条性质

#### Slide 09 - 线性、时移、调制:三条最常用的性质

- **Audience move**: 每换一个信号就重算积分 → 会用性质把新问题化到已知变换对上
- **Relationships**: 三条性质是 membership(同属基本性质);时移与调制之间是 contrast(时域平移对应频域相位,时域相乘对应频域平移)
- **Composition**: 主栏三条公式各占一行带状区,每行右侧一句工程读法
- **Title**: 会用性质,就不用重算积分
- **Core message**: 性质把新信号化归成已知的变换对
- **Content**: 线性:分开算再相加 · 时移:把信号往后挪 t₀,频谱幅度不变,只多一个相位因子 e^{-iωt₀} · 调制:乘一条载波,等于把频谱整体搬到 ω₀ 上——这就是调幅广播在做的事
- **Mathematical content**: a f(t) + b g(t) \leftrightarrow a F(\omega) + b G(\omega), \quad f(t-t_0) \leftrightarrow e^{-i\omega t_0} F(\omega), \quad f(t) e^{i\omega_0 t} \leftrightarrow F(\omega - \omega_0)
- **page_rhythm**: dense

#### Slide 10 - 卷积定理:滤波在频域只是一次乘法

- **Audience move**: 把滤波当成难算的积分 → 知道它在频域是逐点相乘
- **Relationships**: 时域卷积与频域乘积之间是 link(定理两侧);定理与均衡器之间是 parent(原理)与 membership(应用)
- **Composition**: 公式带状区居中放定理,下方一条三步流程:变换 → 相乘 → 变回
- **Title**: 时域卷积,频域相乘
- **Core message**: 一切"滤波""均衡""模糊"都是频域里的一次乘法
- **Content**: 定理(NIST DLMF §1.14):若 f、g 绝对可积,则 f∗g 的傅里叶变换等于 F(ω)·G(ω) · 工程读法:与其在时域逐点卷积,不如变到频域乘一条传递函数,再变回来 · 均衡器就是这条曲线:把某段频率乘大一点,另一段乘小一点
- **Mathematical content**: (f * g)(t) = \int_{-\infty}^{\infty} f(t-s) g(s)\, ds \;\longleftrightarrow\; F(\omega)\, G(\omega)
- **Fact IDs**: F010
- **page_rhythm**: dense

### Part 5: 离散与快速

#### Slide 11 - 计算机只有采样点:积分变回求和

- **Audience move**: 以为连续公式没法上机 → 知道采样定理给了离散化的合法性
- **Relationships**: 采样定理与离散变换之间是 link(前提与结果);连续积分与有限求和之间是 contrast
- **Composition**: 上方一句采样定理与出处,下方公式带状区放 DFT 定义式
- **Title**: 采样让积分变成有限求和
- **Core message**: 离散傅里叶变换是连续变换在采样点上的可计算版本
- **Content**: 采样定理(Shannon,1949):带宽限于 W 的信号,可由每秒 2W 个采样完全确定 · 于是积分换成 N 项求和,连续频率换成 N 个频点 · 边注:N 点输入给出 N 个复数输出,信息量不增不减
- **Mathematical content**: X_k = \sum_{n=0}^{N-1} x_n\, e^{-i 2\pi k n / N}, \quad k = 0, 1, \dots, N-1
- **Fact IDs**: F009
- **page_rhythm**: dense

#### Slide 12 - 直接算要 N² 次:为什么慢

- **Audience move**: 认为 DFT 写出来就能用 → 看清朴素实现的代价
- **Relationships**: 每个频点的求和与 N 个频点之间是 parent-membership,乘出 N² 的量级
- **Composition**: 同一条 DFT 公式带状区居中,量级数字以 Display 体压在右侧,边注写"每个 k 都要走一遍 n"
- **Title**: 每个频点都要遍历所有样本
- **Core message**: 朴素实现的代价随 N 平方增长,长信号直接算不动
- **Content**: 一个 k 要做 N 次复数乘加,N 个 k 就是 N² · 行内量级:N = 1024 时约 1 048 576 次(整理:N² 直接算得) · 边注:实时音频每秒要做很多次这样的变换,N² 撑不住
- **Mathematical content**: \text{cost}_{\text{DFT}} = \mathcal{O}(N^{2})
- **Fact IDs**: F003
- **Motion suggestion**: 与下一页共用同一条公式带:朴素求和式在两页之间变形为奇偶分解式,这是"为什么快"的那一步
- **page_rhythm**: dense

#### Slide 13 - Cooley–Tukey:把一个 N 拆成两个 N/2

- **Audience move**: 觉得 FFT 是黑箱库函数 → 能说出它靠什么把量级降下来
- **Relationships**: 奇偶分解与递归之间是 link;N² 与 N log N 两条曲线之间是 contrast
- **Composition**: 上方公式带状区放奇偶分解式,下方一张两条曲线的对比图,底部来源行
- **Title**: 拆成奇偶两半,再递归下去
- **Core message**: 把一个长度 N 的变换换成两个 N/2 的变换,代价就从 N² 降到 N log N
- **Content**: 分解:偶数下标项给出 E_k,奇数下标项给出 O_k,再用一个旋转因子合起来;对 N/2 继续同样拆分 · 出处:Cooley 与 Tukey,Mathematics of Computation 19(90):297–301,1965 · 史前史:高斯约 1805 年的未发表手稿里已有等价做法(Heideman 等,1984) · 对比图:N² 与 N·log₂N 随 N = 64…4096 的增长(整理:按两条量级公式算出)
- **Mathematical content**: X_k = E_k + e^{-i 2\pi k / N} O_k, \quad E_k = \sum_{m=0}^{N/2-1} x_{2m} e^{-i 2\pi k m /(N/2)}, \quad O_k = \sum_{m=0}^{N/2-1} x_{2m+1} e^{-i 2\pi k m /(N/2)}
- **Visualization**: 复杂度对比折线图 `complexity-compare`(两条序列:N² 与 N·log₂N,N = 64、256、1024、4096);`Native-ready` complexity-compare=yes
- **Fact IDs**: F003, F004
- **Motion suggestion**: 承接上一页公式带的变形,变形结束后对比图再进场
- **page_rhythm**: dense

### Part 6: 用在哪里,以及下一步

#### Slide 14 - 你每天都在用的四个傅里叶

- **Audience move**: 把变换当考试内容 → 认出手机、医院、路由器里都在跑它
- **Relationships**: 四个应用是 membership(同属"已落地的傅里叶");每个应用与其所用的变换形态之间是 link
- **Composition**: 主栏四个等宽条目,每条一个图标 + 一行事实 + 一行出处年份
- **Title**: 图像、医学、无线、声音
- **Core message**: 频域不是黑板上的技巧,它已经写进标准里
- **Content**: JPEG:基线 JPEG 把图像切成 8×8 块做离散余弦变换(ITU-T T.81,1992) · MRI:采集等于在傅里叶空间(k 空间)沿轨迹采样,再变换回图像(Twieg,1983) · Wi-Fi:802.11a(1999)的 20 MHz OFDM 用 64 点 FFT,含 48 个数据子载波与 4 个导频;子载波间隔 312.5 kHz(整理:20 MHz ÷ 64) · 音频均衡:按频段乘一条传递函数再变回时域,正是卷积定理
- **Mathematical content**: \text{JPEG: } S_{vu} = \frac{1}{4} C_u C_v \sum_{x=0}^{7} \sum_{y=0}^{7} s_{yx} \cos\frac{(2x+1)u\pi}{16} \cos\frac{(2y+1)v\pi}{16}
- **Fact IDs**: F005, F006, F007, F008, F010
- **page_rhythm**: dense

#### Slide 15 - 带走三句话和两条路

- **Audience move**: 听完一节课 → 有三句可复述的结论和明确的下一步
- **Relationships**: 三句结论与全卷各节之间是 parent-membership;两条延伸路径之间是 contrast(理论课与动手算)
- **Closing impact**: 收束(binding)——"记号是门槛,思想不是:变换只是把'怎么变'翻译成'由哪些频率组成'",配全卷公式带状区最后一次出现
- **Composition**: 上方三句结论各占一行带状区,下方两条延伸阅读并列,底部来源行
- **Title**: 三句话,和两条继续走的路
- **Core message**: 会读变换对、会用卷积定理、知道 FFT 为什么快,这节课就到位了
- **Content**: 一:时域与频域是同一信息的两种写法,靠一对积分互相翻译 · 二:滤波、均衡、模糊在频域都是一次乘法(卷积定理) · 三:FFT 没有换数学,只换了算法:N² → N log N · 延伸一:Stanford EE261《The Fourier Transform and its Applications》系统讲变换对与性质 · 延伸二:自己写一个 8 点 DFT,再和库函数对一遍结果 · 来源行:本卷事实出处见讲者备注与 sources/fourier_transform_research.facts.json
- **Mathematical content**: f(t) \;\xrightarrow{\;\mathcal{F}\;}\; F(\omega) \;\xrightarrow{\;\mathcal{F}^{-1}\;}\; f(t)
- **Fact IDs**: F012
- **page_rhythm**: anchor

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 每页一段讲稿:先一句进入这页的过渡,再逐符号读出本页公式(把 e^{-iωt}、积分上下限、求和下标读成人话),最后一句给出这页要留下的结论;历史与参数类说法在备注里重复出处与年份,便于讲者当场引用;不改动页面上的事实,不添加页面外的新数字
- **Total duration**: 约 45 分钟(15 页,平均每页 2.5–3.5 分钟,推导页偏长)
- **Notes style**: 讲授式口语,面向大一新生的解释度,允许一次提问互动
- **Presentation purpose**: 先教会时域→频域这条路径,再让公式可带走复用
