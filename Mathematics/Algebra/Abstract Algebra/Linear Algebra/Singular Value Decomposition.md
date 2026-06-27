---
date: 2024-12-08
---
https://www.youtube.com/watch?v=vSczTbgc8Rc
# Applications
- If A is a invertible square matrix then the **condition number** is the largest singular value divided by the smallest singular value
	- Condition number describes the sensitivity of a solution to Ax = b to errors in A
	- A problem with a low condition number is said to be well-conditioned, while a problem with a high condition number is said to be ill-conditioned
	- Describe difficulty in computing inverse
	- Chaos: small change in input results in massive change in output
- Can use SVD to talk about rkA, ColA, RowA, NulA, $(Col\ A)^\perp$, etc.
	- rkA = rk$\Sigma$ 
		- 
	- ColA = U columns through dim A
		- bc $A\vec{v} \propto \vec{u}$
	- Col A perp = U columns after dim A
		- by def
	- Nul A = V columns that correspond to the free columns of U
# Process
$A = U\Sigma V^T$
$U$ and $V$ are square, guaranteed.
1. Singular values: $\sqrt{\text{eigenvalues of } A^T A}$
2. Construct $\Sigma$ using the singular values. $\Sigma$ has the same shape as $A$, with a diagonal matrix of the singular values in the top left corner
3. V = matrix of eigenvectors of $A^T A$
4. Compute an orthonormal basis for Col A: use $A\vec{v_i} = \sigma_i \vec{u_i}$ for dim $V$
5. Afterwhich, extend and fill up the remaining orthonormal basis
	1. Option A: Rawdog it$-$think about it, so to speak
	2. Option B: [[Gram-Schmidt Process]]
	3. Option C: Use $Nul\ AA^T$
6. Construct the columns of $U$ with the $\vec{u_i}$ vectors
7. Note: for U you can also get it via the V process but with $AA^T$, for eigenvalue 0, find eigenvector
8. V and U are orthogonal btw, and they have dimensions of $A^T A$ and $AA^T$

$$
A = \sum^{r}_{s=1} \sigma_s \vec{u}_s \vec{v}^T_s
$$
where $\vec{u}_s$, $\vec{v}_s$ are the $s^{\text{th}}$ columns of $U$ and $V$