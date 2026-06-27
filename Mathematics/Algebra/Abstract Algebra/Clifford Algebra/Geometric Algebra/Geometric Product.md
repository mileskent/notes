---
date: 2026-06-24
---

The Geometric Product is the fundamental operation of [[Geometric Algebra]]. It is a [[Bilinear Map|Bilinear Product]]. We define [[Multivector|Multivectors]] as [[Vector|Vectors]] closed by this product, which make them an [[Algebra over a Field]].

The Geometric Product is the sum of the [[Inner Product]] and the [[Outer Product]]:

$$\vec{a}\vec{b} = \vec{a} \cdot \vec{b} + \vec{a} \wedge \vec{b}$$

# Calculation

The basis vectors $\vec{e}_i$ satisfy:

$$\vec{e}_i^2 = 1 \qquad \vec{e}_i \vec{e}_j = -\vec{e}_j \vec{e}_i \quad (i \neq j)$$

To compute $\vec{a}\vec{b}$, expand in the basis and distribute. For example in $\mathbb{G}^2$ with $\vec{a} = a_1 \vec{e}_1 + a_2 \vec{e}_2$ and $\vec{b} = b_1 \vec{e}_1 + b_2 \vec{e}_2$:

$$\begin{align}
\vec{a}\vec{b} &= a_1 b_1 \vec{e}_1^2 + a_1 b_2 \vec{e}_1 \vec{e}_2 + a_2 b_1 \vec{e}_2 \vec{e}_1 + a_2 b_2 \vec{e}_2^2 \\
&= (a_1 b_1 + a_2 b_2) + (a_1 b_2 - a_2 b_1) \vec{e}_1 \vec{e}_2 \\
&= \vec{a} \cdot \vec{b} + (a_1 b_2 - a_2 b_1) \vec{e}_{12}
\end{align}$$

where $\vec{e}_{12} = \vec{e}_1 \vec{e}_2$ is a bivector
