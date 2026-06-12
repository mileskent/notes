---
date: 2026-06-09
aliases:
  - Power
---
In DSP, *signal power* is the average squared amplitude of a [[Signal]] — the mean of $|x[n]|^2$ over a [[Windowing|window]] of [[Sampling|samples]]:

$$
P = \frac{1}{N} \sum_{n=0}^{N-1} |x[n]|^2
$$

For a complex [[IQ data|IQ signal]], $|x[n]|^2 = I^2 + Q^2$ per sample. Averaging over $N$ samples gives a stable measure of signal strength.

The convention is borrowed from physics, where power is proportional to the square of voltage or current. In DSP the units are abstract, but the squaring relationship is the same.
