# Hypothesis

Reducing Transformer depth from 4 layers to 2 layers will reduce parameter count and computational cost, but may degrade training and validation performance and reduce the coherence of generated text.

This experiment changes only `n_layer` relative to the frozen `n_embd=112` reference configuration.
