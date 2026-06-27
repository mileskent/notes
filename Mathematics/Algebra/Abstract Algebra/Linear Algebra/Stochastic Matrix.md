---
date: 2024-12-08
---
A stochastic matrix is a [[Square Matrix]] $P$ whose columns are [[Probability Vector]]s.

|det(P)| <= 1, only volume contracting or preserving

**Theorem**
 as $k \rightarrow \infty$
$$
\vec{x}_{k+1} = P \vec{x}_k ; k = 0, 1, 2, . . .
$$
 If $P$ is a regular stochastic matrix, then $P$ has a unique steady-state vector $\vec{q}$, and $\vec{x_{k+1}} = P\vec{x_k}$ converges to $\vec{q}$ as $k \rightarrow \infty$; $(P^k \vec{x_0} \longrightarrow_{k\rightarrow \infty} \vec{q})$ where $P\vec{q} = \vec{q}$
# Regular
- Stochastic matrix is regular if there  $\exists (k \geq 1) P^k$ strictly has positive entries
- Regular $\iff$ unique steady state vectors
- Irregular $\iff$ $0\leq n\not = 1$ steady state vectors

