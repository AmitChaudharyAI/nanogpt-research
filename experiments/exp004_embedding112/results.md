# Experiment 004 — Results

## Experiment

Embedding Dimension Ablation

## Controlled Change

Only one model parameter was changed:

**n_embd: 128 → 112**

All other experimental conditions were kept unchanged.

## Quantitative Results

| Metric | Exp 001 — 128D | Exp 004 — 112D |
|---|---:|---:|
| Embedding dimension | 128 | 112 |
| Parameters | 804,096 | 617,568 |
| Training iterations | 2,000 | 2,000 |
| Final training loss | 1.7648 | 1.8489 |
| Final validation loss | 1.8857 | 1.9357 |
| Average iteration time | ~35–40 ms | 33.599 ms |
| Training time | Baseline run | 67.232 seconds |

## Comparison Across Embedding Dimensions

| Embedding | Parameters | Validation Loss |
|---:|---:|---:|
| 64 | 205,440 | 2.0787 |
| 96 | 455,616 | 1.9874 |
| 112 | 617,568 | 1.9357 |
| 128 | 804,096 | 1.8857 |

## Parameter Efficiency

The 112-dimensional model contains 617,568 parameters compared with 804,096 parameters in the 128-dimensional baseline.

This represents approximately a 23.2% reduction in parameter count.

The validation loss increases from 1.8857 to 1.9357, an increase of approximately 2.65%.

## Qualitative Result

The 128-dimensional baseline produced the cleanest and most readable generated text.

The 112-dimensional model produced reasonably readable text and was noticeably better than the 96-dimensional and 64-dimensional models.

The qualitative ordering observed was:

**128D > 112D > 96D > 64D**

in terms of generated-text readability.

## Interpretation

The 112-dimensional configuration provides an intermediate point between the 128-dimensional baseline and the smaller 96- and 64-dimensional configurations.

It substantially reduces the number of parameters while maintaining a validation loss closer to the baseline than the smaller embedding configurations.

The CPU timing also shows that parameter reduction does not necessarily translate proportionally into wall-clock training-speed improvement.

## Conclusion

Experiment 004 supports the hypothesis that reducing embedding dimension from 128 to 112 can reduce model size while maintaining relatively close validation performance to the baseline.

The 112-dimensional configuration produced better validation performance and better generated-text readability than the 96-dimensional and 64-dimensional configurations.

However, this experiment does not establish 112D as an optimal configuration. Further evaluation across multiple seeds, datasets, and computational conditions would be required before making such a claim.

## Reproducibility

- Dataset: Tiny Shakespeare
- Device: CPU
- Training iterations: 2,000
- Random seed: 1337
- n_layer: 4
- n_head: 4
- block_size: 64
- n_embd: 112

Experiment 001, Experiment 002, Experiment 003, and `model.py` were not modified.