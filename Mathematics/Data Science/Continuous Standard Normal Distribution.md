---
aliases:
  - Z Distribution
  - Z Score
---
A [[Continuous Normal Distribution]] that is transformed as follows.

$$
Z \sim \text{N}(0,1)\quad \text{where } \mu=0,\ \sigma^2=1
$$
* [[Probability Density Function|PDF]]: $\phi(z) = \frac{1}{\sqrt{ 2\pi }} \exp\left( -\frac{z^2}{2} \right)$
* $E(Z) = 0$
* $\text{Var}(Z) = 1$
* [[Cumulative Density Function|CDF]]: $\Phi(z) = \int^x_{0} \frac{1}{\sqrt{ 2\pi }} \exp\left( -\frac{z^2}{2} \right)\ dx$
	* No analytic solution. Use a [Z Table](https://www.ztable.net/).

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