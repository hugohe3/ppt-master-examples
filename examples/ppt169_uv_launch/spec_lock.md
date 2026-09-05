<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 中文 Python 开发者与技术负责人,日常靠 pip + venv + requirements.txt 干活,关心迁移成本与能否立即上手
- objective: 讲清 uv 替掉了哪些日常摩擦并用官方与 Astral 公布的口径建立可信度,使听众能复述 uv 的四条项目命令、分清已发布与 preview 能力,并愿意在自己的一个项目上跑通第一条命令
- core_message: uv 是一个 Rust 写的单二进制,把 pip / pip-tools / pipx / pyenv / virtualenv / twine 那一摊收进一套命令并给出跨平台 lockfile;所有性能倍数均为 Astral 在 macOS 上的测量
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: showcase
- mode_behavior: 按发布会节奏推进,每页只放一个能力、一个收益或一个时刻,先让终端跑出来的东西占住画面再用标题给它命名;张力页只讲听众每天在经历的麻烦,定位页把主张单独给整页,能力页让终端窗口与命令序列主导而说明退到从属,证据页只留一个主数字。绝不把两个 reveal 塞进一页,也不用图标阵列冒充能力清单。

## visual_style
- visual_style: custom
- visual_style_references: dark-tech
- visual_style_behavior: 深色画布上做几何精确的分区,页面由近黑蓝底加若干抬起一档的面板构成,面板用 1px 细线勾边而非投影堆叠。终端块是主角载体:等宽字、左侧提示符列、深一档窗口底、顶部一条极细窗口条,窗口边缘用主色一层很淡的辉光标记正在运行。强调色只用在 reveal 的那一件事、改善的那一侧、结尾的那一个动作。数字用等宽字放到很大,靠字号而非装饰建立层级。装饰只有细线、细网格与 4px 微圆角面板。

## colors
- background: #0B1220
- secondary_bg: #131C2E
- primary: #4CC9F0
- accent: #FF8A3D
- secondary_accent: #A78BFA
- body_text: #E6EDF3
- secondary_text: #9BA9BC
- divider: #243349
- surface: #131C2E
- grid: #1E2A3D
- scrim: #04080F
- positive: #4ADE80
- warning: #FBBF24
- negative: #F87171

## typography
- font_family: Microsoft YaHei, Arial, sans-serif
- title_family: Microsoft YaHei, Arial, sans-serif
- display_family: Microsoft YaHei, Arial, sans-serif
- body_family: Microsoft YaHei, Arial, sans-serif
- annotation_family: Microsoft YaHei, Arial, sans-serif
- footnote_family: Microsoft YaHei, Arial, sans-serif
- code_family: Consolas, monospace
- data_family: Consolas, monospace
- body: 24
- display: 64
- title: 42
- subtitle: 32
- lead: 30
- data: 88
- code: 20
- annotation: 18
- footnote: 16

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/terminal-2, tabler-outline/package, tabler-outline/bolt, tabler-outline/lock, tabler-outline/versions, tabler-outline/rocket, tabler-outline/download, tabler-outline/tool, tabler-outline/file-code, tabler-outline/box, tabler-outline/clock-bolt, tabler-outline/check, tabler-outline/arrow-right, tabler-outline/alert-triangle, tabler-outline/world, tabler-outline/stack-2, tabler-outline/refresh, tabler-outline/route, simple-icons/python, simple-icons/pypi, simple-icons/github, simple-icons/rust, simple-icons/astral, simple-icons/linux, simple-icons/apple, simple-icons/windows

## page_rhythm
- P01: anchor
- P02: dense
- P03: anchor
- P04: dense
- P05: dense
- P06: dense
- P07: dense
- P08: dense
- P09: anchor
- P10: dense
- P11: dense
- P12: dense
- P13: breathing
- P14: anchor

## page_visualizations
- P08: table/comparison_matrix
- P09: chart/column_chart
- P11: table/feature_matrix

## pptx_structure
- mode: flat
- template_reuse_scope: style

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 不做 AI 生图、不搜网图 (user)
- 不配音效、不做路径动画 (user)
- 不为"原生可编辑"降级视觉 (user)
