<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 900 383
- format: wechat

## communication
- primary_language: zh-CN
- audience: 公众号"Typst 入门"连载的中文读者，尚未系统学过 Typst
- objective: 让读者一眼认出同一系列并说出本篇主题，用一段逐字取自教程的代码引起兴趣，文末促成关注
- core_message: Typst 让你少配置也能排版精良（整理）
- consumption_mode: presentation

## mode
- mode: custom
- mode_behavior: 系列识别卡组：头图立系列名与一句主张；章节横幅 = 章节序号 + 本篇主题 + 一段逐字源码（左源码、右效果或要点）；文末把四篇路线收束为一个关注动作；标题用名词短语或短主张。

## visual_style
- visual_style: custom
- visual_style_references: swiss-minimal
- visual_style_behavior: 校样台：严格模块网格、左对齐与大留白，加排版校样语言——四角裁切线、极细基线网格、校对红插入光标块与下划校记；代码放墨黑排字条用等宽字，标题宋体大字；平面、无阴影、无渐变，装饰只来自排版工具记号。

## colors
- background: #F3EEE3
- secondary_bg: #E6DECD
- primary: #1D1A17
- accent: #CF3B2A
- secondary_accent: #A87A2A
- body_text: #27231F
- secondary_text: #6B6358
- divider: #CBC0AC

## typography
- font_family: Microsoft YaHei, Arial, sans-serif
- title_family: SimSun, Cambria, serif
- body_family: Microsoft YaHei, Arial, sans-serif
- code_family: Consolas, Microsoft YaHei, monospace
- display_family: SimSun, Cambria, serif
- body: 24
- title: 50
- subtitle: 30
- annotation: 18
- code: 24
- footnote: 15
- display: 96

## icons
- library: none
- inventory: none

## page_rhythm
- P01: anchor
- P02: dense
- P03: dense
- P04: dense
- P05: dense
- P06: anchor

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 别做成通用科技蓝 (user)
