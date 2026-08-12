# Experiment 003 — Embedding Dimension 96

## Overview

This experiment investigates the effect of reducing the nanoGPT embedding dimension from 128 to 96.

The experiment is part of a controlled ablation study examining the trade-off between model capacity, computational efficiency, and language-model quality.

## Research Question

Can an intermediate embedding dimension of 96 provide a better quality-efficiency trade-off than the 64-dimensional model while remaining smaller than the 128-dimensional baseline?

## Experimental Change

Only one parameter was changed:

```text
n_embd: 128 → 96