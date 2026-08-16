# Experiment — Depth Ablation n_layer=6

## Training behavior

Training completed successfully through step 2000 after a fresh initialization from scratch. The initial evaluation recorded train loss 4.1841 and validation loss 4.1780; the final evaluation recorded train loss 1.8254 and validation loss 1.9118.

The model used 919,072 trainable parameters, 768 tokens per iteration, CPU execution, and unfused AdamW. The logged per-batch losses decreased overall while retaining normal batch-to-batch variation. Evaluation checkpoints were run at the requested steps.

## Validation behavior

The validation losses explicitly recorded in `train.log` were:

| Step | Validation loss |
|---:|---:|
| 0 | 4.1780 |
| 250 | 2.4591 |
| 500 | 2.3199 |
| 750 | 2.2108 |
| 1000 | 2.1132 |
| 1250 | 2.0427 |
| 1500 | 1.9959 |
| 1750 | 1.9682 |
| 2000 | 1.9118 |

These values show a decreasing validation loss at each recorded evaluation checkpoint in this run.

## Generated text

The generated output contains 10 samples using the specified sampling settings. Shakespeare-like formatting appears in places, including speaker labels, dialogue-like lines, line breaks, punctuation, and stage-style names. The text also contains malformed words and some low-coherence sequences. These are qualitative observations only; no text-quality metric was fabricated or assigned.

## Warnings and limitations

- The first launch failed before training because it was started outside the repository root and could not resolve `configurator.py`.
- The second launch failed before training because this checkout does not expose `seed` as a valid configurator key. Inspection confirmed that `train.py` hardcodes `torch.manual_seed(1337 + seed_offset)`; the corrected run therefore used the implementation’s seed 1337 without modifying source code.
- The successful run emitted a `FutureWarning` for the deprecated `torch.cuda.amp.GradScaler` API.
- It also emitted a `UserWarning` that GradScaler was disabled because CUDA was unavailable. The experiment remained CPU-only.
- `compile=False` was used.
- The total and average training times in `results.md` are derived by summing the per-iteration `time ...ms` fields in the successful log output, rather than from an independent wall-clock timer.

## Experimental integrity

The successful run used the requested controlled configuration: `n_layer=6`, `n_embd=112`, `n_head=4`, the specified training schedule, CPU device, and fresh initialization. No model or training implementation files were modified. The two pre-training launch errors were corrected by changing only the launch context and removing the unsupported CLI seed override; the built-in seed remained 1337. Previous experiment directories were not edited.
