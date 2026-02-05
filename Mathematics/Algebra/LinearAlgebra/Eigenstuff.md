---
date: 2025-12-12
---
# Eigenvector
In [[Linear Algebra]], an [[#Eigenvector]] is a [[Coordinate Vector]] for which, applying the given [[Linear Transformation]] has the same effect as multiplying that vector by a scalar. In other words, vectors for which the [[Codomain|Output Space]] of the given linear transformation is proportional to the [[Domain|Input Space]].
* Let $A$ be a [[Square Matrix]] that represents a linear transformation. 
* Let $\vec{v}$ be some [[Coordinate Vector]] that we need to solve for.
* Let $\lambda$ be some [[Scalar]] that we need to solve for.
* By solving the following equation, we find eigenstuff
$$
A\vec{v} = \lambda\vec{v}
$$
* Eigenvalues are nonzero scalar values $\lambda$ that solve the equation
* Eigenvectors are coordinate vectors $\vec{v}$ that solve the equation
* Eigenspaces are the spaces that extend from the eigenvectors (the [[Span|spans]] of the eigenvectors)
* Each eigenvector has a corresponding eigenvalue, i.e. each eigenvector has a specific amount that the linear transformation scales it by
* The following GIF shows a linear transformation scaling 2D space. The red lines are the eigenspaces of the transformation. Any coordinate vector part of those spaces is an eigenvector.

![[eigenstuff.gif|300]]

# Eigenvalue
$\lambda$ is an **eigenvalue** for the transformation
* $A \vec{v} = \lambda \vec{v} \implies \det(A - \lambda I) = 0$
* Solve for $\lambda$ in $\det(A-\lambda I)=0$, which yields the [[Characteristic Equation]] for this system, e.g. in a 2D systems it is $\lambda^2 -\text{tr}A \cdot \lambda + \det A = 0$.
- $\lambda > 0 \implies A\vec{v}, \vec{v}$ point same direction
- $\lambda < 0 \implies A\vec{v}, \vec{v}$ point opposite direction
- $\lambda$ can be complex even if nothing else in the equation is
- ***Eigenvalues cannot be determined from the reduced version of a matrix*** ⭐
	- i.e. row reductions change the eigenvalues of a matrix
- The diagonal elements of a triangular matrix are its eigenvalues.
- A invertible iff 0 is not an eigenvalue of A.
- Stochastic matrices have an eigenvalue equal to 1.
- If $\vec{v}_1 , \vec{v}_2, . . . , \vec{v}_k$ are eigenvectors that correspond to distinct eigenvalues, then $\vec{v}_1 , \vec{v}_2, . . . , \vec{v}_k$ are linearly independent

### Defective
An eigenvalue is defective if and only if it ***does not*** have a complete [[Set]] of Linearly Independent eigenvectors.  
$\lambda = 0 \implies \text{ Defective}$
Due to $\mathrm{Im}\ \lambda$'s contribution, $\mathrm{Re}\ \lambda = 0 \not \implies\text{ Defective}$

### Neutral Eigenvalue
$$
\forall \lambda\ s.t. \mathrm{Re}\ \lambda = 0
$$

# Eigenspace
* the span of the eigenvectors that correspond to a particular eigenvalue
- $Nul(A-\lambda I)$