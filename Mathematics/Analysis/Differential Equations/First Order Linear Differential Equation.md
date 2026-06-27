---
date: 2025-10-15
---
A [[Linear Differential Equation]] of [[Differential Equation#Order|Order]] 1. We are assuming it to be a [[Ordinary Differential Equation]].

$$
\frac{dy}{dt} + a(t)\ y = b(t)
$$
# Techniques
## Integrating Factor
If and only if
The given equation is a [[First Order Linear Differential Equation]]
and the coefficient of the first order derivative is 1, i.e. in the given form

$$
\frac{dy}{dt} + a(t)\ y = b(t)
$$

Then it is possible to simplify the process of solving the equation by multiplying both sides of the equation by some function $M(t)$

$$
M(t)\frac{dy}{dt} + M(t)a(t)\ y = M(t)b(t)
$$

Then let $M'(t) = M(t)a(t)$, and you now have a product rule that when integrated and after some algebra gives an explicit solution for $y$ so long as you can solve for whatever $M(t)$ needs to be.

### Example
$$
y' - \frac{3}{4}y = 6\exp\left( -\frac{5}{4} t\right)
$$
$$
M(t)y' - M(t)\frac{3}{4}y = M(t)6\exp\left( -\frac{5}{4} t\right)
$$
$$
\text{Let } M'(t) = \left( -M(t) \frac{3}{4} \right) \quad \implies \quad
(M(t)y)' = M(t)y' - M'(t)y = M(t)6\exp\left( -\frac{5}{4} t\right)
$$
$$
M(t)y = \int M(t)6\exp\left( -\frac{5}{4} t\right)\ dt
$$
$$
\frac{M'}{M} = - \frac{3}{4}
$$
$$
\int \frac{M'}{M}\ dt = - \int \frac{3}{4}\ dt
$$
$$
\int \frac{dM}{M} = - \int \frac{3}{4}\ dt
$$
$$
\ln(M) = - \frac{3}{4} t + C
$$
$$
M(t) = \exp\left(- \frac{3}{4} t + C \right)
$$
$$
\boxed{M(t) = D\exp\left(- \frac{3}{4} t\right)}
$$
$$
 \left(D\exp\left(- \frac{3}{4} t\right)\right)y = \int \left(D\exp\left(- \frac{3}{4} t\right)\right)6\exp\left( -\frac{5}{4} t\right)\ dt
$$
$$
\exp\left(- \frac{3}{4} t\right)y = 6 \int \exp\left(-2 t\right)\ dt
$$
$$
\exp\left(- \frac{3}{4} t\right)y = -3 \exp\left(-2 t\right) + K
$$
$$
\exp\left(- \frac{3}{4} t\right)y = -3 \exp\left(-2 t\right) + K
$$
$$
\boxed{y(t) = -3 \exp\left(-\frac{5}{4} t\right) + K\exp\left(\frac{3}{4} t\right)}
$$
