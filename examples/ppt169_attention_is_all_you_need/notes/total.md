# 01_cover

Welcome. This talk walks through Attention Is All You Need, the 2017 paper from eight Google researchers that introduced the Transformer. The subtitle already gives away the punchline: one architecture, no recurrence, no convolutions, and a training run measured in days rather than weeks. We will read it the way an engineer reads a drawing set, sheet by sheet.

---

# 02_contents

Here is the drawing index. We start with the bottleneck that recurrent and convolutional models ran into, then look at the architecture as a whole. The longest section takes attention apart step by step: scaled dot-product attention, multi-head attention, the three places it is used, and positional encoding. After that we cover the training recipe, the results against the field, and the ablations, and we close with what was built on top of the paper.

---

# 03_bottleneck

Before 2017, the two dominant sequence models both paid for word order with time. A recurrent network computes each hidden state from the previous one, so a sentence of n tokens needs n sequential steps and the signal from position one reaches position n only after n hops; nothing inside a single example can run in parallel. Convolutional models such as ByteNet and ConvS2S fixed the parallelism problem, but two distant positions still meet only after a stack of layers, so the path shrinks to logarithmic length rather than disappearing. Both architectures charge what you might call a distance tax, and the paper's question is simply: what if every path had length one?

---

# 04_idea

The answer is in the abstract. The authors propose a new, simple architecture based solely on attention mechanisms, dispensing with recurrence and convolutions entirely. They back that with three measurable claims. Quality: 28.4 BLEU on English to German, more than two points above the best previous result, ensembles included. Parallelism: the number of sequential operations per layer is constant, so every position is handled at once. And speed: the big model trained for three and a half days on eight P100 GPUs, setting a new single-model record of 41.8 BLEU on English to French.

---

# 05_architecture

This is the whole machine. On the left, the encoder is a stack of six identical layers, each with a multi-head self-attention sub-layer and a position-wise feed-forward network, and every sub-layer is wrapped in a residual connection followed by layer normalization. On the right, the decoder has the same six layers but adds a third sub-layer: a masked self-attention block, then an attention block that reads the encoder output, then the feed-forward network, before a final linear layer and softmax produce output probabilities. Inputs and outputs are embedded and summed with a positional encoding, and everything keeps a common width of 512. The feed-forward inner dimension is 2048, there are eight heads of size 64, and the base model has about 65 million parameters while the big model has 213 million.

---

# 06_scaled_dot_product

Attention itself is one formula. Multiply the queries by the transposed keys to get a score for every query against every key, divide by the square root of the key dimension, take a softmax so each row becomes a set of weights, and use those weights to mix the values. A query says what a position is looking for, a key says what each position offers for matching, and a value is what gets passed along once matched. The scaling matters: with large key dimensions the dot products grow large and push the softmax into regions with tiny gradients, and dividing by eight for a key size of 64 keeps the scores tame.

---

# 07_multi_head

Instead of one attention with full width, the Transformer runs eight of them in parallel. Queries, keys and values are each projected by learned linear maps into a 64-dimensional subspace, each head runs scaled dot-product attention there, the eight outputs are concatenated, and a final linear layer mixes them back to 512 dimensions. Because each head works at reduced width, the eight together cost about as much as a single full-width head. The ablation shows why it is worth it: a single head is 0.9 BLEU worse than the best setting.

---

# 08_three_uses

The same block is used in three places. In the encoder, queries, keys and values all come from the previous layer, so every position looks at every other position in both directions in one step. In the decoder, the self-attention is masked so that position i may only attend to positions up to i, which keeps generation auto-regressive; that is also why the outputs are shifted right by one. And in encoder-decoder attention, the queries come from the decoder while the keys and values come from the encoder output, so every output position can read the whole input sentence, replacing the classic sequence-to-sequence attention.

---

# 09_positional_encoding

Without recurrence, nothing in the model knows where a token sits, so the paper adds a positional encoding to the embedding. Each dimension is a sinusoid with its own wavelength, sine on even dimensions and cosine on odd ones, with wavelengths running from two pi up to ten thousand times two pi, so every position gets a unique code and for any fixed offset the encoding of a later position is a linear function of the earlier one. Learned positional embeddings performed nearly identically in the ablation; the sinusoidal version was kept because it might extrapolate to sequence lengths never seen in training. Note that the encoding is added, not concatenated, so the width stays 512 with no extra parameters.

---

# 10_why_self_attention

Table one compares the costs. Self-attention connects any two positions in a constant number of sequential operations with a constant path length, at a per-layer cost that grows with the square of the sequence length times the dimension. Recurrence is cheaper per layer when sequences are long, but its sequential operations and path length both grow with n; convolution parallelizes but still needs a logarithmic number of layers to connect distant positions. Since word-piece and byte-pair sentences are usually shorter than the representation width, self-attention wins on speed in practice, and a restricted variant with a window r remains available for very long inputs.

---

# 11_training_recipe

Here is the recipe as a spec sheet. English to German used about four and a half million sentence pairs with a shared byte-pair vocabulary of roughly thirty-seven thousand tokens; English to French used thirty-six million sentences with a thirty-two thousand word-piece vocabulary, batched at about twenty-five thousand source and target tokens each. Training ran on one machine with eight P100 GPUs: the base model for one hundred thousand steps at 0.4 seconds each, about twelve hours, and the big model for three hundred thousand steps, three and a half days. The optimizer was Adam with a learning rate that ramps up linearly for four thousand steps and then decays with the inverse square root of the step, plus residual dropout of 0.1 and label smoothing of 0.1.

---

# 12_results

The results are Table two of the paper. On English to German the big Transformer reaches 28.4 BLEU, ahead of every single model and every ensemble in the comparison, and even the base model at 27.3 beats the best prior ensemble. On English to French the big model reaches 41.8, a new single-model state of the art. The cost comparison is the striking part: the base model used about 3.3 times ten to the eighteenth floating-point operations versus 1.8 times ten to the twentieth for the GNMT ensemble, roughly fifty-five times less compute for a better English to German score.

---

# 13_ablations

Table three varies one setting at a time on the base model. A single attention head is 0.9 BLEU worse than the best configuration, and shrinking the key dimension also hurts, which suggests computing compatibility is not a trivial function. Bigger models do better, dropout is very helpful against over-fitting, and learned positional embeddings are nearly identical to the sinusoids. The paper then tests generalization on English constituency parsing: a four-layer Transformer trained on the Wall Street Journal data alone reaches 91.3 F1, and 92.7 with semi-supervised data, supporting the abstract's claim that the architecture works beyond translation with both large and limited data.

---

# 14_legacy

What followed is most of modern machine learning. In 2018, BERT and the first GPT built pretrained language models on the Transformer; in 2021 the Vision Transformer and DALL-E carried it into images; by 2024 systems like Stable Diffusion 3 and Sora used it for image and video generation. As of 2026 the paper has been cited more than two hundred and fifty thousand times, placing it among the ten most-cited papers of this century. All eight authors have since left Google to join other companies or found startups, and the title is still a nod to the Beatles' All You Need Is Love.

---

# 15_ending

So, three things to take away. Drop recurrence and let every position attend to every other in a single step. Eight heads, scaled dot-products and sinusoidal positions do the real work. And the payoff was measurable: 28.4 and 41.8 BLEU after three and a half days on eight GPUs, quality and speed at once. The paper is short and readable; the link on this slide takes you to it on arXiv. Thank you.
