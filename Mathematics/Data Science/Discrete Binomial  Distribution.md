A kind of [[Discrete Distribution]] where $n$ independent and identically distributed [[Discrete Bernoulli Distribution|Bernoulli]] Trials are performed, counting the total number of "successes" after n trials each with [[Probability]] $p$.
$$
X \sim \text{Binomial}(n, p)
$$

* $f(x) = \binom{n}{x} p^x q^{n-x} \quad \text{for } x \in \{0..n\}$
* $E(X) = np$
* $\text{Var}(X) = npq$
* $X_{\text{Bin}} = \sum_{n=1}^{r}X_{i}\sim\text{Ber(p)}$
