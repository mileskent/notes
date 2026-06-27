---
date: 2024-12-08
---

A [[Set]] of [[Vector]]s are an **orthogonal set** of vectors if every pair in the set is [[Orthogonal]] to every other vector in the set.

# Linear Independence for Orthogonal Sets
If there is an orthogonal set of vectors $O$, then
$$
||c_1 \cdot \vec{u}_1 + \cdots  + c_n \cdot \vec{u}_n||^2 = c_1^2 \cdot ||\vec{u}_1||^2 + \cdots + c_n^2 \cdot ||\vec{u}_n||^2
$$
$\vec{0} \not \in O \implies O$ is [[Linear Independence|Linearly Indepedent]]

# Expansion in Orthogonal Basis
If $O$ is the [[Basis]] for [[Subspace]] $W$ in $\mathbb{R}^n$ and $O$ is an orthogonal basis,
then for any vector $\vec{w} \in W$
$$
\vec{w} = c_1 \vec{u}_1 + \cdots + c_n \vec{u}_n
$$
$$
c_i=\frac{\vec{w} \cdot \vec{u}_i}{\vec{u}_i \cdot \vec{u}_i}
$$
