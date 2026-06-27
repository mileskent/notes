---
date: 2026-06-09
---
*Cross-correlation* measures the [[Similarity]] between two [[Discrete-Time Signal|discrete-time signals]] as a function of a time lag $\tau$ applied to one of them:

$$
(f \star g)[\tau] = \sum_{n=0}^{N-1} \overline{f[n]} \cdot g[n + \tau]
$$

The result is a new signal indexed by $\tau$, where each value is the [[Similarity]] score at that offset.

# Motivation
At what phase shift are these two signals most similar?

# Fast Cross-Correlation
Cross-correlation can be computed efficiently using the [[Fast Fourier Transform|FFT]]:

$$
f \star g = \mathcal{F}^{-1}\left\{ \overline{\mathcal{F}\{f\}} \cdot \mathcal{F}\{g\} \right\}
$$

This reduces the [[Time Complexity]] from $O(n^2)$ to $O(n \log n)$.

# Autocorrelation
When both signals are the same ($f = g$), cross-correlation becomes *autocorrelation*, measuring how similar a signal is to a shifted version of itself. Useful for detecting periodicity.

# Applications
- **[[Radar]]**: cross-correlate the return with the transmitted [[Physics/Electromagnetism/Pulse|pulse]]; the peak lag gives range
- **[[Monopulse Radar]]**: cross-correlate $\Sigma$ and $\Delta$ channels to determine whether a coherent signal is present in both
- **[[Direct Sequence Spread Spectrum|DSSS]]**: cross-correlate the received signal with the known [[Pseudo-Noise|pseudo-noise]] (PN) spreading code to despread it
- **Time synchronization**: align two recordings of the same event by finding the lag where they match best
