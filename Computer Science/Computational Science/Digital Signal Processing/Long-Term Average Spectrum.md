---
date: 2026-06-09
aliases:
  - LTAS
---
A *long-term average spectrum* (LTAS) is the time-averaged [[Power Spectrum]] computed over many FFT frames, used to characterize persistent spectral content and estimate a stable noise floor.

$$
\bar{P}[k] = \frac{1}{M} \sum_{m=0}^{M-1} P_m[k]
$$

* where $P_m[k]$ is the [[Power Spectrum]] at frame $m$ and $M$ is the number of frames.

In real-time processing, the LTAS is often maintained as an [[Exponential Moving Average]] over successive frames rather than a finite sum.
