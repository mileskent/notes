---
date: 2026-06-16
aliases:
---
The *Delay Operator* $\mathcal{R}$ is a [[Linear Unary Operator]] that maps a [[Discrete-Time Signal]] to a copy delayed by one sample:

$$
\mathcal{R}\{x[n]\} = x[n-1]
$$

It is equivalent to multiplication by $z^{-1}$ in the [[Z Transform]] domain, so $\mathcal{R} \leftrightarrow z^{-1}$.

# Operator Algebra

First of all, see [[Linear Unary Operator#Operator Notation]] first. 

Systems expressible as [[Discrete-Time Linear Time-Invariant System|difference equations]] can be written as polynomials in $\mathcal{R}$ and manipulated algebraically. The difference machine $y[n] = x[n] - x[n-1]$ becomes:

$$
Y = (1 - \mathcal{R})X
$$

Cascading two such systems multiplies their polynomials:

$$
Y_2 = (1-\mathcal{R})(1-\mathcal{R})X = (1 - 2\mathcal{R} + \mathcal{R}^2)X
$$

which corresponds to $y_2[n] = x[n] - 2x[n-1] + x[n-2]$.

$\mathcal{R}$ distributes over addition. It does not commute with arbitrary operators in general.


# Operator Reciprocals

![[Linear Unary Operator#Operator Reciprocals]]
