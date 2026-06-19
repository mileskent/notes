---
date: 2026-06-16
---
Let $f$ be analytic inside and on a simple closed positively oriented contour $\gamma$, and let $z_0$ be any point in the interior of $\gamma$. Then:

$$f(z_0) = \frac{1}{2\pi i} \oint_\gamma \frac{f(z)}{z - z_0}\, dz$$

The formula recovers the value of $f$ at any interior point entirely from its values on the boundary, a consequence of [[Cauchy's Theorem]] and the structure of analytic functions.

# Generalized Form for Derivatives

The formula extends to all higher-order derivatives. For $n \geq 0$:

$$f^{(n)}(z_0) = \frac{n!}{2\pi i} \oint_\gamma \frac{f(z)}{(z - z_0)^{n+1}}\, dz$$

The $n = 0$ case recovers the basic formula. This is proved by differentiating under the integral sign, which is justified by uniform convergence on $\gamma$.

# Infinite Differentiability

If $f$ is analytic on an open set $U$, then $f$ is infinitely differentiable on $U$, and every derivative $f^{(n)}$ is itself analytic on $U$. This stands in sharp contrast to real analysis, where a function can be differentiable exactly $k$ times and no more. Analyticity in the complex sense is a far stronger condition.

# Connection to Residues

The integrand $f(z)/(z - z_0)$ has a simple pole at $z_0$ with [[Residue]]:

$$\operatorname{Res}_{z = z_0} \frac{f(z)}{z - z_0} = f(z_0)$$

The Cauchy Integral Formula is therefore a direct application of the residue theorem: the contour integral equals $2\pi i$ times the sum of residues of enclosed poles. With $f$ analytic inside $\gamma$, the only singularity of the integrand is the simple pole at $z_0$, giving exactly $2\pi i \cdot f(z_0)$.

More generally, the generalized formula extracts the coefficient of $(z - z_0)^n$ in the Laurent expansion of $f(z)/(z-z_0)^{n+1}$, which is the residue at the order-$(n+1)$ pole.
