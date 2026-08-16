# Observations — Attention-Head Ablation n_head=8

## Training behavior

Training completed successfully through step 2000. The model was initialized from scratch, ran on CPU, used 768 tokens per iteration, and used unfused AdamW. The training loss decreased overall from 4.2051 at step 0 to 1.8466 at step 2000, with batch-to-batch variation in the per-iteration losses.

## Validation behavior

The validation losses recorded in `train.log` were:

| Step | Training loss | Validation loss |
|---:|---:|---:|
| 0 | 4.2051 | 4.2040 |
| 250 | 2.4774 | 2.4832 |
| 500 | 2.2883 | 2.2942 |
| 750 | 2.1755 | 2.2111 |
| 1000 | 2.0591 | 2.1366 |
| 1250 | 1.9752 | 2.0551 |
| 1500 | 1.9072 | 1.9923 |
| 1750 | 1.8429 | 1.9765 |
| 2000 | 1.8466 | 1.9583 |

The validation loss decreased overall across the recorded checkpoints, with a small increase from step 1750 to step 2000.

## Generated text

The generated output contains 10 samples using `start=\\n`, `max_new_tokens=500`, `temperature=0.8`, and `top_k=200`. It includes line breaks, punctuation, dialogue-like formatting, and speaker-style labels in several samples. It also contains malformed words and low-coherence sequences. These are qualitative observations only; no text-quality score is assigned.

## Warnings and limitations

- No training or generation errors occurred.
- PyTorch emitted a `FutureWarning` for the deprecated `torch.cuda.amp.GradScaler` API.
- PyTorch emitted a `UserWarning` that GradScaler was disabled because CUDA was unavailable.
- The log records `using fused AdamW: False` and CPU execution.
- The run used `compile=False`.
- Timing totals and averages are derived from the per-iteration timing fields in `train.log`, not from an independent wall-clock timer.

## Experimental integrity

The run used `n_embd=112`, `n_layer=2`, and changed only `n_head` from the reference value of 4 to 8. The dataset, training schedule, optimizer, learning rate, batch configuration, seed mechanism, CPU device, scratch initialization, and sampling configuration were kept as specified. No previous experiment or model source file was modified.
