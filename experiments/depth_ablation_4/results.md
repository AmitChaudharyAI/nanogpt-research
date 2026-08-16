# Results: Depth Ablation — n_layer=4

## Exact configuration

The exact configuration recorded in `config_used.txt` and the saved checkpoint is:

| Setting | Value |
|---|---|
| Dataset | `shakespeare_char` (`data/shakespeare_char`) |
| `n_embd` | 112 |
| `n_layer` | 4 |
| `n_head` | 4 |
| `block_size` | 64 |
| `batch_size` | 12 |
| Gradient accumulation | 1 |
| Maximum iterations | 2000 |
| Evaluation interval | 250 |
| Evaluation iterations | 20 |
| Log interval | 1 |
| Optimizer | AdamW, unfused on CPU |
| Learning rate | 0.001 |
| Minimum learning rate | 0.0001 |
| Warmup iterations | 100 |
| `beta2` | 0.99 |
| Dropout | 0.0 |
| Device | CPU |
| Compile | False |
| Random seed | 1337 (nanoGPT default) |

## Measured values

- Training completed through iteration 2000.
- Parameter count: **617,568** trainable parameters, reported by the training log as 616,560 decayed parameters plus 1,008 non-decayed parameters.
- Final training loss at evaluation step 2000: **1.8489**.
- Final validation loss at evaluation step 2000: **1.9357**.
- The checkpoint records `iter_num=2000` and `best_val_loss=1.9357`.
- The training log reports `using fused AdamW: False`.

## Timing

The log contains 2,001 per-iteration timing fields. Summing those logged fields gives **58.0047 seconds**; the derived mean is **28.988 ms per logged iteration**. These are derived from the raw `time ...ms` entries in `train.log`, not from an independent wall-clock measurement.

## Evaluation checkpoints

| Step | Train loss | Validation loss |
|---:|---:|---:|
| 0 | 4.1957 | 4.1896 |
| 250 | 2.4390 | 2.4630 |
| 500 | 2.3087 | 2.3230 |
| 750 | 2.1817 | 2.2000 |
| 1000 | 2.0675 | 2.1075 |
| 1250 | 1.9417 | 2.0287 |
| 1500 | 1.9012 | 1.9878 |
| 1750 | 1.8586 | 1.9474 |
| 2000 | 1.8489 | 1.9357 |

No cross-experiment comparison or conclusion is made here.
