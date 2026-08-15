# Experiment 003 — Depth Ablation

This experiment evaluates the effect of reducing Transformer depth from 4 layers to 2 layers while preserving the frozen `n_embd=112` configuration from the previous embedding-dimension ablation.

The experiment uses the verified Tiny Shakespeare character-level dataset and the same CPU training and sampling procedure as the frozen reference experiment.

Controlled variable:

- `n_layer`: 4 -> 2

All other model, optimizer, dataset, training, and sampling settings remain unchanged.
