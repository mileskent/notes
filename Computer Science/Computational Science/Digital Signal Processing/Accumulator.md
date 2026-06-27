---
date: 2026-06-15
---
The accumulator is a [[Discrete-Time Linear Time-Invariant System|DT LTI System]] system that computes the running sum of an input [[Computer Science/Computational Science/Digital Signal Processing/Signal|signal]]. 
* It is the [[Discrete-Time Signal|Discrete-Time]] equivalent of [[Integral|Integration]]
* It is a [[Feedback]] system
* Its [[Impulse Response]] is the [[Unit Step]] $u[n]$

# Forms
## Difference Equation

$$
y[n] = x[n] + y[n-1]
$$

## Block Diagram

```tikz
\usetikzlibrary{positioning, shapes.geometric}
\begin{document}
\begin{tikzpicture}[>=latex, scale=0.7, transform shape]
    \node (in) {$x[n]$};
    \node [draw, circle, right=2.5cm of in] (sum) {$+$};
    \node [right=2.5cm of sum] (out) {$y[n]$};
    \coordinate [right=1.25cm of sum] (branch);
    \node [draw, rectangle, below=1.5cm of branch] (delay) {$\mathcal{R}$};

    \draw [->] (in) -- (sum);
    \draw [->] (sum) -- (out);
    \draw [->] (branch) -- (delay);
    \draw [->] (delay) -| (sum);
\end{tikzpicture}
\end{document}
```

## Operator Form
### Implicit Operator Form
$$
(1 - \mathcal{R})Y = X
$$
### Explicit Operator Form
$$
Y = \frac{1}{1 - \mathcal{R}}X = \sum_{k=0}^{\infty} \mathcal{R}^k X
$$

