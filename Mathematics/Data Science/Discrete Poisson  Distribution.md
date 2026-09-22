A kind of [[Discrete Distribution]] that models the count of events occurring in a fixed interval of time or space, assuming events happen independently at a constant average rate $\lambda$.

* $f(x) = \frac{\lambda^x e^{-\lambda}}{x!} \quad \text{for } x \in \mathbb{N}_{0}$
* $E(X) = \lambda$
* $\text{Var}(X) = \lambda$
* $X_{\text{Poisson}(n\lambda)} = \sum_{1}^{n} X_{i, \text{Poisson}(\lambda)}$
