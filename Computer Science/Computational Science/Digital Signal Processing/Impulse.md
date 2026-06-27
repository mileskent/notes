---
date: 2026-05-27
---
In [[Discrete-Time Signal|Discrete-Time]] land, an Impulse $\delta[n]$ is a [[Computer Science/Computational Science/Digital Signal Processing/Signal|Signal]] that is the [[Unit Sample]]

$$
\begin{align}
\delta[n] = \begin{cases} 1, & n = 0 \\ 0, & n \neq 0 \end{cases}\\ \\
\delta[n] = [1, \vec{0}]
\end{align}
$$

Note that for [[Convolution]]s, this unit impulse is like the [[Identity]]

$$
x[n] * \delta[n] = x[n]
$$

Similar to the [[Step Function]], you can scale or shift the delta function. Furthermore, you can compose these scaled and shifted delta functions to create *ANY* given signal.

For example, $x[n]$ is a signal that goes: 1, 2, 3.

$$
x[n] = 1 \cdot \delta[n] + 2 \cdot \delta[n-1] + 3 \cdot \delta[n-2]
$$