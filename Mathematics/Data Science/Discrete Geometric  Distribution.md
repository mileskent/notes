A kind of [[Discrete Distribution]] that models the number of independent [[Discrete Bernoulli Distribution|Bernoulli]] Trials until the first Success, where each trial has a [[Probability]] $p$ of success.
$$
X \sim \text{Geometric}(p)
$$

* $f(x) = p q^{x-1}  \quad \text{for } x \in \mathbb{Z}^+$
* $E(X) = \frac{1}{p}$
* $\text{Var}(X) =\frac{1}{p} \left( \frac{1}{p} - 1 \right) = \frac{q}{p^2}$
