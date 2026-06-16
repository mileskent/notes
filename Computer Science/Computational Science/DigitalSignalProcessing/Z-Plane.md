---
date: 2026-06-15
---
The [[Complex Plane]] used in [[Z Transform]] analysis. Each point $z \in \mathbb{C}$ corresponds to a complex frequency in the discrete-time domain.

Related to the [[S-Plane]] by $z = e^{sT}$, where $T$ is the [[Sampling|sampling interval]]. This mapping wraps the $s$-plane onto the $z$-plane periodically.

# Stability Regions

| Region | Condition | Behavior |
| ------ | --------- | -------- |
| Inside unit circle | $\|z\| < 1$ | Stable (decaying) |
| Unit circle | $\|z\| = 1$ | Marginally stable (oscillatory) |
| Outside unit circle | $\|z\| > 1$ | Unstable (growing) |

The unit circle in the $z$-plane corresponds to the imaginary axis in the [[S-Plane]]; evaluating $H(z)$ on the unit circle ($z = e^{j\omega}$) gives the frequency response. Poles of $H(z)$ inside the unit circle are required for [[Stability#Asymptotically Stable|asymptotic stability]]; see [[Infinite Impulse Response Filter]].
