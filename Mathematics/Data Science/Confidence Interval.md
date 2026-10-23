A *Confidence Interval* is a technique in [[Statistics]], where instead of estimating a [[Parameter]] by a [[Point Estimation|Point Estimator]] alone, we create an interval that we know contains the unknown parameter with a certain [[Probability]].

A $100(1-\alpha)\%$ *Confidence Interval* for an unknown parameter $\theta$ is given by $L,U \in\text{RV}$ satisfying
$$
P(L \leq \theta \leq U) = 1-\alpha
$$
* where $L$ is the lower bound
* where $U$ is the upper bound
* where $1-\alpha$ is the Confidence Coefficient

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
