---
date: 2026-06-16
---
The *residue* of a [[Complex Number|complex]] function $f$ at an isolated singularity $z_0$ is the coefficient $A_{-1}$ of $(z - z_0)^{-1}$ in its [[Laurent Series]] expansion. It is the unique part of the singularity that survives a contour integral.

When you integrate $(z - z_0)^n$ around a closed contour, every $n \neq -1$ gives zero because $(z - z_0)^n$ has an antiderivative. The $n = -1$ term is the exception: its antiderivative $\log(z - z_0)$ picks up a branch contribution of $2\pi i$ each time the contour winds around $z_0$:

$$
\oint_\gamma (z - z_0)^n\, dz = \begin{cases} 2\pi i & n = -1 \\ 0 & n \neq -1 \end{cases}
$$

Integrating the Laurent series term by term, all coefficients cancel except $A_{-1}$, giving:

$$
\oint_\gamma f(z)\, dz = 2\pi i \cdot A_{-1}
$$

So via the [[Cauchy Integral Formula]]:

$$
\operatorname{Res}(f,\, z_0) = A_{-1} = \frac{1}{2\pi i} \oint_\gamma f(z)\, dz
$$

where $\gamma$ is any simple positively-oriented contour encircling $z_0$ and no other singularity. A function can have arbitrarily bad singular behavior at $z_0$, but none of it affects the contour integral. Only the $-1$ power does.

# Computing Residues

For a simple pole (order 1):

$$
\operatorname{Res}(f,\, z_0) = \lim_{z \to z_0} (z - z_0)\, f(z)
$$

For a pole of order $m$:

$$
\operatorname{Res}(f,\, z_0) = \frac{1}{(m-1)!} \lim_{z \to z_0} \frac{d^{m-1}}{dz^{m-1}} \left[(z - z_0)^m f(z)\right]
$$
