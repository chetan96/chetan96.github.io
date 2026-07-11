---
title: Optimizing Vision Transformers with Triton
subtitle: A custom FlashAttention 2.0 kernel in Triton for ViT inference
summary: Custom FlashAttention 2.0 kernel in Triton for Vision Transformers, using block-wise SRAM-aware computation to eliminate large intermediate matrices. Cut ViT inference latency up to 13.2% vs the Hugging Face baseline while preserving numerical accuracy.
dates: Jan 2025 – April 2025
tags: [triton, vit, flashattention, gpu]
featured: true
order: 2
links: []
---

## Overview

A FlashAttention 2.0 kernel written in Triton and integrated into a Vision Transformer inference path. The kernel keeps `Q·Kᵀ` and the softmax stats in on-chip SRAM and processes attention block-wise, avoiding the large `N × N` materialization that dominates a naive attention implementation.

## Result

- **Up to 13.2% latency reduction** on ViT inference vs. the Hugging Face baseline
- Numerical parity with the reference attention output

<!--
Sections to flesh out later:
- Kernel walk-through: block size choices, tiling strategy, softmax rescale
- Benchmark methodology and full table
- Where the remaining gap to a hand-tuned CUTLASS/CUDA kernel is
- Code link, if/when public
-->
