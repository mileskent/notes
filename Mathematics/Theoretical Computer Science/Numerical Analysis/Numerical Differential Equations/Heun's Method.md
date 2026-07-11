---
date: 2025-10-15
---
Also called "Improved Euler's Method". A numerical method for approximating the values of a solution $y(t)$ of a [[Differential Equation]], by discretizing the differential equation into a difference equation that can be used to find the approximate solution $y_n$ through recursive definition. Similar methods include [[Euler's Method]] and [[Runge-Kutta Method]]
$$
y' = f(t, y),\ y(t_{0}) = y_{0}
$$
$$
t_{n}, y_{n} \rightarrow t_{n+1},y_{n+1}
$$
![[Pasted image 20251206173934.png|300]]
* $t_{n+1} =t_{n} + h$
* $y_{n+1} = y_{n} + hk(t_{n}, y_{n})$
* $k(t_{n}, y_{n}) = \text{avg}(k_{n,1}, k_{n,2})$
* where $k_{n,1} = f(t_{n}, y_{n})$
* where $k_{n,2} = f(t_{n} + h, y_{n} + hk_{n,1})$
* Local Truncation Error: $O(h^3)$
* Global Truncation Error: $O(h^2)$
