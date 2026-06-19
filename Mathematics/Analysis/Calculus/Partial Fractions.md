---
date: 2022-12-15
aliases:
  - Partial Fraction Decomposition
---
$$
\frac{5x+3}{(x+1)(x+2)} = \frac{A}{x+1} + \frac{B}{x+2}
$$
$$
\begin{aligned}
5x+3 = A(x+2) + B(x+1) \\
5x+3 = (A+B)x + (2A+B) \\
A+B = 5, \quad 2A+B = 3 \\
\rightarrow A = -2, \quad B = 7 \\
\end{aligned}
$$
$$
\boxed{\frac{5x+3}{(x+1)(x+2)} = \frac{-2}{x+1} + \frac{7}{x+2}}
$$


For partial fractions, if you have a repeated factor such as $(x-a)^n$ in the denominator, you must have degrees 1 through $n$ in your partial fraction sum.
$$
\frac{\cdots}{\cdots (x-a)^n} = \cdots + \sum_{i=1}^{n} \frac{c_i}{(x-a)^i}
$$

This is really thorough: https://www.mathsisfun.com/algebra/partial-fractions.html

# Example
$$
\int^2_{-2} \frac{1}{(x+7)(x^2+9)}dx
$$
Use partial fractions on the integrand
$$
\begin{aligned}
\frac{1}{(x+7)(x^2+9)} &= \frac{A}{x+7} + \frac{Bx + C}{x^2 + 9} \\ 
1 &= A(x^2 + 9) + (Bx + C)(x+7) \\ 
1 &= A(x^2 + 9) + (Bx + C)(x+7) \\ 
(0)x^2 + (0)x + 1 &= (A + B)x^2 + (7B + C)x + (9A + 7C) \\
&\text{3 equations, 3 unknowns} \\
&A = \frac{1}{58}, B = -\frac{1}{58}, C = \frac{7}{58}
\end{aligned}
$$
Finish the integral
$$
\begin{aligned}
\frac{1}{58} \int^2_{-2} \left( \frac{1}{x+7} + \frac{7 - x}{x^2 + 9} \right)dx &= \\
\frac{1}{58} \int^2_{-2} \left( \frac{1}{x+7} + \frac{7}{x^2 + 9} - \frac{x}{x^2 + 9}\right)dx &= \\
\frac{1}{58} \left( \int \frac{1}{x+7} dx + \int\frac{7}{x^2 + 9}dx - \int\frac{x}{x^2 + 9}dx \right)\bigg|^2_{-2}&= \\
\frac{1}{58} \left( \int \frac{du}{u} + \int\frac{7}{x^2 + 9}dx - \int\frac{x}{x^2 + 9}dx + C\right)\bigg|^2_{-2}&= \\
\frac{1}{58} \left( \ln(x+7) + \int\frac{7}{x^2 + 9}dx - \int\frac{x}{x^2 + 9}dx + C\right)\bigg|^2_{-2}&= \\
\frac{1}{58} \left( \ln(x+7) + \int\frac{7}{x^2 + 9}dx - \frac{1}{2}\int\frac{du}{u} + C\right)\bigg|^2_{-2}&= \\
\frac{1}{58} \left( \ln(x+7) + \int\frac{7}{x^2 + 9}dx - \frac{1}{2}\ln(x^2+9) + C\right)\bigg|^2_{-2}&= \\
\frac{1}{58} \left( \ln(x+7) + \frac{7}{9}\tan^{-1}\left( \frac{x}{3} \right) - \frac{1}{2}\ln(x^2+9) + C\right)\bigg|^2_{-2}&=\\
& \text{and so on}
\end{aligned}
$$
