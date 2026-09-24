*Chebyshev's Inequality* is used to give the [[Probability]] of a [[Sample]] being beyond/within $k$ standard deviations of the mean.

$$
\frac{
E[X]=\mu
\quad
\text{Var}(X) = \sigma^2
\quad
k > 0
}{

P(|X-\mu| \geq k\sigma) \leq \frac{1}{k^2}
\quad
P(|X-\mu| < k\sigma) \geq 1 - \frac{1}{k^2}
}
$$

or equivalently

$$
\frac{
E[X]=\mu
\quad
\text{Var}(X) = \sigma^2
\quad
k > 0
}{

\max(P(|X-\mu| \geq k\sigma)) = \frac{1}{k^2}
\quad
\min(P(|X-\mu| < k\sigma)) = 1 - \frac{1}{k^2}
}
$$
