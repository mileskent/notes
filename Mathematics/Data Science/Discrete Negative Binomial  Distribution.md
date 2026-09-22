A kind of [[Discrete Distribution]] that models the number of independent [[Discrete Bernoulli Distribution|Bernoulli]] Trial until the $r^\text{th}$ Success, where each trial has a [[Probability]] $p$ of success.
$$
X \sim \text{NB}(r,p)
$$

* $f(x) = \binom{x-1}{r-1} p^r q^{x-r} \quad \text{for } x \in \mathbb{N}_{0} + r$
* $E(X) = \frac{r}{p}$
* $\text{Var}(X) = \frac{r}{p} \left( \frac{1}{p} - 1 \right) = \frac{r(1-p)}{p^2}$
* $X_{\text{NB}} = \sum_{i=1}^{r}X_{i}\sim\text{Geo(p)}$
