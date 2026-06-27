---
date: 2024-12-08
---
A [[Vector Space]]'s version of a [[Subset]], with some constraints.

While, a subspace does inherit the [[Vector Space#Axioms|axioms of a Vector Space]]. Verifying a subset is a subspace is simpler; A [[Subset]] $H$ of $\mathbb{R}^n$ is a subspace if it is [[Closure|closed]] within scalar multiplication and vector addition:
$$
\begin{gathered}
\text{For}\ c \in \mathbb{R},\ \vec{u}, \vec{v} \in H\\
H \text{ is a subspace}\\
\iff\\
c \vec{u} \in H\quad \land\quad
\vec{u} + \vec{v} \in H\quad \land\quad
\vec{0} \in H
\end{gathered}
$$

> [!note] Properties
> * $\text{span}\ H = H$, i.e. the [[Span]] of any subset is identical to itself

# Four Fundamental Subspaces
For [[Matrix]] $A \in \mathbb{R}^{m \times n},\ r =\text{rank}\ A$
![[Pasted image 20251229130812.png|400]]
* The [[Subspace]]s are linked by the [[Fundamental Theorem of Linear Algebra]]
	* [[Rowspace]]
	* [[Nullspace]] of $A$
	* [[Columnspace]]
	* [[Nullspace]] of $A^T$, "Left Nullspace"
* Shows the relationship between the dimensions of the subspaces
	* $\dim\text{Col } A = r$
	* $\dim\text{Row } A = r$
	* $\dim\text{Nul } A = n-r$
	* $\dim\text{Nul } A^T = m-r$
* Shows the [[Morphism]]s between different subspaces of a matrix
	* Show existence of solutions: 
		* $T(x): \mathbb{R}^n \rightarrow \mathbb{R}^m \equiv Ax$
		* $\exists x \in \mathbb{R}^n,\ Ax = b \iff b \in\text{Col } A$
* Shows the [[Orthogonal|Orthogonality]] relationship between related subspaces of a matrix
	* $(\text{Row}\ A)^{\perp} = \text{Nul}\ A$
	* $(\text{Col}\ A)^{\perp} = \text{Nul} (A^T)$