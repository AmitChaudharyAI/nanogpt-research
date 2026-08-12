# Experiment 003 — Results

## Experiment

Embedding Dimension Ablation

## Controlled Change

Only one model configuration parameter was changed:

**n_embd: 128 → 96**

All other experimental conditions were kept unchanged.

## Quantitative Results

| Metric | Exp 001 — 128D | Exp 003 — 96D | Change |
|---|---:|---:|---:|
| Embedding dimension | 128 | 96 | -25.0% |
| Parameters | 804,096 | 455,616 | -43.3% |
| Training iterations | 2,000 | 2,000 | No change |
| Total training time | Baseline run | 49.635 s | — |
| Average iteration time | ~35–40 ms | 24.805 ms | Faster |
| Final training loss | 1.7648 | 1.8800 | Increased |
| Final validation loss | 1.8857 | 1.9874 | Increased |

## Comparison with Experiment 002

Experiment 002 used an embedding dimension of 64.

| Metric | Exp 001 — 128D | Exp 003 — 96D | Exp 002 — 64D |
|---|---:|---:|---:|
| Embedding dimension | 128 | 96 | 64 |
| Parameters | 804,096 | 455,616 | 205,440 |
| Final training loss | 1.7648 | 1.8800 | 2.0038 |
| Final validation loss | 1.8857 | 1.9874 | 2.0787 |
| Iteration speed | ~35–40 ms | 24.805 ms | ~20–23 ms |

## Qualitative Result

The generated text from the 96-dimensional model was less readable than the 128-dimensional baseline.

However, it was noticeably cleaner and more readable than the generated text from the 64-dimensional model.

The observed qualitative ordering was:

**128D > 96D > 64D**

in terms of readability and coherence.

## Interpretation

The 96-dimensional model provides an intermediate point between the 128-dimensional baseline and the 64-dimensional ablation.

Reducing the embedding dimension from 128 to 96 substantially reduces the parameter count while maintaining better validation performance than the 64-dimensional model.

Across the three tested configurations, validation loss increased as embedding dimension decreased:

- 128D: 1.8857
- 96D: 1.9874
- 64D: 2.0787

This suggests a capacity-efficiency trade-off under the tested configuration.

## Conclusion

Experiment 003 supports the hypothesis that an intermediate embedding dimension can provide a middle ground between model capacity and computational efficiency.

The 96-dimensional model uses substantially fewer parameters than the 128-dimensional baseline and trains faster, while its validation loss remains lower than that of the 64-dimensional model.

However, the experiment covers only three embedding dimensions on the Tiny Shakespeare dataset, so the observed relationship should not yet be generalized beyond the tested setup.

## Reproducibility Note

The prepared Tiny Shakespeare dataset artifacts were initially missing and caused a pre-training failure. Matching existing `train.bin`, `val.bin`, and `meta.pkl` files were restored, after which the unchanged Experiment 003 command completed successfully.

No changes were made to `model.py`, Experiment 001, or Experiment 002.