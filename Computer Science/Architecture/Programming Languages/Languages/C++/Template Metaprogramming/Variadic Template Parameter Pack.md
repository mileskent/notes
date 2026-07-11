A *Variadic Template Parameter Pack* is a [[C++ Template Metaprogramming|Template Metaprogramming]] pattern in [[C++]] that lets a function accept any number of arguments of any types, resolved at [[Compile-Time]].

# Syntax

```cpp
template <typename... Args>
void foo(Args... args) {
    bar(args...);  // pack expansion -- forwards all args to bar
}
```

- typename... Args declares a **template parameter pack** (zero or more types)
- Args... args declares a **function parameter pack** (one parameter per type in Args)
- args... is a **pack expansion** (the compiler substitutes each element)

# How it works

Each call site generates a unique specialization:

```cpp
foo(42, "hello", 3.14);
// Compiler generates:
// void foo(int args0, const char* args1, double args2) {
//     bar(args0, args1, args2);
// }
```

This is zero-cost: no runtime dispatch, no type erasure. The compiler produces exactly the code you'd write by hand for each combination of argument types.

# Patterns

## Fold

```cpp
template <typename... Args>
auto sum(Args... args) {
    return (args + ...);  // right fold: a + (b + (c + d))
}
```

## sizeof

```cpp
template <typename... Args>
constexpr std::size_t count(Args...) {
    return sizeof...(Args);  // number of types in the pack
}
```

