---
date: 2025-12-01
---
*Statistics* is the study of predicting [[Population|Populations]] from [[Sample|Samples]] ^063192

![[Statistic]]

In the real world, you don't [[Parameter]]s, so you have to approximate them with [[Statistic]]s. In Statistics, our goal is to analyze population(s) without omnipotence.

# Point Estimation
![[Point Estimation]]

# Sampling Distribution
A *Sampling Distribution* is a [[Distribution]] of a [[Statistic]].  

## Chi Squared Distribution
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

## t distribution
$$
T \equiv \frac{Z}{\sqrt{ Y/k }} \sim t_{(k)}
$$

## F distribution
$$
F\equiv \frac{X/m}{Y/m} \sim F(n,m)
$$