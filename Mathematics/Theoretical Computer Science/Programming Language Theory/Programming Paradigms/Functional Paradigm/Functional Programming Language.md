---
date: 2025-01-07
aliases:
  - Functional Paradigm
  - Functional Programming Language
  - FP
  - FPL
---
The applied intersection of [[Programming Language Theory]], [[Category Theory]], and [[Logic]] to Computation. Designing a [[Program]] around [[Pure Function|pure functions]] and immutable data. Essentially, the mathematical way of programming, where functions behave like they do in math, and data consists of mathematical objects that have a single identity, not a changing one. Instead of changing the state of [[Object Oriented Programming Language|objects]], data is transformed by being passed through a composition of functions.

# Algebraic Pillars

The function paradigm consists of two pillars of algebraic computation.
- Structural Algebra
	- Describes the shape of algebraic types
		- Algebraic Type + Shape = [[Algebraic Data Type]]
			- [[Algebraic Data Type|Sum Type]]
				- Traffic light signal. Red or Yellow or Green.
			- [[Algebraic Data Type|Product Type]]
				- Coordinate. x and y and z.
- Operational Algebra
	- Describes the behavior of algebraic types
		* An algebraic type that has a particular behavior (e.g. operations and laws) is an [[Algebraic Structure]]
			- [[Monoid]]
				- Booleans under [[AND]]
			- [[Functor]]
				- Doubling every value in a [[Tree]]
			- [[Monad]]
				- [[Monadic Chaining]]