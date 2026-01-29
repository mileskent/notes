---
date: 2026-01-23
---
A [[Member Function]] of a Base [[Class]] that can be overidden in derived classes, implying [[Polymorphism#Dynamic Polymorphism]]. 
* Virtual designation indicates that we want to look inside the data a pointer owns to see what its type is before calling its function. If a member function is non-virtual and overriden in derived classes, calls to a child stored in the base class will execute the non-virtual base class function, not the child function. 
# Language Specific Details
* In [[C++]], member functions are non-virtual by default, and must be opted-in to through the `virtual` keyword
* In [[Java]], all non-static non-final member "methods" are virtual by default, you must opt-out through the `final` keyword