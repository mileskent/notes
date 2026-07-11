---
date: 2025-10-15
---
[[Numerical Analysis|Numerical]] methods for [[Differential Equation]]s.
# [[Euler's Method]]
$$
y' = f(t, y),\ y(t_{0}) = y_{0}
$$
$$
t_{n}, y_{n} \rightarrow t_{n+1},y_{n+1}
$$
![[Pasted image 20251206173529.png|300]]
* $t_{n+1} =t_{n} + h$
* $y_{n+1} = y_{n} + hk_{n}$
* where $k_{n} = f(t_{n}, y_{n})$
* Local Truncation Error: $O(h^2)$
* Global Truncation Error: $O(h)$
# [[Heun's Method]]
$$
y' = f(t, y),\ y(t_{0}) = y_{0}
$$
$$
t_{n}, y_{n} \rightarrow t_{n+1},y_{n+1}
$$
![[Pasted image 20251206173934.png|300]]
* $t_{n+1} =t_{n} + h$
* $y_{n+1} = y_{n} + h \cdot\text{avg}(k_{n,1}, k_{n,2})$
* where $k_{n,1} = f(t_{n}, y_{n})$
* where $k_{n,2} = f(t_{n} + h, y_{n} + hk_{n,1})$
* Local Truncation Error: $O(h^3)$
* Global Truncation Error: $O(h^2)$
# [[Runge-Kutta Method]]
$$
y' = f(t, y),\ y(t_{0}) = y_{0}
$$
$$
t_{n}, y_{n} \rightarrow t_{n+1},y_{n+1}
$$
![[Pasted image 20251206174316.png|300]]
* $t_{n+1} =t_{n} + h$
* $y_{n+1} = y_{n} + h \cdot\text{avg}(k_{n,1}, k_{n,2}, k_{n,2}, k_{n,3}, k_{n,3}, k_{n,4})$
* where $k_{n,1} = f(t_{n}, y_{n})$
* where $k_{n,2} = f\left( t_{n} + \frac{1}{2}h, y_{n} + \frac{h}{2}k_{n,1} \right)$
* where $k_{n,3} = f\left( t_{n} + \frac{1}{2}h, y_{n} + \frac{h}{2}k_{n,2} \right)$
* where $k_{n,4} = f\left( t_{n} + h, y_{n} + \frac{h}{2}k_{n,3} \right)$
* Local Truncation Error: $O(h^5)$
* Global Truncation Error: $O(h^4)$