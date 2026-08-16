# Experiment 003 — Observations

## Training behavior

- The run initialized from scratch with `n_layer=2`, `n_embd=112`, `n_head=4`, and vocabulary size 65.
- The run completed through step 2,000 and saved a checkpoint in the experiment directory.
- The log reports 768 tokens per iteration and unfused AdamW on CPU.
- The logged training loss decreased from 4.2051 at step 0 to 1.8395 at step 2,000.

## Validation behavior

- The logged validation loss decreased from 4.2040 at step 0 to 1.9495 at step 2,000.
- Validation loss at the recorded checkpoints was: 2.4818 (250), 2.2922 (500), 2.2073 (750), 2.1222 (1000), 2.0488 (1250), 1.9837 (1500), 1.9737 (1750), and 1.9495 (2000).
- Between steps 1,750 and 2,000, training loss changed from 1.8359 to 1.8395 while validation loss changed from 1.9737 to 1.9495.

## Generated text

- The sampler produced 10 samples using 500 new tokens per sample, temperature 0.8, top-k 200, and a newline start prompt.
- The output contains Shakespeare-style speaker labels, line breaks, punctuation, and recurring character-like formatting.
- The output also contains many malformed or nonstandard word sequences. This is a qualitative observation only; no text-quality score was computed.

## Warnings and limitations

- The log contains a `FutureWarning` that `torch.cuda.amp.GradScaler` is deprecated.
- The log contains a `UserWarning` that GradScaler was disabled because CUDA was unavailable; the run was CPU-only as configured.
- The reported total training time and average iteration time are derived from per-iteration `time` fields in the log, not from a separately recorded wall-clock measurement.
- No comparison with another depth is made here. This document records only evidence from the Experiment 003 depth-2 artifacts.
