The marginal distribution isolates the probability distribution of one variable while ignoring the value of the other variable.

# Discrete Case (Marginal PMF)
- $f_X(x) = P(X = x) = \sum_{y} f(x,y)$
- $f_Y(y) = P(Y = y) = \sum_{x} f(x,y)$

# Continuous Case (Marginal PDF)
- $f_X(x) = \int_{-\infty}^{\infty} f(x,y) \, dy$
- $f_Y(y) = \int_{-\infty}^{\infty} f(x,y) \, dx$

# Marginal CDF
- $F_X(x) = P(X \le x) = \lim_{y \to \infty} F(x,y)$
- $F_Y(y) = P(Y \le y) = \lim_{x \to \infty} F(x,y)$