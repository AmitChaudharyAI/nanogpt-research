# Hypothesis — Attention-Head Ablation n_head=8

Increasing the number of attention heads from the 4-head reference to 8 heads may alter the model's ability to represent different attention patterns. Because the embedding dimension remains fixed at 112, increasing the number of heads reduces the dimensionality available to each head from 28 dimensions per head to 14 dimensions per head. The effect on validation performance is therefore empirical.

