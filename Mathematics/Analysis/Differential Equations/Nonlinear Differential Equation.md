---
date: 2025-10-15
---
A [[Differential Equation]] is nonlinear if terms don't appear only as
$$
f(t) \cdot y^{(n)}(t)
$$
Note that $y^{(n)}(t)$ is the $n^\text{th}$ derivative of $y(t)$ in Lagrange notation.

| Linear                        | Nonlinear           |
| ----------------------------- | ------------------- |
| $y'+2y=0$                     | $y'+y^2 = 0$        |
| $y'+2y=t^2$                   | $y'+y^2 = t^2$      |
| $y'+t^3y=0$                   | $y'+ty^3 = 0$       |
| $t^2 y''' - \cos(t)y''+y = 0$ | $y''+3yy'=7\cos(t)$ |

# First Order
$$
\frac{dy}{dt} = f(t,y)
$$
**Solution Method**
No guaranteed general solution method. However, [[Separable Differential Equation#Separation of Variables]] is sometimes possible.
**General Solution**
Will have a free parameter $C$