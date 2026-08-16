# Results — Attention-Head Ablation n_head=8

## Exact configuration

| Setting | Value |
|---|---|
| Dataset | `shakespeare_char` |
| Dataset path | `data/shakespeare_char` |
| `n_embd` | 112 |
| `n_layer` | 2 |
| `n_head` | 8 |
| Head dimension | 14 (`112 / 8`) |
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
- Exact parameter count derived from the logged groups: **316,064**.
- Final training loss: **1.8466**.
- Final validation loss: **1.9583**.
- Tokens per iteration: **768**.
- Optimizer: **unfused AdamW**.
- Device: **CPU**.

## Timing

The successful log contains 2,001 per-iteration timing entries. Derived from those entries:

- Total logged iteration time: **42.198 seconds**.
- Average logged iteration time: **21.088 ms/iteration**.

These values are derived from the `time ...ms` fields in `train.log`, not from an independent wall-clock timer.

## Evaluation checkpoints

| Step | Train Loss | Validation Loss |
|------:|------------:|---------------:|
| 0 | 4.2051 | 4.2040 |
| 250 | 2.4774 | 2.4832 |
| 500 | 2.2883 | 2.2942 |
| 750 | 2.1755 | 2.2111 |
| 1000 | 2.0591 | 2.1366 |
| 1250 | 1.9752 | 2.0551 |
| 1500 | 1.9072 | 1.9923 |
| 1750 | 1.8429 | 1.9765 |
| 2000 | 1.8466 | 1.9583 |

## Comparison with existing attention-head experiments

The following values use the existing Depth-2 4-head artifacts, the completed 7-head artifacts, and this 8-head run.

| Heads | Head Dimension | Parameters | Final Train Loss | Final Val Loss |
|------:|---------------:|-----------:|-----------------:|---------------:|
| 4 | 28 | 316,064 | 1.8395 | 1.9495 |
| 7 | 16 | 316,064 | 1.8410 | 1.9561 |
| 8 | 14 | 316,064 | 1.8466 | 1.9583 |

Lower validation loss is better. Differences are calculated as `new loss - old loss`; positive values indicate a higher validation loss.

| Transition | Absolute validation-loss difference | Percentage difference |
|---|---:|---:|
| 4 → 7 | +0.0066 | +0.3385% |
| 4 → 8 | +0.0088 | +0.4514% |
| 7 → 8 | +0.0022 | +0.1125% |

These comparisons report the recorded results only and do not establish statistical significance or a broad research conclusion.

## Warnings and errors

No training or generation errors occurred. The log contains the standard PyTorch GradScaler deprecation warning and the warning that GradScaler was disabled because CUDA was unavailable.

## Experimental integrity

The successful run initialized from scratch with CPU execution and used only the requested architectural change, `n_head=8`. No previous experiment or source file was modified. The checkpoint is local to this experiment directory and was not added to Git.
