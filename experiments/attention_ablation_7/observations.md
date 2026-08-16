# Observations — Attention-Head Ablation n_head=7

## Training behavior

Training completed successfully through step 2000. The model was initialized from scratch using the repository’s built-in seed mechanism, ran on CPU, used 768 tokens per iteration, and used unfused AdamW.

The training loss decreased overall from 4.2052 at step 0 to 1.8410 at step 2000, with normal batch-to-batch variation in the per-iteration losses. The checkpoint was saved inside this experiment directory.

## Validation behavior

The validation losses explicitly recorded in `train.log` were:

| Step | Training loss | Validation loss |
|---:|---:|---:|
| 0 | 4.2052 | 4.2040 |
| 250 | 2.4714 | 2.4779 |
| 500 | 2.2828 | 2.2828 |
| 750 | 2.1638 | 2.2090 |
| 1000 | 2.0413 | 2.1167 |
| 1250 | 1.9732 | 2.0426 |
| 1500 | 1.9034 | 1.9883 |
| 1750 | 1.8390 | 1.9758 |
| 2000 | 1.8410 | 1.9561 |

The recorded validation loss decreased at each evaluation checkpoint after step 0.

## Generated text

The generated output contains 10 samples produced with the reference settings: `start=\\n`, `max_new_tokens=500`, `temperature=0.8`, and `top_k=200`. It includes line breaks, punctuation, dialogue-like formatting, and speaker-style labels in several samples. It also contains malformed words and low-coherence sequences. These observations are qualitative only and are not treated as a quantitative text-quality metric.

## Warnings and errors

- No training or sampling errors occurred.
- PyTorch emitted a `FutureWarning` that `torch.cuda.amp.GradScaler` is deprecated.
- PyTorch emitted a `UserWarning` that GradScaler was disabled because CUDA was unavailable.
- The log records `using fused AdamW: False`.
- The run used `compile=False` and CPU execution.

## Experimental integrity

The run used `n_embd=112`, `n_layer=2`, and changed only `n_head` from the Depth-2 reference value of 4 to 7. The dataset, optimizer, learning-rate schedule, batch configuration, iteration count, sampling settings, CPU device, scratch initialization, and seed mechanism were kept as specified. No previous experiment was modified, and no model-code change was made.
