## Qualitative Comparison

Generated text was inspected for all three embedding configurations.

The 128-dimensional baseline produced the cleanest and most readable text.

The 96-dimensional model produced less readable text than the baseline, but its output was noticeably better than the 64-dimensional model.

The 64-dimensional model produced the least readable output of the three configurations.

The qualitative trend therefore broadly agrees with the validation-loss results.

128 → lowest validation loss → best observed text quality
96  → intermediate validation loss → intermediate text quality
64  → highest validation loss → poorest observed text quality