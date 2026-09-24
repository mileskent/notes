--

A kind of [[Continuous Distribution]] that is symmetric and bell-shaped, completely characterized by its mean $\mu$ and variance $\sigma^2$, where outcomes cluster around the center.
$$
X \sim \text{N}(\mu, \sigma^2) \quad \text{for } x \in \mathbb{R},\ \sigma^2 > 0
$$

* $f(x) = \frac{1}{\sigma \sqrt{2\pi}} \exp\left(-\frac{(x-\mu)^2}{2\sigma^2}\right) \quad \text{for } x \in (-\infty, \infty)$
* $E(X) = \mu$
* $\text{Var}(X) = \sigma^2$
* There is no [[Analytic Function|analytic]] solution for: $F_{X}(x) = \int^x_{-\infty}\frac{1}{\sigma \sqrt{2\pi}} \exp\left(-\frac{(x-\mu)^2}{2\sigma^2}\right)$

# Standard Normal Distribution
![[Continuous Standard Normal Distribution]]