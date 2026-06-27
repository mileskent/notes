---
date: 2026-05-27
---
A discrete [[Convolution]], is a convolution applied to [[Discrete-Time Signal|Discrete-Time]] functions, rather than [[Analog Signal|Continuous-Time]] functions. We assume that our input signals have finite lengths and start at index zero, due to the [[Digital Signal Processing]] context.

$$
\begin{align}
y[n] = \sum_{k=0}^{\text{length}(h)-1}\ h[k] \cdot x[n-k]\\ \\
\text{length}(y) = \text{length}(x) + \text{length}(h) - 1
\end{align}
$$

Here $h[k]$ is the [[Impulse Response]] of the system; this is the discrete analog of [[Duhamel's Principle]], where $y_p(t) = h * f$.
