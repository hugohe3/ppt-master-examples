# 摩擦点 — apollo_photo_essay（Default / photo-editorial × narrative / 13 页 / 10 张照片）

按对本次运行的实际代价排序。前五条影响了返工轮次或构图决策，后面的是记录。

---

## 1. `text_measure.py calibrate` 对 `Times New Roman, SimSun` 栈的 Latin/DIGITS 速率低估约 18%（造成早期门两条 blocking）

早期门唯一的两条 error 同源：`subtitle`（40px，`Times New Roman, SimSun`）上的时间戳 `1969.07.20 20:17:40 UTC`。

- calibrate 给出的速率：Latin 4.4 / DIGITS 4.1 / CAPS 3.7 chars per 100px → 该串估算 559px。
- checker 实测：661px（报错信息里写作 `≈31.5 px per Latin char at 40px incl. headroom`），即 **28.7 px/char**。
- 偏差 18%，两条 error 的溢出量都恰好是 5.2%（刚过 5% 的门槛）。

CJK 方向是相反的：calibrate 的 CJK 速率带足了 headroom，实测比估算窄。所以这不是"整体加安全系数"能解决的，而是**同一张校准表里 CJK 偏保守、Latin/DIGITS 偏乐观**。

本卷采用的方法级修正（早期门后全卷执行）：CJK 用表内速率原值；Latin / 空格 / 标点 / DIGITS / CAPS 一律 `chars ÷ rate × 100 × 1.25`；结果再要求 ≤ 0.95 × bounds 宽度。改用这个算法后，P06–P13 共 8 页 60 余个文本块，最终门只剩 1 条 2.3% 的纵向溢出警告（已修）。

> 记忆里已有一条"calibrate 率 ≠ checker 率（差 3–5%）"（a4 茶手页）与一条"Latin 率偏乐观 15–20%"（英文 brutalist deck）。**本次是第三次在同一处踩到，且这次能定位到具体字族**：偏差随字族变化，衬线 Latin 面（Times New Roman）比无衬线（Arial）严重得多。校准表按 role 给了 family 列，但速率显然不是按该 family 实测的。

## 2. 「放宽 bounds」与「root group 不得重叠」两条提示互相打架

checker 在文字溢出时给的建议是 *"expand the root module bounds into available non-overlapping space"*，但相邻模块往往正好占着那块空间，于是照做就直接换来一条 blocking：

- P11：`p11-days` 纵向溢出 2.3%（warning）→ 把 bounds 从 `840 556 368 100` 放宽到 `840 548 368 116` → 立刻与 `mission-ledger`（`72 248 1136 302`，下边界 550）重叠 2px → **error**。最终要同时改两个模块的 bounds 才收敛。
- P10：`p10-body` 为了容纳一行正文取了 `72 178 1136 44`（贯穿整页宽），与右上角的放大镜组 `p10-lens` 重叠 190×44 → **error**。正文实际只有 689px 宽，把 bounds 收到 900 就好了 —— 也就是说，**bounds 写得"大方"（文档建议的"make each zone as generous as the canvas and siblings allow"）在有浮动构件的页面上是主动制造 error 的写法**。

建议：溢出提示里如果能顺带报出"该轴上最近的相邻 bounds 边界是多少"，这两轮返工都能省掉。

## 3. `image_treat.py` 只能输出 PNG，使 checker 的「换个小一点的源文件」建议在照片上无解

终检剩下的 3 条 warning 全是同一条：

```
Image ../images/02_earthrise.jpg is 5550x4446 and renders at 0.23x scale …
the source is 9.7 MiB — file-size advisory only … consider a smaller source asset
```

触发条件是 `render_scale < 0.25 且 源文件 ≥ 1 MiB`（`checker.py` 的 `IMAGE_DOWNSIZE_WARN_RATIO = 4.0` / `IMAGE_DOWNSIZE_WARN_MIN_BYTES = 1 MiB`）。要消掉它只有两条路：

1. 把源缩到 render_scale ≥ 0.25 —— 对 5550×4446 就是 ≤5120px 宽；
2. 把源压到 < 1 MiB。

但**项目内唯一的缩放工具 `image_treat.py --fit` 只接受 `.png` 输出**（`--output` 明确要求 bare `.png`）。实测把 02_earthrise 缩到 2200×1760 的 PNG 是 **4.7 MB**（原 JPEG 9.7 MB）——比原文件小，但离 1 MiB 还差得远；要压到 1 MiB 以下大约得缩到 1100px 宽，那时 `render_scale` 会翻到 1.16 并转而触发 **upscale** 警告。也就是说这条 advisory 在"高质量档案照片 + 满版出血"这个组合下**没有合规的消除路径**。

本卷的处置：保留 3 条 advisory 不动。理由是 (a) checker 自己标注 `file-size advisory only`；(b) 导出器默认 `--image-max-dimension 2560` 会在打包时重编码，最终 PPTX 的 `ppt/media` 只有 11 MB（11 张原图合计约 28 MB），成品不受影响；(c) 为了消警告而改画幅会直接损害构图。

建议：`image_treat.py --fit` 支持保留源格式（JPEG in → JPEG out，带 `--quality`），这条路才走得通。

## 4. `image_search.py --batch` 回写时静默丢弃 `provider` 字段

`image_queries.json` 里每一行我都钉了 `"provider": "wikimedia"`（NASA 档案照片必须走 Wikimedia，stock 提供方会用旅游快照顶包）。批量跑完之后，runner 把 manifest 整个重写，**10 行的 `provider` 全部消失**，只保留了 `query` / `query_variants` / `required_terms` / 分页字段。

后果：第二次为未决行重跑 `--batch` 时，provider chain 会悄悄退回默认链（pexels → pixabay → openverse → wikimedia）。本次是因为要改 query 才重写了整个 manifest 并重新写入 provider，才没有踩到。`min_width` / `min_height` / `orientation` 等其它输入字段都被保留了，唯独 `provider` 没有——看起来是回写时的字段白名单漏了它。

## 5. 排名第一的候选可以是靠 `required_terms` 蒙混过关的无关主体

`05_bootprint` 行的 `required_terms` 是 `["Apollo 11", "bootprint|boot print|footprint"]`，看起来足够紧。返回的 **candidate_01 是 "Washington Monument, Apollo 11 50th annivesary, footprint.jpg"**（华盛顿纪念碑上的登月五十周年投影），元数据把两组词都占全了，排名却在真正的 AS11-40-5878 之前。

这正是 `image-searcher.md` 说的"a generic `required_terms` pass is not acceptance"，规程本身是对的；记在这里是因为它说明**在 NASA 档案这种"周年纪念衍生品极多"的题材上，metadata-ranked 的无视觉路径风险特别高**——如果这次是没有视觉能力的运行，best-only 模式会直接把纪念碑下载下来当鞋印。

---

## 其余记录（不影响本次产出）

- **`--candidate-page 2` 的报错信息不完整**：改了 `query-variant` 而保持 `query` 不变时报 `--candidate-page 2 must keep the pool's query 'Apollo 11 Saturn V launch'`，但实际上 variants 也必须一致。信息只点名了 `query`，第一次按字面改回 query 仍然失败。
- **任务书给的两个照片编号是错的，research worker 查出来了**：`AS11-40-5875`（应为 `AS11-40-5868`）与 `AS17-134-20463`（JSC 库对该帧返回 `Image Caption: none`，无法证实）。这是 topic-research 阶段"照片编号溯源"缺口的直接收益——如果不把编号核验列进研究缺口，这两个错号会直接印到页面上。
- **`AS17-140-21496` 在 Wikimedia 上找不到单帧**：只有一张 2025 年由用户拼接的 `AS17-140-21493+AS17-140-21497` 全景（17758×8463）。本卷改用 NASA 官方发布的单帧 **S73-22871**（6932×3982，1.74:1，几乎正好 16:9），并同步改了 §VIII Reference、§IX 图注与 P13 编号清单。
- **photo-editorial 的"满版出血"在真实纪实照片上常常没有安静区**：8 个出血页里有 6 页的 scrim 是逐页手调停靠点（不是套一个通用渐变），另外 2 页（P06 鞋印、P10 巨砾）照片本身填满画幅、任何位置的文字都压在中等亮度的月壤上，最后用实色卡片／色带承字。风格文件写了"没有可用图片就退回 editorial"，但没写"有可用图片、却没有可压字区域"这一档——而后者才是纪实照片的常态。
- **`image_search.py` 没有 `--list-providers`**：`--help` 里能看到 `--provider` 的枚举，但没有独立的列举子命令；第一次尝试 `--list-providers` 报 unrecognized。纯属摸索成本，不重要。
