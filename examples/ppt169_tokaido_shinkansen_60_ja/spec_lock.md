<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: ja-JP
- audience: 一般の聴講者(新幹線の利用経験はあるが技術・統計の詳細は知らない市民)
- objective: 60年の歩みを検証できる数字で振り返り、速さ・本数・定時性・安全の積み上げの仕組みを示して、聴衆が主要な数字を仕組みと結びつけて説明し、中央新幹線の公表済み計画と未確定点を区別できるようにする
- core_message: 東海道新幹線の60年は速さ・本数・定時性・安全を同時に積み上げた60年であり、次の60年はその大動脈を二重にする段階に入っている
- consumption_mode: presentation

## mode
- mode: custom
- mode_references: narrative
- mode_behavior: 1964年の出発の瞬間から始め、速さ→本数→安全の三章で各章の山場に一つの決定的な数字を見せてから仕組みを説明し、最後に次の60年の未確定点を正直に示して二重化の問いで結ぶ。タイトルは物語を一歩進める判断文にする。

## visual_style
- visual_style: custom
- visual_style_references: vintage-poster
- visual_style_behavior: 昭和の記念ポスター。クリーム色の紙の地に藍の大きな平面ブロック・朱の太陽円盤・黄土の帯を少数重ね、角の丸い幾何形とやや斜めの帯でレトロな緊張を出す。数字はポスター級で一点に置き、細い二重罫と丸いバッジで出典や年代を添える。網点と紙の粒子を低い不透明度で重ね、影やグラデーションではなく重なりで奥行きを出す。見出しは明朝、本文はゴシック、巨大数字は極太サンセリフ。

## colors
- background: #F3ECDD
- secondary_bg: #E6DCC6
- primary: #1F3F74
- accent: #C8442C
- secondary_accent: #D9A33A
- body_text: #22262E
- secondary_text: #5E5A52
- divider: #C7B99D
- image_rendering: custom
- image_rendering_references: vintage-poster
- image_rendering_behavior: 1960年代の旅行ポスターのような簡略化した平面ブロックで描き、輪郭は太く手の気配を残し角は丸い。藍・朱・黄土・クリームの限られた平面色に網点を10〜15%重ね、わずかな版ずれと紙の粒子で印刷の古さを出す。山・太陽・高架橋・列車を記号的な形に還元し、影ではなく重なりで奥行きを作る。文字・数字・企業ロゴ・社章は描かない。

## typography
- font_family: 'Segoe UI', 'Yu Gothic', sans-serif
- title_family: 'Times New Roman', 'Yu Mincho', serif
- body_family: 'Segoe UI', 'Yu Gothic', sans-serif
- display_family: 'Arial Black', 'Yu Gothic', sans-serif
- kpi_family: 'Arial Black', 'Yu Gothic', sans-serif
- body: 28
- title: 48
- subtitle: 34
- annotation: 22
- lead: 32
- footnote: 16
- cover_title: 96
- display: 132
- kpi: 64

## icons
- library: chunk-filled
- inventory: chunk-filled/train, chunk-filled/clock, chunk-filled/stopwatch, chunk-filled/gauge-high, chunk-filled/users, chunk-filled/calendar, chunk-filled/shield-check, chunk-filled/bolt, chunk-filled/waveform, chunk-filled/bridge, chunk-filled/mountains, chunk-filled/magnet, chunk-filled/route, chunk-filled/map-pin, chunk-filled/leaf, chunk-filled/link, chunk-filled/chair, chunk-filled/power, chunk-filled/signal, chunk-filled/wrench, chunk-filled/flag

## images
- cover: images/cover_poster.jpg | source=ai | crop=adaptive
- era: images/era_1964.jpg | source=ai | crop=adaptive
- rails: images/rails_dusk_duotone.jpg | source=ai | crop=adaptive
- guideway: images/guideway_dawn.jpg | source=ai | crop=adaptive

## page_rhythm
- P01: anchor
- P02: breathing
- P03: dense
- P04: anchor
- P05: dense
- P06: dense
- P07: anchor
- P08: dense
- P09: dense
- P10: dense
- P11: breathing
- P12: dense
- P13: dense
- P14: dense
- P15: anchor

## page_visualizations
- P03: chart/horizontal_bar_chart
- P06: table/record_table
- P09: chart/column_chart

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
