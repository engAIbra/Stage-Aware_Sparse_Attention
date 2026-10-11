# Stage-Aware Sparse Attention

## Paper

> **"Stage-Aware Sparse Attention: Decoupling Prefill and Decode Optimization for Resource-Constrained LLM Inference"**
> Ahmed Ibrahim, Ahmed Elliethy, Gouda I. Salama — under review (Springer, *Advances in Computational Intelligence*).

This repository hosts the paper's reference code: the evaluation harness for stage-aware sparse-attention LLM inference (see *Coming soon* for the release plan).

## Overview

Sparse attention is usually tuned as a single choice. This repo implements the paper's core idea: treat attention sparsification as a **composition of two stage-specific design choices** — one method for **prefill** (full-prompt processing) and one for **generation** (autoregressive decoding) — and evaluate every pair under one unified pipeline. Five prefill methods × six generation methods = **30 combinations across 10 different tasks**, scored by a unified cross-entropy proxy plus task-native metrics (ROUGE, F1 Score, Recall, Accuracy).

Key results: **dense prefill is the most reliable** choice; sparse decoders tolerate **75–93% aggregate generation sparsity**; **prefill is compute-bound** while **decoding is memory-bandwidth-bound**. Architecture details and the full results discussion ship with the release (`docs/architecture.md`, `docs/results.md`).

## Coming soon

The code accompanying the paper — the complete evaluation harness (implementations, datasets, results, and docs) — will be **publicly released upon the paper's acceptance**. Until then it is available here for preview.

## Citation

```bibtex
@unpublished{ibrahim2026stageaware,
  title  = {Stage-Aware Sparse Attention: Decoupling Prefill and Decode Optimization for Resource-Constrained {LLM} Inference},
  author = {Ibrahim, Ahmed and Elliethy, Ahmed and Salama, Gouda I.},
  note   = {Under review at Springer, Advances in Computational Intelligence},
  year   = {2026}
}
```
