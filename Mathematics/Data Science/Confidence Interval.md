---
date: 2026-11-02
---
A *Confidence Interval* is a technique in [[Statistics]], where instead of estimating a [[Parameter]] by a [[Point Estimation|Point Estimator]] alone, we create an interval that we know contains the unknown parameter with a certain [[Probability]].

A $100(1-\alpha)\%$ *Confidence Interval* for an unknown parameter $\theta$ is given by $L,U \in\text{RV}$ satisfying
$$
P(L \leq \theta \leq U) = 1-\alpha
$$
* where $L$ is the lower bound
* where $U$ is the upper bound
* where $1-\alpha$ is the Confidence Coefficient

# Confidence Interval Scenarios
* 1 population Confidence Interval
	* $\mu$
		* $\sigma^2$ known
			* $Z = \frac{\overline{X} - \mu}{\sigma / \sqrt{ n } } \sim N(0,1)$
			* $\mu \in \overline{X} \pm z_{\alpha/2} \frac{\sigma}{\sqrt{ n }}$
		* $\sigma^2$ unknown
			* $T = \frac{\overline{X} - \mu}{S / \sqrt{ n } } \sim t_{(n-1)}$
			* $\mu \in \overline{X} \pm t_{\alpha/2,(n-1)} \frac{S}{\sqrt{ n }}$
    * $\sigma^2$
        * $\chi^2 = \frac{(n-1)S^2}{\sigma^2} \sim \chi^2_{(n-1)}$
        * $\sigma^2 \in \left[\frac{(n-1)S^2}{\chi^2_{1-\alpha/2, (n-1)}}, \frac{(n-1)S^2}{\chi^2_{\alpha/2, (n-1)}}\right]$
	* $p$ 
		* $Z = \frac{\overline{X} - p}{\sqrt{pq/n}} = \frac{\hat{p} - E(\hat{p})}{\sqrt{\text{Var}(\hat{p})}} \sim N(0,1)$ 
		* $p \in \overline{X} \pm z_{\alpha/2} \sqrt{\frac{\overline{X}(1 - \overline{X})}{n}}$
- 2 population Confidence Interval
    * $\mu_{X} -\mu_{Y}$
        * $\forall \sigma^2$ known
            * $Z = \frac{(\overline{X} - \overline{Y}) - (\mu_X - \mu_Y)}{\sqrt{\frac{\sigma_X^2}{n_X} + \frac{\sigma_Y^2}{n_Y}}} \sim N(0,1)$
            * $(\mu_X - \mu_Y) \in (\overline{X} - \overline{Y}) \pm z_{\alpha/2} \sqrt{\frac{\sigma_X^2}{n_X} + \frac{\sigma_Y^2}{n_Y}}$
        * $\forall \sigma^2\text{ unknown} \land \sigma^2_{X} = \sigma^2_{Y}$
			* $T = \frac{(\overline{X} - \overline{Y}) - (\mu_X - \mu_Y)}{\sqrt{\frac{S_p^2}{n_X} + \frac{S_p^2}{n_Y}}} \sim t_{(n_X + n_Y - 2)}$
			* $S_p^2 = \frac{(n_X - 1)S_X^2 + (n_Y - 1)S_Y^2}{n_X + n_Y - 2}$; bonus: is unbiased estimator for $\sigma^2$
			* $(\mu_X - \mu_Y) \in (\overline{X} - \overline{Y}) \pm t_{\alpha/2,(n_X + n_Y - 2)} \sqrt{\frac{S_p^2}{n_X} + \frac{S_p^2}{n_Y}}$
        * $\forall \sigma^2\text{ unknown} \land \sigma^2_{X} \not= \sigma^2_{Y}$
            * $T = \frac{(\overline{X} - \overline{Y}) - (\mu_X - \mu_Y)}{\sqrt{\frac{S_X^2}{n_X} + \frac{S_Y^2}{n_Y}}} \sim t_{(\nu)}$
            * $\nu = \frac{\left(\frac{S_X^2}{n_X} + \frac{S_Y^2}{n_Y}\right)^2}{\frac{(S_X^2 / n_X)^2}{n_X + 1} + \frac{(S_Y^2 / n_Y)^2}{n_Y + 1}} - 2$
            * $(\mu_X - \mu_Y) \in (\overline{X} - \overline{Y}) \pm t_{\alpha/2,\nu} \sqrt{\frac{S_X^2}{n_X} + \frac{S_Y^2}{n_Y}}$
    * $\frac{\sigma^2_{X}}{\sigma^2_{Y}}$
		* $F = \frac{S_X^2 / \sigma_X^2}{S_Y^2 / \sigma_Y^2} \sim \frac{\chi^2_{n_X - 1} / (n_X - 1)}{\chi^2_{n_Y - 1} / (n_Y - 1)} \sim F_{(n_X - 1, n_Y - 1)}$
        * $\frac{\sigma^2_X}{\sigma^2_Y} \in \left[\frac{S_X^2}{S_Y^2} \frac{1}{F_{\alpha/2, (n_X - 1, n_Y - 1)}}, \frac{S_X^2}{S_Y^2} \frac{1}{F_{1-\alpha/2, (n_X - 1, n_Y - 1)}}\right]$
    * $p_{X} - p_{Y}$
        * $Z = \frac{(\hat{p}_X - \hat{p}_Y) - (p_X - p_Y)}{\sqrt{\frac{\hat{p}_X(1-\hat{p}_X)}{n_X} + \frac{\hat{p}_Y(1-\hat{p}_Y)}{n_Y}}} \sim N(0,1)$
        * $(p_X - p_Y) \in (\hat{p}_X - \hat{p}_Y) \pm z_{\alpha/2} \sqrt{\frac{\hat{p}_X(1-\hat{p}_X)}{n_X} + \frac{\hat{p}_Y(1-\hat{p}_Y)}{n_Y}}$


# Variation of Sidedness
$$
\begin{align*}
\theta \in \hat\theta \pm H && \text{2 sided CI}\\
\theta < \hat\theta + H && \text{1 sided lower CI}\\
\theta > \hat\theta - H && \text{1 sided upper CI}\\
\end{align*}
$$

# Calculating Sample Size from Half Width
Example using 1 population, $\mu$, unknown $\sigma^2$

$$
\begin{align*}
H &\le \epsilon \\
t_{\alpha/2, (n-1)} \frac{S}{\sqrt{n}} &\le \epsilon \\
\frac{t_{\alpha/2, (n-1)} S}{\epsilon} &\le \sqrt{n} \\
\left( \frac{t_{\alpha/2, (n-1)} S}{\epsilon} \right)^2 &\le n \\
n &\ge \left( \frac{t_{\alpha/2, (n-1)} S}{\epsilon} \right)^2
\end{align*}
$$


# Mean CI Variance Known
$$
\begin{array}{}
\mu \in \overline{X} \pm z_{\alpha/2} \frac{\sigma}{\sqrt{ n }}\\
\end{array}
$$

$H$ is called **half-width**
$$
H \equiv z_{\alpha/2} \frac{\sigma}{\sqrt{ n }}
$$


$$
\begin{array}{}
\begin{array}{}
X_{1..n} \sim^{\text{iid}} N(\mu,\sigma^2)&
\sigma^2 \text{ known}&
\hat{\theta} = \overline{X} = \sum_{i} X_{i} /n
\end{array}
\\ \hline
Z \equiv \frac{\overline{X}-\mu}{\sqrt{ \sigma^2 / n }} \sim N(0,1)
\\ \hline
\begin{array}{l}
1-\alpha
&= P(-z_{\alpha / 2} \leq Z \leq z_{\alpha / 2}) \\
&= P(-z_{\alpha / 2} \leq \frac{\overline{X}-\mu}{\sqrt{ \sigma^2 / n }} \leq z_{\alpha / 2}) \\
&= P(-z_{\alpha / 2}\sqrt{\sigma^2 / n} \leq \overline{X}-\mu \leq z_{\alpha / 2}\sqrt{\sigma^2 / n}) \\
&= P\left(\underbrace{\overline{X} - z_{\alpha / 2}\sqrt{\sigma^2 / n}}_{L} \leq \mu \leq \underbrace{\overline{X} + z_{\alpha / 2}\sqrt{\sigma^2 / n}}_{U}\right)
\end{array}
\end{array}
$$

In order to reduce half length $H$ below a tolerance error $\epsilon$
$$
H =z_{\alpha / 2} \frac{\sigma}{\sqrt{ n }} \leq \epsilon
\iff
n \geq (\sigma z_{\alpha / 2} / \epsilon)^2
$$
# Mean CI Variance Unknown
$$
\begin{array}{}
\mu \in \overline{X} \pm t_{\alpha/2(n-1)} \frac{S}{\sqrt{ n }}\\
H \equiv t_{\alpha/2(n-1)} \frac{S}{\sqrt{ n }}
\end{array}
$$
