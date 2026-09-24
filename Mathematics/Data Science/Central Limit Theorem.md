The *Central Limit Theorem* states that no matter the shape or distribution of the original data, if you take a large enough random sample, and average the values, those sample averages will form a [[Continuous Normal Distribution|Normal Distribution]]. Furthermore, the sample mean will approach the population mean, and sample mean variance will shrink to 0.

$$
\frac{
X_{1..n}\quad
\forall i,j \in [1,n],\ X_{i} \sim^{iid} X_{j}\quad
E[X_{i}]=\mu\quad \text{Var}(X_{i}) = \sigma^2\quad
n \rightarrow \infty
}
{
Z_{n} = 
\frac{\sum_{k=1}^n X_{k} - n \mu}{\sigma \sqrt{ n }} = 
\frac{\bar{X}-\mu}{\sigma / \sqrt{ n }} =
\frac{\bar{X}-E[\bar{X}]}{\sqrt{ \text{Var}(\bar{X}) }}
\rightarrow^d \text{Nor}(0,1)
}
$$
