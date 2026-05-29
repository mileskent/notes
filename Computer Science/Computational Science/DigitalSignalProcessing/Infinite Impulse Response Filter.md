---
date: 2026-05-25
aliases:
  - IIR Filter
---
$$
\begin{align}
y[n] &= \sum^M_{k=0} b_{k}\ x[n - k] - \sum^N_{k=1} q_{k} \cdot y[n-k] \\ \\
H(z) &= \frac{\sum^M_{k=0}b_{k}z^{-k}}{\sum^N_{k=0} a_{k}z^{-k}},\ a_{0} = 1 \\
&= \frac{b_{0}\prod^M_{k=1}(1-c_{k}z^{-1})}{\prod^N_{k=1}(1-d_{k}z^{-1})} \\ \\
h[n] &= \sum^N_{k=1} A_{k}(d_{k})^n\ u[n]
\end{align}
$$