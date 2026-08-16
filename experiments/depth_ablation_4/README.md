# Depth Ablation — n_layer=4

This controlled experiment uses the frozen `n_embd=112` configuration and evaluates a 4-layer Transformer under the same CPU training and generation procedure as the prior depth-2 experiment.

Controlled experiment setting:

- `n_layer=4`

All other model, optimizer, dataset, training, and sampling settings are held constant.
