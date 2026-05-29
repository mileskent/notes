---
date: 2026-05-28
---
A *Complex Matrix* is a [[Matrix]] for which all entries are [[Complex Number|Complex Numbers]]

$$
\begin{align}
Z \in \mathbb{C}^{m \times n}\\
\end{align}
$$

# Unique Operations
In addition to all of the operations a regular matrix has, such as multiplication, addition, and so forth, the complex nature of the entries of complex matrices impart additional possibilities.

## Conjugate
$$
Z = (z_{i,j}) \implies  \bar{Z} = (\bar{z}_{i,j})
$$
## Hermitian
Pretty much everywhere (formulae) that [[Matrix#Transpose]] is used for real matrices, the Hermitian is used for complex matrices.
$$
Z^H = (\bar{Z})^T
$$
### Hermitian Properties
* $(A^H)^H = A$
* $(A+B)^H = A^H + B^H$
* $(cA)^H = \bar{c} A^H$
* $(AB)^H = B^H A^H$


### Hermetian Inner Product
$$
\vec{y}^H \vec{x}
$$

The length squared of a complex vector is
$$
\vec{z}^H \vec{z}
$$

### Hermetian Symmetric Matrix
$$
Z \text{ is a } S \iff Z^H = Z
$$
### Hermetian Orthogonal Matrix
Hermetian + [[Orthogonal Matrix|Orthogonal]] = Unitary

$$
\begin{align}
Z \text{ is a } Q 
&\iff 
q_{i}^H q_{j} =
\begin{cases}
0 & i \neq j \\
1 & i = j 
\end{cases}\\
&\iff
Z^H Z = I
\end{align}
$$
