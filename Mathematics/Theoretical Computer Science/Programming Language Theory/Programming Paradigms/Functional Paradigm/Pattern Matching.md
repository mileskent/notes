---
date: 2026-07-12
aliases:
  - Pattern Matching
---
The elimination form for [[Algebraic Data Type|Algebraic Data Types]]. Inspects which variant a sum type holds and destructures the fields of a product type in a single expression.

Exhaustiveness checking ensures every variant is handled at compile time, making illegal states unrepresentable and unhandled cases impossible.

In Rust: `match`. In Haskell: case expressions and function clause definitions. In C++17: `std::visit` over `std::variant`.

Distinct from regex pattern matching or string matching. This is structural pattern matching over the shape of data.
