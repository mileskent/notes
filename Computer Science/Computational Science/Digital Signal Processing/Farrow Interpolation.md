---
date: 2026-06-09
---
*Farrow interpolation* is a computationally efficient method for implementing a variable [[Fractional Delay Filter]]. The interpolated output is expressed as a polynomial in the fractional delay $\mu \in [0, 1)$:

$$
y[\mu] = \sum_{m=0}^{M} v_m \cdot \mu^m
$$

* where each $v_m = \sum_{n} c_m[n] \cdot x[k-n]$ is the output of a fixed [[Finite Impulse Response Filter|FIR]] subfilter with precomputed coefficients $c_m[n]$.
* The subfilter outputs $v_m$ are combined at runtime using [[Horner's Method]], making the cost of varying $\mu$ very low.
* [[Lagrange Polynomial Interpolation]] is a special case of Farrow interpolation.
