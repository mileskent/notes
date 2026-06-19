---
date: 2026-06-16
---

A Laurent series generalizes the [[Taylor Series]] to functions that may have isolated singularities, by allowing negative powers of $(z - z_0)$.

Let $f$ be holomorphic on an annulus $\{z \in \mathbb{C} : r < |z - z_0| < R\}$ where $0 \le r < R \le \infty$. The Laurent series of $f$ centered at $z_0$ is

$$f(z) = \sum_{n=-\infty}^{\infty} a_n (z - z_0)^n$$

convergent throughout the annulus. The series splits into two parts:

- the analytic part: $\sum_{n=0}^{\infty} a_n (z - z_0)^n$
- the principal part: $\sum_{n=1}^{\infty} a_{-n} (z - z_0)^{-n}$

# Coefficient Formula

The coefficients are given by

$$a_n = \frac{1}{2\pi i} \oint_\gamma \frac{f(z)}{(z - z_0)^{n+1}}\, dz$$

where $\gamma$ is any positively oriented simple closed contour lying in the annulus and encircling $z_0$. This follows directly from the [[Cauchy Integral Formula]]. The coefficient $a_{-1}$ is the [[Residue]] of $f$ at $z_0$.

# Distinction from Taylor Series

A Taylor series requires $f$ to be holomorphic in a full disk around $z_0$, so all negative-power coefficients vanish. A Laurent series is needed when $z_0$ is a singularity or is excluded from the domain, and the principal part captures the singular behavior.

# Classification of Isolated Singularities

The structure of the principal part classifies the isolated singularity at $z_0$:

- Removable singularity: the principal part is identically zero (all $a_n = 0$ for $n < 0$).
- Pole of order $m$: the principal part has finitely many terms, with $a_{-m} \ne 0$ and $a_n = 0$ for all $n < -m$.
- Essential singularity: the principal part has infinitely many nonzero terms.

# Uniqueness

The Laurent expansion in a given annulus is unique. If two Laurent series agree on the annulus, their coefficients are identical term by term.

# Convergence

The analytic part converges for $|z - z_0| < R$ and the principal part converges for $|z - z_0| > r$. Both converge absolutely and uniformly on compact subannuli $r' \le |z - z_0| \le R'$ with $r < r' < R' < R$.
