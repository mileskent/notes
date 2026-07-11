---
date: 2026-02-07
---
# Formal Definition
Adjunction is a relationship only between [[Functor|Functors]]. Only functors can be *Adjoint* to each other.

* Let $\mathcal{A}$ and $\mathcal{B}$ be [[Category|Categories]]
* Let $L$ and $R$ be Functors.
	* Left Adjoint (Functor)
		* $L: \mathcal{A} \rightarrow \mathcal{B}$
	* Right Adjoint (Functor)
		* $R: \mathcal{B} \rightarrow \mathcal{A}$
* Let $A \in\text{obj}(\mathcal{A})$
* Let $B \in\text{obj}(\mathcal{B})$
$$
\text{hom}_{\mathcal{B}}(L(A), B)=
\text{hom}_{\mathcal{A}}(A, R(B))
$$
