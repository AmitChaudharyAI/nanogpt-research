# Experiment 003 — Hypothesis

## Research Question

Can an intermediate embedding dimension of 96 provide a better quality-efficiency trade-off than the 64-dimensional model while remaining smaller than the 128-dimensional baseline?

## Hypothesis

Reducing the embedding dimension from 128 to 96 will reduce the number of trainable parameters and computational cost.

Because the reduction is smaller than the 128 → 64 ablation, the 96-dimensional model is expected to show a smaller degradation in validation performance than the 64-dimensional model.

## Predictions

| Metric | Expected Change |
|---|---|
| Parameter count | Decrease relative to 128 |
| Training speed | Increase |
| Training loss | Increase slightly |
| Validation loss | Increase slightly |
| Generated text quality | Slightly worse than 128, but better than 64 |

## Independent Variable

Embedding dimension:

128 → 96

## Controlled Variables

The following variables are kept unchanged from the baseline:

- Dataset: Tiny Shakespeare
- Number of layers: 4
- Number of attention heads: 4
- Context length: 64
- Training iterations: 2,000
- Optimizer: AdamW
- Learning-rate schedule
- Batch configuration
- CPU execution
- Other model and training settings

## Expected Outcome

The 96-dimensional model is expected to occupy a middle position between the 128-dimensional baseline and the 64-dimensional ablation in terms of both model capacity and language-model performance.