# Experiment 002 — Hypothesis

## Research Question

How does reducing the embedding dimension from 128 to 64 affect the performance and efficiency of the nanoGPT model?

## Hypothesis

Reducing the embedding dimension from 128 to 64 will reduce the number of trainable parameters and computational cost.

This should make training faster, but the reduced representational capacity is expected to increase validation loss and potentially reduce the quality and coherence of generated text.

## Predictions

| Metric | Expected Change |
|---|---|
| Parameter count | Decrease |
| Training time | Decrease |
| Computational cost | Decrease |
| Training loss | Possibly increase |
| Validation loss | Increase |
| Generated text quality | Potentially decrease |

## Controlled Variables

The following will remain unchanged:

- Dataset
- Number of layers
- Number of attention heads
- Context length
- Number of training iterations
- Optimizer
- Learning-rate schedule
- Batch configuration
- Random seed, where applicable

## Independent Variable

Embedding dimension:

128 → 64