---
date: 2026-01-22
aliases:
  - reduce
  - accumulate
---
In [[Functional Programming Language|Functional Programming]], a *fold* is a [[Higher-Order Function]] that processes a [[Data Structure]], typically an [[Array]], into a single cumulative result.

All folds have an accumulator (aka seed), which is the initial value that the operation starts with. We then go through the data structure performing some processing that effects the accumulator.

# Fold Trinity
```tikz
\begin{document}
\begin{tikzpicture}[>=latex, scale=0.5, transform shape,
    every node/.style={font=\sffamily\large},
    outer/.style={circle, draw, minimum size=2cm, align=center},
    center/.style={circle, draw, fill=gray!15, minimum size=2.5cm, align=center, font=\sffamily\Large\bfseries},
    is/.style={->, thick, >=stealth}
]
\node[center] (fold) at (0,0) {fold};
\node[outer] (map) at (90:4cm) {map};
\node[outer] (filter) at (210:4cm) {filter};
\node[outer] (reduce) at (330:4cm) {reduce};
\draw[is] (map) -- (fold);
\draw[is] (filter) -- (fold);
\draw[is] (reduce) -- (fold);
\end{tikzpicture}
\end{document}
```
There are 3 kinds of folds.
* map
	* Transform every element. The structure is preserved, only the values change
	* An empty list is the accumulator
	* e.g. apply a square function to a list of errors, as part of performing a regression
* filter
	* Keep only elements that satisfy a condition
	* The data structure is the accumulator
	* e.g. give only the even values of this list
* reduce
	* Collapse all elements into a single value using a binary operation
	* The first element as the accumulator
	* e.g. give the sum of a list