---
aliases:
  - Template Metaprogramming
  - TMP
---
*Template Metaprogramming* (TMP) is a technique in [[C++]] where templates are used to perform computation at [[Compile-Time]]. The compiler acts as an interpreter: template instantiation is Turing-complete, so any computable function can (in principle) be evaluated before the program runs.

The core idea is that types and constant expressions are the "values" of a compile-time language, and template specialization is its "branching."

# Topic List
- [[Type Trait|Type Traits]]
- [[Substitution Failure Is Not An Error]]
- [[constexpr#constexpr Functions]]
- [[Concept|Concepts]]
- [[Variadic Template Parameter Pack]]
- [[Curiously Recurring Template Pattern]]

# Type Traits
![[Type Trait]]

# SFINAE
![[Substitution Failure Is Not An Error]]

# constexpr Functions
![[constexpr#constexpr Functions]]

![[constexpr#if constexpr]]

# Concepts
![[Concept]]

# Variadic Template Parameter Pack
![[Variadic Template Parameter Pack]]

# Curiously Recurring Template Pattern
![[Curiously Recurring Template Pattern]]
