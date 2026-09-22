A kind of [[Continuous Distribution]] that is symmetric and bell-shaped, completely characterized by its mean $\mu$ and variance $\sigma^2$, where outcomes cluster around the center.
$$
X \sim \text{N}(\mu, \sigma^2) \quad \text{for } x \in \mathbb{R},\ \sigma^2 > 0
$$

* $f(x) = \frac{1}{\sigma \sqrt{2\pi}} \exp\left(-\frac{(x-\mu)^2}{2\sigma^2}\right) \quad \text{for } x \in (-\infty, \infty)$
* $E(X) = \mu$
* $\text{Var}(X) = \sigma^2$
* There is no [[Analytic Function|analytic]] solution for: $F_{X}(x) = \int^x_{-\infty}\frac{1}{\sigma \sqrt{2\pi}} \exp\left(-\frac{(x-\mu)^2}{2\sigma^2}\right)$

# Standard Normal Distribution
$$
Z \sim \text{N}(0,1)\quad \text{where } \mu=0,\ \sigma^2=1
$$
* $\phi(z) = \frac{1}{\sqrt{ 2\pi }} \exp\left( -\frac{z^2}{2} \right)$
* $E(Z) = 0$
* $\text{Var}(Z) = 1$

Any normal distribution can be easily changed to a standard normal distribution

$$
Z = \frac{X-\mu}{\sigma} \sim \text{N}(0,1)
$$
* $F(Z) =\Phi(z) = P(Z \leq z) = \int_{-\infty}^z \phi(t)\ dt = \int^z_{-\infty} \frac{1}{\sqrt{ 2\pi }} \exp\left( -\frac{t^2}{2}\ dt \right)$

## Properties
* $\phi(x) = \phi(-x)$
* $\Phi(-x) = 1 - \Phi(x)$
* $P(Z > z) = 1 - P(Z < -z)$
* $P(a < Z < b) = P(Z < b) - P(Z < a) = \Phi(b) - \Phi(a)$
* If $P(Z < z_\alpha) = \alpha$, then $P(Z > z_\alpha) = 1 - \alpha$
* If $\Phi(z_\alpha) = \alpha$, then $z_\alpha = \Phi^{-1}(\alpha)$
* $z_{1-\alpha} = -z_\alpha$
