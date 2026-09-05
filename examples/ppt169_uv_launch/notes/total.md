# 01_cover

先看这句话:一个极快的 Python 包与项目管理器,用 Rust 写成。这是 uv 官方文档首页的开门句,我照抄过来,没有加工。今天要讲的不是又一个包管理器,而是一个把 pip、pip-tools、pipx、pyenv、virtualenv、twine 这一整摊工具收进同一个命令入口的二进制。屏幕下方这六个名字,今天会一个一个被它接管。版本我也写在这里了,零点十二点十,发布日期是二零二六年九月四日,取自它的 CHANGELOG。整场分享我会守一条纪律:凡是出现倍数,我都会说清楚是谁测的、在什么机器上、什么时候。

---

# 02_tension

先不急着讲 uv,先讲你每天在经历的那件事。左边这六个小窗口是我们熟悉的分工:pip 装包,pip-tools 锁版本,pipx 跑命令行工具,pyenv 管 Python 版本,virtualenv 建虚拟环境,twine 把包发到索引。每一件工具单独看都没问题,问题在它们之间的缝。第一条缝:装 Python 和装包是两套东西,各有各的失败方式。第二条缝:requirements.txt 不跨平台,换一台机器就要重新解析一次。第三条缝:环境重建太慢,慢到没人愿意把 venv 删掉重来,于是环境越用越脏。右下角这句话是 Astral 自己在二零二四年二月十五号的发布博文里写的:Python 的工具链是一种低信心的体验,把一个新项目或老项目立起来要花掉大量工作,而且命令会以让人困惑的方式失败。我们要修的从来不是某一件工具,是缝。

---

# 03_positioning

那 uv 是什么。官方文档首页 Highlights 的第一条写得很直接:一个工具,替掉 pip、pip-tools、pipx、poetry、pyenv、twine、virtualenv,以及更多。注意这是文档原话,不是我的转述,也不是市场话术。左边这六个刚才还各自为政的名字,现在收进了同一个块。它凭什么能这么做,右边三条属性回答了:它是用 Rust 写成的单个静态二进制;安装它本身不需要你先有 Rust 或者 Python;它提供一份跨平台的 uv.lock,一份锁文件可以走遍不同机器。最后再重复一次我的口径承诺:后面每一个倍数,我都会标出谁测的、什么机器、什么时候。

---

# 04_project_flow

先看它怎么用。日常项目工作流只有四个动作,按顺序是:uv init 建项目,uv add 加依赖,uv run 在项目环境里跑命令,uv lock 生成或更新锁文件。下面这个终端窗口是官方文档 Working on projects 页给的例子:建一个 hello-world,进去,加一个 requests,然后 uv run hello-world,打印出 Hello from hello-world。这里有一个很关键的机制:你第一次运行任何项目命令时,uv 会自动帮你创建 .venv 和 uv.lock,不需要你手动建环境。右边是这四步留下的三样东西:pyproject.toml 声明依赖和项目元数据;uv.lock 是精确的解析结果,应该提交到版本库;点 venv 目录是这个项目自己的隔离环境。

---

# 05_demo_moment

现在把那个终端窗口放大,完整看一遍。这一段是 uv 官方文档首页 Projects 段的示例会话,我逐行照抄,一个字没改。uv init example 建好项目;uv add ruff 时它先创建虚拟环境,然后解析两个包用了一百七十毫秒,构建用了六百二十七毫秒,安装用了一毫秒;接着 uv run ruff check 通过;最后 uv lock 重新解析这两个包只用了零点三三毫秒。我要特别说明的是,这些耗时是文档页上的示例输出,官方没有公布这段是在什么机器、什么网络条件下跑的,我今天也没有在本机做任何复测。所以请把它当作一个数量级的示意,而不是你机器上的承诺。

---

# 06_scripts_tools

uv 收编的不只是项目。上面这个窗口讲的是单文件脚本:uv add --script example.py requests,依赖就被写进脚本文件本身,成为内联依赖元数据;然后 uv run example.py,它读取内联元数据,装了五个包用了十二毫秒,打印出 Response 200。整个过程你没有手动建过任何环境。下面左边是临时跑一次的场景,uvx 是 uv tool run 的别名,在一个临时环境里跑完就走;右边是装成常驻,uv tool install ruff 之后你可以直接敲 ruff。选择很简单:临时用 uvx,常用就 install。右边这一栏是三点小结,最后一句请记住:脚本、工具、项目、pip 接口这几块可以单独采用,不必整套迁移。

---

# 07_python_versions

再往下一层,Python 本身也归它管。uv python install 一次装三个版本;uv venv --python 3.12.0 会在需要时按需下载缺失的版本;uv python pin 3.11 把当前目录钉到某个版本,写进 .python-version 文件。这个文件决定 uv 给这个项目建虚拟环境时用哪个 Python。这一屏还有一个细节值得留意:输出里每一行结尾都是 macos-aarch64,这说明官方这段示例是在 macOS 上跑的,你在自己机器上跑出来的标识会不一样。我把它指出来,是因为后面讲性能数字时,平台差异会是关键。

---

# 08_before_after

那迁移到底要付多少学习成本。这张表把同一件事的两套命令逐行对齐:建虚拟环境,以前是 python -m venv,现在是 uv venv;装包,pip install 变成 uv pip install;锁定依赖,pip-compile 变成 uv pip compile;同步环境,pip-sync 变成 uv pip sync;跑命令行工具,pipx run 变成 uvx;装 Python 版本,pyenv install 变成 uv python install。命令形状是刻意保持熟悉的,所以迁移不是重学,是逐条替换。但有两条提醒必须说清楚。第一,uv 不依赖也不调用 pip,这个名字只表示这组低层命令与 pip 的接口对齐。第二,官方明确写了:这些命令并非逐字实现 pip 的全部行为,你越偏离常见工作流,差异越可能出现。

---

# 09_proof_point

现在讲那个你一定听过的数字。答案是:它取决于缓存是冷是热。图上这两根柱子取的是 Astral 公布区间的下限:无缓存八倍,热缓存八十倍。右边这四行是这个数字的完整口径,请一起记住:测量者是 Astral,也就是 uv 的作者;平台是 macOS,非 uv 的对照工具用的是 Python 3.12.4;测量对象是 Trio 这个项目的 docs-requirements.in;日期是二零二四年二月十五号的发布博文。博文的原句给的其实是区间,不是单一数字:无缓存快八到十倍,热缓存快八十到一百一十五倍。官方文档首页写得更粗一些,叫做比 pip 快十到一百倍,指向的是同一份 BENCHMARKS.md。而 BENCHMARKS.md 自己提醒:不同操作系统和文件系统上的表现可能差异很大,不同的依赖集也会显著改变结果。所以这不是你机器上的结果,本次分享也没有做本机复测。

---

# 10_capability_landscape

把前面几块拼起来看,官方是这样切分它的界面的。第一块是 Python 版本,install、list、find、pin、uninstall。第二块是脚本,uv run 加上给脚本增删依赖。第三块是项目,init、add、remove、sync、lock、run、tree、build、publish,是最完整的一块。第四块是工具,uvx 等于 uv tool run,再加上 install、uninstall、list。第五块是 pip 接口,uv venv 加上 uv pip 的那一组。最下面用虚线框出来的是 Utility,不算能力块,是管理 uv 自己的状态:清缓存、看目录、自更新。这里最重要的一句是官方原话:uv 的界面可以拆成若干部分,这些部分既可以单独使用,也可以合起来用。也就是说,迁移可以从任意一块开始,不是全有或全无。

---

# 11_shipped_vs_preview

讲能力就必须讲边界。这张表把能力分成两类。上面三行是已经稳定的,都在零点十二点零这个版本发布,时间是二零二六年七月二十八号:packaged-init 让 uv init 默认声明 build system;venv-safe-clear 让 uv venv --clear 拒绝清空不是虚拟环境的目录;target-workspace-discovery 让 uv run 从脚本所在目录去发现项目。下面四行是仍然挂着 preview 的:content-addressed-cache 按内容哈希对缓存中的 wheel 去重;index-by-name 允许按名字选已配置的索引;cache-physical-space 报告实际回收的磁盘空间;missing-exclude-newer-package-lock 让锁文件省略无关的新鲜度设置。下面这条命令示范了 preview 怎么用,要显式加 --preview-features 再写上特性名。请注意:preview 能力不带稳定承诺,不要把它写进团队的标准流程。

---

# 12_availability

接下来是最实际的问题:在哪能装,怎么装。三个平台都支持,macOS、Linux、Windows。macOS 和 Linux 用官方独立安装脚本,一行 curl 管道给 sh;Windows 用 PowerShell,irm 拉下来交给 iex。这里有一条属性值得单独强调,也是官方首页原话:安装 uv 不需要先有 Rust,也不需要先有 Python,它就是一个二进制。除了官方脚本,你也可以用 pip、pipx、Homebrew 等渠道,完整清单在官方安装页。最后一条是给已有项目的:如果你要升到零点十二,而你的 build-system 表里对 uv_build 设了版本上界,把它改成大于等于零点十一点三二、小于零点十三。uv 构建后端的配置本身没有破坏性变更,只需要放开这一个上界。

---

# 13_sources

在给结论之前,先把出处交代清楚,这样今天讲的每一句你都能自己查回去。第一个地方是官方文档,docs.astral.sh 斜杠 uv,今天所有的命令、示例输出和能力划分都来自它,支撑第三页到第八页,还有第十、第十二页。第二个是 CHANGELOG,版本号、发布日期、preview 与稳定的分界都从这里读,支撑第一、第十一、第十二页。第三个是 Astral 的发布博文,那两组倍数的原始出处就在这里,日期是二零二四年二月十五号,支撑第二页和第九页。第四个是仓库里的 BENCHMARKS.md,它只写测量条件和告诫,本身不含数字,支撑第九页。这四个链接在 PowerPoint 里都可以直接点开。再重复一次口径:本卷所有性能倍数都是 Astral 在 macOS 上的测量,没有在本机复测;命令和输出都是照官方文档原样引用。

---

# 14_next_step

最后只留一件事给你。不用整套迁移,也不用今天就改流程。第一步,装上 uv,就是这一行 curl。第二步,挑一个你手上现成的项目,进去,uv venv 建环境,uv pip install -r requirements.txt 装依赖。就这两条,命令形状你已经很熟悉,零配置。两个前提我要说在前面:uv 建出来的虚拟环境是符合标准的,可以和其他工具互换使用,不会把你锁死;同时 uv pip 不调用 pip,越偏离常见工作流,差异越可能出现,所以先在一个项目上试,不要一次全换。跑通之后,你再决定要不要用 uv init 把工程重建成项目式的工作流。今天的结论就一句:先换一条命令,再谈换一套流程。
