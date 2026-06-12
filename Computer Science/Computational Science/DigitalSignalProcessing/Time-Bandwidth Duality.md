---
date: 2026-06-10
---
*Time-Bandwidth Duality* is the principle that a [[Signal|signal's]] duration and [[Bandwidth|bandwidth]] are inversely related: compressing a signal's duration expands its its bandwidth, and vice versa. This is expressed by the time-bandwidth product inequality:

$$
T \cdot B \geq \frac{1}{2}
$$

where equality holds for a [[Gaussian]] [[Pulse]]. In practice, to transmit [[Symbol|symbols]] faster (shorter $T$), more [[Bandwidth|bandwidth]] $B$ is required.

# Intuition
Imagine a signal that starts at zero, briefly peaks, and then returns to zero. To make a signal that cancels out somewhere, there must be destructive interference. However, in order to get both the destructive interference almost everywhere **and** the brief peak where there is constructive interference, you need many sinusoids, spanning a broad spectrum. If we only had a narrow band of frequencies, the sinusoids would not be different enough to **both** totally cancel out in most of the time domain, but also peak in the middle.