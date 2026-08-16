# Experiment: Depth Ablation — n_layer=6

## Objective

Measure the effect of increasing Transformer depth to 6 layers while keeping the embedding dimension, attention heads, training procedure, dataset, and other hyperparameters fixed.

## Hypothesis

Increasing the number of Transformer layers while keeping the embedding dimension, attention heads, training procedure, dataset, and other hyperparameters fixed is expected to improve language-model validation performance by increasing representational capacity, but at the cost of increased parameter count and computational cost.

This experiment tests n_layer=6 with n_embd=112 and n_head=4.

## Key configuration

- `n_layer=6`
- `n_embd=112`
- `n_head=4`
- `block_size=64`
- `batch_size=12`
- `gradient_accumulation_steps=1`
- `learning_rate=0.001`
- `min_lr=0.0001`
- `warmup_iters=100`
- `beta2=0.99`
- `dropout=0.0`
- Optimizer: AdamW, unfused on CPU
- Random seed: 1337
- Initialization: scratch

## Dataset and device

- Dataset: Tiny Shakespeare character-level dataset, `shakespeare_char`
- Dataset path: `data/shakespeare_char`
- Device: CPU
- Compile: `False`
- Number of iterations: 2,000

## Recorded results

- Parameter count: **919,072**
- Final training loss: **1.8254**
- Final validation loss: **1.9118**

## Artifacts

- [config_used.txt](config_used.txt) — exact configuration and sampling settings
- [train.log](train.log) — complete training output
- [generated_text.txt](generated_text.txt) — generated samples
- [observations.md](observations.md) — evidence-based observations
- [results.md](results.md) — recorded metrics and analysis
- [ckpt.pt](ckpt.pt) — local checkpoint

This experiment is part of the controlled depth ablation series using 2, 4, and 6 Transformer layers.
