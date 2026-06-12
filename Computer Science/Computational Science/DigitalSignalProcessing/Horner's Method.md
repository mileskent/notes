---
date: 2026-06-09
---
*Horner's method* is an efficient [[Computer Science/Data Structures/Algorithm|algorithm]] for evaluating a [[Polynomial]] by factoring out $x$ repeatedly, eliminating the need to compute powers of $x$ directly.

For example, a cubic polynomial:

$$
p(x) = a_3 x^3 + a_2 x^2 + a_1 x + a_0
$$

is evaluated as:

$$
p(x) = ((a_3 \cdot x + a_2) \cdot x + a_1) \cdot x + a_0
$$
