---
aliases:
  - Point Estimator
---

A *Point Estimator* is a [[Statistic]] that is designed to estimate a [[Parameter]]. 

* A regular statistic is just any feature from the data, whereas a Point Estimator specifically involves using the feature to predict the population parameter
* In order to *evaluate how good* a Point Estimator is, our goal is to minimize [[#Mean Squared Error]], i.e. both [[#Bias]] *and* [[#Variance]]. Minimizing MSE maximizes accuracy of the Point Estimator.
* In order to *find* a Point Estimator we can use techniques such as
	* [[#Method of Moments]]
	* [[#Maximum Likelihood Estimator]]

# Bias
Bias is a measure of the expected difference between a Point Estimator and a Parameter. Imagine shooting arrows at a target. Bias refers to displacement of the center of the cluster from the bullseye.
$$
\frac{
\begin{matrix}
X_{1..n} \sim^{iid} f(x; \theta) &
T: \mathbb{R}^n \rightarrow \mathbb{R} &
\hat{\theta} = T(X_{1..n})
\end{matrix}
}
{
\text{Bias}(\hat{\theta}) = E[\hat{\theta}] - \theta
}
$$
* where $T$ is a Statistic
* where $\theta$ is a Parameter of $X_{1..n}$
* where $\hat{\theta}$ is a Point Estimator 

# Variance
Variance measures spread of a Point Estimator. Imagine shooting arrows at a target. Variance measures how spread out the arrows are from **each other** (and specifically **not** from the bullseye). 

# Point Estimation Features
* Standard Error $\sqrt{ \text{Var}(\hat{\theta}) }$
* Sample Mean $\overline{X}$
	* $E(\overline{X}) = \mu$
	* $\text{Var}(\overline{X}) = \frac{\sigma^2}{n}$
	* $S.E. = \frac{\sigma}{\sqrt{ n }}$

# Mean Squared Error
Mean Squared Error (MSE) measures how good a Point Estimator is. The lower the MSE, the more accurate a Point Estimator is, *even if it does not minimize Bias*.

$$
\text{MSE}(\hat{\theta}) = E[(\hat{\theta} - \theta)^2] = \text{Bias}(\hat{\theta})^2 + \text{Var}(\hat{\theta})
$$

# Finding a Point Estimator
## Method of Moments
The $k^\text{th}$ moment for RV $X$ is
$$
E[X^k] = \text{sum}\ x^k f(x)
$$

For $X_{1..n} \sim^{iid}$ from PMF/PDF $f(x)$, then the Method of Moments estimator for $E(X^k)$ is 
$$
\frac{1}{n} \sum^n_{i=1} X^k_{i}
$$
## Maximum Likelihood Estimator
For $X_{1..n} \sim^{iid} f(x;\theta)$

We find *MLE*, which is the $\theta$ that maximizes the Likelihood Function $L$. $L$ is a scoring function that tells you how well your $\theta$ matches the observed data. 

$$
L(\theta) = \prod^n_{i=1} f(x_{i})\\
\begin{matrix}
\max L = L(\text{MLE})
\end{matrix}
$$

The trick for finding MLE
* Find $\ln(L(\theta))$
* Find $\frac{\partial}{\partial \theta} \ln(L(\theta))$
	* Recall $\frac{d}{dx} (\ln(f(x))) = \frac{f'(x)}{f(x)}$
* Find where this equals 0
* Find which root is the max
* The $\max (\ln L) = \ln L$