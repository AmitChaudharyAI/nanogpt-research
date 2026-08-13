# Experiment 004 — Embedding Dimension 112

## Overview

Experiment 004 investigates the effect of reducing the nanoGPT embedding dimension from 128 to 112.

This experiment is part of a controlled embedding-dimension ablation study examining the relationship between model capacity, parameter count, computational efficiency, and language-model quality.

## Research Question

Can an embedding dimension of 112 provide a better quality-efficiency trade-off than the smaller embedding configurations while remaining more efficient than the 128-dimensional baseline?

## Experimental Change

Only one parameter was changed:

```text
n_embd: 128 → 112