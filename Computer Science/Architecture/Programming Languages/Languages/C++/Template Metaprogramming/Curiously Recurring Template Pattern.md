---
date: 2026-01-23
aliases:
  - CRTP
  - C++ CRTP
---
In [[C++]], a Curiously Recurring Template Pattern is an idiomatic approach to achieving [[Polymorphism#Static Polymorphism]], where a class $X$ derives from a class [[Template]] instantiation using $X$ itself as the template argument.

```cpp
template <typename Derived>
struct Shape {
    double area() const {
        return static_cast<const Derived*>(this)->area_impl();
    }
};

struct Circle : Shape<Circle> {
    double radius;
    double area_impl() const { return 3.14159 * radius * radius; }
};

struct Square : Shape<Square> {
    double side;
    double area_impl() const { return side * side; }
};
```