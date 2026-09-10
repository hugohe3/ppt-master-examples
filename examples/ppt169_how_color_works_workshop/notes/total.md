# 01_cover

Open on the picture rather than the title. One beam of white light goes into the prism and a whole spectrum comes out the other side, and that single fact is the reason every argument in this room about colour is possible at all. Say plainly what this session is not: it is not ninety minutes of taste, and nobody is going to be told their palette is wrong because someone senior prefers blue. What is not printed on the slide is the promise behind it, which is that by the end each person will be able to defend a colour decision with a number instead of an adjective. If someone asks whether this is an accessibility session, the honest answer is that accessibility is where the only hard rule lives, so we go there, but the rule turns out to be useful far beyond compliance.

---

# 02_objectives

Read the four objectives as things people will do, not topics they will hear about. The one worth pausing on is the third, because it is the only one that requires them to touch their own material, and it is the one they will be doing at the fifty-minute mark. The run sheet on the right is there so nobody has to ask how long this goes on; point at the twelve-minute block and say that it is real working time, not a demo. The question that usually comes now is whether they need special software, and the answer is no, any image and one free web checker. Mention the simplification note at the bottom before anyone catches it later: this deck flattens two things on purpose, and both are marked where they happen.

---

# 03_three_cones

The spectrum band across the top is the thing being sampled, and the point of the faded ends is that the boundary is a rounding convention, not a wall. Different textbooks give 380 to 700, 380 to 750, or 400 to 700 nanometres, so treat any exact figure with suspicion. The chart underneath is the whole of colour vision in three bars: three cone types, with measured mean peaks at about 420, 534 and 563 nanometres from the classic Bowmaker and Dartnall measurement. Say the number that usually lands hardest, which is that there are only about six million cones against a hundred and twenty million rods, so colour is a thin, expensive layer of vision concentrated in the middle of the retina. Then mark the simplification out loud: the real sensitivity curves are broad and heavily overlapping, not three clean spikes, and anyone who wants the actual tabulated curves can get them from the Colour and Vision Research Lab at UCL.

---

# 04_two_mixings

Both diagrams have exactly the same geometry on purpose, so the only thing that differs is what happens where the circles cross. On the dark side you are adding light and the overlaps get brighter until all three together give white, which is how every screen in the room works. On the light side you are adding ink to paper that already reflects everything, and each layer takes part of the spectrum away, so the overlaps get darker and all three together approach black. The relationship worth stating slowly is that each primary in one system is a secondary mixture in the other, which is why cyan, magenta and yellow are not an arbitrary choice by printers. The practical consequence is the one to leave hanging: a colour picked on a screen has no obligation whatsoever to be reachable in ink, and that is where most print surprises come from.

---

# 05_three_dials

Introduce hue, saturation and lightness as three independent controls, and make sure the hue dial is understood as an angle rather than a list of colour names. The wheel on the right is Johannes Itten's twelve-hue wheel from his 1961 Art of Color, built out of the course he taught at the Bauhaus, and he presented those schemes as one of several kinds of contrast useful for teaching, not as a law. Draw the line between the two opposite wedges and say that this is all a complementary pair is: two positions a hundred and eighty degrees apart on a circle somebody drew. Munsell drew a different circle using perceptually equal steps, and on that circle the complements land somewhere else, which is the whole argument in one sentence. Anyone who wants to defend harmony rules should be free to use them, but they are inherited practice and not something you could derive from the physics on the previous pages.

---

# 06_lightness_rule

This is the hinge of the session, so slow down. The W3C's text-contrast rule is written purely as a function of relative luminance, and if you read the formula on the slide you will notice there is no term in it for hue and no term for saturation at all. The two demonstrations make the same point from opposite directions: red and green sit a hundred and twenty degrees apart and still measure 1.10 to 1, which is effectively no contrast, while two tones of one blue measure 9.90 to 1 and read cleanly. The wheel on the right is the same wheel from the previous page with the hue and saturation drained out, leaving only what the rule actually measures, and the two so-called complementary wedges come out at 2.78 to 1 either way. The instruction that follows is simple enough to remember without notes: judge the pair in greyscale first, and only argue about hue after it passes.

---

# 07_wcag_thresholds

Treat this as the page they photograph. There are only five numbers in the whole rule, and the most used one is 4.5 to 1 for normal body text at level AA. Large text drops to 3 to 1, and large text has an exact definition worth reading out because people guess it wrong: eighteen point, or fourteen point bold, which the spec itself puts at roughly twenty-four and eighteen and a half pixels. The row that surprises people is the last one, because 1.4.11 puts a 3 to 1 floor on interface components and on graphics you need in order to understand the content, which means icons, chart lines and form borders, not just text. Mention that the ratio must not be rounded before comparing, because a 4.49 that someone reported as 4.5 is a fail.

---

# 08_demo_extract

Do this live rather than describing it. The print is Hokusai's Under the Wave off Kanagawa from around 1830, and it works for this exercise because it is genuinely public domain and because its colours are structural rather than decorative. Narrate the order out loud as you sample, because the order is the transferable part: largest area first, then the darkest, then the lightest, and only then two accents chosen because they carry meaning rather than because they cover ground. Keep writing the region next to each swatch, since a hex value with no memory of where it came from is the thing people cannot defend a week later. End on the unglamorous line at the bottom rather than on the palette, because five samples that look pleasant together have not been tested against anything yet.

---

# 09_demo_measure

The palette from the previous page comes across unchanged, and now every pair gets measured against the 4.5 to 1 body-text floor. Walk the grid quickly rather than reading it; the useful observation is how few pairs actually clear the line once you stop trusting your eye. The circled cell is the interesting one because it fails at 4.29, which is close enough that nobody would have caught it by looking. Show the repair as a single move: hue held, saturation held, lightness taken down about one percent, and the ratio clears at 4.55 while the palette still reads as the same palette. Close honestly, because someone always asks whether passing means good: it does not, it means usable, and taste starts after the floor is met, not instead of it.

---

# 10_practice

Hand this over cleanly and then stop talking. The task is on their own image, because a palette pulled from something they care about is the one they will remember. Read the success condition word for word, since a vague success condition is why exercises drift: five hex values written down, one measured ratio, and that ratio at 4.5 to 1 or above. The escape route matters more than it looks, because the people who stall are almost always stalling on meaning rather than sampling, so tell them to fall back to sampling by area. Give the twelve minutes properly and give a two-minute warning; if the room is running behind, cut the comparison at the end rather than cutting the working time.

---

# 11_mistake_saturation

Show the three states in order and let the middle one do the work. The caption starts at 2.63 to 1, which fails, and the instinctive fix is to push the colour until it looks stronger. Pushing saturation to full takes it to 2.28 to 1, which is worse, and the reason is on the strip below: the relative luminance actually went up, from 0.33 to 0.38, which moved it closer to the page rather than further from it. Lowering lightness instead drops the luminance to 0.17 and the ratio clears at 4.53. Be generous about why the mistake happens, because on a large bright monitor the louder colour really does look stronger to the person making it, and that is a perception problem rather than carelessness.

---

# 12_mistake_rainbow

Put the two ramps side by side and read the luminance numbers under them out loud, because that is the entire argument. The rainbow ramp goes 0.02, 0.17, 0.26, 0.73 and then back down to 0.16, so the fourth step is by far the brightest and the last step is darker than the second, which means the ordering the reader perceives is not the ordering in the data. Borland and Taylor documented three separate defects in 2007 and they are worth naming individually, because people usually only know the accessibility one. Crameri and colleagues found in 2020 that these maps are still common in published science and proposed perceptually uniform alternatives. The chart at the bottom is why this compounds: about one man in twelve has a colour vision deficiency, deuteranomaly alone accounts for five percent, and a hue-only encoding excludes all of them at once.

---

# 13_check

Give the room a minute on the three questions before showing the answers, and resist answering them yourself in the meantime. The first question is really asking whether they understood that the fix lives on the lightness dial and not the hue dial. The second is checking whether the rule and convention distinction survived, and the correct answer is that none of the triadic claim is a rule. The third is checking whether the rainbow objection is understood as a data problem before it is understood as an accessibility problem. If anybody gets all three, they are ready to argue this in a design review, which was the point of the session.

---

# 14_recap_next

Close by mapping the four capabilities back onto the four promises from the second page, in the same order, so the progress is visible rather than asserted. The single sentence at the top is the one to leave them with, because it compresses ninety minutes into an order of operations they can actually follow under deadline. Point at the destinations and say which one to open first: the contrast checker, today, on whatever they are currently building. End on the simplification note rather than on a flourish, since the cone curves really do overlap far more than three bars suggest, and a contrast ratio really is a floor rather than a measure of quality.
