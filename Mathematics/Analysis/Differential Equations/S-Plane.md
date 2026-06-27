---
date: 2026-06-15
---
The [[Complex Plane]] used in [[Laplace Transform]] analysis, where $s = \sigma + j\omega$.

$$
s = \underbrace{\sigma}_{\text{damping}} + j\underbrace{\omega}_{\text{frequency}}
$$

The real axis $\sigma$ controls exponential growth or decay; the imaginary axis $j\omega$ controls oscillation frequency. Setting $\sigma = 0$ recovers the Fourier Transform along the imaginary axis.

# Stability Regions

| Region | Condition | Behavior |
| ------ | --------- | -------- |
| Left half-plane | $\sigma < 0$ | Stable (decaying) |
| Imaginary axis | $\sigma = 0$ | Marginally stable (oscillatory) |
| Right half-plane | $\sigma > 0$ | Unstable (growing) |

The discrete-time analog is the [[Z-Plane]], related by $z = e^{sT}$. The left half of the $s$-plane maps to the interior of the unit circle in the $z$-plane.
