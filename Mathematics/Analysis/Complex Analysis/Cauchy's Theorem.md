---
date: 2026-06-16
aliases:
  - Cauchy-Goursat Theorem
---
If $f$ is analytic on and inside a simple closed positively-oriented contour $\gamma$, then:

$$
\oint_\gamma f(z)\, dz = 0
$$

# Consequences

Path independence: the integral of an analytic function between two points is independent of the path taken, as long as the path stays within a simply-connected region of analyticity. Any two paths with the same endpoints can be combined into a closed contour, which integrates to zero.

Deformation invariance: a contour can be continuously deformed within a region of analyticity without changing the value of the integral. This allows residue calculations to use any convenient contour encircling the poles of interest.

# Relation to Cauchy Integral Formula

The [[Cauchy Integral Formula]] is derived from Cauchy's Theorem. The integrand $f(z)/(z - z_0)$ fails to be analytic at $z_0$, so the theorem does not apply directly. Instead, a small circle around $z_0$ is excised, the theorem is applied to the resulting annular region, and the limit as the circle shrinks recovers the formula.
