# Results — Attention-Head Ablation n_head=7

## Exact configuration

| Setting | Value |
|---|---|
| Dataset | `shakespeare_char` |
| Dataset path | `data/shakespeare_char` |
| `n_embd` | 112 |
| `n_layer` | 2 |
| `n_head` | 7 |
| Head dimension | 16 (`112 / 7`) |
| `block_size` | 64 |
| `batch_size` | 12 |
| Gradient accumulation steps | 1 |
| `max_iters` | 2000 |
| `lr_decay_iters` | 2000 |
| `eval_iters` | 20 |
| `log_interval` | 1 |
| Dropout | 0.0 |
| Optimizer | AdamW, unfused on CPU |
| Learning rate | 0.001 |
| Minimum learning rate | 0.0001 |
| Warmup iterations | 100 |
| `beta2` | 0.99 |
| Device | CPU |
| Compile | False |
| Random seed | 1337, repository default mechanism |
| Initialization | `scratch` |
| Sampling start | `\n` |
| Sampling count | 10 |
| Sampling max new tokens | 500 |
| Sampling temperature | 0.8 |
| Sampling top-k | 200 |

## Measured values

- Training completed through step 2000.
- Rounded parameter count printed by nanoGPT: **0.31M**.
- Decayed parameters: **315,504**.
- Non-decayed parameters: **560**.
- Exact parameter count derived from the logged parameter groups: **316,064**.
- Final training loss at step 2000: **1.8410**.
- Final validation loss at step 2000: **1.9561**.
- Tokens per iteration: **768**.
- Optimizer: **unfused AdamW**.
- Device: **CPU**.

## Timing

The successful log contains 2,001 per-iteration timing entries. Derived from those entries:

- Total logged iteration time: **39.963 seconds**.
- Average logged iteration time: **19.971 ms/iteration**.

These timing values are derived from the `time ...ms` fields in `train.log`, not from an independent wall-clock timer.

## Evaluation checkpoints

| Step | Train Loss | Validation Loss |
|------:|------------:|----------------:|
| 0 | 4.2052 | 4.2040 |
| 250 | 2.4714 | 2.4779 |
| 500 | 2.2828 | 2.2828 |
| 750 | 2.1638 | 2.2090 |
| 1000 | 2.0413 | 2.1167 |
| 1250 | 1.9732 | 2.0426 |
| 1500 | 1.9034 | 1.9883 |
| 1750 | 1.8390 | 1.9758 |
| 2000 | 1.8410 | 1.9561 |

No final claim about whether seven heads are better than four heads is made here.
