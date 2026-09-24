*Markov's Inequality* uses [[Expected Value]] to find the upper bound of the Probability of a nonnegative [[Random Variable]] being at least $c$

$$
\frac
{
X \text{ is RV}\quad
P(X\geq 0) = 1\quad
c>0
}
{
P(X \ge c) \le \frac{E[X]}{c}
}
$$ 
# Proof
$$
\begin{aligned}
E[X] = \int_{0}^{\infty} x f(x) dx \ge &\int_{c}^{\infty} x f(x) dx \ge c \int_{c}^{\infty} f(x) dx = c P(X \ge c)\\
E[X] &\ge c P(X \ge c)\\
\frac{E[X]}{c} &\ge P(X \ge c)\\
&\Box
\end{aligned}
$$ 
