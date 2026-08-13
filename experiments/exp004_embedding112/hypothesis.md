# Experiment 004 — Hypothesis

## Research Question

Can an embedding dimension of 112 provide a better quality-efficiency trade-off than the smaller embedding configurations while remaining more efficient than the 128-dimensional baseline?

## Hypothesis

Reducing the embedding dimension from 128 to 112 will reduce the number of trainable parameters and computational cost.

Because the reduction is relatively small, the 112-dimensional model is expected to show only a small degradation in validation performance compared with the 128-dimensional baseline.

It is also expected to outperform the 96-dimensional and 64-dimensional configurations in validation loss, while using fewer parameters than the 128-dimensional baseline.

## Predictions

| Metric | Expected Result |
|---|---|
| Parameter count | Lower than 128D |
| Training speed | Faster than 128D |
| Training loss | Slightly higher than 128D |
| Validation loss | Slightly higher than 128D |
| Generated text | Slightly less coherent than 128D |
| Comparison with 96D | Better validation performance |
| Comparison with 64D | Better validation performance |

## Independent Variable

Embedding dimension:

128 → 112

## Controlled Variables

The following should remain unchanged:

- Dataset: Tiny Shakespeare
- Number of layers: 4
- Number of attention heads: 4
- Context length: 64
- Training iterations: 2,000
- Optimizer: AdamW
- Learning rate and schedule
- Batch configuration
- Random seed, where applicable
- CPU execution
- All other model and training settings

## Expected Outcome

The 112-dimensional configuration is expected to provide a point closer to the 128-dimensional baseline in language-model quality while requiring fewer parameters and less computation.