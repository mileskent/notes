---
aliases:
  - constexpr
---
constexpr is a [[C++]] specifier that marks an entity as evaluable at [[Compile-Time]]. It can be applied to variables, functions, and if statements.

# constexpr Variables

constexpr variables are essentially the C++ answer to the issues with [[C Macro|C Macros]]. The compiler evaluates the code at Compile-Time but also with type, scope, operator precedence, etc. Whereas macros are literally dumb text substitution.

```cpp
#define AREA 2 * 3 + 4         // expands to 2 * 3 + 4 = 10, not (2 * 3 + 4) = 10
int x = AREA * 2;              // 2 * 3 + 4 * 2 = 14, not 20

constexpr int area = 2 * 3 + 4;  // = 10, a real typed value
int y = area * 2;                 // = 20
```

# constexpr Functions

A constexpr function can be evaluated at compile-time when given constant arguments, or at runtime otherwise.

```cpp
constexpr int factorial(int n) {
    return (n <= 1) ? 1 : n * factorial(n - 1);
}

static_assert(factorial(5) == 120);  // computed at compile-time
int x = factorial(runtime_value);    // computed at runtime
```

> [!example]- Prior to constexpr, this functionality would have required recursive templating
> And effectively, this is what is happening under the hood.
> 
> ```cpp
> template <int N>
> struct Factorial {
>     static constexpr int value = N * Factorial<N - 1>::value;
> };
> 
> template <>
> struct Factorial<0> {
>     static constexpr int value = 1;
> };
> 
> static_assert(Factorial<5>::value == 120);
> ```
> 
> Prefer constexpr functions. They're simpler and the compiler enforces the same guarantees.

# if constexpr

if constexpr provides [[Compile-Time]] branching inside templates. The discarded branch is not instantiated, so it can contain code that would be ill-formed for the given type.

```cpp
template <typename T>
std::string serialize(const T& value) {
    if constexpr (std::is_integral_v<T>) {
        return std::to_string(value);
    } else if constexpr (std::is_same_v<T, std::string>) {
        return value;
    } else {
        static_assert(sizeof(T) == 0, "unsupported type");
    }
}
```

This replaces most uses of [[Substitution Failure Is Not An Error|SFINAE]] and recursive template tricks.
