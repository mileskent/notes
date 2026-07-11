---
aliases:
---
A *concept* (C++20) is a named set of constraints on a template parameter in [[C++]]. It is the [[C++ Template Metaprogramming|Template Metaprogramming]] equivalent of a Rust trait bound.

# Example

```cpp
template <typename T>
concept Numeric = std::is_arithmetic_v<T>;

template <Numeric T>
T add(T a, T b) { return a + b; }

add(1, 2);       // ok
add("a", "b");   // compile error: const char* does not satisfy Numeric
```

# Defining Concepts

Concepts can compose [[Type Trait|type traits]], expressions, and other concepts:

```cpp
template <typename T>
concept Printable = requires(T t) {
    { std::cout << t } -> std::same_as<std::ostream&>;
};

template <typename T>
concept Summable = requires(T a, T b) {
    { a + b } -> std::convertible_to<T>;
};
```

The requires expression lists what the type must support. If any expression inside is ill-formed, the concept evaluates to false.

# Syntax Variants

```cpp
// Shorthand: concept as type constraint
template <Numeric T>
T square(T x) { return x * x; }

// Requires clause
template <typename T>
requires Numeric<T>
T square(T x) { return x * x; }

// Trailing requires
template <typename T>
T square(T x) requires Numeric<T> { return x * x; }

// Abbreviated function template (auto)
auto square(Numeric auto x) { return x * x; }
```

Concepts are the closest C++ gets to [[Rust]] traits, but they only constrain; Rust traits also provide default implementations.
