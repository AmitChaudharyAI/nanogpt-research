# Experiment: Attention-Head Ablation — n_head=8

This is the final controlled attention-head ablation with `n_embd=112` and `n_layer=2`.

- Only changed variable: `n_head=8`
- Head dimension: `112 / 8 = 14`
- Dataset: `shakespeare_char` at `data/shakespeare_char`
- Device: CPU
- Training iterations: 2,000
- Optimizer: AdamW, unfused on CPU
- Initialization: scratch
- Random seed: 1337 using the repository’s seed mechanism

The experiment belongs to the controlled attention-head series using 4, 7, and 8 heads. Raw training output, configuration, generated samples, analysis, and the local checkpoint are stored in this directory.
