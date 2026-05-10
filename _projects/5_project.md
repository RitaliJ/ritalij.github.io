---
layout: page
title: "Joint Vertex-Time Graph Signal Processing"
description: "CS 179, Spring 2025 — CUDA implementation of Fast Fourier–Chebyshev filter for 3D time-vertex meshes"
img: assets/img/cs179-2025spring-gpu.png
importance: 5
category: coursework
tags: [GPU Computing, CUDA, Signal Processing]
---

CUDA implementation of a Fast Fourier–Chebyshev filter for 3D time-vertex meshes. Chebyshev polynomial approximation avoids O(N³) eigendecomposition. Pipeline: cuFFT → cuSPARSE SpMV → inverse FFT. Results compared against a CPU reference implementation using FFTW and Eigen.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/cs179-2025spring-gpu.png" title="Graph signal processing on GPU" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
