---
aliases:
  - Linear Map
  - Linear Mapping
date: 2026-01-11
---

A Linear transformation is a [[Transformation]]  where $T: \mathbb{R}^n \rightarrow \mathbb{R}^m, T(\vec{v}) = A \vec{v}$
* where $A \in R^{m \times n}$
* [[Domain]] of T is $\mathbb{R}^n$ (where we start)
* [[Codomain]] or **target** of T is $\mathbb{R}^m$
* The vector $T(\vec{x})$ is the **image** of $\vec{x}$ under T
* The set of all possible images is called the **range**
* image $\in$ range $\in$ codomain
* When the domain and codomain are both $\mathbb{R}$, you can represent them as a Cartesian Graph in $\mathbb{R}^2$, as in *a mapping of* $\mathbb{R} \rightarrow \mathbb{R}$
	* If y is the codomain and x is the domain, the range is the range, the domain is all the images of f(x)
* Addition Rule
	* T(u + v) = T(u) + T(v)
* Multiplication Rule
	* T(c$\vec{v}$) = cT(v)
*  Prove a transformation is linear by proving the addition and multiplication rules.
* "Principle of Superposition"
	* If we know $T(e_1)$, ...,  $T(e_n)$ then we know every T(v)


# 1-1
![[Injective]]
* 1-1 $\iff$ every column of T is a pivot column
* 1-1 iff standard matrix has pivot in every column
# Onto
![[Surjective]]
* TLDR: Onto $\iff$ every row of T is a pivot row
* onto iff the standard matrix has a pivot in every row
* The matrix A has columns which span $\mathbb{R}^m$.
* The matrix A has all pivotal rows.

# Bijective
![[Bijective]]
* Needs square matrix

# Matrix Multiplication is a Linear Transformation
$$
A = \begin{bmatrix}
1 & 1 \\
0 & 1 \\
1 & 1
\end{bmatrix}, \vec{u} = \begin{bmatrix}
3 \\
4
\end{bmatrix}, \vec{b} = \begin{bmatrix}
7 \\
5 \\
7
\end{bmatrix}
$$
$$
T: \mathbb{R}^2 \rightarrow \mathbb{R}^3
$$
Compute $T(\vec{u})$
$$
A \vec{u} = \begin{bmatrix}
1 & 1 \\
0 & 1 \\
1 & 1
\end{bmatrix}\begin{bmatrix}
3 \\
4
\end{bmatrix} = \begin{bmatrix}
7 \\
4 \\
7
\end{bmatrix}
$$
Calculate $\vec{v} \in \mathbb{R}^2$ so that $T(\vec{v}) = \vec{b}$
$$
A\vec{v} = \vec{b}
$$
$$
\begin{bmatrix}
1 & 1 & 7\\
0 & 1 & 5\\
1 & 1 & 7
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 2\\
0 & 1 & 5\\
1 & 1 & 7
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 2\\
0 & 1 & 5\\
0 & 1 & 5
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 2\\
0 & 1 & 5\\
0 & 0 & 0
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 2\\
0 & 1 & 5\\
\end{bmatrix}
$$
$$
\vec{v} = \begin{bmatrix}
2 \\
5
\end{bmatrix}
$$
Give a 
$\vec{c} \in \mathbb{R}^3 | \neg \exists \vec{v} | T(\vec{v}) = \vec{c}$
$\lor$
Give a $\vec{c}$ that is not in the range of $T$
$\lor$
Give a $\vec{c}$ that is not in the span of the columns of $A$
(Same question for all)

Range of $T$ is a bunch of images of the following form:
$$
A \vec{v} = \begin{bmatrix}
v_1 + v_2 \\
v_2 \\
v_1 + v_2
\end{bmatrix}
$$
For $\vec{c}$ to not be in the range of $T$, it cannot be in the above form, e.g. it can be
$$
\begin{bmatrix}
1 \\
2 \\
3
\end{bmatrix}
$$
