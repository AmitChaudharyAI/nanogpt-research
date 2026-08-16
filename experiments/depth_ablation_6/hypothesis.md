# Hypothesis — Depth Ablation n_layer=6

Increasing the number of Transformer layers while keeping the embedding dimension, attention heads, training procedure, dataset, and other hyperparameters fixed is expected to improve language-model validation performance by increasing representational capacity, but at the cost of increased parameter count and computational cost.

This experiment tests n_layer=6 with n_embd=112 and n_head=4.
