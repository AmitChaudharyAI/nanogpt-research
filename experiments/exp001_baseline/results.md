# Experiment 001 — Baseline Reproduction

## Objective

Reproduce the nanoGPT Tiny Shakespeare baseline on CPU without modifying the model architecture.

## Configuration

| Parameter | Value |
|---|---:|
| Layers | 4 |
| Attention Heads | 4 |
| Embedding Dimension | 128 |
| Context Length | 64 |
| Training Iterations | 2000 |
| Parameters | 804,096 |

## Dataset

Tiny Shakespeare

## Optimizer

AdamW

## Learning Rate Schedule

- Warmup: 100 steps
- Scheduler: Cosine decay
- Initial learning rate: 1e-3
- Final learning rate: 1e-4

## Results

| Metric | Value |
|---|---:|
| Training Loss | 1.7648 |
| Validation Loss | 1.8857 |

## Execution

- Hardware: CPU
- Baseline completed successfully: Yes

## Problems Encountered

During the experiment, path-resolution issues, a CPU timeout for the larger configuration, and PowerShell execution-policy restrictions were encountered.

## Observations

1. The reduced CPU configuration completed successfully.
2. The final training loss was 1.7648.
3. The final validation loss was 1.8857.
4. Validation loss was higher than training loss.
5. No model architecture changes were made.

## Conclusion

The Tiny Shakespeare baseline was successfully reproduced on CPU using the reduced configuration.

This experiment establishes the baseline against which future ablation experiments will be compared.

## Next Experiment

Investigate the effect of reducing the embedding dimension from 128 to 64.