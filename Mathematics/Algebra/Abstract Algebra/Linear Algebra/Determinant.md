---
date: 2026-01-11
---

Imagine the area of parallelogram created by the basis of a standard vector space, like $\mathbb{R}^2$. Now apply a linear transformation $A$ to that vector space. The new area of the new parallelogram has been scaled by a factor of the determinant.
$S$ is the parallelopiped. 
$$
\text{area}(T(S)) = |\det(A)| \cdot \text{area}(S)
$$
You can also just think of it as the area of the parallelogram spanned by the columns of a matrix

$\mathbb{R}^3$: parallelopiped and volume

(assume n by n matrix because we only know how to find determinants for square matrices)

You can also get the area of S by using the determinant of the matrix created by the vectors that span S, i.e.
$|\vec{a} \times \vec{b}| = area(S) \implies |det([\vec{a}\ \ \vec{b}])| = area(S)$
because you are shifting the standard basis vectors into the vector space dictated by S
# Determinant Laws
- det(A) = 0 $\iff$ A is singular
	- det(A) $\not =$ 0 $\iff$ A is invertible
- det(Triangular) = product of diagonals
- det A = det $A^T$ 
- det(AB) = det A · det B
- $det(A^{-1}) = \frac{1}{det(A)}$
- $det(kA) = k^n det(A)$
# Determinant Post Row Operations
if A square:
* if adding rows to rows on A to get B then $det A = det B$
* if swapping rows in A to get B then $-det A = det B$
* if scaling one row of A by k, then $k \cdot det(A)$ = $det(B)$
Exactly the same for columns