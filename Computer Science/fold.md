---
aliases:
  - reduce
  - accumulate
---
In [[Functional|Functional Programming]], a *fold* is a [[Higher-Order Function]] that processes a [[Data Structure]], typically an [[Array]], into a single cumulative result. 
* Folds have a *seed/accumulator*, which is the initial value that the operation starts with
```
fold(operation, seed, list)
```

Common aliases are `foldl` and `foldr` which use the leftmost and rightmost element as the seed:
```
foldl(operation, list) = fold(operation, list.first, list)
foldr(operation, list) = fold(operation, list.last, list)
```

Summation would be an example of a fold:
```
sum(list) = foldl(+, list)
```
