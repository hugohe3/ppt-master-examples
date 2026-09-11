<!-- ppt-master-schema: design-spec/v1 -->
# tokaido_shinkansen_60_ja - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | tokaido_shinkansen_60_ja |
| Canvas Format | ppt169 (1280×720) |
| Page Count | 15 |
| Primary Language | ja-JP |
| Target Audience | 一般の聴講者。新幹線に乗った経験はあるが、技術や統計の詳細は知らない市民(鉄道ファンに限らない) |
| Communication Intent | 60年の歩みを検証できる数字で振り返り(伝える)、速さ・本数・定時性・安全がどう積み上がったかの仕組みを示し(説明する)、最後に次の60年(中央新幹線)を公表情報どおりに位置づける |
| Desired Audience Outcome | 聴衆が「4時間→2時間21分」「1日60本→395本」「乗車中の死傷事故ゼロ」を仕組みと結びつけて説明でき、中央新幹線について公表済みの計画と未確定の点を区別できる |
| Core Message / Ask / Action | 東海道新幹線の60年は、速さだけでなく本数・定時性・安全を同時に積み上げてきた60年であり、次の60年はその大動脈を二重にする段階に入っている |
| Delivery Context | 主:登壇者による一般向け講演(会場投影、約25分);副:講演後の配布資料としての閲覧 |
| Artifact Afterlife | 講演資料として配布・再利用。各数字を出典名と参照年で追跡できること |
| Reading Mode | presentation |
| Content Strategy | balanced default(空欄のまま確認) |
| Design Style | 昭和の記念ポスター — custom mode(narrative 基盤)+ custom visual style(vintage-poster 基盤)+ custom rendering(vintage-poster 基盤) |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — final Stage-2 proactive policy(委任確認で推奨値を採用) |
| Custom Animations | enabled — explicit instruction(依頼書:主役の登場・枠は動かさない・脇役は動かさない;オブジェクト単位) |
| Narration Audio | disabled — workflow default |
| Created Date | 2026-09-11 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 左右 64px、上 56px、下 48px |
| Content Area | x 64–1216、y 56–672 |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: narrative
- **Mode Behavior**: 1964年の開業という「出発の瞬間」から始め、速さ→本数→安全という三つの章で「どうやって積み上げたか」を一つずつ解き明かし、各章の山場で一つの決定的な数字を見せてから仕組みを説明する。最後に「次の60年」で未確定の点を正直に示し、二重化という次の章の問いで結ぶ。タイトルは物語の一歩を進める判断文にする。
- **Visual style**: custom
- **Visual Style References**: vintage-poster
- **Visual Style Behavior**: 昭和の記念ポスター。クリーム色の紙の地に、藍の大きな平面ブロック・朱の太陽円盤・黄土の帯を少数だけ重ね、角の丸い幾何形とやや斜めの帯でレトロな緊張を出す。数字はポスター級の大きさで一点に置き、細い二重罫と丸いバッジで出典や年代を添える。網点(ハーフトーン)と紙の粒子を低い不透明度で重ねて印刷物の質感を出し、影やグラデーションは使わず重なりで奥行きを出す。見出しは明朝の落ち着き、本文はゴシックの読みやすさ、巨大数字は極太のサンセリフ。
- **Theme**: 60年目の記念ポスター — 藍の軌道線(横に走る一本の太い帯)が各ページを貫き、年表の軸・グラフの基線・区切りとして役割を変えて繰り返す
- **Tone**: 温かく、誇らしく、しかし事実に厳密

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #F3ECDD | クリーム色の紙の地 |
| Secondary background | #E6DCC6 | 一段濃い紙色の面・パネル |
| Primary | #1F3F74 | 藍。見出し・大きな平面ブロック・軌道線 |
| Accent | #C8442C | 朱。太陽円盤・強調する一点の数字 |
| Secondary accent | #D9A33A | 黄土。帯・年代バッジ・補助の強調 |
| Body text | #22262E | 本文 |
| Secondary text | #5E5A52 | キャプション・出典・注記 |
| Divider | #C7B99D | 罫線・細線 |

### AI Image Strategy

- **Image Rendering**: custom
- **Image Rendering References**: vintage-poster
- **Image Rendering Behavior**: 1960年代の旅行ポスターのような簡略化した平面ブロックで描き、輪郭は太く手の気配を残し、角は丸い。藍・朱・黄土・クリームの限られた平面色の上に網点を10〜15%重ね、わずかな版ずれと紙の粒子で印刷の古さを出す。写実ではなく、山・太陽・高架橋・列車を記号的な形に還元し、影ではなく形の重なりで奥行きを作る。文字・数字・企業ロゴ・車体の社章は一切描かない。
- **Visual**: 富士山・朝日・高架橋・軌道・ガイドウェイを記号化した平面ポスター画
- **Mood**: 懐かしく前向き — 1964年の観光ポスターを60年後に新しく刷り直したような温かさ

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 落ち着いた明朝の見出し | Yu Mincho | Times New Roman | serif |
| Body | 読みやすいゴシック | Yu Gothic | Segoe UI | sans-serif |
| Display | ポスター級の極太数字 | Yu Gothic | Arial Black | sans-serif |
| Kpi | 数字ブロックの極太数字 | Yu Gothic | Arial Black | sans-serif |

- **Title stack**: 'Times New Roman', 'Yu Mincho', serif
- **Body stack**: 'Segoe UI', 'Yu Gothic', sans-serif
- **Display stack**: 'Arial Black', 'Yu Gothic', sans-serif
- **Kpi stack**: 'Arial Black', 'Yu Gothic', sans-serif
- **Role rationale**: Display は巨大な数字(4:00・395・0 など)を複数ページで繰り返すため、見出しの明朝から離れた極太ライニング数字を別ファミリーとして固定する。Kpi(64px)は複数ページの数字ブロックで繰り返すため、同じ極太ライニング数字の系統に揃える。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 28 |
| Title | 48 |
| Subtitle | 34 |
| Annotation | 22 |
| Lead | 32 |
| Footnote | 16 |
| Cover title | 96 |
| Display | 132 |
| Kpi | 64 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 左上の判断文の見出し → 一つの主役(巨大数字・図・画像) → 補足と出典の順に視線が流れる
- **Composition tendency**: 大きな平面ブロックと太陽円盤で紙面を二つか三つのゾーンに分け、主役は一点に集中させる。均等なカードの格子は避ける
- **Cross-page continuity**: 藍の軌道線(太い横帯)を毎ページどこかに置き、役割(年表の軸・基線・区切り)を変えて繰り返す。出典は各ページ下部の細い行に置く
- **Spacing posture**: presentation 読みで余白は広め。dense ページも一画面一主張
- **Spacing anchors**: page margin 64px / block gap 32px / column gutter 40px / corner radius 16px / body leading 1.5

## VI. Icon Usage Specification

- **Primary bundled library**: chunk-filled

| Icon Path | Suitable Scenarios |
| --- | --- |
| icons/chunk-filled/train.svg | |
| icons/chunk-filled/clock.svg | |
| icons/chunk-filled/stopwatch.svg | |
| icons/chunk-filled/gauge-high.svg | |
| icons/chunk-filled/users.svg | |
| icons/chunk-filled/calendar.svg | |
| icons/chunk-filled/shield-check.svg | |
| icons/chunk-filled/bolt.svg | |
| icons/chunk-filled/waveform.svg | |
| icons/chunk-filled/bridge.svg | |
| icons/chunk-filled/mountains.svg | |
| icons/chunk-filled/magnet.svg | |
| icons/chunk-filled/route.svg | |
| icons/chunk-filled/map-pin.svg | |
| icons/chunk-filled/leaf.svg | |
| icons/chunk-filled/link.svg | |
| icons/chunk-filled/chair.svg | |
| icons/chunk-filled/power.svg | |
| icons/chunk-filled/signal.svg | |
| icons/chunk-filled/wrench.svg | |
| icons/chunk-filled/flag.svg | |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P03 | chart | horizontal_bar_chart | 東京〜大阪の所要時間を在来線・開業時・翌年・現在で比べる |
| P06 | table | record_table | 7つの型式を営業開始・最高速度・技術の要点で並べる |
| P09 | chart | column_chart | 輸送人キロの年度推移(2002〜2025年度)を示す |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cover_poster.jpg | 2752×1536 | 16:9 | 表紙の主視覚:60年の出発点を一枚のポスター画で示す | Hero illustration | 右側の大きなアーチ窓に切り抜き、左の無地のクリーム面に題字を置く(画像の上に題字を載せない) | adaptive | ai | Generated | 朝日を背にした富士山の前を、白い流線形の高速列車が長い高架橋を渡る。列車は右下へ向かい、画面左1/3は空と紙の余白。列車は特定の型式を再現しない記号的な形 | none | hero_page |
| era_1964.jpg | 1856×2304 | 4:5 | P04:開業の朝の空気を伝える | Illustration | 縦長の窓として右側に置き、角丸の枠で切り抜く | adaptive | ai | Generated | 1960年代のプラットホームで、旗を振って見送る人々の後ろ姿と、丸い先頭の白と青の列車が朝の光の中で出発を待つ。人物は顔を描かない簡略化したシルエット | none | local |
| rails_dusk.png | 2752×1536 | 16:9 | 安全章の背景の元画像(派生の親) | Source | 直接は置かない | adaptive | ai | Generated | 夕暮れに遠くへ収束する複線の軌道と架線柱、線路脇の小さな機器箱。人物・列車なし、静かで整然 | none | local |
| rails_dusk_duotone.jpg | 1600×900 | 16:9 | P11:「死傷事故ゼロ」の背景として紙面全体を静かに支える | Background | 全面の背景に敷き、左側に藍の平面を重ねて数字の地を作る | adaptive | ai | Generated | Derived from rails_dusk.png; treatment=duotone+fit; 藍 #1F3F74 と クリーム #F3ECDD の二色化、1600×900 に縮小 | none | local |
| guideway_dawn.jpg | 2752×1536 | 16:9 | P14:次の60年(超電導リニア)への視線を作る | Illustration | 朱の太陽円盤の形に丸く切り抜き、右側に大きく置く | adaptive | ai | Generated | 夜明けの山あいを貫くU字形のコンクリートのガイドウェイがトンネルへ吸い込まれる。車両は描かないか、形の定まらない白い光の筋だけ。ロゴ・文字なし | none | local |

## IX. Content Outline

### Part 1: 出発

#### Slide 01 - 表紙

- **Audience move**: これから何の話か知らない → 「60年前の一本の線がいまも日本の大動脈である」という入口に立つ
- **Relationships**: none
- **Composition**: 左に題字と副題の縦の列、右に大きなアーチ窓のポスター画。藍の軌道線が下端を横切る
- **Title**: 東海道新幹線 60年
- **Core message**: 1964年10月1日に走り出した一本の線は、60年でどこまで来たのか
- **Content**: 副題:速さ・本数・安全を積み上げた大動脈の60年 · 日付バッジ:1964.10.1 → 2024.10.1 · 出典:JR東海 ニュースリリース(2024)
- **Cover impact**: 「1964年10月1日」という出発の瞬間を題字の上の小さなバッジで示し、画像は朝日と列車(フック)。構図は Reference
- **Images**: cover_poster.jpg
- **Fact IDs**: F001
- **Motion suggestion**: 題字が先に、ポスター画はその後に静かに現れる

#### Slide 02 - 60年を四つの数字で

- **Audience move**: 漠然と「速い新幹線」 → 今日の話が四つの数字(速さ・本数・定時性・安全)でできていると知る
- **Relationships**: membership:四つの数字は同じ60年の成果の四つの側面;order:以降の章の順番
- **Composition**: 四つの数字ブロックを大小差をつけて配置(均等なカードにしない)。章の予告として番号を添える
- **Title**: 60年は、四つの数字で語れる
- **Core message**: 速さ・本数・定時性・安全の四つが同時に積み上がったことが、この60年の本質である
- **Content**: 2時間21分(東京〜新大阪 最速、2026年3月) · 395本/日(2025年度) · 平均遅延1.0分(2025年度) · 乗車中の死傷事故ゼロ(開業以来) · 注記:四つの切り口は当資料による整理
- **Fact IDs**: F009, F005, F007, F008
- **Motion suggestion**: 四つの数字を章の順に一つずつ

#### Slide 03 - なぜ新幹線だったのか

- **Audience move**: 開業前の移動を知らない → 在来線の約6時間が4時間、翌年3時間10分になった落差を実感する
- **Relationships**: contrast:在来線と新幹線の所要時間;order:在来線 → 開業時 → 翌年 → 現在
- **Composition**: 横棒グラフが主役、右に「日帰り圏になった」の一行
- **Title**: 6時間の旅が、4時間になった
- **Core message**: 開業は東京〜大阪の移動時間を一気に3分の2に縮め、翌年には半分近くまで縮めた
- **Content**: 在来線 約6時間 · 1964年 開業時 4時間 · 1965年 3時間10分(210km/h運転) · 2026年 2時間21分 · 注記:在来線の値は「約6時間」
- **Visualization**: travel-time-bars — 横棒グラフ(単位:分、軸タイトル「所要時間(分)」)
- **Native-ready**: travel-time-bars=yes
- **Fact IDs**: F011, F009

#### Slide 04 - 1964年の選択

- **Audience move**: 開業時の姿を知らない → 0系・210km/h・1日60本という出発点を具体的に思い描く
- **Relationships**: membership:開業時の三つの事実(型式・速度・本数)
- **Composition**: 巨大な「4:00」が主役、下に三つの事実、右に縦長の窓の画像。0系の先頭形を思わせる丸い記号が次ページへ受け渡される
- **Title**: 1964年、4時間で走り出した
- **Core message**: 開業時の東海道新幹線は0系・最高210km/h・1日平均60本で東京〜新大阪を4時間で結んだ
- **Content**: 4:00(開業時の東京〜新大阪) · 0系 最高速度210km/h · 1日平均60本(開業時) · 開業日 1964年10月1日
- **Images**: era_1964.jpg
- **Fact IDs**: F001, F004, F011, F012
- **Motion suggestion**: 「4:00」と丸い先頭の記号が次ページの年表の最初の節点へ Morph で移る

### Part 2: 速さを積み上げる

#### Slide 05 - 所要時間の階段

- **Audience move**: 速くなったことは知っている → 7世代の車両の交代と、4:00→2:21の短縮が対応していると理解する
- **Relationships**: order:0系 → 100系 → 300系 → 700系 → N700系 → N700A → N700S(営業開始年順);link:各型式とその時代の最速所要時間
- **Composition**: 藍の軌道線を年表の軸にし、7つの節点を並べる。節点ごとに型式・年・最高速度、上段に所要時間の推移
- **Title**: 7世代で、4時間は2時間21分に
- **Core message**: 型式が代わるたびに最高速度と所要時間が段階的に更新され、60年で約1時間40分短くなった
- **Content**: 0系 1964 210km/h(4:00) · 100系 1985 220km/h · 300系 1992 270km/h(2:30) · 700系 1999 270km/h · N700系 2007 270km/h(2:25) · N700A 2013 285km/h(2:22、2015年3月から285km/h) · N700S 2020 285km/h(2:21) · 注記:年表は当資料による整理
- **Fact IDs**: F010, F012, F013, F014, F015, F016, F017, F018
- **Motion suggestion**: 前ページから受け渡された「4:00」を起点に、節点を左から右へ

#### Slide 06 - 何が速さを生んだか

- **Audience move**: 速さ=モーターの力と思っている → 軽量化・車体傾斜・ブレーキ・半導体など、型式ごとの具体的な技術が速さと安全を支えたと知る
- **Relationships**: parent:各型式 → その技術の要点
- **Composition**: 表が主役、左上に判断文、表の上に一行の読み方
- **Title**: 速さは、軽さと賢さの積み重ねだった
- **Core message**: 型式ごとの技術の要点を並べると、速さは軽量化・曲線通過・制動・省エネの改良の積み重ねで生まれたとわかる
- **Content**: 表(型式/営業開始/最高速度(東海道区間)/技術の要点):0系 1964年10月 210→220km/h オール電動車で開業 · 100系 1985年10月 220km/h 新幹線初の2階建て車両 · 300系 1992年3月 270km/h アルミ合金車体と誘導電動機で0系比約30%軽量化 · 700系 1999年3月 270km/h 空力を改善した先頭形状 · N700系 2007年7月 270→285km/h 新幹線初の車体傾斜システム · N700A 2013年2月 285km/h 中央締結ブレーキディスクと地震ブレーキ · N700S 2020年7月 285km/h 高速鉄道で世界初のSiC素子
- **Visualization**: rolling-stock-table — 7行×4列の記録表
- **Native-ready**: rolling-stock-table=yes
- **Fact IDs**: F012, F013, F014, F015, F016, F017, F018, F037, F038, F039

### Part 3: 本数を積み上げる

#### Slide 07 - 60本から395本へ

- **Audience move**: 速さの話だと思っていた → 次の主役は「本数」だと切り替わる
- **Relationships**: contrast:開業時と2025年度の1日の本数
- **Composition**: 章の扉。巨大な「395」が主役、小さく「60」、倍数の丸いバッジ
- **Title**: 次の主役は、本数だった
- **Core message**: 1日の列車本数は開業時の平均60本から2025年度には395本、約6.6倍になった
- **Content**: 60本/日(開業時の1日平均) · 395本/日(2025年度、臨時列車を含む) · 約6.6倍(当資料による計算)
- **Fact IDs**: F004, F005
- **Motion suggestion**: 「395」の数字ブロックが次ページで本数の推移の終点へ Morph で移る

#### Slide 08 - 本数を増やした三つの手

- **Audience move**: 本数が増えたことを知った → 品川駅開業・全列車270km/h化・「のぞみ」中心ダイヤがそれを可能にしたと理解する
- **Relationships**: order:1992年度 → 2003年度 → 2019年度 → 2026年3月;link:施策と「のぞみ」本数の増加
- **Composition**: 左に「395」を受け取った数字ブロック、右に「のぞみ」の1時間あたり最大本数が1→7→12→13と増える段
- **Title**: 1時間に「のぞみ」13本の時代へ
- **Core message**: 2003年の品川駅開業と全列車270km/h化で本数の天井が上がり、「のぞみ」は1時間あたり最大1本から13本へ増えた
- **Content**: 「のぞみ」1時間あたり片道最大本数:1992年度 1本 · 2003年度 7本(品川駅開業・全列車270km/h化) · 2019年度 12本 · 2026年3月 13本 · 2024年度の1日平均 383本
- **Fact IDs**: F019, F021, F004, F005

#### Slide 09 - 運んだ量

- **Audience move**: 本数の話を聞いた → 実際に運んだ量(輸送人キロ)がコロナ禍で落ち込み、2025年度にはコロナ前の水準を上回ったと知る
- **Relationships**: order:年度の推移;contrast:2019年度・2020年度・2025年度
- **Composition**: 縦棒グラフが主役。量級の違う1987年度の値は別の数字ブロックで倍数を添える
- **Title**: 落ち込んでも、以前を上回った
- **Core message**: 輸送人キロは2020年度にコロナ禍で182億人キロまで落ちたが、2025年度には609億人キロとコロナ前(2018年度563)を上回った
- **Content**: 縦棒:2002〜2025年度の輸送人キロ(億人キロ) · 数字ブロック:1987年度 321 → 2025年度 609(約1.9倍) · 2025年度 1日50.4万人・年間1億8,400万人
- **Visualization**: pkm-columns — 縦棒グラフ(単位:億人キロ、軸タイトル「輸送人キロ(億人キロ)」、カテゴリ「年度」)
- **Native-ready**: pkm-columns=yes
- **Fact IDs**: F020, F006

#### Slide 10 - 正確さと輸送力

- **Audience move**: 量の多さを知った → 多いのに遅れない(平均1.0分)、席数は航空の約13倍という「大量・正確」の組み合わせに驚く
- **Relationships**: contrast:新幹線と航空の輸送力・シェア
- **Composition**: 左に大きな「1.0分」、右に38万席と3万席の対比(倍数を添える)、下にシェアの帯
- **Title**: たくさん走らせて、遅れは平均1.0分
- **Core message**: 1日395本を走らせながら平均遅延は1.0分で、東京圏〜大阪圏の輸送力は航空の約13倍、シェアは86%に達する
- **Content**: 平均遅延 1.0分/列車(2025年度、自然災害等を含む) · 1日の輸送力 約38万席 vs 航空 約3万席(2025年4月、約13倍は当資料による計算) · 対航空シェア 鉄道86%・航空14%(東京圏〜大阪圏、2024年度) · 1座席当たりエネルギー 約8分の1、CO₂ 約12分の1(対航空機)
- **Fact IDs**: F007, F022, F023, F024

### Part 4: 安全を積み上げる

#### Slide 11 - 死傷事故ゼロ

- **Audience move**: 速さと量の話を聞いた → そのすべての前提に「乗車中の死傷事故ゼロ」があると気づく
- **Relationships**: none
- **Composition**: 全面に二色化した軌道の画像、左に藍の平面、その上に巨大な「0」と一行
- **Title**: 60年間、乗車中の死傷事故はゼロ
- **Core message**: 開業以来、乗車中のお客様が死傷される列車事故は一度も起きていない
- **Content**: 0 · 開業以来、乗車中のお客様が死傷される列車事故ゼロ · 出典:JR東海 ファクトシート2026
- **Images**: rails_dusk_duotone.jpg
- **Fact IDs**: F008

#### Slide 12 - 揺れより先に止める

- **Audience move**: 地震国でなぜ安全なのか疑問 → 地震計でP波を捉えて送電を止め、列車を自動で止める仕組みを理解する
- **Relationships**: order:地震発生 → P波検知(遠方地震計・沿線地震計・緊急地震速報) → 送電停止 → 列車の非常ブレーキ
- **Composition**: 左から右への流れ図(地震計 → 変電所 → 列車)、下に早期化の数字
- **Title**: 大きな揺れが来る前に、列車を止める
- **Core message**: 地震防災システムは遠方地震計・沿線地震計・緊急地震速報でP波を捉え、送電を止めて列車を自動的に緊急停止させる
- **Content**: 遠方地震計 21箇所 · 沿線地震計 50箇所 · 緊急地震速報(地震計 約1,000) · 送電停止 → 非常ブレーキ · 通称「テラス」、2008年から緊急地震速報と併用 · 推定に必要なデータ 2秒→1秒 · 海底地震観測網で 南海トラフ最大約15秒・日本海溝最大約30秒 早く検知 · 注記:流れ図はJR東海資料をもとに当資料で整理
- **Fact IDs**: F025, F026, F027
- **Motion suggestion**: 流れ図の矢印を左から順に

#### Slide 13 - 線路と構造物を守る

- **Audience move**: 列車を止める仕組みを知った → 止めた後に脱線させない・構造物を壊さない備えも進んでいると知る
- **Relationships**: membership:脱線・逸脱防止と構造物の耐震補強と大規模改修(三つの備え)
- **Composition**: 三つの数字の塊を大小差をつけて置く。脱線防止ガードの進捗を主役に
- **Title**: 止めたあとも、脱線させない
- **Core message**: 脱線防止ガードは約937kmが完了し2028年度に全線完了の見込み、構造物の耐震補強や大規模改修も進めている
- **Content**: 脱線防止ガード 約937km完了(2025年度末)、2028年度までに全線完了見込み · 逸脱防止ストッパ 全車両に設置済み · 耐震補強完了:高架橋柱 約19,600本・橋脚 約900基・盛土 約9.4km(2025年度末) · 大規模改修工事 2013年度に着手
- **Fact IDs**: F028, F029, F035

### Part 5: 次の60年

#### Slide 14 - 次の60年:中央新幹線

- **Audience move**: 60年の積み上げを理解した → 次の段階が「大動脈の二重化」であり、開業時期は未定だと区別して理解する
- **Relationships**: contrast:東海道新幹線と中央新幹線の所要時間;membership:公表済みの事実と未確定の点
- **Composition**: 右に太陽円盤に切り抜いたガイドウェイの画像、左に所要時間の比較、下に「決まっていること/決まっていないこと」の二段
- **Title**: 次の60年は、大動脈を二重にする
- **Core message**: 中央新幹線は最高500km/hで品川〜名古屋を最速40分で結ぶ計画だが、静岡工区の着手の見込みが立たず、開業時期は見通せない
- **Content**: 品川〜名古屋 最速86分→40分 · 品川〜大阪 最速134分→67分 · 営業速度500km/h · 決まっていること:技術開発は完了と評価(国交省評価委員会)・工事契約82件・用地取得約85%(2026年3月末) · 決まっていないこと:開業時期(「2027年以降」の計画、静岡工区の掘削着手の見込みが立たず見通せない)・総工事費は7.04兆円から11.0兆円の見通し(2025年10月) · 目的:東海道新幹線の経年劣化と大規模災害に備える二重系化
- **Images**: guideway_dawn.jpg
- **Fact IDs**: F030, F031, F032, F033, F034, F036

#### Slide 15 - 結び

- **Audience move**: 情報を受け取った → 「速さ・本数・安全を同時に積み上げた60年」という一文を持ち帰り、出典をたどれる
- **Relationships**: link:四つの数字 → 一つの結論;order:次の60年への問い
- **Composition**: 上半分に結論の一文、下半分に主要出典のリンク一覧(ページ下部の帯)
- **Title**: 積み上げた60年、二重にする次の60年
- **Core message**: 東海道新幹線は速さ・本数・定時性・安全を同時に積み上げた。次の60年は、その大動脈を二重にして守る段階にある
- **Content**: 結論の一文(当資料による整理) · 主要出典(リンク):JR東海 ファクトシート2026「東海道新幹線」https://company.jr-central.co.jp/ir/factsheets/_pdf/factsheets2026-02-01.pdf · 同「地震対策」https://company.jr-central.co.jp/ir/factsheets/_pdf/factsheets2026-03.pdf · 同「中央新幹線計画」https://company.jr-central.co.jp/ir/factsheets/_pdf/factsheets2026-07.pdf · JR東海 ニュースリリース(2024年2月15日)https://jr-central.co.jp/news/release/_pdf/000043174.pdf · JR東海 ニュースリリース(2017年10月30日)https://jr-central.co.jp/news/release/_pdf/000035513.pdf · JR東海 採用サイト「新幹線鉄道事業」https://saiyo.jr-central.co.jp/company/business/shinkansen.html · 上野雅之(2017)日本機械学会誌 https://www.jstage.jst.go.jp/article/jsmemag/120/1179/120_10/_pdf/-char/ja
- **Closing impact**: 「速さ・本数・安全を同時に積み上げた60年、次は二重にして守る60年」を結論として持ち帰らせる。構図は Reference
- **Fact IDs**: F003, F005, F008, F009, F036

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 各ページの判断文を話し言葉で補い、数字は出典名と参照年を添えて読み上げる。スライドにない数字は研究ノート(sources/tokaido_shinkansen_60_research.md)の事実IDに限る。日本語で書く
- **Total duration**: 約25分(1ページ平均1分40秒)
- **Notes style**: conversational(一般聴衆への語りかけ、問いかけで次ページへ橋渡し)
- **Presentation purpose**: 60年の歩みを検証できる数字で振り返り、速さ・本数・定時性・安全の積み上げの仕組みを示し、次の60年(中央新幹線)を公表情報どおりに位置づける
