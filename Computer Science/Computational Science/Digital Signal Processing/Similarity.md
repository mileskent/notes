---
date: 2026-05-28
---
Similarity between [[Discrete-Time Signal|Discrete-Time Signals]] and is computed by summing the element-wise product of their [[Sampling#Sample|Samples]]

$$
S(x,y) = \sum_{i} x[i] \cdot y[i]
$$

* Similarity is only defined for two signals of exactly the same length
* Similarity is a [[fold]], unlike a [[Convolution]]

Alternatively, if you want to think of the signals as finite [[Coordinate Vector|1 dimensional vectors]],, similarity is just the [[Dot Product]] of the two signals of the same length

$$
S(\vec{x}, \vec{y}) = \vec{x} \cdot \vec{y}
$$

For [[Analog Signal|Continuous-Time Signals]] you just slightly adjust it to a continuous land sum ([[Integral]])

$$
S(x,y) = \int x(t) \cdot y(t)\ dt
$$
