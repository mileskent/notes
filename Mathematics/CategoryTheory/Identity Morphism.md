---
date: 2025-12-12
---
The morphism mapping [[Mathematical Object|Object]] a [[Category]] to itself
* Every object has a identity morphism

Consider the identity of category $X$
$$
\begin{gathered}
\text{id}_{X}: X \rightarrow X\\
f\ \circ\ \text{id}_{X} = f = \text{id}_{X} \circ\ f
\end{gathered}
$$
* Depending on the context, the subscript may not be neccessary

# Identity Composition
Composing with the identity has no effect.

```tikz
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd}[column sep=large, row sep=huge]
\textrm{X} 
	\arrow[r, "id"] 
	\arrow[rr, bend right, "M\ \circ\ id\ =\ M"'] 
& \textrm{X}
	\arrow[r, "M"] 
& \textrm{X'}
\end{tikzcd}
\end{document}
```
