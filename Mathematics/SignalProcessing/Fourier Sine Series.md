---
date: 2025-02-03
---
Because $\sin(mt)$ is an [[Odd Function]] we can write any odd function as
$$
\mathbb{O}(t) = \frac{1}{\pi} \sum^{\infty}_{m=0} \mathbb{O}_{m}\sin(mt)
$$
where the set of coefficients of $\mathbb{O}_m$ define the series
and $\mathbb{O}(t)$ is over $(-\pi, \pi)$
This function only sometimes works, but we should assume it will work generally in Physics

#### Finding the coefficients of $\mathbb{O}(t)$
Exactly the same as the derivation in [[Fourier Cosine Series]], except with sines.
$$
\mathbb{O}_{m} = \int^\pi_{-\pi} \mathbb{O}(t) \sin (mt) dt
$$
