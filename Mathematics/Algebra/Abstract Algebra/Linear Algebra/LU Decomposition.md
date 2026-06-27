---
date: 2026-01-11
---

If A is an $m \times n$ [[Matrix]] that can be [[Row Reduction|row reduced]] to [[Echelon Form]]
without row exchanges, then
$$
A = LU
$$
* where $L \in \mathbb{R}^{m \times m}$ is a composition of [[Elementary Matrix|elementary matrices]] such that it is a [[Lower Triangular Matrix]] where all of its diagonal entries are 1
* $U$ is an [[Echelon Form]] of $A$

# The Process
Suppose A can be row reduced to echelon form U without interchanging rows, i.e. 
$$
\begin{align}
E_p\ ... E_0 A &= U\\
A &= (E_p\ ... E_0)^{-1}U
A &= LU
\end{align}
$$

You can construct $L$ by finding each $E$ and multiplying them all together. Alternatively you can construct $L$ such that the sequence of row operations that convert $A$ to $U$ would convert $L$ to $I$
