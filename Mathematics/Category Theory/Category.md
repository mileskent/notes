---
date: 2025-12-12
---
# Category
A *Category* consists of a collection of 
* [[Mathematical Object|Objects]]
* [[Morphism|Morphisms]]

where there is a definition for
* [[Mathematics/Category Theory/Composition|Composition]]
* [[Identity Morphism]]
```tikz
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd}[column sep=large, row sep=huge]
\textrm{A} 
	\arrow[r, "M_{ab}"] 
	\arrow[rd, "M_{bc}\ \circ\ M_{ab}"'] 
	\arrow[loop left, "id"]
& \textrm{B}
	\arrow[d, "M_{bc}"] \\
& \textrm{C}
\end{tikzcd}
\end{document}
```
* $M_{ab}$ is a [[Morphism]] from $A$ to $B$
* $M_{bc}$ is a [[Morphism]] from $B$ to $C$
* $M_{bc}$ $\circ$ $M_{ab}$ is the *Composition* of the above morphisms that maps $A$ to $C$
	* It is equivalent to applying $M_{ab}$, then applying $M_{bc}$
	* It can be thought of as: $M_{bc}$ follows $M_{ab}$
	* [[Mathematics/Category Theory/Composition|Composition]] is [[Associativity|Associative]] $\rightarrow(f\circ g) \circ h = f\circ (g \circ h)$
* id is the [[Identity Morphism]], which is depicted above to map $A$ to $A$
	* It exists for all [[Mathematical Object|Objects]], but is intentionally omitted for $B$ and $C$
* Think of a Category as a generalized version of *Elements*, *[[Mathematics/Set Theory/Function|Functions]]*, and Operations in [[Set Theory]].

# Examples of Categories
## The Category of Proofs
* Objects: [[Proposition|Propositions]]
* Arrows: [[Proof|Proofs]]
## Set Categories
* Objects: [[Set|Sets]]
* Arrows: [[Mathematics/Set Theory/Function|Functions]]
## [[Functional Programming Language|Functional Programming]] Type Categories
* Objects: [[Data Type]]
* Arrows: [[Computer Science/Function|Function]]
## Vector Space Categories
- Objects: [[Vector Space|Vector Spaces]]
- Arrows: [[Linear Transformation]]
