---
title: Warpscope
subtitle: NVBit-based GPU profiler for detecting warp idleness
summary: NVBit-based CUDA profiler that measures warp idleness with BarrFrac and CompFrac metrics; used to guide warp specialization in FlashAttention, cutting warp idle time 3.7× on KV-cache decode.
dates: Feb 2026 – April 2026
tags: [cuda, nvbit, profiling, flashattention]
featured: true
order: 1
links:
  - name: GitHub
    url: "https://github.com/chetan96/warpscope"
---

## Overview

Warpscope is a GPU profiler that instruments CUDA kernels with NVBit to detect and quantify warp idleness. It emits two per-warp metrics that make it easy to see where cycles are being lost:

- **`BarrFrac`** — fraction of active cycles a warp spent waiting on barriers.
- **`CompFrac`** — fraction of active cycles a warp spent issuing compute instructions.

## Application: FlashAttention

I applied the profiler's warp-idleness insights to guide warp specialization in FlashAttention kernels, achieving a **3.7× reduction in warp idle time** on KV-cache decode workloads.

<!--
Sections to flesh out later:
- Motivation: what gap in existing profilers this fills
- Design: how the NVBit instrumentation works internally
- Case study: FlashAttention decode walkthrough with numbers
- A devlog: add posts with `project: warpscope` in the front matter,
  and they'll appear under this page automatically.
-->
