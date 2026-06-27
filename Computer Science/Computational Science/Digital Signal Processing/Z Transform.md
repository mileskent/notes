---
date: 2026-02-14
---
An [[Integral Transform]], that is the [[Laplace Transform]] but [[Discrete-Time Signal|Discrete-Time]].

$$
X(z) = \mathcal{Z}\{x[n]\}(z) = \sum_{n=0}^{\infty} x[n]\, z^{-n}
$$

Related to the Laplace Transform by $z = e^{sT}$, where $T$ is the [[Sampling|sampling interval]]. This means the imaginary axis in the $s$-plane maps to the unit circle $|z| = 1$ in the $z$-plane.

The Z Transform converts [[Discrete Convolution]] into multiplication, turning difference equations into polynomial equations in $z$, analogous to how the Laplace Transform handles differential equations.

# Stability

Poles of $H(z)$ inside the unit circle ($|z| < 1$) correspond to a [[Stability#Stable]] system, analogous to $\text{Re}(s) < 0$ for the Laplace Transform.