---
aliases:
---
A *type trait* is a [[C++ Template Metaprogramming|Template Metaprogramming]] pattern in [[C++]]. It is a template struct that exposes a [[Compile-Time]] fact about a type, typically through a static constexpr member called value or a member type alias called type. It is equivalent to [[Rust]]'s trait bounds.
# Example

```cpp
// Is T a pointer?
template <typename T>
struct is_pointer {
    static constexpr bool value = false;
};

// Partial specialization: T* is a pointer
template <typename T>
struct is_pointer<T*> {
    static constexpr bool value = true;
};

static_assert(is_pointer<int>::value == false);
static_assert(is_pointer<int*>::value == true);
```

The standard library provides dozens of these in <type_traits>: std::is_integral, std::is_same, std::remove_const, std::decay, etc.

# Convenience Aliases

By convention, traits that produce a type have a _t alias, and traits that produce a value have a _v alias:

```cpp
// Instead of: typename std::remove_const<T>::type
std::remove_const_t<T>

// Instead of: std::is_integral<T>::value
std::is_integral_v<T>
```

