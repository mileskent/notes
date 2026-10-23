An *F [[Distribution]]* is a kind of [[Sampling Distribution]] formed by combining two independent [[Chi Squared Distribution]]s in the following fasion

$$
F\equiv \frac{\chi^2_{(n)}/n}{\chi^2_{(m)}/m} \sim F(n,m)
$$

* F shows up when we want to find [[Confidence Interval]]s or conduct Hypothesis Tests

# F Quantiles
If $F\sim F(n, m)$ then the $(1-\alpha)$ [[Quantile|quantile]] is denoted $F_{\alpha, n, m}$
* where $P(F>F_{\alpha,n,m})=\alpha$
* where the [[Cumulative Density Function|CDF]] does not have a simple closed form, and the [[Probability Density Function|PDF]] is a mess
* where $\alpha$ is type I error
* where $n,m$ are separate [[Degree of Freedom]]s
* where $F_{1-\alpha,n,m} = 1/F_{\alpha,n,m}$

![[Pasted image 20261023175111.png|281]]