## Research Brief

- **Supplied-material baseline**: none — the request names the paper "Attention Is All You Need" as a topic only.
- **Requested outcome**: an English-language explainer deck of the paper for a technical audience (what problem it solved, the architecture, the key mechanisms, training recipe, results, and legacy).
- **Declared gaps**: (1) bibliographic identity; (2) architecture hyperparameters and formulas; (3) complexity argument; (4) translation results and training cost; (5) training recipe; (6) ablations and generalization; (7) legacy and impact.
- **Audience / intent**: technical explainer; the user asked for Quick generation written in English.

## Gap 1 — Bibliographic identity

- Paper: *Attention Is All You Need*, arXiv 1706.03762, first submitted 12 June 2017; latest revision v7 dated 2 August 2023 (F001).
- Authors in order: Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N. Gomez, Łukasz Kaiser, Illia Polosukhin — all eight affiliated with Google at publication (F001, F002).
- Published at the 31st Conference on Neural Information Processing Systems (NeurIPS), December 2017 (F002).
- The title references the Beatles song "All You Need Is Love" (F020).

## Gap 2 — Architecture and formulas

- The Transformer is an encoder-decoder model "based solely on attention mechanisms, dispensing with recurrence and convolutions entirely" (F003).
- Base model: N = 6 identical layers in both encoder and decoder; d_model = 512; h = 8 heads; d_k = d_v = d_model / h = 64; d_ff = 2048; about 65 million parameters (F004).
- Big model: N = 6; d_model = 1024; h = 16; d_ff = 4096; about 213 million parameters (F005).
- Scaled dot-product attention: Attention(Q, K, V) = softmax(QKᵀ / √d_k) V (F006).
- Multi-head attention: MultiHead(Q, K, V) = Concat(head_1, …, head_h) W^O, where head_i = Attention(Q W_i^Q, K W_i^K, V W_i^V) (F007).
- Sinusoidal positional encoding: PE(pos, 2i) = sin(pos / 10000^(2i/d_model)); PE(pos, 2i+1) = cos(pos / 10000^(2i/d_model)) (F008).
- Learned positional embeddings produced "nearly identical results" to the sinusoidal version (F016); sinusoids were chosen because PE(pos+k) is a linear function of PE(pos) for any fixed offset k, which may help relative-position learning and extrapolation (F026); wavelengths form a geometric progression from 2π to 10000·2π (F029).
- Scaling by 1/√d_k counteracts large dot products that would push softmax into small-gradient regions (F022). Each head works in a reduced dimension, so multi-head cost is similar to single-head attention at full dimensionality (F023).
- Attention is used three ways: encoder self-attention; masked decoder self-attention (no leftward flow); encoder-decoder attention with decoder queries and encoder keys/values (F024).
- Position-wise FFN(x) = max(0, xW₁ + b₁)W₂ + b₂ with d_ff = 2048 (F025). Every sub-layer is wrapped as LayerNorm(x + Sublayer(x)); all outputs have dimension d_model = 512 (F028).

## Gap 3 — Why self-attention (complexity argument)

- Per-layer complexity, sequential operations, and maximum path length (F009):
  - Self-attention: O(n²·d), O(1), O(1)
  - Recurrent: O(n·d²), O(n), O(n)
  - Convolutional: O(k·n·d²), O(1), O(log_k n)
  - Restricted self-attention (window r): O(r·n·d), O(1), O(n/r)
- Self-attention beats recurrence on speed whenever n < d, the usual case for word-piece / BPE sentence representations in MT (F030).

## Gap 4 — Translation results and training cost

- WMT 2014 English→German (newstest2014) BLEU and training cost in FLOPs (F010):
  - ByteNet 23.75; GNMT+RL 24.6 (2.3·10¹⁹); ConvS2S 25.16 (9.6·10¹⁸); MoE 26.03 (2.0·10¹⁹); GNMT+RL ensemble 26.30 (1.8·10²⁰); ConvS2S ensemble 26.36 (7.7·10¹⁹); Transformer base 27.3 (3.3·10¹⁸); Transformer big 28.4 (2.3·10¹⁹).
- WMT 2014 English→French BLEU and FLOPs (F011):
  - Deep-Att+PosUnk 39.2 (1.0·10²⁰); GNMT+RL 39.92 (1.4·10²⁰); ConvS2S 40.46 (1.5·10²⁰); MoE 40.56 (1.2·10²⁰); Deep-Att ensemble 40.4 (8.0·10²⁰); GNMT+RL ensemble 41.16 (1.1·10²¹); ConvS2S ensemble 41.29 (1.2·10²¹); Transformer base 38.1; Transformer big 41.8.
- Headline claims: 28.4 BLEU on EN-DE improves over the best prior results, including ensembles, by over 2 BLEU; 41.8 BLEU on EN-FR is a new single-model state of the art after 3.5 days of training on eight GPUs (F012).

## Gap 5 — Training recipe

- Data: EN-DE about 4.5 million sentence pairs with a shared byte-pair-encoding vocabulary of about 37,000 tokens; EN-FR 36 million sentences with a 32,000 word-piece vocabulary; batches of about 25,000 source and 25,000 target tokens (F013).
- Hardware and time: one machine with 8 NVIDIA P100 GPUs; base model 0.4 s per step, 100,000 steps ≈ 12 hours; big model 1.0 s per step, 300,000 steps ≈ 3.5 days (F014).
- Optimizer: Adam with β₁ = 0.9, β₂ = 0.98, ε = 10⁻⁹; learning-rate warmup over 4,000 steps then inverse-square-root decay (F015); lrate = d_model⁻⁰·⁵ · min(step⁻⁰·⁵, step · warmup⁻¹·⁵) (F027).
- Regularization: residual dropout P_drop = 0.1 (0.3 for the big EN-FR model); label smoothing ε_ls = 0.1 (F015).

## Gap 6 — Ablations and generalization

- Single-head attention is 0.9 BLEU worse than the best setting; reducing d_k hurts quality; bigger models are better; dropout helps; learned and sinusoidal positional encodings are nearly identical (F016).
- English constituency parsing, WSJ Section 23 F1: a 4-layer Transformer scores 91.3 trained on WSJ only and 92.7 semi-supervised (F017).

## Gap 7 — Legacy and impact

- As of 2026 the paper has been cited more than 250,000 times, among the top ten most-cited papers of the 21st century (F018).
- Later systems built on the Transformer architecture include BERT (2018), the GPT series (from 2018), Vision Transformer / ViT (2021), DALL-E (2021), Stable Diffusion 3 (2024), and Sora (2024) (F019).
- All eight authors subsequently left Google to join other companies or found startups (F021).
