# Experiment 004 — Observations

## Quantitative Observation

Reducing the embedding dimension from 128 to 112 reduced the parameter count from 804,096 to 617,568.

The final validation loss increased from 1.8857 in the 128-dimensional baseline to 1.9357 in the 112-dimensional model.

Across the tested embedding dimensions, validation loss followed the trend:

128D < 112D < 96D < 64D

in terms of validation-loss value.

## Qualitative Observation

The generated text from the 128-dimensional baseline was the cleanest and most readable.

The 112-dimensional model produced reasonably readable text and was noticeably better than the 96-dimensional and 64-dimensional models.

The 96-dimensional model produced less readable text, while the 64-dimensional model produced the least readable output.

Therefore, the qualitative ordering observed was:

128D > 112D > 96D > 64D

in terms of generated-text readability.

## Efficiency Observation

The 112-dimensional model used substantially fewer parameters than the 128-dimensional baseline.

However, the measured CPU iteration time did not decrease proportionally with parameter count. Therefore, parameter reduction should not be interpreted as a directly proportional reduction in wall-clock training time.

## Overall Observation

Experiment 004 provides an intermediate point between the 128-dimensional baseline and the smaller 96- and 64-dimensional configurations.

The 112-dimensional configuration retains better validation performance and generated-text readability than the smaller configurations while using fewer parameters than the baseline.