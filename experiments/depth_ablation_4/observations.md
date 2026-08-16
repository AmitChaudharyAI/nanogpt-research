# Observations: Depth Ablation — n_layer=4

## Training

Training completed successfully through iteration 2000. The run initialized a new model from scratch, used 768 tokens per iteration, and saved a checkpoint to this experiment directory at the evaluation checkpoints. AdamW was run unfused, as recorded in the raw log.

## Loss behavior

The evaluation records in `train.log` show training loss decreasing from 4.1957 at step 0 to 1.8489 at step 2000. Validation loss decreased from 4.1896 to 1.9357 over the same recorded checkpoints. The final validation evaluation was recorded at step 2000.

The raw per-iteration losses vary from batch to batch; the checkpoint values above are the explicitly logged evaluation values, not estimates from generated text.

## Generated text

`generated_text.txt` contains 10 samples generated with the recorded settings: `start=\\n`, `max_new_tokens=500`, `temperature=0.8`, and `top_k=200`. The output includes Shakespeare-style speaker labels, line breaks, and dialogue-like sequences. It also contains malformed or nonsensical word sequences, which is a qualitative observation only and is not treated as a quantitative text-quality metric.

## Warnings and limitations

- PyTorch emitted a `FutureWarning` that `torch.cuda.amp.GradScaler` is deprecated in favor of `torch.amp.GradScaler('cuda', ...)`.
- PyTorch emitted a `UserWarning` that GradScaler was disabled because CUDA was unavailable. This run was configured for CPU execution.
- The reported total training time and average iteration time in `results.md` are derived from the per-iteration timing fields in `train.log`; the raw log does not provide a separate start-to-finish wall-clock total.
- No comparison with another experiment and no conclusion about relative depth quality is made here.
