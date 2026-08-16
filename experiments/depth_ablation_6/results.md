# Depth Ablation Results — n_layer=6

## Exact configuration

| Setting | Value |
|---|---|
| Dataset | `shakespeare_char` |
| Dataset path | `data/shakespeare_char` |
| `n_embd` | 112 |
| `n_layer` | 6 |
| `n_head` | 4 |
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
| Random seed | 1337, hardcoded by this nanoGPT checkout |
| Initialization | `scratch` |
| Sampling `start` | `\n` |
| Sampling `num_samples` | 10 |
| Sampling `max_new_tokens` | 500 |
| Sampling `temperature` | 0.8 |
| Sampling `top_k` | 200 |

## Measured values

- Training completed at step 2000.
- Parameter count reported by the log: 0.91M.
- Exact parameter count derived from the logged parameter groups: **919,072** (`917,616` decayed + `1,456` non-decayed).
- Final training loss at step 2000: **1.8254**.
- Final validation loss at step 2000: **1.9118**.
- Tokens per iteration: **768**.
- Optimizer: **unfused AdamW**.
- Device: **CPU**.

Derived timing values from the 2,001 successful per-iteration timing entries:

- Total logged iteration time: **105.216 seconds**.
- Average logged iteration time: **52.582 ms/iteration**.

These timing values are derived from `train.log`; they are not an independently measured wall-clock duration.

## Evaluation checkpoints

| Step | Train Loss | Validation Loss |
|------:|------------:|----------------:|
| 0 | 4.1841 | 4.1780 |
| 250 | 2.4534 | 2.4591 |
| 500 | 2.2912 | 2.3199 |
| 750 | 2.1701 | 2.2108 |
| 1000 | 2.0431 | 2.1132 |
| 1250 | 1.9747 | 2.0427 |
| 1500 | 1.9053 | 1.9959 |
| 1750 | 1.8650 | 1.9682 |
| 2000 | 1.8254 | 1.9118 |

## Comparison with previous depths

The following values are transcribed from the existing Depth-2 and Depth-4 result artifacts and the completed Depth-6 log. No previous experiment files were modified.

| Depth | Parameters | Final Train Loss | Final Val Loss |
|------:|-----------:|-----------------:|---------------:|
| 2 | 316,064 | 1.8395 | 1.9495 |
| 4 | 617,568 | 1.8489 | 1.9357 |
| 6 | 919,072 | 1.8254 | 1.9118 |

Validation-loss changes:

| Transition | Absolute change | Percentage change | Interpretation |
|---|---:|---:|---|
| Depth 4 → Depth 6 | -0.0239 | -1.2347% | Validation loss decreased; lower is better. |
| Depth 2 → Depth 6 | -0.0377 | -1.9338% | Validation loss decreased; lower is better. |

The percentage changes are calculated as `(new loss - old loss) / old loss × 100` using the recorded final validation losses.

## Preliminary interpretation

Within this small-scale Shakespeare character-level nanoGPT experiment, the recorded final validation loss decreased across the listed Depth-2, Depth-4, and Depth-6 artifacts. This is an observational result for these runs only. It does not establish universal superiority of deeper models, statistical significance, or generalization beyond this experiment.
