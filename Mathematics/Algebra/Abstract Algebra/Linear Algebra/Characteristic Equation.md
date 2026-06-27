---
date: 2026-01-11
---

$det(A-\lambda I) = 0$ to get values for $\lambda$. Recall $det(T)=0$ means noninvertible. If a matrix isn't invertible, then we won't get trivial solutions when solving. Also the idea of reducing the dimension through the transformation is relevant; squishing the basis vectors all onto the same span where the area/volume is 0. Recall eigenvectors remain on the same span despite a linear transformation.

$\lambda$ is an eigenvalue of A $\iff$ $(A-\lambda I)$ is singular

trace of a Matrix $tr(M)$ is the sum of diagonal

# Characteristic Polynomial
$det(A-\lambda I)$
n degree polynomial -> n roots -> maximum n eigenvalues (could be repeated)
![[Pasted image 20241007112930.png|400]]

## Algebraic Multiplicity
Algebraic multiplicity of an eigenvalue is how many times an eigenvalue repeatedly occurs as the root of the characteristic polynomial.

## Geometric Multiplicity
- Geometric multiplicity of an eigenvalue is the number of eigenvectors associated with an eigenvalue; $dim(Nul(A-\lambda I))$, which is saying how many eigenvector solutions does this eigenvalue have (recall $dim(B)$ is number of free vars in $B$)