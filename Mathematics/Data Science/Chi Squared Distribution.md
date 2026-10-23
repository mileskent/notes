A $\chi^2$ *[[Distribution]]* is a kind of [[Sampling Distribution]] formed by combining iid squared [[Continuous Standard Normal Distribution|Z Distribution]]s through addition. 
* $\chi^2$ shows up when we try to estimate [[Variance]]

$$
\frac{
Z_{1..k} \sim^\text{iid} N(0,1)
}
{
\chi^2_{(k)}
\sim
\sum^k_{i=1} Z_{i}^2 
}
$$
* $E[Y] =k$
* $\text{Var}(Y) =2k$
* $\chi^2_{(1)} = Z^2$
* $\chi^2_{(2)} =\text{Exp}\left( \frac{1}{2} \right)$
* $\chi^2_{(\text{big})} \approx N$
* $k$ is [[Degree of Freedom]]


# Additive Property
The sum of iid $\chi^2$ variables is also $\chi^2$

$$
\frac{
Y_{1..n} \sim^\text{indep} \chi^2_{(k_{i})}
}
{
\sum^n_{i=1} Y_{i} \sim \chi^2_{\left(\sum_{i=1}^n k_{i}\right)}
}
$$

# Chi Squared Quantiles
If $Y \sim \chi^2_{(k)}$ then $(1-\alpha)$ [[Quantile|quantile]] is denoted $\chi^2_{\alpha, k}$
* where $P(Y>\chi^2_{\alpha,k}) = 1-F(\chi^2_{\alpha,k}) = \alpha$
* where $F$ is the $\chi^2$ [[Cumulative Density Function|CDF]]
* where $\alpha$ is type I error
* where $k$ is [[Degree of Freedom]]

![[Pasted image 20261023171417.png|275]]