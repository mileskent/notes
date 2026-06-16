---
date: 2026-06-15
aliases:
  - LCCDE
  - LCCD Equation
---
A Linear Constant Coefficient Difference [[Equation]] (LCCDE) describes a class of [[System|systems]] that are a [[Linear Time-Invariant System]], causal, and expressible as a finite-order recurrence relation. Constant coefficients imply [[Shift-Invariance|Time Invariance]].

# Representations
There are many ways to represent an LCCDE system. Each representation has its own advantages.
## Verbal Description
Verbal description is good for communicating intuitively and accessibly, but potentially imprecise.

> The nth output signal of this system is the difference of the previous two input signals.
## Difference Equation
Using a [[Difference Equation]] is mathematically precise and compact, but lacks the potential for conceptual expressiveness and intuition that language can provide. A difference equation is declarative. Algebraic equivalences that are trivially spottable in algebraic form, can be extremely unintuitive to spot in either of the other forms.
$$
y[n] = x[n] - x[n-1]
$$
## Block Diagram
Using a [[Block Diagram]] is good for conveying the step-by-step procedure of a system, like a circuit schematic, but is potentially unintuitive in expressively conveying ultimate effect of the system and requires tracing to understand.
```tikz
\usetikzlibrary{positioning, shapes.geometric}
\begin{document}
\begin{tikzpicture}[>=latex, scale=0.7, transform shape]
    \node (in) {$x[n]$};
    \node [draw, circle, right=2.5cm of in] (sum) {$+$};
    \node [right=2.5cm of sum] (out) {$y[n]$};
    \node [draw, rectangle, below=1.5cm of sum] (delay) {Delay};
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, left=1cm of delay] (neg) {$-1$};

    \draw [->] (in) -- (sum);
    \draw [->] (sum) -- (out);
    \draw [->] (in) |- (neg.west);
    \draw [->] (neg.east) -- (delay);
    \draw [->] (delay) -- (sum);
\end{tikzpicture}
\end{document}
```
