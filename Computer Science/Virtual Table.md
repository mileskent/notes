---
date: 2026-01-23
aliases:
  - vtable
  - Virtual Method Table
  - Virtual Table
---
In statically-typed, [[Object Oriented|Object Oriented Language]]s (e.g. [[C++]], [[Java]]), a vtable is a lookup table 
* Created by the [[Compiler]] to support [[Dynamic Dispatch]].
* Used at [[Runtime]], when a virtual member function is called, the [[Process]] follows the [[#vptr]] to the vtable, and then calls the function through the function pointer associated with that class.
* That is a static [[Array]] of [[Function Pointer]]s created for every [[Class]] that contains [[Virtual Function]]s, i.e. that uses [[Polymorphism#Dynamic Polymorphism]], where if a derived class overrides a base class implementation, then the base class function pointer is replaced with the derived class function pointer.
# vptr
Every instance of a class contains a [[Pointer]] to the vtable.

