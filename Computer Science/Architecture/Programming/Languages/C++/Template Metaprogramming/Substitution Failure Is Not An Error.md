---
aliases:
  - SFINAE
  - Substitution Failure Is Not An Error
---
*Substitution Failure Is Not An Error* (SFINAE) is a [[C++ Template Metaprogramming|Template Metaprogramming]] rule in [[C++]]: when the compiler substitutes template arguments and the result is ill-formed, that specialization is silently discarded from the overload set rather than producing a compile error.

> [!warning]
*SFINAE has largely been superceded by [[constexpr#if constexpr]] and [[Concept|Concepts]]. Use with caution!*

# Example

```cpp
// Only enabled when T is an integral type
template <typename T>
auto to_string(T value) -> std::enable_if_t<std::is_integral_v<T>, std::string> {
    return std::to_string(value);
}

// Only enabled when T has a .str() method
template <typename T>
auto to_string(T value) -> decltype(value.str()) {
    return value.str();
}
```

If T = double, the first overload's enable_if_t produces an invalid type and is discarded. If T = int, the second overload's decltype(value.str()) is ill-formed and is discarded. No error, the compiler just picks whichever overload survives.

# enable_if

The standard mechanism for SFINAE:

```cpp
template <bool Condition, typename T = void>
struct enable_if {};           // no 'type' member when false

template <typename T>
struct enable_if<true, T> {
    using type = T;            // 'type' exists only when true
};
```
