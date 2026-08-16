# Hypothesis — Attention-Head Ablation n_head=7

Changing the number of attention heads while keeping the embedding dimension and depth fixed may affect validation performance by changing how the representation is divided across attention heads. Increasing the number of heads may provide more distinct attention patterns, but each head will operate on a smaller head dimension.

For n_embd=112:

- 4 heads = 28 dimensions/head
- 7 heads = 16 dimensions/head

This experiment tests whether 7 attention heads provide a useful quality–efficiency trade-off relative to the existing 4-head reference.
