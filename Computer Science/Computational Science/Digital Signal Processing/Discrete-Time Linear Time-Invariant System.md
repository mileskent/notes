---
date: 2026-06-15
aliases:
  - DT LTI System
  - Discrete LTI System
  - Discrete-Time LTI System
---
An [[Linear Time-Invariant System]] that is [[Discrete-Time Signal|Discrete-Time]]

# Representations
There are many ways to represent an DT LTI system. Each representation has its own advantages.
## Verbal Description
Verbal description is good for communicating intuitively and accessibly, but potentially imprecise.

> Next year, your account will contain $p$ times your balance from this year plus the money that you added this year.
## Linear Difference Equation
Using a [[Difference Equation]] is mathematically precise and compact, but lacks the potential for conceptual expressiveness and intuition that language can provide. A difference equation is declarative. Algebraic equivalences that are trivially spottable in algebraic form, can be extremely unintuitive to spot in either of the other forms.
$$
y[n+1] = x[n] + p \cdot y[n]
$$
## Operator Polynomial Equation
Using [[Linear Unary Operator#Operator Notation]] is as mathematically precise as the [[#Linear Difference Equation]], while being even more compact. The algebraic form admits standard polynomial operations: factoring, root finding, partial fraction decomposition, etc. without requiring sample-by-sample reasoning. This form is extremely useful, as it enables the powerful tools of algebra to intuitively be applied to systems. Its strength is abstraction. Note that the order of the polynomial corresponds to the order of the system.
$$
(1-p\mathcal{R})Y = \mathcal{R}X
$$
## Block Diagram
Using a [[Block Diagram]] is good for conveying the step-by-step procedure of a system, like a circuit schematic, but is potentially unintuitive in expressively conveying ultimate effect of the system and requires tracing to understand.
```tikz
\usetikzlibrary{positioning, shapes.geometric}
\begin{document}
\begin{tikzpicture}[>=latex, scale=0.7, transform shape]
    \node (in) {$x[n]$};
    \node [draw, circle, right=2.5cm of in] (sum) {$+$};
    \node [draw, rectangle, right=1.5cm of sum] (delay) {$\mathcal{R}$};
    \node [right=1.5cm of delay] (out) {$y[n]$};
    \coordinate [right=1cm of delay] (branch);
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, shape border rotate=180, below=1.5cm of branch, xshift=-1.5cm] (gain) {$p$};

    \draw [->] (in) -- (sum);
    \draw [->] (sum) -- (delay);
    \draw [->] (delay) -- (out);
    \draw [->] (branch) |- (gain.east);
    \draw [->] (gain.west) -| (sum);
\end{tikzpicture}
\end{document}
```
