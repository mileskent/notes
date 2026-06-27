---
date: 2025-12-12
---
A functor is a [[Morphism]] between [[Category|Categories]]

If you have Category $A$ and Category $B$, a functor 
* Maps every [[Mathematical Object|Object]] in $A$ to an object in $B$
	* $O \in A \implies F(O) \in B$
* Maps every [[Morphism]] in $A$ to a morphism in $B$
	* $f:O_{1}\rightarrow O_{2} \implies F(f):F(O_{1}) \rightarrow F(O_{2})$
* Preserves [[Mathematical Structure|Structure]]
	* Preserving Identity: $F(\text{id}_{O}) =\text{id}_{F(O)}$
	* Preserving Composition: $F(g\ \circ\ f) = F(g)\ \circ\ F(f)$
	