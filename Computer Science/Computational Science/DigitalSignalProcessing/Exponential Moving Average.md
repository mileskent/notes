---
date: 2026-06-09
aliases:
  - EMA
---
An *Exponential Moving Average* (EMA) is a first-order [[Infinite Impulse Response Filter|IIR Filter]] that weights recent samples more heavily than older ones. Each output is a blend of the current input and the previous output:

$$
y[n] = \alpha \cdot x[n] + (1 - \alpha) \cdot y[n-1]
$$

* where $\alpha \in (0, 1)$ controls how quickly the average responds; a larger $\alpha$ reacts faster to changes, a smaller $\alpha$ smooths more aggressively.

# Asymmetric EMA
Instead of a single $\alpha$, use separate values for growth and decay:

$$
\alpha = \begin{cases} \alpha_{grow} & x[n] > y[n-1] \\ \alpha_{decay} & x[n] < y[n-1] \end{cases}
$$

Useful in signal tracking where reacting quickly to a rising signal but holding on longer to a falling one reduces false "signal gone" declarations.
