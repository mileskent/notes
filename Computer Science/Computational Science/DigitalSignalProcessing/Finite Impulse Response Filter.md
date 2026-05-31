---
date: 2026-05-31
aliases:
  - FIR Filter
---
A *Finite Impulse Response Filter* is a kind of [[Filter]] whose [[Impulse Response]] eventually becomes zero, or in other words, the duration of response to the [[Impulse|Impulse Signal]] is **finite**. This property is due to such filters being [[Feed-Forward]].

$$
\begin{matrix}
\mathcal{H}:\mathbb{R}^\mathbb{Z} \times \mathbb{Z} \to \mathbb{R} \\
 \mathcal{H}(x,n) = y[n] \\
y[n] = \sum_{k=0}^M b_{k} \cdot x[n-k]
\end{matrix}
$$

$$
\begin{align}
H(z) &= \sum^M_{k=0} b_{k} \cdot z^{-k} \\
&= b_{0} \prod_{k=1}^M (1-c_{k}z^{-1}) \\ \\
\end{align}
$$

$$
h[n] = \begin{cases}
b_{n} & 0 \leq n \leq M \\
0 & \text{else}
\end{cases}
$$
