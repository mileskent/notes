---
date: 2026-02-01
---
The act of combining the application of multiple [[Mathematics/Set Theory/Function|Function]]s into one function.

```tikz
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd}[column sep=large, row sep=huge]
\textrm{People} 
	\arrow[r, "Age"] 
	\arrow[rd, "GreaterThan18\ \circ\ Age"'] 
	\arrow[loop left, "id"]
& \textrm{Integers}
	\arrow[d, "GreaterThan18"] \\
& \textrm{Booleans}
\end{tikzcd}
\end{document}
```
* Age is a function that maps People to Integers
* GreaterThan18 is a function that maps Integers to Booleans
* GreaterThan18 $\circ$ Age is the *Composition* of the above functions that maps People to Booleans
	* It is equivalent to applying Age, then applying GreaterThan18
	* It can be thought of as: GreaterThan18 follows Age
	* GreaterThan18 $\circ$ Age = Age(GreaterThan18(...))
* id is the [[Identity Morphism]], which is depicted above to map People to People
	* It exists for all sets, but is omitted for the others