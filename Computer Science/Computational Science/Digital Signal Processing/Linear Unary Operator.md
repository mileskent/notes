---
date: 2026-06-15
---
A linear unary operator maps a single input [[Computer Science/Computational Science/Digital Signal Processing/Signal|signal]] to a single output signal linearly. Let $H$ denote a linear unary operator applied to signal $X$, written $HX$.

# Operator Notation
All *Linear Unary Operators* can be expressed and manipulated algebraically.

## Operator Expressions are Operators
A polynomial expression built from operators is itself a new operator. For example, $X - HX$ can be factored as $(1 - H)X$, which is equivalent to $GX$ where $G = (1 - H)$. The expression $G$ is a new operator that can be applied to any signal, composed with other operators, and manipulated algebraically like any other linear unary operator.

## Composition
[[Cascaded System|Cascading]] two linear unary operators multiplies their expressions:
$$Y = H_2(H_1 X) = H_2 H_1 X$$

## Distributive Property
Multiplication distributes over addition:
$$H(X_1 + X_2) = HX_1 + HX_2$$

## Polynomial Expansion
Composed operators expand like polynomials.
$$(1 - H)^2 X = (1 - 2H + H^2)X$$

# Operator Reciprocals

Two operators are reciprocals if their product is the identity operator. The reciprocal of $(1 - H)$ is the geometric series:

$$
\frac{1}{1 - H} = \sum_{k=0}^{\infty} H^k
$$

Verified by synthetic division:

$$
(1 - H)(1 + H + H^2 + \cdots) = 1
$$

More generally, the reciprocal of $(1 - pH)$ for scalar $p$ is:

$$
\frac{1}{1 - pH} = \sum_{k=0}^{\infty} p^k H^k
$$

This shows that an implicit system $(1 - pH)Y = X$ is equivalent to an infinite explicit sum $Y = \sum_{k=0}^{\infty} p^k H^k X$.

# Explicit and Implicit Forms

A system can be represented in two forms depending on whether the output is directly computed from the input or only constrained by it.

## Explicit Form

An explicit operator expression is a **recipe**; it directly specifies how to compute the output from the input. It is imperative: it tells you what to do.

$$
Y = (1 - H)X
$$

This corresponds to a [[Feed-Forward]] structure. The output is a function purely of current and past inputs.

## Implicit Form

An implicit operator expression is a **constraint**; it states a rule the input and output must satisfy, without directly giving a formula for the output. It is declarative: it tells you what must be true.

$$
(1 - H)Y = X
$$

This is the same algebraic content rearranged so that $Y$ appears on both sides. Solving for $Y$ requires inverting the operator, which produces a [[Feedback]] structure.

The accumulator $y[n] = x[n] + y[n-1]$ is the canonical implicit system:

$$
Y = HY + X \implies (1 - H)Y = X
$$

The output depends on its own past value, so there is no closed-form recipe that avoids self-reference.
