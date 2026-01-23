---
date: 2026-01-22
---
In [[Lambda Calculus]], a *function application* refers to applying the [[Transformation]] defined by a [[Function Abstraction]], $\lambda x.E$, to an argument $A$. This works through [[Beta Reduction]].
$$
(\lambda x.E)\ A
$$

For example, the function that adds one to its input, being applied to 1.
$$
\begin{gathered}
(\lambda x.x+1)\ 1\\
1+1\\
2
\end{gathered}
$$