# Experiment 002 — Results

## Ablation

Embedding dimension:

128 → 64

All other experimental conditions were kept unchanged.

## Quantitative Results

| Metric | Exp 001 Baseline | Exp 002 | Change |
|---|---:|---:|---:|
| Embedding dimension | 128 | 64 | -50% |
| Parameters | 804,096 | 205,440 | -74.4% |
| Training loss | 1.7648 | 2.0038 | Increased |
| Validation loss | 1.8857 | 2.0787 | Increased |
| Iteration speed | ~35–40 ms | ~20–23 ms | Faster |

## Qualitative Result

The baseline generated text was cleaner and more readable.

The 64-dimensional model produced less coherent text, with poorer word formation and fewer clearly recognizable words.

## Conclusion

Reducing the embedding dimension from 128 to 64 substantially reduced model size and improved training speed. However, the smaller model showed higher training and validation loss and qualitatively poorer generated text.

The observed results are consistent with the hypothesis that reducing embedding dimensionality creates a trade-off between computational efficiency and language-model quality.