# swiss_grid_systems — Design Spec

> Human-readable design narrative for a Swiss International Typographic Style lecture deck. Machine-readable contract: `spec_lock.md`.

## I. Project Information

| Item | Value |
| ---- | ----- |
| **Project Name** | swiss_grid_systems |
| **Canvas Format** | PPT 16:9 (1280×720) |
| **Page Count** | 14 |
| **Design Style** | A) General Versatile + Swiss International Typographic Style / minimalist grid / Müller-Brockmann hommage |
| **Target Audience** | 设计师 / 设计学生 / 文化机构活动观众 |
| **Use Case** | 约 25 分钟设计史小型 lecture |
| **Created Date** | 2026-05-17 |

---

## II. Canvas Specification

| Property | Value |
| -------- | ----- |
| **Format** | PPT 16:9 |
| **Dimensions** | 1280×720 |
| **viewBox** | `0 0 1280 720` |
| **Margins** | left/right 64px, top/bottom 56px（4×16 模数） |
| **Content Area** | 1152×608（严格 4 列网格：列宽 264px，列间距 32px） |

---

## III. Visual Theme

### Theme Style

- **Style**: Swiss International Typographic Style，纯白纸面 + 黑色字体 + 朱红点睛
- **Theme**: Light theme
- **Tone**: 克制、理性、可读、版面冲击；网格是骨架，留白是语言

### Color Scheme

| Role | HEX | Purpose |
| ---- | --- | ------- |
| **Background** | `#FFFFFF` | 纸白底，留白主体 |
| **Secondary bg** | `#F4F4F4` | 极淡浅灰，仅用于 P10/P11 的图样区分块 |
| **Primary** | `#1A1A1A` | 文字、主几何、海报黑 |
| **Accent** | `#D9251D` | 瑞士朱红（点睛 / 红圆 / 标尺） |
| **Secondary accent** | `#1A4FA0` | 印刷克莱因蓝（备用，仅章节区分） |
| **Body text** | `#1A1A1A` | 主体文字 |
| **Secondary text** | `#666666` | 注释、副标、年份 |
| **Tertiary text** | `#999999` | 页码、footer |
| **Border/divider** | `#E8E8E8` | 极淡网格线 / 分隔 |
| **Success** | `#1A4FA0` | （备用，本 deck 不需要状态色，使用蓝替代以避免色彩污染） |
| **Warning** | `#D9251D` | （备用，与 Accent 共用） |

> 60-30-10 严格执行：白 (≥60%) + 黑 (~30%) + 红 (≤10%)。蓝仅作章节/类别区分备用，全文最多出现 1-2 次。

### AI Image Strategy

- **Image Rendering**: `minimalist-swiss`
- **Image Palette**: `mono-ink`

> 锁定一次，三张 AI 图全部沿用：纸白 60-70% + 近黑 25-30% + 朱红 <10%。

### Gradient Scheme

不使用渐变。瑞士极简风格的核心之一是拒绝渐变和阴影；所有色彩都是纯色块。

---

## IV. Typography System

**Typography direction**: 单一家族（Arial 系，Helvetica 的 Windows 等价）内部以 weight + size 做层级。瑞士国际主义的核心字体语法。

| Role | Chinese | English | Fallback tail |
| ---- | ------- | ------- | ------------- |
| **Title** | `"Microsoft YaHei"` | `"Arial Black"` | `sans-serif` |
| **Body** | `"Microsoft YaHei"` | `Arial` | `sans-serif` |
| **Emphasis** | `"Microsoft YaHei"` | `Arial`（weight 700） | `sans-serif` |
| **Code** | — | `Consolas, "Courier New"` | `monospace` |

**Per-role font stacks**:

- Title: `"Arial Black", "Microsoft YaHei", sans-serif`
- Body: `Arial, "Microsoft YaHei", sans-serif`
- Emphasis: `Arial, "Microsoft YaHei", sans-serif`（with `font-weight="700"`）
- Code: `Consolas, "Courier New", monospace`

### Font Size Hierarchy

**Baseline**: Body = **18px**（lecture 信息密度中等偏紧凑，瑞士本色"密而清"）

| Purpose | Ratio to body | Example @ body=18 | Weight |
| ------- | ------------- | ----------------- | ------ |
| Cover title (hero headline) | 2.5-5x | 60-90px | Bold/Heavy |
| Chapter / section opener | 2-2.5x | 36-45px | Bold |
| Page title | 1.5-2x | 27-36px | Bold |
| Hero number | 1.5-2x | 27-36px | Bold |
| Subtitle | 1.2-1.5x | 22-27px | SemiBold |
| **Body** | **1x** | **18px** | Regular |
| Annotation / caption | 0.7-0.85x | 13-15px | Regular |
| Page number / footnote | 0.5-0.65x | 9-12px | Regular |

---

## V. Layout Principles

### Page Structure

- **Header area**: 顶部 56px 内不放标题（瑞士风常将页码/章节号置顶左对齐，标题压在内容区上沿）
- **Content area**: 64px 边距内自由排布；多页采用 4 列 264×608 网格
- **Footer area**: 底部 32px 高，左侧"页码 / 14"右对齐，中央 / 右侧空

### Layout Pattern Library

本 deck 主要采用以下模式：

| Pattern | Used in pages |
| ------- | ------------- |
| **Single column centered** | P14 结语 |
| **Asymmetric split (2:8 / 3:7)** | P02 引言 / P09 模数示意 |
| **Three/four column cards** | P05 人物 / P07 字体 / P11 应用 |
| **Matrix grid (2×2)** | P08 网格四类 |
| **Top-bottom split** | P03 起源 / P06 生平 / P12 数字时代 |
| **Negative-space-driven** | P10 留白即结构 |
| **Full-bleed + floating text** | P01 封面 / P14 结语 |
| **Vertical list** | P04 八条原则 |
| **Icon-grid** | P13 当代品牌 |

### Spacing Specification

**Universal**:

| Element | Range | This deck |
| ------- | ----- | --------- |
| Safe margin | 40-60px | **64px**（4×16 模数） |
| Content block gap | 24-40px | **32px** |
| Icon-text gap | 8-16px | **12px** |

**Cards** (P05 / P07 / P11 / P13):

| Element | Range | This deck |
| ------- | ----- | --------- |
| Card gap | 20-32px | **32px** |
| Card padding | 20-32px | **24px** |
| Card border radius | 8-16px | **0**（瑞士极简严格无圆角） |
| Three-column card width | 360-380px | **361px**（4 列网格中三列合并） |

**Non-card containers** (P02 / P09 / P10 / P14):
- 行高 = 1.5 × body
- 全幅留白驱动，文字块用大段空白分隔，不依赖分隔线

---

## VI. Icon Usage Specification

### Source

- **Generic library**: `tabler-outline`（stroke-width **1.5**）—— 仅在极少处点缀
- **Brand library**: `simple-icons`（仅 P13 当代品牌墙使用）

> 瑞士极简的本意是去装饰，本 deck 主体不依赖图标承担信息；图标只在 P13 充当品牌识别符号。其他页面以纯字体 + 几何 + 留白构成。

### Recommended Icon List

| Purpose | Icon Path | Page |
| ------- | --------- | ---- |
| 引文符号（可选） | `tabler-outline/blockquote` | P02 |
| 网格示意 | `tabler-outline/grid-3x3` | P08（小标记） |
| Apple logo | `simple-icons/apple` | P13 |
| Google logo | `simple-icons/google` | P13 |
| Spotify logo | `simple-icons/spotify` | P13 |
| Airbnb logo | `simple-icons/airbnb` | P13 |
| IBM logo | `simple-icons/ibm` | P13 |
| Lufthansa logo | `simple-icons/lufthansa` | P13 |

---

## VII. Visualization Reference List

Catalog read: 71 templates

| Page | Template | Path | Summary-quote (verbatim) | Usage |
| ---- | -------- | ---- | ------------------------- | ----- |
| P03 | timeline | `templates/charts/timeline.svg` | "Pick for 3-8 milestone events on a horizontal time axis (no duration). Skip for tasks with start/end ranges (use gantt_chart) or vertical layout (use roadmap_vertical)." | 瑞士风格的双源头年代节点（1896 Akzidenz / 1908 Basel / 1918 Keller / 1936 JMB / 1957 Helvetica） |
| P04 | vertical_list | `templates/charts/vertical_list.svg` | "Pick for 3-6 numbered key points each with a short description — design principles, core tenets, action items, key takeaways, recommendations, executive summary points. Skip for icon-style cards (use icon_grid) or sequential steps (use numbered_steps)." | 八条核心原则（8 项编号清单 + 极短描述） |
| P05 | team_roster | `templates/charts/team_roster.svg` | "Pick for 3-12 leadership/team profile cards (photo + name + title + short bio). Skip for reporting hierarchy (use top_down_tree)." | 关键人物群像（8 位代表性设计师卡片，无照片用名字 + 生卒 + 一行贡献） |
| P06 | timeline | `templates/charts/timeline.svg` | "Pick for 3-8 milestone events on a horizontal time axis (no duration). Skip for tasks with start/end ranges (use gantt_chart) or vertical layout (use roadmap_vertical)." | Müller-Brockmann 生平节点（1914 / 1936 / 1950 / 1957 / 1958 / 1981 / 1996） |
| P07 | comparison_columns | `templates/charts/comparison_columns.svg` | "Pick for 2-4 pricing/service tier cards in side-by-side columns (marketing layout). Skip for dense feature comparison (use comparison_table)." | 三款字体对比（Akzidenz-Grotesk / Helvetica / Univers）卡片化对比 |
| P08 | quadrant_text_bullets | `templates/charts/quadrant_text_bullets.svg` | "Pick for any 2×2 framework where each quadrant holds a titled bullet list — SWOT (Strengths/Weaknesses/Opportunities/Threats, internal-external × helpful-harmful), Ansoff (Existing/New Markets × Existing/New Products), or any named two-axis matrix with text content. Skip for items plotted as points (use matrix_2x2) or bubble-sized portfolios (use quadrant_bubble_scatter)." | 网格四种类型 2×2（手稿 / 列状 / 模数 / 层级） |
| P11 | icon_grid | `templates/charts/icon_grid.svg` | "Pick for 4-9 parallel features/capabilities/services as icon cards — feature grid, service lineup, benefits matrix, brand values, product highlights. Skip for sequential ordering (use numbered_steps) or hierarchical layers (use pyramid_chart)." | 输出到企业 VI / 机场标识 / 出版业 / 教育的四象限（这里用文字而非彩色 icon） |
| P12 | numbered_steps | `templates/charts/numbered_steps.svg` | "Pick for 3-6 horizontal sequential steps with numeric emphasis — how-it-works section, getting-started guide, methodology overview, implementation phases. Skip if steps need connector arrows (use process_flow) or named output artifacts (use pipeline_with_stages)." | 数字时代延续（960 Grid → Bootstrap 12 → CSS Grid → Design Systems 四阶段） |
| P13 | icon_grid | `templates/charts/icon_grid.svg` | （same as P11） | 当代品牌身影（六个品牌 logo 网格） |

**Runners-up considered**:

- `numbered_steps` | rejected for P04: 八原则不是 sequential 步骤，更适合 vertical_list 的"编号 + 描述卡"形式，避免暗示顺序依赖
- `concentric_circles` | rejected for P10: 同心圆把"留白即结构"具象化反而破坏了 negative-space-driven 的本意；P10 走 no-template 自由留白
- `comparison_table` | rejected for P07: 三款字体只需简洁三列卡，feature-row 矩阵密度过高，违反"密而清"中"清"的边界

---

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Layout pattern | Acquire Via | Status | Reference | text_policy | page_role |
| -------- | --------- | ----- | ------- | ---- | -------------- | ----------- | ------ | --------- | ----------- | --------- |
| cover_bg.jpg | 1280×720 | 1.78 | 封面 hero 背景 | Background | #38 image-as-canvas with text-block inset + #1 full-bleed background with floating title | ai | Pending | 一组瑞士网格几何抽象：横竖黑色细线网格在纯白底上构成 4×3 矩阵，一枚红圆悬于第三列第二行的网格交点，左下区域留大块纯白用于压标题；构图严格对称去中心，几何 absolutely 主导 | none | hero_page |
| negative_space.jpg | 1280×720 | 1.78 | P10 留白即结构 hero | Background | #46 image-as-canvas with caption-stripe overlay + #39 image-as-canvas with mega-headline | ai | Pending | 纯白画面中央偏左 1/3 处一枚 80px 直径红色实心圆，右下角一根 1px 黑色水平基线长度仅占画面 12%；其余 90% 纯白；红圆与黑线之间形成隐性张力，整画是"留白"本身的论证 | none | hero_page |
| closing_grid.jpg | 1280×720 | 1.78 | P14 结语 hero | Background | #38 image-as-canvas with text-block inset + #29 two-stop scrim | ai | Pending | 由细密的黑色网格线（间距 16px）铺满整个画面，网格交点处部分高亮成红点形成稀疏星图，构图严格几何；左下 1/3 留出 8% 不透明白色叠层用于浮文字 | none | hero_page |

> 三张图全部 `minimalist-swiss × mono-ink`，rendering + palette 由 §III AI Image Strategy 提供；Reference 字段不重复 style 词与 HEX。

---

## IX. Content Outline

### Part 1: 引入

#### Slide 01 - 封面

- **Audience move**: 把网格当作排版工具 → 意识到它是一种“看世界的方式”
- **Relationships**: 主标题与英文副题为 parent;三位人物/字体名 membership 于瑞士风格;其余 none

- **Layout**: Full-bleed + floating text（封面 hero）
- **Title**: 网格系统
- **Subtitle**: The Grid as a Way of Seeing
- **Info**: A Lecture on Swiss International Typographic Style · 2026

#### Slide 02 - 引言

- **Audience move**: 以为网格是保证 → 听到布罗克曼说它只是辅助、需要练习
- **Relationships**: 引文与出处为 parent;“aid”与“guarantee”为 contrast

- **Layout**: Asymmetric split 3:7（左侧大引号 + 右侧引文）
- **Title**: （无标题；引文直接是 hero）
- **Content**:
  - "The grid system is an aid, not a guarantee. It permits a number of possible uses and each designer can look for a solution appropriate to his personal style. But one must learn how to use the grid; it is an art that requires practice."
  - — Josef Müller-Brockmann, *Grid Systems in Graphic Design*, 1981

### Part 2: 历史与原则

#### Slide 03 - 双源头

- **Audience move**: 以为风格一夜诞生 → 看到 1896–1957 六十年的双源头累积
- **Relationships**: 各年份事件为 order(时间线);两条源头为 contrast;每个事件与说明为 parent

- **Layout**: Top-bottom split（上方时间轴，下方简短叙述）
- **Title**: 双源头 · 1896 → 1957
- **Visualization**: timeline
- **Content**:
  - 1896 Akzidenz-Grotesk 由 Berthold 铸字行发行
  - 1908 Basel School of Design 改革
  - 1918 Ernst Keller 入苏黎世应用艺术学院
  - 1936 Müller-Brockmann 开设工作室
  - 1957 Helvetica + Univers 同年问世
  - 一句结论：理性主义不是凭空到来，而是来自半个世纪的字体 + 学校 + 教学

#### Slide 04 - 八条核心原则

- **Audience move**: 只知道“瑞士风”这个词 → 记住八条核心原则
- **Relationships**: 八条原则为 order(01–08);八者 membership 于同一体系;中英标题为 parent

- **Layout**: Vertical list（编号 + 一行原则 + 注释）
- **Title**: 八条核心原则
- **Visualization**: vertical_list
- **Content**:
  1. 客观先于表达 · Objectivity over expression
  2. 数学网格为骨架 · Mathematical grid
  3. 非对称构图 · Asymmetric layout
  4. 无衬线字体 · Sans-serif typography
  5. 齐左不齐右 · Flush-left ragged-right
  6. 客观摄影 · Objective photography
  7. 留白是结构 · Negative space as structure
  8. 可重复可规模化 · Reproducible at scale

#### Slide 05 - 关键人物

- **Audience move**: 把风格归功于一个人 → 认识八位共同建造者
- **Relationships**: 八位人物为 order;每人与其贡献为 parent;八者 membership 于瑞士学派

- **Layout**: Four-column cards × 2 行（8 人）
- **Title**: 八位塑造者
- **Visualization**: team_roster
- **Content**:
  - Ernst Keller (1891–1968) · 苏黎世学派奠基
  - Théo Ballmer (1902–1965) · 网格早期实验者
  - Max Bill (1908–1994) · 包豪斯→乌尔姆
  - Emil Ruder (1914–1970) · 巴塞尔 Typographie
  - Armin Hofmann (1920–2020) · 巴塞尔海报
  - Josef Müller-Brockmann (1914–1996) · 苏黎世 Grid Systems
  - Max Miedinger (1910–1980) · 1957 设计 Helvetica
  - Adrian Frutiger (1928–2015) · 1957 设计 Univers

#### Slide 06 - Müller-Brockmann

- **Audience move**: 只知道布罗克曼的名字 → 用七个时刻理解他的一生
- **Relationships**: 七个时刻为 order(生平);人物档案与时刻 parent;年份与事件 link

- **Layout**: Top-bottom split（上方时间轴，下方关键事件文字）
- **Title**: Josef Müller-Brockmann · 1914–1996
- **Visualization**: timeline
- **Content**:
  - 1914 生于瑞士拉珀斯维尔
  - 1936 苏黎世独立工作室
  - 1950 Tonhalle Musica Viva 海报系列起
  - 1957 苏黎世应用艺术学院教授
  - 1958 创办 *Neue Grafik* 期刊
  - 1981 出版 *Grid Systems in Graphic Design*
  - 1996 在 Unterengstringen 逝世

### Part 3: 字体与网格

#### Slide 07 - 三款决定性字体

- **Audience move**: 分不清三款无衬线 → 记住 Akzidenz / Helvetica / Univers 的年份与差异
- **Relationships**: 三款字体为 contrast;每张卡片的字样与说明为 parent;年份 order

- **Layout**: Three-column cards
- **Title**: 三款决定性字体
- **Visualization**: comparison_columns
- **Content**:
  - **Akzidenz-Grotesk · 1896** · Berthold · 第一款现代意义的商业无衬线 · 瑞士学派早期首选
  - **Helvetica · 1957** · Miedinger + Hoffmann · 拉丁文"瑞士"为名 · 中性客观可读至极
  - **Univers · 1957** · Frutiger · 21 字重首次数字坐标系统化 · 字体家族工程的开端

#### Slide 08 - 网格四种类型

- **Audience move**: 只会用列网格 → 知道四种网格类型及各自适用场景
- **Relationships**: 四种类型为 order(01–04);每种与适用场景为 parent;四者 membership 于布罗克曼 1981 分类

- **Layout**: Matrix grid 2×2
- **Title**: 网格四种类型
- **Visualization**: quadrant_text_bullets
- **Content**:
  - **手稿网格 Manuscript** · 单栏 · 古老 · 长文唯一选项
  - **列状网格 Column** · 多栏并列 · 期刊与报纸的语法
  - **模数网格 Modular** · 横列 × 纵行的方格矩阵 · 海报与目录利器
  - **层级网格 Hierarchical** · 不规则但内部有逻辑 · 复合排版

#### Slide 09 - 模数网格示意

- **Audience move**: 凭感觉定尺寸 → 看到一切尺寸如何从 16px 基本单位派生
- **Relationships**: BASE UNIT 与所有派生尺寸为 parent;各派生值之间 membership;倍数关系 link

- **Layout**: Asymmetric split 2:8（左侧数值说明，右侧 SVG 几何绘制 8×6 模数图）
- **Title**: 一切都是可计算的
- **Content**:
  - 列宽 = 264px · 列间距 = 32px · 行高 = body × 1.5
  - 安全边距 = 64px = 4 × 16px 基础模数
  - 右侧画出 4×6 模数网格，每格 264×96，红色线标记一个跨 3 列的图像区

#### Slide 10 - 留白即结构

- **Audience move**: 把留白当剩余 → 理解留白即结构、是信息载体
- **Relationships**: 红圆与黑线为 contrast(唯一两个元素);留白与元素为 link(张力来源);标题与论点 parent

- **Layout**: Negative-space-driven（90% 纯白 + 一枚红圆 + 一行短句）
- **Title**: 留白即结构
- **Content**:
  - 一句：留白不是剩余，留白是信息的载体
  - 一句：The space between is the message
  - hero 图作为整页主体（red dot + 极细水平线）

### Part 4: 影响与遗产

#### Slide 11 - 输出到现代世界

- **Audience move**: 觉得瑞士风只存在于海报 → 看到它输出到企业 VI 等四个方向
- **Relationships**: 四个输出方向为 membership;每个方向与案例为 parent;1960s 起点 order

- **Layout**: Four cards
- **Title**: 输出到现代世界 · 1960s →
- **Visualization**: icon_grid
- **Content**:
  - **企业 VI** · IBM、Knoll、Lufthansa · 把瑞士理性变成"识别系统"产业
  - **机场 / 地铁标识** · 纽约 Unimark、巴黎机场 Frutiger 字体
  - **出版业** · *Du* 杂志、*Eye*、*Domus* 的版面语法
  - **设计教育** · 巴塞尔与苏黎世学派学生散播至全球

#### Slide 12 - 数字时代的延续

- **Audience move**: 以为网格止于纸面 → 看到 960 Grid 到今天的屏幕网格谱系
- **Relationships**: 各年份系统为 order(2008 → 今天);每个系统与说明为 parent;栏数 link 于纸面网格

- **Layout**: Top-bottom split（上方四阶段，下方一行论断）
- **Title**: 数字时代的延续
- **Visualization**: numbered_steps
- **Content**:
  - 01. 960 Grid System · 2008 · 第一次把网格语法搬上 Web
  - 02. Bootstrap 12 栏 · 2011 · 模数网格民主化
  - 03. CSS Grid · 2017 · 浏览器原生网格
  - 04. Design Systems · 2020s · 大企业 VI 在屏幕上的延续

#### Slide 13 - 当代品牌的瑞士血脉

- **Audience move**: 不知道瑞士血脉在哪 → 在六个当代品牌里认出它
- **Relationships**: 六个品牌为 membership;每个品牌与继承点为 parent;六者与瑞士网格 link

- **Layout**: Six icon cards 3×2
- **Title**: 当代品牌的瑞士血脉
- **Visualization**: icon_grid
- **Content**:
  - Apple · 极简理性产品语言
  - Google · Material 网格 + 几何字体
  - Spotify · 杂志感版面语法
  - Airbnb · 模数 grid + 极简识别
  - IBM · 1967 起的瑞士血统（JMB 任顾问）
  - Lufthansa · Otl Aicher 1962 VI 至今

#### Slide 14 - 结语

- **Audience move**: 把网格当限制 → 接受“网格是自由的语法”
- **Relationships**: 中英结语为 parent;“限制”与“自由”为 contrast;结语 link 回 P02 引文

- **Layout**: Full-bleed + floating text（封面回声）
- **Title**: 网格不是限制
- **Subtitle**: 是自由的语法
- **Info**: The grid is not a constraint. It is a grammar of freedom.

---

## X. Speaker Notes Requirements

- **Filename**: 对应 SVG 文件名（`01_cover.svg` → `notes/01_cover.md`）
- **Tone**: 半正式的 lecture 口吻 + 偶尔现场示例（指代台上视觉元素）
- **Length per page**: 80-180 字中文（约 30-60 秒语速）
- **Total presentation duration**: 25 分钟（14 页平均 ~107 秒/页）
- **Purpose**: 教学 + 启发，让设计师重新理解"网格作为系统而非装饰"

---

## XI. Technical Constraints Reminder

### SVG Generation Must Follow

1. viewBox: `0 0 1280 720`
2. 背景用 `<rect>`
3. 文字换行用 `<tspan>`（禁 `<foreignObject>`）
4. 透明度默认用 `fill-opacity` / `stroke-opacity`；`rgba()` 保持转换兼容
5. 禁 `mask` / `<style>` / `class` / `foreignObject`
6. 禁 `textPath` / `animate*` / `script`
7. 字符用 Unicode（`—` `–` `©` `®` `→` 等），HTML 实体禁
8. `marker-start` / `marker-end` 仅在 `<defs>` 内三角/菱形/圆形且 `orient="auto"`
9. `clipPath` 仅用于 `<image>`，单 shape 子元素

### Project-specific

- 严格无圆角（rx = 0）—— 瑞士极简核心；唯一例外是品牌 logo 来自 simple-icons 内置
- 严格无渐变 —— `linearGradient` / `radialGradient` 整 deck 不出现
- 严格无阴影 —— `filter` 整 deck 不出现
- 仅四色 —— 白 / 黑 / 朱红 / 浅灰（border）；蓝色每次出现需自检为何不能用红替代
