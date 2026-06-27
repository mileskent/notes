---
date: 2026-06-15
aliases:
  - Difference Machine
---
The differencer is a [[Discrete-Time Linear Time-Invariant System|DT LTI System]] system that computes the first difference of an input [[Computer Science/Computational Science/Digital Signal Processing/Signal|signal]]. 
* It is the [[Discrete-Time Signal|Discrete-Time]] equivalent of a [[Derivative]]
* This system is [[Feed-Forward]]
* Its [[Impulse Response]] is $\delta[n] - \delta[n-1]$, a difference of the [[Unit Sample]]

$$
\begin{align}
y[n] &= x[n] - x[n-1]\\
Y &= (1 - \mathcal{R})X
\end{align}
$$

```tikz
\usetikzlibrary{positioning, shapes.geometric}
\begin{document}
\begin{tikzpicture}[>=latex, scale=0.7, transform shape]
    \node (in) {$x[n]$};
    \node [draw, circle, right=2.5cm of in] (sum) {$+$};
    \node [right=2.5cm of sum] (out) {$y[n]$};
    \node [draw, rectangle, below=1.5cm of sum] (delay) {$\mathcal{R}$};
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, left=1cm of delay] (neg) {$-1$};

    \draw [->] (in) -- (sum);
    \draw [->] (sum) -- (out);
    \draw [->] (in) |- (neg.west);
    \draw [->] (neg.east) -- (delay);
    \draw [->] (delay) -- (sum);
\end{tikzpicture}
\end{document}
```

