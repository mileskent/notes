---
date: 2026-07-13
aliases:
  - Monadic Chaining
  - Monadic Bind
---
Monadic Chaining is the concept of using a type based on the Mathematical [[Monad]] to "chain functions with choice". That is, chaining functions where those functions are over types with context, where there are multiple valid paths down the "decision [[Tree|tree]]" of possibilities. 

# Examples
## Trivial Optional
```
Option<Value> = getValue()
```

In this example, the decision tree of monadic chaining is a single function. The tree is literally just the root node.

## Nested Lookup
```
Option<UserZipcode> = getUser(id)
  .and_then(|u| u.address)
  .and_then(|a| a.zip_code)
```

In this example the decision tree is almost degenerate. It is a [[Degenerate|Degenerate Tree]] where for each node going in the degenerate direction, there is a single node going in the opposite direction. Basically what a comb looks like. This is because for each [[Function Application]], there are two outcomes: the value is Some or None. The decision tree can only go deeper for Somes; all Nones are leaves. All leaves are Nones except for the Some that yields the user's zipcode. 