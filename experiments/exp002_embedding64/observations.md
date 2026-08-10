# Experiment 002 — Observations

## Quantitative Observations

Reducing the embedding dimension from 128 to 64 resulted in a substantial reduction in model size.

- Parameters decreased from 804,096 to 205,440.
- Training became faster, with approximately 20–23 ms/iteration compared with approximately 35–40 ms/iteration for the baseline.
- Final training loss increased from 1.7648 to 2.0038.
- Final validation loss increased from 1.8857 to 2.0787.

## Qualitative Observations

The generated text from Experiment 001 (128-dimensional embeddings) appeared cleaner and more readable.

The generated text from Experiment 002 (64-dimensional embeddings) was less coherent. Recognizable words appeared less frequently and word formation was poorer compared with the baseline.

## Interpretation

The results are consistent with the hypothesis that reducing embedding dimensionality decreases model capacity.

The 64-dimensional model achieved lower computational cost and faster iteration speed, but this came with a degradation in language-model performance under the tested training configuration.

## Important Limitation

The qualitative assessment of generated text is subjective. Therefore, it is treated as supporting evidence rather than a primary quantitative metric.