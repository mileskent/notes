* For a "syntactically valid" program, what is the behavior?
* How do we mathematically formalize the semantics of a program in an unambiguous way?
* Formally precisely and unamiously specify what happens for a given program
* Specification needs to be composition, defining *what* happens for a big program should be decomposed into *what happens* for the individual operations and subexpressions
* Multiple strategies and formulation exists
* Note [[Curry-Howard Correspondence]] / [[Curry-Howard-Lambek Correspondance]]
* See also [[Formal Semantics]]
## Semantics Example
This snippet is written in C

```c
while (x < 7) ++x;
```

This program increments x until it is 7. However, we are making some assumptions. We assume that x is a variable that can be incremented. We assume that x is a variable that points to memory that is existent and valid and *writeable*. We assume that there is a notion of lines of code (locations in the "control flow graph") in this program that we can loop through (as opposed to lambda calculus where there is no such notion, even though is still a valid program). 