---
date: 2026-10-15
---
# Statistic
A *Statistic* is a scalar feature extracted from a [[Sample]] that represents it in some way. As opposed to [[Parameter]]. 

$$
T: X_{1..n} \in \text{RV} \rightarrow \mathbb{R}
$$
# Sample Statistic
* Sample Mean $\overline{X} = \frac{\sum X}{n}$
* Sample Median: Middle entry in Sample
* Sample Mode: Most occurences in Sample
* Sample Variance $S^2 = \frac{\sum (X - \overline{X})^2}{n - 1}$
* Sample Standard Deviation $S$
* Sample Proportion $\hat{p} = \frac{x}{n}$

# Centrality Features
* Sample Mean, Median, Mode. Median is best.

# Spread Features
* Sample Range $\max X - \min X$
* Sample Variance, Standard Deviation
* Percentile
* Quartile, Inter Quartile Range

# Grouped Features
$$
\overline{X} - \frac{1}{n} \sum^p_{j=1} f_{j}x_{j}\quad\quad
S^2 = \frac{1}{n-1} \left(\sum_{j=1}^p f_{j} x^2_{j} - nx^2\right)
$$
