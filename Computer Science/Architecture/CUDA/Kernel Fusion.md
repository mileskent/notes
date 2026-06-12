---
date: 2026-06-10
---
*Kernel fusion* is a [[CUDA]] optimization that merges multiple kernels into a single kernel. This reduces kernel launch overhead and eliminates intermediate global [[Memory]] reads and writes between kernels, since fused operations can pass data through registers or shared memory instead.
