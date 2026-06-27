---
date: 2026-06-22
aliases:
  - CT LTI System
  - Continuous LTI System
  - Continuous-Time LTI System
---
An [[Linear Time-Invariant System]] that is [[Analog Signal|Continuous-Time]]

# Representations
## Verbal Description

> Your account will grow in proportion to your balance plus the rate at which you deposit.

## Linear Differential Equation
$$
y'(t)=x(t)+p\cdot y(t)
$$

See [[Linear Differential Equation]]

## Operator Polynomial Equation
$$
(1-p \mathcal{A}) Y = \mathcal{A}X
$$

## Block Diagram
```tikz
\usetikzlibrary{positioning, shapes.geometric}
\begin{document}
\begin{tikzpicture}[>=latex, scale=0.7, transform shape]
    \node (in) {$x(t)$};
    \node [draw, circle, right=2.5cm of in] (sum) {$+$};
    \node [draw, rectangle, right=1.5cm of sum, minimum width=1.2cm, minimum height=0.8cm] (int) {$\mathcal{A}$};
    \node [right=1.5cm of int] (out) {$y(t)$};
    \coordinate [right=1cm of int] (branch);
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, shape border rotate=180, below=1.5cm of branch, xshift=-1.5cm] (gain) {$p$};

    \draw [->] (in) -- (sum);
    \draw [->] (sum) -- (int);
    \draw [->] (int) -- (out);
    \draw [->] (branch) |- (gain.east);
    \draw [->] (gain.west) -| (sum);
\end{tikzpicture}
\end{document}
```

