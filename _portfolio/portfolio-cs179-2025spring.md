---
title: "Qwen2 LLM / Transformer Inference accelerated on GPU"
excerpt: "(ML, GPUs) Transformer Inference Logic and Kernels written from scratch on GPU <br/><img src='/images/cs179-2025spring-llm.png'>"
collection: portfolio
---
# Qwen2 Transformer Inference from Scratch (GPU)

## Overview

I implemented a GPU-based inference engine for the **Qwen2** large language model (LLM), from scratch and without using any external GPU libraries. This project deepened my understanding of the transformer architecture and GPU programming, including kernel-level implementations of core model components.

## Background

Qwen2 is a family of open-weight LLMs developed by Alibaba, structurally based on Meta’s LLaMA models. While the architecture is largely similar, Qwen2 introduces subtle differences such as the inclusion of biases in the QKV matrices.

The model incorporates:

- **Grouped-query attention**
- **Layer normalization with zero mean**
- **SwiGLU feed-forward networks**
- **Rotary positional embeddings**

We focused solely on **autoregressive single-token decoding**, which simplifies attention computation and avoids masked attention kernels typically optimized with libraries like FlashAttention.

## Goals & Constraints

This project required implementing **all inference kernels from scratch**, with **no use of GPU helper libraries** such as cuBLAS, CUTLASS, or Thrust. The implementation supports:

- **bfloat16** weights and key/value caches (for memory efficiency)
- **float32** accumulation (to preserve numerical accuracy)
- **Row-major memory layout** for all tensors
- **No batching** or multi-token decoding

## Key Implementations

- Custom CUDA kernels for:
  - LayerNorm
  - Linear layers
  - SwiGLU activation
  - Rotary positional embeddings
  - Attention mechanism with grouped-query attention
- Efficient handling of the key/value (KV) cache
- Optimized GPU memory access patterns
- Inference loop that generates one token at a time

## Limitations Compared to Production-Grade LLMs

This implementation intentionally excludes several advanced features commonly used in real-world LLM inference:

- Batch processing and prefill with masked attention
- Tensor core acceleration
- Quantization
- Mixture-of-Experts (MoE) routing
- Multi-GPU or distributed inference
- KV cache offloading and paging
- Sampling techniques such as Top-K or Top-P

## Takeaways

This project offered hands-on experience in:

- Writing and debugging custom CUDA kernels
- Memory layout decisions and performance tradeoffs
- Transformer inference internals at the lowest level
- Numerical precision and type casting on GPUs
- The practical challenges of building a working LLM inference engine from scratch

It served as a deep dive into the mechanics behind modern transformer models and the GPU-level optimization challenges of inference at scale.