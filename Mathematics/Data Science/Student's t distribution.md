---
aliases:
  - t distribution
---
A *Student's $t$ [[Distribution]]* is a kind of [[Sampling Distribution]] formed by combining a [[Continuous Standard Normal Distribution|Z Distribution]] and [[Chi Squared Distribution]] in the following fashion

$$
T \equiv \frac{Z}{\sqrt{ \chi^2_{(k)}/k }} \sim t_{(k)}
$$

- $t$ shows up when we try to estimate $\mu$ when the $\sigma^2$ is unknown.
- $t_{(k)}$ looks like $Z$ but with a fatter tail to account for the extra uncertainty of using $S^2$ instead of $\sigma^2$
- $t_{(k\to \infty)} = Z$
- $E[T] = 0$
- $\text{Var}(T) = \frac{k}{k-2}\quad\text{for }\ k>2$

# Student's t Quantiles
If $T\sim t_{(k)}$ then the $(1-\alpha)$ [[Quantile|quantile]] is denoted $t_{\alpha,k}$
* where $P(T>t_{\alpha,k}) = 1-F(t_{\alpha,k}) = \alpha$
* where $F$ is the [[Cumulative Density Function|CDF]]
* where $\alpha$ is type I error
* where $k$ is [[Degree of Freedom]]
* where the distribution is symmetrical so $t_{1-\alpha,k} = -t_{\alpha,k}$

![[Pasted image 20261023173841.png|440]]