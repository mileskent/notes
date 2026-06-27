---
date: 2026-06-24
aliases: [Wedge Product, Exterior Product]
---

The Outer Product $\vec{a} \wedge \vec{b}$ is the oriented parallelogram with sides $\vec{a}$ and $\vec{b}$. It is the fundamental operation of [[Exterior Algebra]].

Oriented means swapping the sides reverses the orientation:

$$\vec{b} \wedge \vec{a} = -(\vec{a} \wedge \vec{b})$$

From antisymmetry, $\vec{a} \wedge \vec{a} = 0$ (a degenerate parallelogram has no area). The result of the outer product of two vectors is a [[Bivector]] (grade 2).

# Axioms

- Distributivity: $\vec{a} \wedge (\vec{b} + \vec{c}) = (\vec{a} \wedge \vec{b}) + (\vec{a} \wedge \vec{c})$
- Scalar associativity: $\alpha(\vec{a} \wedge \vec{b}) = (\alpha\vec{a}) \wedge \vec{b} = \vec{a} \wedge (\alpha\vec{b})$
- Antisymmetry: $\vec{b} \wedge \vec{a} = -(\vec{a} \wedge \vec{b})$

# Calculation

Expand in the standard basis and apply the axioms. All $\vec{e}_i \wedge \vec{e}_i = 0$ terms drop, and $\vec{e}_j \wedge \vec{e}_i = -\vec{e}_i \wedge \vec{e}_j$ for $i \neq j$, so the result is a linear combination of basis bivectors $\vec{e}_i \wedge \vec{e}_j$ for $i < j$.

In $\mathbb{R}^2$ with $\vec{a} = a_1\vec{e}_1 + a_2\vec{e}_2$ and $\vec{b} = b_1\vec{e}_1 + b_2\vec{e}_2$:

$$\vec{a} \wedge \vec{b} = (a_1 b_2 - a_2 b_1)(\vec{e}_1 \wedge \vec{e}_2) = |\vec{a}||\vec{b}|\sin\theta\,(\vec{e}_1 \wedge \vec{e}_2)$$

Every bivector in $\mathbb{R}^2$ is a scalar multiple of $\vec{e}_1 \wedge \vec{e}_2$.

In $\mathbb{R}^3$ with $\vec{a} = a_1\vec{e}_1 + a_2\vec{e}_2 + a_3\vec{e}_3$ and $\vec{b} = b_1\vec{e}_1 + b_2\vec{e}_2 + b_3\vec{e}_3$:

$$\vec{a} \wedge \vec{b} = \begin{vmatrix} a_1 & a_2 \\ b_1 & b_2 \end{vmatrix}(\vec{e}_1 \wedge \vec{e}_2) + \begin{vmatrix} a_2 & a_3 \\ b_2 & b_3 \end{vmatrix}(\vec{e}_2 \wedge \vec{e}_3) + \begin{vmatrix} a_1 & a_3 \\ b_1 & b_3 \end{vmatrix}(\vec{e}_1 \wedge \vec{e}_3)$$

# In terms of the Geometric Product

$$\vec{a} \wedge \vec{b} = \frac{1}{2}(\vec{a}\vec{b} - \vec{b}\vec{a})$$
