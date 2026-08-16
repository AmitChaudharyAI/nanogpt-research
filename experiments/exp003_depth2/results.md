# Experiment 003 — Depth Ablation Results

## Exact configuration

The configuration below is transcribed from `config_used.txt` and the applied overrides in `train.log`.

| Setting | Value |
|---|---|
| Dataset | `shakespeare_char` (`data/shakespeare_char`) |
| `n_embd` | 112 |
| `n_layer` | 2 |
| `n_head` | 4 |
| `block_size` | 64 |
| `batch_size` | 12 |
| Gradient accumulation | 1 |
| Training iterations | 2,000 |
| Evaluation iterations | 20 |
| Log interval | 1 |
| Dropout | 0.0 |
| Optimizer | AdamW, unfused on CPU |
| Learning rate | 0.001 |
| Minimum learning rate | 0.0001 |
| Warmup iterations | 100 |
| `beta2` | 0.99 |
| Device | CPU |
| Compile | False |
| Random seed | 1337 (nanoGPT default) |

Sampling used `num_samples=10`, `max_new_tokens=500`, `temperature=0.8`, `top_k=200`, and `start="\\n"`, as recorded in `config_used.txt`.

## Measured values

- Rounded parameter count printed by nanoGPT: **0.31M**.
- Decayed parameters printed by nanoGPT: **315,504**.
- Non-decayed parameters printed by nanoGPT: **560**.
- Final measured training loss at step 2,000: **1.8395**.
- Final measured validation loss at step 2,000: **1.9495**.
- Tokens per iteration: **768**.
- Fused AdamW: **False**.

## Derived values

- Exact parameter count derived from the two logged parameter groups: **316,064** (`315,504 + 560`).
- Logged training time derived by summing the `time` fields for iterations 0–2,000: **35.390 seconds**.
- Average iteration time derived from those 2,001 logged `time` fields: **17.686 ms/iteration**.

These timing values are derived from per-iteration log entries, not from an independently recorded wall-clock timer.

## Evaluation checkpoints

| Step | Train loss | Validation loss |
|---:|---:|---:|
| 0 | 4.2051 | 4.2040 |
| 250 | 2.4747 | 2.4818 |
| 500 | 2.2837 | 2.2922 |
| 750 | 2.1629 | 2.2073 |
| 1000 | 2.0517 | 2.1222 |
| 1250 | 1.9727 | 2.0488 |
| 1500 | 1.8975 | 1.9837 |
| 1750 | 1.8359 | 1.9737 |
| 2000 | 1.8395 | 1.9495 |

No comparative conclusion is recorded here.
