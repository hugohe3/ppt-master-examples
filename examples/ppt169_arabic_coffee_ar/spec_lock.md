<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: ar-SA
- audience: جمهور عام يحضر محاضرة عامة باللغة العربية دون معرفة متخصصة
- objective: تعريف الحاضرين بالقهوة العربية لغةَ ضيافة وشرح تحضيرها وآدابها واعترافها الدولي وبيانات إنتاجها، بحيث يستطيع الحاضر شرح رمزيتها وترتيب التقديم وإشارة هزّ الفنجان والتمييز بين إدراجي 2015 و2022
- core_message: القهوة العربية ليست مشروباً فحسب، بل لغة ضيافة لكل خطوة فيها معنى؛ ولهذا صارت تراثاً إنسانياً
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: narrative, instructional
- mode_behavior: خطاف سردي في الافتتاح ثم شرح تعليمي متدرّج (المعنى، التحضير، الآداب، الاعتراف، الأرقام) بعناوين تقريرية تحمل حكماً واحداً لكل صفحة وخطوات متوازية البنية وإشارات انتقال في الملاحظات

## visual_style
- visual_style: custom
- visual_style_references: editorial, photo-editorial
- visual_style_behavior: هيكل تحريري من اليمين إلى اليسار بمسطرة رأسية نحاسية رفيعة يتدلّى منها النص، عنوان نسخي كبير ومتن بلا زوائد وكيكر صغير، أعمدة غير متساوية؛ صور طبيعة صامتة دافئة في النصف الأيسر أو مجال كامل تُقصّ في قوس المجلس أو دائرة المقلاة؛ لا بطاقات مكرّرة ولا ظلال زخرفية، والتدرّج الوحيد ستارة لقراءة النص فوق الصورة

## colors
- background: #F6EFE4
- secondary_bg: #EADCC6
- primary: #4A2C1D
- accent: #B8862B
- secondary_accent: #5E7D4F
- body_text: #2B1D15
- secondary_text: #6E5A4C
- divider: #D6C3A5
- scrim: #1E120B
- image_rendering: custom
- image_rendering_references: corporate-photo
- image_rendering_behavior: تصوير طبيعة صامتة تحريري منخفض الإضاءة بضوء نافذة جانبي دافئ وخلفية بنية داكنة غير مركّزة وعمق ميدان ضحل ومواد حقيقية، مدرّج نحو البنّ المحمّص مع لمعات نحاسية ولمسة خضراء من الهيل، بلا نص ولا شعارات ولا وجوه

## typography
- font_family: 'Segoe UI', sans-serif
- title_family: 'Times New Roman', serif
- body_family: 'Segoe UI', sans-serif
- display_family: 'Times New Roman', serif
- body: 26
- title: 48
- subtitle: 34
- lead: 30
- annotation: 20
- footnote: 16
- kicker: 20
- display: 96
- cover_title: 120

## icons
- library: tabler-outline
- stroke_width: 1.5
- inventory: tabler-outline/coffee, tabler-outline/flame, tabler-outline/seedling, tabler-outline/mountain, tabler-outline/link, tabler-outline/world, tabler-outline/calendar, tabler-outline/users, tabler-outline/sun, tabler-outline/droplet, tabler-outline/hand-stop, tabler-outline/arrow-narrow-left, tabler-outline/chevron-left, tabler-outline/map-pin, tabler-outline/building-arch, tabler-outline/leaf, tabler-outline/certificate, tabler-outline/filter, tabler-outline/hourglass, tabler-outline/external-link, tabler-outline/grain

## images
- dallah_hero: images/dallah_hero.jpg | source=ai | crop=adaptive
- roasting_tawa: images/roasting_tawa.jpg | source=ai | crop=adaptive
- three_dallahs: images/three_dallahs.jpg | source=ai | crop=adaptive
- cardamom: images/cardamom.jpg | source=ai | crop=adaptive
- finjan_hand: images/finjan_hand.jpg | source=ai | crop=adaptive
- terraces: images/terraces.jpg | source=ai | crop=adaptive
- terraces_duo: images/terraces_duo.jpg | source=ai | crop=adaptive
- dallah_hero_blur: images/dallah_hero_blur.jpg | source=ai | crop=adaptive

## page_visualizations
- P07: table/comparison_matrix
- P13: chart/horizontal_bar_chart

## page_rhythm
- P01: anchor
- P02: dense
- P03: dense
- P04: breathing
- P05: dense
- P06: dense
- P07: dense
- P08: dense
- P09: breathing
- P10: dense
- P11: dense
- P12: anchor
- P13: dense
- P14: dense
- P15: anchor

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
