---
date: 2026-01-11
aliases:
  - Continuous
---
In layman's terms, when a [[Computer Science/Architecture/Programming/Function]] can be drawn without "picking up the pen".

$$
\begin{gathered}
f\text{ is continuous}\\
\iff\\
\forall \epsilon > 0,\ \exists \delta > 0\\ \text{ s.t. } \forall x \in D\\
\ |x-d| < \delta \implies |f(x) - f(d)| < \epsilon\\
\text{for}\ f : D \rightarrow C,\ d \in D
\end{gathered}
$$
* where $D$ is the [[Domain]] of the function
* where $C$ is the [[Codomain]] of the function
