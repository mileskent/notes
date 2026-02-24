---
date: 2025-02-03
---
Because $\cos(mt)$ is an [[Even Function]] we can write any even function as
$$
\mathbb{E}(t) = \frac{1}{\pi} \sum^{\infty}_{m=0} \mathbb{E}_{m}\cos(mt)
$$
where the set of coefficients of $\mathbb{E}_m$ define the series
and $\mathbb{E}(t)$ is over $(-\pi, \pi)$
This function only sometimes works, but we should assume it will work generally in Physics


#### Finding the Coefficients
$$
\mathbb{E}(t) = \frac{1}{\pi} \sum^{\infty}_{m'=0} \mathbb{E}_{m'}\cos(m't)
$$
$$
\int^{\pi}_{-\pi} \mathbb{E}(t) \cos(mt) dt = \frac{1}{\pi} \sum^{\infty}_{m'=0} \int^\pi_{-\pi}\mathbb{E}_{m'}\cos(m't) \cos(mt) dt
$$
Using [[Kronecker Delta Function]], simplify the integral
$$
\int^{\pi}_{-\pi} \mathbb{E}(t) \cos(mt) dt = \frac{1}{\pi} \sum^{\infty}_{m'=0} \mathbb{E}_{m'} \pi \delta_{m',m}
$$
The sum only contributes once when $m' = m$, giving one $\pi$
$$
\int^{\pi}_{-\pi} \mathbb{E}(t) \cos(mt) dt = \frac{1}{\pi}  \mathbb{E}_{m} \pi 
$$
$$
\implies \mathbb{E}_{m} = \int^{\pi}_{-\pi} \mathbb{E}(t) \cos(mt) dt 
$$
