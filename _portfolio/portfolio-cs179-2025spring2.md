---
title: "Joint Vertex Time Graph Signal Processing for Dynamic Mesh Data"
excerpt: "(GPUs) Accelerating low pass and nonseparable wave filtering of spatiotemporal dancer data <br/><img src='/images/cs179-2025spring-gpu.png'>"
collection: portfolio
---

# Fast Fourier–Chebyshev Filtering on CPU & GPU


## Abstract
This project demonstrates a CUDA implementation of a fast Fourier–Chebyshev (FFC)
filter for 3-D time-vertex meshes together with the original CPU reference
(FFTW + Eigen). 

---

## Algorithm Advantages
The filter accepts a precomputed spatial graph Laplacian. The algorithm
never explicitly computes eigenvalues or eigenvectors of the
graph Laplacian (an *O(N³)* cost).  
Instead, the spectral response \(h(\lambda, \omega)\) is approximated by a
degree-*M* Chebyshev polynomial and evaluated via the three-term recurrence

\[
T_0 = x,\qquad
T_1 = \tilde L\,x,\qquad
T_{k} = 2\,\tilde L\,T_{k-1} - T_{k-2},
\]

where \(\tilde L = \tfrac{2}{\lambda_{\max}}L - I\).  
Only sparse matrix–vector multiplies are required.

---

## Project Description
For each vertex-wise time signal \(x_v(t)\):

1. **FFT** across time \(t\to\omega\) for every vertex row.  
2. **Chebyshev filtering** (low-pass and wavelet) in the graph
   spectral domain for every frequency \(\omega_k\).  
3. **Inverse FFT** to recover filtered time-domain signals.  

The following libraries were used to compute these steps:

| Component | CPU | GPU |
|-----------|-----|-----|
| FFT/IFFT  | FFTW | cuFFT |
| SpMV in Chebyshev | Eigen sparse | cuSPARSE |
| Mixing Wave Output | host (Eigen) | device add-kernel |

Features
* Real→complex forward FFT, complex→real inverse FFT.  
* Configurable filter order *M*, cut-offs `lcut`, `wcut`, sigmoid sharpness `r`.  
* Automatic Laplacian rescaling & power-iteration estimate of \(\lambda_{\max}\).  
* End-to-end GPU pipeline; CLI tool processes `mesh.txt` + `laplacian.txt`.  

---
