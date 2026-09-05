<!-- ppt-master-schema: design-spec/v1 -->
# uv_launch - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | uv_launch |
| Canvas Format | ppt169 (1280×720) |
| Page Count | 14 |
| Primary Language | zh-CN |
| Target Audience | 中文 Python 开发者与技术负责人:日常靠 pip + venv + requirements.txt 干活,听说过 uv 但没系统了解,关心迁移成本与"能不能今天就用" |
| Communication Intent | 先讲清 uv 到底替掉了哪些日常摩擦(说明,最高优先级),再用官方文档与 Astral 自己公布的基准说法建立可信度(说服),最后给一条今天就能执行的第一步(动员);顺序即优先级 |
| Desired Audience Outcome | 听完能说出 uv 收编了哪几件工具、能复述项目工作流的四条命令、知道哪些能力还挂着 preview 标记、并且愿意在自己的一个项目上跑通第一条命令 |
| Core Message / Ask / Action | uv 是一个 Rust 写的单二进制,把 pip / pip-tools / pipx / pyenv / virtualenv / twine 那一摊收进一套命令,并给出跨平台 lockfile;所有性能倍数都来自 Astral 在 macOS 上的测量,不是听众自己机器上的结果 |
| Delivery Context | 主用途:presenter-led 的团队内部技术分享,约 25–30 分钟;次要用途:会后当作迁移参考文档自读 |
| Artifact Afterlife | 供团队传阅与复用,作为是否迁移到 uv 的决策参考材料 |
| Reading Mode | balanced |
| Content Strategy | 贴近源:命令、终端输出、版本号、发布日期一律照官方文档与 CHANGELOG 原样引用,不改写、不取整、不合并;中文只用于解释与串联 |
| Design Style | Direction 2「终端里的深色发布会」:showcase 叙事 + dark-tech 视觉,深底之上让终端块与倍数数字自己发光 |
| AI Image Acquisition Path | not applicable(本 deck 不使用 AI 图像) |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 工作流默认值(Stage 2 主动建议 true,用户未反对) |
| Custom Animations | enabled — 用户在任务书中显式要求写 animations.json 并给出 Morph 与入场要求 |
| Narration Audio | disabled — 工作流默认值 |
| Created Date | 2026-09-05 |

- **Template Application**: 采用 library Style `product-launch` 的沟通方法与评估口径,不引入任何原型或结构:§II 的"先演示再命名""标题写用户得到什么""已发布/preview/计划中必须一眼分开""每个性能数字带测量口径与日期"整段照用;§III 的九个页面角色作为骨架来源,按实际内容决定各角色占几页;§IV 的证据纪律照用(图表只在数字本身是重点时使用,轴不裁、基线不省,数字紧邻其出处)。§V 的 `photo-editorial` 与 §VI 的 `corporate-photo` 不采纳——本 deck 没有任何照片或产品界面截图可用,照片主导的构图语言在这里会落空;改用 dark-tech,把 §V "让画面保持中性或深色,让主角占住视线"和"只留一个强调色"的意图用终端块+发光强调色实现。页面为 flat 自由设计。

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | ppt169 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 上下 56px,左右 72px |
| Content Area | x 72–1208,y 56–664(可用 1136 × 608) |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: showcase
- **Mode Behavior**: 按发布会节奏推进:每页只放一个能力、一个收益或一个时刻,并且先让终端跑出来的东西占住画面,再用标题给它命名。张力页只讲听众自己每天在经历的那件麻烦事,定位页把主张单独给整页,能力页让"制品"(终端窗口、命令序列、文件树)主导而说明退到从属位置,证据页只留一个主数字。整卷不把两个 reveal 塞进一页,也不用图标阵列冒充能力清单。
- **Visual style**: custom
- **Visual Style References**: dark-tech
- **Visual Style Behavior**: 深色画布上做几何精确的分区:整页由一个近黑蓝底 + 若干抬起一档的面板构成,面板用 1px 细线勾边而不是投影堆叠。终端块是本卷的主角载体——等宽字、左侧命令提示符列、深一档的窗口底、顶部一条极细的窗口条,窗口边缘用主色发一层很淡的辉光标记"这是正在跑的东西"。强调色只用在三处:reveal 的那一件事、改善的那一侧、结尾的那一个动作。数字用等宽字放到很大,靠字号而不是装饰建立层级。装饰只有细线、细网格和方角/微圆角(4px)的面板,不用渐变网格、不用漂浮粒子、不用多层阴影。
- **Theme**: 一个二进制把一摊工具收干净——整卷的连续物是"终端窗口":它在张力页是六个各自为政的小窗,在定位页合成一个,在能力页放大成主角,在结尾缩回一条可以照抄的命令。
- **Tone**: 克制、工程口吻、有把握但不吹;所有倍数与版本号都紧挨着出处和日期出现。

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #0B1220 | 整卷页底,近黑的深蓝,让终端块和数字自己发光 |
| Secondary background | #131C2E | 面板、终端窗口底、表格底,比页底抬起一档 |
| Primary | #4CC9F0 | 主强调:reveal 的那一件事、终端窗口的辉光边、命令关键字、当前页的标记 |
| Accent | #FF8A3D | 改善侧与结尾动作的唯一强调色,也用于 uv 一侧的对照 |
| Secondary accent | #A78BFA | 仅用于 preview 状态标记与次级注记,不参与常规强调 |
| Body text | #E6EDF3 | 正文与终端输出文字 |
| Secondary text | #9BA9BC | 注记、出处行、页脚、表格次要列 |
| Divider | #243349 | 分隔线、面板描边、表格行线 |

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Display | 无衬线/重字重,封面与收束页的主张尺度 | Microsoft YaHei | Arial | sans-serif |
| Title | 无衬线/中等字重,靠字号建立层级 | Microsoft YaHei | Arial | sans-serif |
| Body | 无衬线/常规字重,长段中文可读 | Microsoft YaHei | Arial | sans-serif |
| Code | 等宽/终端口吻,数字为等宽等高数字 | Consolas | Consolas | monospace |
| Data | 等宽/超大号,倍数与版本号 | Consolas | Consolas | monospace |
| Annotation | 无衬线/小号,出处与口径 | Microsoft YaHei | Arial | sans-serif |

- **Display stack**: Microsoft YaHei, Arial, sans-serif
- **Title stack**: Microsoft YaHei, Arial, sans-serif
- **Body stack**: Microsoft YaHei, Arial, sans-serif
- **Code stack**: Consolas, monospace
- **Data stack**: Consolas, monospace
- **Annotation stack**: Microsoft YaHei, Arial, sans-serif
- **Role rationale**: Display 承担封面与收束页的主张尺度(anchor 页共三处),与 Title 同族但另立锚点,避免结构性标题依赖执行期的稀疏例外;Code 与 Data 另立等宽族——终端输出与命令必须列对齐,倍数/版本号需要等高数字;两者共用 Consolas 但字号锚点不同,Data 是页面主角尺度,Code 是可读的正文尺度。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Display | 64 |
| Title | 42 |
| Subtitle | 32 |
| Lead | 30 |
| Data | 88 |
| Code | 20 |
| Annotation | 18 |
| Footnote | 16 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 视线先落在页面主角(终端块、大数字、对照表),再上移读标题,最后下移到出处行;标题与主角不争夺同一区域。
- **Composition tendency**: 单焦点为主——reveal 与 demonstration 页给主角整幅或近整幅,说明退到一侧的窄栏;landscape、availability、来源页允许多区,但每区仍只讲一件事。
- **Cross-page continuity**: 终端窗口的窗口条与左侧提示符列在整卷保持同一形制;右下角固定一条极细的出处行位置;强调色的用法在整卷保持同一含义。
- **Spacing posture**: variable by page rhythm——anchor 页最松,dense 页允许信息密但仍留出主角呼吸区。
- **Spacing anchors**: 页边距 72px;块间距 32px;栏间距 40px;圆角 4px;正文行高 1.6(38px)。

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2
- **Brand-logo library**: simple-icons(内容里出现的真实品牌:Python、PyPI、GitHub、Rust、Astral,以及三个平台标)

| Icon Path | Suitable Scenarios |
| --- | --- |
| tabler-outline/terminal-2 | 终端、命令、演示时刻 |
| tabler-outline/package | 包、依赖、安装 |
| tabler-outline/bolt | 速度、性能主张 |
| tabler-outline/lock | lockfile、可复现 |
| tabler-outline/versions | Python 版本管理、多版本切换 |
| tabler-outline/rocket | 发布、上手、第一步 |
| tabler-outline/download | 安装方式、获取渠道 |
| tabler-outline/tool | 工具运行与安装(uvx / uv tool) |
| tabler-outline/file-code | 脚本、内联依赖元数据 |
| tabler-outline/box | 虚拟环境、项目环境 |
| tabler-outline/clock-bolt | 冷/热缓存、耗时对比 |
| tabler-outline/check | 已发布状态 |
| tabler-outline/arrow-right | 迁移方向、前后对照 |
| tabler-outline/alert-triangle | preview / 有条件、注意事项 |
| tabler-outline/world | 跨平台、跨机器可复现 |
| tabler-outline/stack-2 | 能力全景、多层结构 |
| tabler-outline/refresh | 自更新、缓存清理 |
| tabler-outline/route | 迁移路径、下一步 |
| simple-icons/python | Python 生态 |
| simple-icons/pypi | 包索引 |
| simple-icons/github | 源码与 CHANGELOG 出处 |
| simple-icons/rust | uv 用 Rust 写成 |
| simple-icons/astral | uv 背后的 Astral |
| simple-icons/linux | 支持平台 |
| simple-icons/apple | 支持平台(也是 Astral 基准的测量平台) |
| simple-icons/windows | 支持平台 |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P08 | table | comparison_matrix | 把同一件任务的传统命令与 uv 命令逐行对齐,让改善被看见而不是被断言 |
| P09 | chart | column_chart | 用 Astral 自己公布的倍数下限比较冷缓存与热缓存两种场景 |
| P11 | table | feature_matrix | 按能力 × 状态展示已发布与 preview 的分界及其出处版本 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

> 本 deck 的图像来源为 `none`:开发者工具的"制品"就是终端与它的输出,没有任何可用的产品界面截图、实物或现场照片;Style §VI 明确禁止把不存在的界面画成近似图形冒充产品真实输出,AI 生成的假终端也属同一禁区。所有视觉主角由原生 SVG 的终端块、原生表、原生图表与图标承担。

## IX. Content Outline

### Part 1: 张力与定位

#### Slide 01 - 封面:一个二进制,收干净一摊工具

- **Audience move**: 以为这又是一个"再来一个包管理器" → 认出这是把一整摊工具收编成一个入口的东西
- **Relationships**: 主张(一个二进制收编一摊工具)与其身份证明(版本 0.12.10、发布日期 2026-09-04、Rust、Astral)是 parent 关系;六个被收编的工具名之间是 membership,并与主张 contrast
- **Cover impact**: hook = 官方首页开门那句「An extremely fast Python package and project manager, written in Rust.」与它取代的六个工具名并置;composition Reference = 六个小终端窗名牌散在深底上,一个亮起的 uv 窗压在中央
- **Composition**: 单焦点。中央一块发光的终端窗承担主标题,六个工具名以熄灭状态围绕
- **Title**: 一个二进制,把 Python 装包的那一摊收干净
- **Core message**: uv 不是又一个包管理器,而是把 pip、pip-tools、pipx、poetry、pyenv、twine、virtualenv 的职责收进同一个命令入口
- **Content**: · 主标题句 · 副标题:极快的 Python 包与项目管理器,用 Rust 写成(docs.astral.sh/uv 首页原句译述,英文原句同页保留)· 身份行:uv 0.12.10 · 2026-09-04 发布 · 六个熄灭的工具名:pip / pip-tools / pipx / pyenv / virtualenv / twine · 页脚出处行
- **Fact IDs**: 源自 `sources/uv.md` Highlights 第 1 条与 `sources/uv_CHANGELOG.md` 0.12.10 段
- **Motion suggestion**: 六个工具名先在,uv 窗后亮;为 P02 的散落状态留出承接
- **page_rhythm**: anchor

#### Slide 02 - 你每天在修的,是工具之间的缝

- **Audience move**: 觉得"现在这套也能用" → 认出自己每天花的时间都花在工具边界上
- **Relationships**: 六件工具各管一段职责,彼此是 membership;职责之间的缝(谁装 Python、谁锁版本、谁建环境、谁发包)与"低信心体验"这一结论是 link
- **Composition**: 六个小终端窗横向排开、各自孤立,下方一条引用带承载 Astral 的原话
- **Title**: 你每天在修的,不是包,是工具之间的缝
- **Core message**: 传统链路里没有一件工具对"从零到能跑"负全责,缝隙就是每天被消耗掉的时间
- **Content**: · 六件工具各自的职责一行一件(装包 / 锁版本 / 跑命令行工具 / 管 Python 版本 / 建虚拟环境 / 发包)· 缝在哪:装 Python 与装包是两套、锁文件不跨平台、环境重建慢 · Astral 博文原话引用:「Python tooling can be a low-confidence experience: it's a significant amount of work to stand up a new or existing project, and commands fail in confusing ways.」(astral.sh/blog/uv,2024-02-15)· 出处行
- **Motion suggestion**: 六个窗依次入场制造"各自为政"的感觉;它们是 P03 汇聚动作的承接物
- **page_rhythm**: dense

#### Slide 03 - 它把这一摊收成一个命令入口

- **Audience move**: 知道有缝 → 知道 uv 的定位就是把缝消掉,而不是再加一件工具
- **Relationships**: 定位主张与它取代的工具清单是 contrast;主张与三条支撑属性(Rust 单二进制 / 不依赖 Python 即可安装 / 跨平台 lockfile)是 parent
- **Composition**: 主张独占上半页,六个工具名在下方汇聚进一个 uv 块;右侧一条窄栏放三条支撑属性
- **Title**: 一个入口,替掉一整排命令
- **Core message**: uv 的定位是「A single tool to replace pip, pip-tools, pipx, poetry, pyenv, twine, virtualenv, and more」——这句话来自官方首页,不是市场话术
- **Content**: · 定位句(引官方首页 Highlights 第 1 条,英文原句 + 中文解释)· 三条支撑:用 Rust 写成的单个静态二进制 / 不需要先有 Rust 或 Python 就能装 / 提供跨平台的 uv.lock · 一条口径提醒:后面每一个倍数都会标出它是谁在什么机器上什么时候测的 · 出处行 + 超链接 https://docs.astral.sh/uv/
- **Motion suggestion**: 承接 P02 的六个工具窗,让它们移动并合成中央的 uv 块
- **page_rhythm**: anchor

### Part 2: 能力与演示

#### Slide 04 - 从零到能跑,只有四条命令

- **Audience move**: 想知道"具体怎么用" → 记住 init / add / run / lock 这四个动作及其先后
- **Relationships**: 四条命令之间是 order;每条命令与它产生的文件(pyproject.toml / uv.lock / .venv)是 link
- **Composition**: 左侧一列四条命令按序排列,右侧一个终端窗预览;终端窗保持整卷同一形制
- **Title**: 从零到能跑,你只需要记住四个动作
- **Core message**: uv init 建项目、uv add 加依赖、uv run 跑命令、uv lock 锁版本——四个动作覆盖日常项目工作流的绝大部分
- **Content**: · uv init:建项目,生成 pyproject.toml、.python-version、README.md 与 src/ 布局 · uv add:加依赖,同时更新 lockfile 与项目环境 · uv run:在项目环境里跑命令,跑之前先校验 lockfile 与 pyproject.toml 是否一致 · uv lock:生成/更新跨平台 uv.lock · 一句机制说明:uv 会在你第一次跑项目命令时自动建 .venv 与 uv.lock(引 docs.astral.sh/uv/guides/projects/)
- **Fact IDs**: 源自 `sources/Working_on_projects_uv.md` 与 `sources/Features_uv.md` Projects 段
- **Motion suggestion**: 右侧终端窗是 P05 放大动作的承接物,四条命令依序进场
- **page_rhythm**: dense

#### Slide 05 - 看它跑一遍(官方文档原样输出)

- **Audience move**: 听说很快 → 亲眼看到一次完整会话的真实输出与耗时
- **Relationships**: 会话内五条命令是 order;每条命令与其输出行是 parent
- **Composition**: 终端窗占满画面主体,只留标题带与一条出处行;窗内不做任何删改
- **Title**: 看它跑一遍:五条命令,一次装完
- **Core message**: 官方文档给出的这段会话是可以逐字核对的——命令、输出、耗时都照抄,没有加速也没有剪辑
- **Content**: · 终端块逐行原样引用 docs.astral.sh/uv 首页 Projects 段:`uv init example` → `Initialized project 'example' at '/home/user/example'`;`uv add ruff` → `Creating virtual environment at: .venv` / `Resolved 2 packages in 170ms` / `Prepared 2 packages in 627ms` / `Installed 2 packages in 1ms` / `+ ruff==0.5.4`;`uv run ruff check` → `All checks passed!`;`uv lock` → `Resolved 2 packages in 0.33ms`;`uv sync` → `Resolved 2 packages in 0.70ms` / `Checked 1 package in 0.02ms` · 一行口径说明:这是官方文档页上的示例会话,机器与网络条件未公布;本页不做任何本机复测
- **Fact IDs**: 源自 `sources/uv.md` Projects 段
- **Motion suggestion**: 由 P04 右侧的小终端窗放大而来,窗体是承接物;窗内各行按命令顺序揭示
- **page_rhythm**: dense

#### Slide 06 - 一个脚本也能有自己的依赖

- **Audience move**: 以为脚本只能靠全局环境 → 知道单文件脚本可以自带依赖声明并在隔离环境里跑
- **Relationships**: 「给脚本加依赖」与「在隔离环境跑脚本」是 order;`uvx` 与 `uv tool install` 是 contrast(临时 vs 常驻)
- **Composition**: 上下两个终端块——上块是脚本内联依赖,下块是 uvx 临时运行;右侧窄栏放一句区分
- **Title**: 一个脚本也能有自己的依赖,不用先建环境
- **Core message**: uv 把「脚本」和「命令行工具」也纳入同一套命令,不需要为它们各自准备环境
- **Content**: · 脚本:`uv add --script example.py requests` 写入内联依赖元数据 → `uv run example.py` 输出 `Reading inline script metadata from: example.py` / `Installed 5 packages in 12ms` / `<Response [200]>`(引官方首页 Scripts 段)· 工具:`uvx` 是 `uv tool run` 的别名,在临时环境里跑;`uv tool install ruff` 装成常驻可执行文件 · 区分:临时用 uvx,常用就 install
- **Fact IDs**: 源自 `sources/uv.md` Scripts / Tools 段与 `sources/Features_uv.md`
- **page_rhythm**: dense

#### Slide 07 - Python 本身也由它来装

- **Audience move**: 还在用 pyenv 或系统 Python → 知道 Python 版本这一层也被同一个二进制接管
- **Relationships**: 「装版本」「按需下载」「钉住版本」三件事是 order;它们与 pyenv 的职责是 contrast
- **Composition**: 单个终端块居中,左侧一列三个动作标签与图标
- **Title**: 连 Python 版本也归它管,不用再装一个 pyenv
- **Core message**: uv python install / uv python pin 把版本管理收进同一个入口,uv venv --python 还能按需下载缺失的版本
- **Content**: · `uv python install 3.10 3.11 3.12` 一次装多个版本 · `uv venv --python 3.12.0` 需要时按需下载 · `uv python pin 3.11` 写入 `.python-version` 钉住当前目录 · 一行说明:`.python-version` 决定 uv 给这个项目建环境时用哪个版本(引 docs.astral.sh/uv/guides/projects/)
- **Fact IDs**: 源自 `sources/uv.md` Python versions 段与 `sources/Working_on_projects_uv.md`
- **page_rhythm**: dense

### Part 3: 对照与证据

#### Slide 08 - 同一件事,两套命令

- **Audience move**: 担心迁移要重学 → 看到每一件熟悉的事都有一条一一对应的 uv 命令
- **Relationships**: 每一行的「传统命令」与「uv 命令」是 link;所有行之间是 membership(同一张迁移对照)
- **Composition**: 一张对照表占据主体,uv 一侧用强调色标出;表下一条注记说明 uv pip 不是在调用 pip
- **Title**: 同一件事,你只是换了一条命令
- **Core message**: 迁移不是重学,而是逐条替换——uv 的 pip 接口刻意保持了熟悉的命令形状
- **Content**: · 原生对照表:建虚拟环境 `python -m venv .venv` → `uv venv`;装包 `pip install X` → `uv pip install X`;锁定 `pip-compile requirements.in` → `uv pip compile requirements.in`;同步 `pip-sync requirements.txt` → `uv pip sync requirements.txt`;跑命令行工具 `pipx run X` → `uvx X`;装 Python 版本 `pyenv install 3.12` → `uv python install 3.12` · 注记(引官方 pip 接口页原话):uv 不依赖也不调用 pip,这个名字只表示这组低层命令与 pip 的接口对齐 · 注记二:这些命令并非逐字实现 pip 的全部行为,越偏离常见工作流差异越可能出现
- **Visualization**: 原生对照表 `tool-replacement-matrix`(table/comparison_matrix,行=任务,列=传统命令 / uv 命令)
- **Native-ready**: tool-replacement-matrix=yes
- **Fact IDs**: 源自 `sources/The_pip_interface_uv.md`、`sources/Features_uv.md`、`sources/uv.md`
- **Motion suggestion**: 表格按行揭示,uv 一列稍后于传统一列到位
- **page_rhythm**: dense

#### Slide 09 - 快多少:Astral 自己是这么测的

- **Audience move**: 听过「10-100x」但不知道口径 → 知道倍数分冷/热两种场景,且知道它是谁在什么机器上测的
- **Relationships**: 冷缓存倍数与热缓存倍数是 contrast;两者与同一套测量条件(macOS、Python 3.12.4、Trio 的 docs-requirements.in)是 membership
- **Composition**: 一张两柱图占左侧主体,右侧一列放测量口径四行;口径与图表并列而不是缩到脚注
- **Title**: 快多少,取决于缓存是冷是热
- **Core message**: Astral 公布的倍数是「无缓存 8–10 倍、热缓存 80–115 倍」,这是 2024-02-15 在 macOS 上对 Trio 依赖集的测量,不是你机器上的结果
- **Content**: · 原生柱状图:冷缓存 8×、热缓存 80×(取 Astral 公布区间的下限,区间上限在柱旁标注为 10× 与 115×)· 测量口径四行:测量者 Astral;平台 macOS,非 uv 工具用 Python 3.12.4;对象 Trio 的 docs-requirements.in;日期 2024-02-15(博文)· 官方文档首页另给一个更粗的说法「10-100x faster than pip」,指向同一份 BENCHMARKS.md · 一条不确定性说明(引 BENCHMARKS.md 原文):不同操作系统与文件系统上表现可能差异很大,uv 在 macOS 用 reflink、在 Linux 用 hardlink;不同依赖集也会显著改变结果 · 明确一行:本 deck 未做本机复测,页面上不出现任何本机数字
- **Visualization**: 原生柱状图 `astral-speedup-claim`(chart/column_chart,两类:无缓存 / 热缓存,值为 Astral 公布倍数区间下限)
- **Native-ready**: astral-speedup-claim=yes
- **Fact IDs**: 源自 `sources/uv_Python_packaging_in_Rust.md`(8-10x / 80-115x 原句)、`sources/uv.md`(10-100x)、`sources/uv_BENCHMARKS.md`(测量条件与告诫)
- **page_rhythm**: anchor

### Part 4: 全景、边界与下一步

#### Slide 10 - 五个区块,可以分开用也可以合起来用

- **Audience move**: 担心是「全有或全无」的迁移 → 知道每个区块都能独立采用
- **Relationships**: 五个区块(Python 版本 / 脚本 / 项目 / 工具 / pip 接口)与 Utility 是 membership;官方原话说明它们之间是「可独立使用也可合并使用」的 link
- **Composition**: 五个等宽区块横向排列,每块一句职责与两三条代表命令;下方一条 Utility 带
- **Title**: 你可以只用其中一块,也可以整套换过来
- **Core message**: uv 的界面被官方切成可独立使用的几段,迁移可以从任意一段开始
- **Content**: · Python 版本:uv python install / list / find / pin / uninstall · 脚本:uv run / uv add --script / uv remove --script · 项目:uv init / add / remove / sync / lock / run / tree / build / publish · 工具:uvx(= uv tool run)/ uv tool install / uninstall / list · pip 接口:uv venv / uv pip install / compile / sync / freeze / tree · Utility:uv cache clean / prune / dir、uv self update · 官方原话依据:「uv's interface can be broken down into sections, which are usable independently or together.」
- **Fact IDs**: 源自 `sources/Features_uv.md`
- **Motion suggestion**: 五个区块作为 P11 状态表行标签的承接物,整体框架保持一致
- **page_rhythm**: dense

#### Slide 11 - 哪些已经稳定,哪些还挂着 preview

- **Audience move**: 以为文档里写的都能直接用 → 能分清已发布能力与需要显式开启的 preview 能力
- **Relationships**: 每个能力与它的状态是 link;「已发布」组与「preview」组是 contrast;preview 能力与其出处版本号是 parent
- **Composition**: 一张状态表占主体,两种状态用不同标记而不是只靠颜色;表下一条说明 preview 要显式开启
- **Title**: 分清哪些能拿来用,哪些要显式开启
- **Core message**: uv 把稳定与试验分得很清楚——0.12.0 一次稳定了一批旧 preview,而当前仍有一批能力需要显式加 --preview-features 才生效
- **Content**: · 已稳定(在 0.12.0,2026-07-28 发布):packaged-init(uv init 默认声明 build system)、target-workspace-discovery、venv-safe-clear、init-project-flag、project-directory-must-exist、publish-require-normalized、special-conda-env-names、toml-backwards-compatibility、adjust-ulimit · 仍在 preview:content-addressed-cache(缓存去重,0.12.6/0.12.8)、index-by-name(按名字选已配置的索引,0.12.5)、artifact-hash-filtering(0.12.6)、cache-physical-space(0.12.2)、missing-exclude-newer-package-lock(0.12.10)· 用法示例(引依赖文档原句):`uv add --preview-features index-by-name torch --index pytorch` · 一句边界:preview 能力不带稳定承诺,别把它写进团队标准流程
- **Visualization**: 原生状态表 `capability-status-matrix`(table/feature_matrix,行=能力,列=状态 / 出处版本)
- **Native-ready**: capability-status-matrix=yes
- **Fact IDs**: 源自 `sources/uv_CHANGELOG.md` 0.12.0–0.12.10 各段与 `sources/Managing_dependencies_uv.md`
- **Motion suggestion**: 承接 P10 的区块框架,状态标记后于行文字到位
- **page_rhythm**: dense

#### Slide 12 - 在哪能装、怎么装、要不要先有 Python

- **Audience move**: 担心安装本身就是一道坎 → 知道三个平台都支持且不需要先有 Python 或 Rust
- **Relationships**: 三个平台是 membership;四种安装方式是 membership 并与「不需要先有 Python/Rust」这一属性是 link
- **Composition**: 上半页三个平台标 + 一句支持声明,下半页两个安装终端块并列(curl / PowerShell),右侧窄栏列其余渠道
- **Title**: 三个平台都能装,而且不用先有 Python
- **Core message**: uv 以独立安装脚本分发,macOS、Linux、Windows 都支持,安装它不需要先有 Rust 或 Python
- **Content**: · 平台:macOS / Linux / Windows(引官方首页 Highlights)· 官方独立安装脚本:`curl -LsSf https://astral.sh/uv/install.sh | sh`;Windows:`powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"` · 其余渠道:pip、pipx、Homebrew 等,见官方安装页 · 关键属性:Installable without Rust or Python via curl or pip(官方首页原句)· 一条给已有项目的提醒:若 `[build-system]` 里对 uv_build 有上界,升到 0.12 需要改成 `uv_build>=0.11.32,<0.13`(引 CHANGELOG 0.12.0)
- **Fact IDs**: 源自 `sources/uv.md` Installation 段与 `sources/uv_CHANGELOG.md` 0.12.0 段
- **page_rhythm**: dense

#### Slide 13 - 每一句都能查回去

- **Audience move**: 想自己核对 → 拿到四个可点击的出处入口和各自负责的内容
- **Relationships**: 四个来源与它们各自支撑的页面是 link;四者之间是 membership
- **Composition**: 四行来源块纵向排列,每行左侧图标、中间链接文字、右侧一句「本卷哪几页靠它」
- **Title**: 本卷每一句的出处都在这四个地方
- **Core message**: 命令与示例输出来自官方文档,版本与日期来自 CHANGELOG,倍数说法来自 Astral 博文与 BENCHMARKS.md——四者分工明确,可逐条核对
- **Content**: · 官方文档 https://docs.astral.sh/uv/(命令、示例输出、能力划分;支撑 P03–P08、P10、P12)· 更新日志 https://raw.githubusercontent.com/astral-sh/uv/main/CHANGELOG.md(版本号、发布日期、preview 与稳定分界;支撑 P01、P11、P12)· Astral 发布博文 https://astral.sh/blog/uv(定位说法与 8-10x / 80-115x 的原始出处,2024-02-15;支撑 P02、P09)· 基准说明 https://raw.githubusercontent.com/astral-sh/uv/main/BENCHMARKS.md(测量条件与告诫,本身不含数字;支撑 P09)· 一行口径复述:本卷所有性能数字均为 Astral 在 macOS 上的测量,未在本机复测
- **page_rhythm**: breathing

#### Slide 14 - 今天可以做的第一件事

- **Audience move**: 认可 uv → 知道下一步具体敲哪一条命令,以及它不会动现有环境
- **Relationships**: 「装 uv」与「在一个项目上试」是 order;这一动作与它的前提(不需要先有 Python、不改现有 venv)是 link
- **Composition**: 单个大终端块居中承载唯一动作,上方一行说明,下方一行前提;整页只有一个动作
- **Title**: 今天先做一件事:在一个项目上跑通 uv pip install
- **Core message**: 不用整套迁移——先装上 uv,挑一个现有项目用 uv venv + uv pip install 走一遍,熟悉的命令形状,零配置
- **Closing impact**: 唯一动作 = 装好 uv 后在一个现有项目里跑 `uv venv` 与 `uv pip install -r requirements.txt`;composition Reference = 一个居中放大的终端块,只放这两行
- **Content**: · 第一步:`curl -LsSf https://astral.sh/uv/install.sh | sh` · 第二步:在一个现有项目里 `uv venv` 然后 `uv pip install -r requirements.txt` · 前提与边界:uv 的虚拟环境符合标准、可与其他工具互换使用;`uv pip` 不调用 pip,越偏离常见工作流越可能遇到差异 · 一句收束:先换一条命令,再谈换一套流程
- **Fact IDs**: 源自 `sources/uv.md` Installation / The pip interface 段与 `sources/uv_Python_packaging_in_Rust.md`
- **Motion suggestion**: 终端块由上一页缩放承接而来,两行命令依序到位
- **page_rhythm**: anchor

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 每页讲稿以该页最终 SVG 上的可见内容为准,补充口头串联、上下页过渡与页面上放不下的背景;凡涉及性能倍数,讲稿必须复述测量者、平台与日期;不引入源文件之外的事实
- **Total duration**: 约 25 分钟(14 页,平均每页 1.5–2 分钟,P05 与 P09 各留 3 分钟)
- **Notes style**: conversational(工程师之间的分享口吻,不用市场话术)
- **Presentation purpose**: 先讲清 uv 替掉了哪些日常摩擦,再用官方与 Astral 自己公布的口径建立可信度,最后给一条今天就能执行的第一步
