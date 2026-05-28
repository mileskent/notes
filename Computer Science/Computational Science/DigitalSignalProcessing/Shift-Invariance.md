---
date: 2026-05-27
---
*Shift-Invariance* means that a delay can be applied either before or after a system, and produce the same result. 

# Formal Definition
Let $\Delta$ be a $n_{0}$-step delay [[Filter]] for some fixed by delay $n_{0} \in \mathbb{N}$, where $\vec{0} \in \mathbb{R}^{1 \times n_{0}}$

$$
\Delta = [\vec{0}, 1]
$$

so that [[Convolution]] with signal $x$ yields

$$
(\Delta * x)[n] = x[n-n_{0}]
$$

A filter $g$ is *shift-invariant* if
$$
\forall n_{0}\ \forall x\ g(\Delta * x) = \Delta * g(x)
$$
