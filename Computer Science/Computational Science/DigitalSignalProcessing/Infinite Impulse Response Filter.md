---
date: 2026-05-31
aliases:
  - IIR Filter
---
$$
\begin{matrix}
\mathcal{H}:\mathbb{R}^\mathbb{Z} \times \mathbb{R}^\mathbb{Z} \times \mathbb{Z} \to \mathbb{R} \\
 \mathcal{H}(x, y, n) = y[n] \\
y[n] = \sum^M_{k=0} b_{k}\ x[n - k] - \sum^N_{k=1} a_{k} \cdot y[n-k] \\ \\
\end{matrix}
$$

$$
\begin{align}
H(z) &= \frac{\sum^M_{k=0}b_{k}z^{-k}}{\sum^N_{k=0} a_{k}z^{-k}},\ a_{0} = 1 \\
&= \frac{b_{0}\prod^M_{k=1}(1-c_{k}z^{-1})}{\prod^N_{k=1}(1-d_{k}z^{-1})} \\ \\
\end{align}
$$
 
$$
h[n] = \sum^N_{k=1} A_{k}(d_{k})^n\ u[n]
$$