---
date: 2026-06-15
aliases:
  - unit sample signal
  - δ[n]
---
The [[Kronecker Delta Function]] as a [[Discrete-Time Signal]], denoted $\delta[n]$. Serves as a primitive building-block signal from which more complex discrete-time signals can be constructed.

$$\delta[n] = \begin{cases} 1, & n = 0 \\ 0, & \text{otherwise} \end{cases}$$

# Impulse Representation
![[Impulse]]

# Sifting Property
![[Sampling#Sifting Property]]

# Relationship to Unit Step
$$\delta[n] = u[n] - u[n-1]$$
