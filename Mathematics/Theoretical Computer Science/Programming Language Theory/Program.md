---
date: 2025-01-07
---
# Program
A set of syntactical characters that describe some kind of behavior (semantics), defined by a [[Programming Language]].

Programs can take many forms.

| Program Form                                                                    | What it is                                                                                     |
| ------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| ADD R6, R6, -1                                                                  | Assembly instruction to decrement                                                              |
| x = 5                                                                           | Assignment instruction of x as 5                                                               |
| $f(x, y) = g(x, 5),\ g(x, y) = x^2 + y^2$                                       | Definition and partial application of a function                                               |
| fib(x) { fib(x - 1) + fib(x - 2) }                                              | Definition of a recursive function                                                             |
| $E(2) \iff 2=2k,\ s.t. k\in \mathbb{Z},\ 1\in \mathbb{Z} \therefore E(2), \Box$ | Proof that 2 is even                                                                           |
| $H = \frac{1}{1- \mathcal{R}} = \frac{Y}{X}$                                    | Operator transfer function of an accumulator representative of block diagram / digital circuit |

# C Program Pipeline
![[Pasted image 20250923202345.png]]
Note that an [[Assembler]] isn't shown, because a separate step for assembling is slower. You would only do that if you were very limited in [[Memory]], e.g. you are in 1970.