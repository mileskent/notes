---
date: 2026-07-13
aliases:
  - Monad Implementation
---
A [[Monad]] is implemented as a type constructor "M" with two operations:
* fn unit : a → M(a)
	* Wraps a plain value into the monadic context
* fn bind : M(a) → (a → M(b)) → M(b)
	* Unwraps the value, applies a function that produces a new wrapped result
	* This is what enables [[Monadic Chaining]]