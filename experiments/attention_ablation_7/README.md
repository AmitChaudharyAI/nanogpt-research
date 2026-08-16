# Experiment: Attention-Head Ablation — n_head=7

This experiment changes only the number of attention heads relative to the existing Depth-2 reference.

- Frozen embedding dimension: `n_embd=112`
- Frozen depth: `n_layer=2`
- Experimental head count: `n_head=7`
- Head dimension: `112 / 7 = 16`
- Dataset: `shakespeare_char` at `data/shakespeare_char`
- Device: CPU
- Training iterations: 2,000
- Optimizer: AdamW, unfused on CPU
- Random seed: 1337 using the repository’s built-in seed mechanism

The complete configuration, training output, generated samples, observations, results, and local checkpoint are stored in this directory.
