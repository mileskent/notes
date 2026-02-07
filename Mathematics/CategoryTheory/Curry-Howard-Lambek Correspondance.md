---
date: 2026-02-07
---

An expansion of [[Curry-Howard Correspondence]], the idea that not only [[Simply Typed Lambda Calculus]] and [[Propositional Logic]] are [[Isomorphism|isomorphic]], but that [[Category Theory]] has an [[Equivalence]] relationship to them. 

Because an *equivalence* is a looser version of an *isomorphism*, you could also use the less encompassing statement that [[Simply Typed Lambda Calculus]], [[Propositional Logic]], and [[Category Theory]] are *equivalent*.

| Category Theory                   | Logic                                                | STLC              |
| --------------------------------- | ---------------------------------------------------- | ----------------- |
| [[Mathematical Object\|Object]]   | [[Proposition]]                                      | Type              |
| [[Morphism]] ($f: A \to B$)       | [[Proof]]                                            | Term / Program    |
| [[Terminal Object]] ($1$)         | Truth ($\top$)                                       | Unit Type         |
| [[Product Object]] ($A \times B$) | [[Propositional Logic#Conjunction]] ($A \land B$)    | Pair / Tuple Type |
| [[Exponential Object]] ($B^A$)    | [[Propositional Logic#Implication]] ($A \implies B$) | Function Type     |
