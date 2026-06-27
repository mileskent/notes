---
date: 2024-12-08
---

Perpendicular. 
* $\vec{a}$ and $\vec{b}$ are orthogonal if $\vec{a} \cdot \vec{b} = 0$
- $||\vec{u} + \vec{w}||^2 = ||\vec{u}||^2 + ||\vec{w}||^2 \lor \vec{u} \cdot \vec{w} = 0 \implies \text{Orthogonal}$
- If $W$ is a subspace of $\mathbb{R}^n$ and $\vec{z} \in \mathbb{R}^n$, $\vec{z}$ is orthogonal to $W$ if it is orthogonal to every vector in $W$
- The set of all vectors orthogonal to a subspace is a itself a subspace, called the [[Orthogonal Complement]] of $W$, $W^{\perp}$, W perp
	- $W^{\perp} = \{\vec{z} \in \mathbb{R}^n \mid \forall (\vec{w} \in W)\ \vec{z} \cdot \vec{w} = 0\}$
- $dim(Row\ A) = dim(Col\ A)$
- $(Row\ A)^{\perp} = Nul\ A$
- $(Col\ A)^{\perp} = Nul (A^T)$

$\vec{x} \in Nul(A) \iff$
- $A\vec{x} = \vec{0}$
- $\vec{x}$ is orthogonal to each row of $A$
- $Row\ A$ is orthogonal complement to $Nul\ A$
- $dim(Row\ A) + dim(Nul\ A) =$ number of columns

$\vec{a} \cdot \vec{b} = 0 \land \vec{a} \not = \vec{0}, \vec{b} \not = 0 \iff \vec{a} \perp \vec{b} \iff a \text{ and } b \text{ are Orthogonal}$