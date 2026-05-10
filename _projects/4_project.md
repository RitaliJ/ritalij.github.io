---
layout: page
title: "Qwen2 LLM Inference on GPU"
description: "CS 179, Spring 2025 — GPU inference engine for Qwen2 LLM written from scratch"
img: assets/img/cs179-2025spring-llm.png
importance: 4
category: coursework
tags: [GPU Computing, CUDA, ML Systems]
---

GPU inference engine for the Qwen2 LLM written from scratch — no cuBLAS or CUTLASS. Custom CUDA kernels for LayerNorm, linear layers, SwiGLU activation, Rotary Positional Encoding (RoPE), and grouped-query attention. Uses bfloat16 weights with float32 accumulation.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/cs179-2025spring-llm.png" title="Qwen2 LLM GPU inference" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
