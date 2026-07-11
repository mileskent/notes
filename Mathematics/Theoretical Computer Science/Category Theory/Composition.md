---
date: 2026-02-01
---

```tikz
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd}[column sep=large, row sep=huge]
\textrm{A} 
	\arrow[r, "M_{ab}"] 
	\arrow[rd, "M_{bc}\ \circ\ M_{ab}"'] 
& \textrm{B}
	\arrow[d, "M_{bc}"] \\
& \textrm{C}
\end{tikzcd}
\end{document}
```
* $M_{ab}$ is a [[Morphism]] from $A$ to $B$
* $M_{bc}$ is a [[Morphism]] from $B$ to $C$
* $M_{bc}$ $\circ$ $M_{ab}$ is the *Composition* of the above functions that maps $A$ to $C$
	* It is equivalent to applying $M_{ab}$, then applying $M_{bc}$
	* It can be thought of as: $M_{bc}$ follows $M_{ab}$
	* [[Mathematics/Theoretical Computer Science/Category Theory/Composition|Composition]] is [[Associativity|Associative]] $\rightarrow(f\circ g) \circ h = f\circ (g \circ h)$
