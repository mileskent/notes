---
date: 2026-06-15
---
A linear unary operator maps a single input [[Computer Science/Computational Science/DigitalSignalProcessing/Signal|signal]] to a single output signal linearly. Let $H$ denote a linear unary operator applied to signal $X$, written $HX$.

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
