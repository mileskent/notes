---
date: 2025-10-15
---
A convolution is a kind of product that results in a blend/weighted overlap/smooth combination between two functions based on how much one function overlaps with a shifted and flipped version of another.
General Convolution
$$
(f * g)(t) = \int^{\infty}_{-\infty}f(t-s)g(s)\ ds
$$
Causal Convolution (used with [[Laplace Transform]]s)
$$
(f * g)(t) = \int^{t}_{0}f(t-s)g(s)\ ds
$$
![[Convolution_of_spiky_function_with_box2.gif]]

# Commutative Property
$$
f * g = g * f
$$
# Associative Property
$$
g*(h*x) = (g*h)*x
$$
# Distributive Over Addition
$$
h*x_{1}+h*x_{2}=h*(x_{1}+x_{2})
$$
