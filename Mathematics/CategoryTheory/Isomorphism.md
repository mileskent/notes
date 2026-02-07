---
date: 2025-12-12
---
# Formal Definition
An *Isomorphism* is a kind of [[Morphism]] between objects in a [[Category]] that is *Invertible*.

Let $f_{AB}$ be a [[Morphism]] and $A,B$ be objects
$$
\begin{gathered}
\exists\ f_{AB} : A \rightarrow B,\ f_{AB}^{-1} : B \rightarrow A\\
f_{AB}^{-1}\ \circ f_{AB} = \text{id}_{A} \land f_{AB}\ \circ f_{AB}^{-1} = \text{id}_{B}\\
\iff\\
A \cong B
\end{gathered}
$$
# Isomorphism Facts
* Isomorphisms are unique
* If there exists an isomorphism between objects, then those objects are *isomorphic* with each other
* If $A$ and $B$ are isomorphic, then $A \cong B$
* When objects are isomorphic, we can say that they have the same internal structure, without having to actually look inside the objects
* For example, as [[Vector Space]]s: $\mathbb{C} \cong \mathbb{R}^2$ (not as [[Algebraic Field]]s though)

# Isomorphism of Categories
Categories contain Objects, and Objects can be anything, including Categories! 
* [[Functor|Functors]] connect Categories
* Morphisms connect Objects
* Our Objects *are* Categories
* Thus, our morphisms are functors
The Objects of a Categories being Categories themselves, is just a special case of Category. Therefore, the same general [[#Formal Definition]] applies. However, it can also be reexpressed in terms of functors, where $\mathcal{A},\ \mathcal{B}$ are categories, and $F_{\mathcal{AB}}$ is a functor.
$$
\begin{gathered}
\exists\ F_{\mathcal{AB}}: \mathcal{A} \rightarrow \mathcal{B}
,\ 
\ F_{\mathcal{AB}}^{-1}: \mathcal{B} \rightarrow \mathcal{A}\\
F_{\mathcal{AB}}^{-1}\ \circ\ F_{\mathcal{AB}} = \text{id}_{\mathcal{A}}\\
F_{\mathcal{AB}}\ \circ\ F_{\mathcal{AB}}^{-1} = \text{id}_{\mathcal{B}}\\
\iff\\
\mathcal{A} \cong \mathcal{B}
\end{gathered}
$$

# Size Intuition
* When there is a notion of size, this invertibility can be thought of as a [[Transformation#Bijective]] [[Morphism]] between a pair of [[Mathematical Object|Objects]]; a relationship where one object can be converted and restored to and from another object. 
* A [[Bijective]] [[Homomorphism]].

Consider the [[Morphism|Arrows]] to and from category $A$ to $B$, that are [[Bijective]] because $A$ and $B$ have the size
$$
\begin{gathered}
f_{AB}: A \rightarrow B\\
f_{BA}: B \rightarrow A\\
f_{AB}^{-1} = f_{BA}\\
f_{AB}^{-1}\ \circ f_{AB} = \text{id}_{A}\\
f_{AB}\ \circ f_{AB}^{-1} = \text{id}_{B}
\end{gathered}
$$
```tikz
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd}[column sep=large, row sep=huge]
\textrm{A} 
	\arrow[r, bend left, "f_{AB}"] 
	\arrow[loop left, "id_A"] 
& \textrm{B}
	\arrow[l, bend left, "f_{AB}^{-1}"] 
	\arrow[loop right, "id_B"] 
\end{tikzcd}
\end{document}
```

