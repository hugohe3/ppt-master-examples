# 规程与工具摩擦点 — solar_cheapest_power（Default Generate，pyramid × swiss-minimal，15 页）

按影响排序。每条只描述观察到的事实与它造成的返工，不改仓库文件。

## 1. 行宽估算率对中英混排系统性偏乐观 10–20%（最大摩擦）

`text_measure.py calibrate` 给出的 Latin / CAPS / DIGITS 率是样本均值，文档提示"保持在 bounds 宽度以下约 5%"。
对纯 CJK 行这条成立；对**中英混排行**（含 `$`、`%`、`–`、`→`、全角括号、机构名）实测偏差远超 5%。

终检 13 条阻断里有 11 条属于这一类，实测偏差：

| 行 | 我的估算 | checker 实测 | 偏差 |
| --- | ---: | ---: | ---: |
| P15 建议 03 支撑行 | ~946 | 1385.9 | +46% |
| P13 页脚第二行 | ~964 | 1374.1 | +42% |
| P14 引文行 | ~569 | 1272.0 | +124%（含全角引号） |
| P10 firm LCOE 行 | ~982 | 1318.5 | +34% |
| P06 累计装机行 | ~430 | 621.3 | +45% |

规律：CJK 与 Latin 交替越频繁、标点越多，偏差越大——加性模型把每段边界的进位吃掉了。
**规程建议**：文档现在说"留 5% 余量"，对混排行应改成"必须用 `text_measure.py measure` 实测"，或给出混排专用的经验余量（本次实测需要 30–45%，5% 完全不够）。这条如果只靠 calibrate 表心算，长中英混排 deck 每次都会在终检批量返工。

## 2. `stamp_native_fallbacks.py` 没有出现在 Step 6 的页面循环动作里

`native-data-interface.md` §2 要求"marker + JSON + stamp 是一个原子写作单元"，`executor-base.md` §3 Checkpoints 里也有这一句，
但 `generate-pptx.md` Step 6 的 **Cadence** 与 **Visual Construction Phase** 段落只列了 checker 调用点，没有把 stamp 列成"每写完一个 marker 就执行"的并列动作。
结果：P02/P03 三个 marker 全部漏 stamp，直到早期门才以 3 条 blocking 暴露。
**规程建议**：把 stamp 提到 Step 6 的 Visual Construction Phase 步骤里，与 marker 写入并列，而不是只留在 executor-base 的长段落中。

## 3. `font-family="Arial"` 用在含 CJK 的图表标签上是静默陷阱

导出按"栈里第一个 Latin face 填 `latin`、第一个 CJK face 填 `ea`"解析。
给一条含中文的图表类别标签写 `font-family="Arial"`（我在 P03 十条、P13 四条上这么做了，动机是让数字用等高线性数字），
栈里没有命名任何 CJK face，`ea` 无来源。**checker 不报，导出也不报**——`font_portability` 只在整栈没有具体族时才 warn。
这与仓库既有的 "font-family 栈尾通用族" 问题同源，但触发条件不同（这次是栈太短而不是栈太长）。
**规程建议**：checker 增加一条 advisory——"该 `<text>` 含 CJK 字符，但其 `font-family` 未命名任何 CJK face"。

## 4. 原生图表 `style.text_color` 的判据是"数出现次数"，但写 payload 时会按语义填

`native-data.md` §2 把它写成 parity 检查（"differs from fallback dominant text_color"），
但写 payload 的时刻是在写作，不是在校验。自然的写法是填**语义上的次要文本色**（我填了 `#6E6E6E`），
而 fallback 的**主导**色是数量更多的类别标签色 `#1A1A1A`。P03 与 P13 各中一次。
**规程建议**：在写作侧补一句可执行规则——"写 `style.text_color` 前先数 fallback 里每种文本色出现的次数，取最多的那个"。

## 5. `calibrate --outline` 的"最长计划行"覆盖不到真正最长的行

`--outline` 只扫描 Design Spec §IX 的 `Content`。本卷真正最长的行几乎全部是**页脚来源行**和**图表注解**，
它们按规程本来就不属于 §IX（来源脚注是 Executor 的呈现决定，图表注解是 payload 的 companion note）。
所以 outline 提示的最长行（P14 body 2916px）和实际返工的行完全不是同一批。
**规程建议**：outline 输出加一句边界说明——"仅覆盖 §IX 计划措辞；页脚、来源行与图表注解需另行估算"，避免把 outline 当成全量清单。

## 6. （次要）normalize 与 stamp 的顺序只能靠读文档推出来

`compact_svg_styles.py --inplace` 会重写 chart fallback 子树，因此必须 **normalize → stamp → 终检**。
反过来先 stamp 再 normalize 会静默产生 stale baseline，只在终检以 blocking 暴露。
文档在 `shared-standards-core.md` §1 的括号里写了这个顺序，但 `svg-pipeline.md` 的 Recommended Pipeline 段没有写死它。
