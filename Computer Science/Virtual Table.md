---
date: 2026-01-23
aliases:
  - vtable
  - Virtual Method Table
---
In statically-typed, [[Object Oriented|Object Oriented Language]]s (e.g. [[C++]], [[Java]]), a vtable is a lookup table used by the [[Compiler]] to support [[Dynamic Dispatch]].
* A vtable is static [[Array]] of [[Function Pointer]]s created for every [[Class]] that contains [[Virtual Function]]s, i.e. that uses [[Polymorphism#Dynamic Polymorphism]], where if a derived class overrides a base class implementation, then the base class function pointer is replaced with the derived class function pointer

#todo Clarify specifics