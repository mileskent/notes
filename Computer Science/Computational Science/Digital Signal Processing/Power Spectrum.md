---
date: 2026-06-09
---
The *power spectrum* is the distribution of [[Signal Power]] across frequency, computed by taking the squared magnitude of each [[Discrete Fourier Transform|DFT]] bin $k$:

$$
P[k] = |X[k]|^2 = I[k]^2 + Q[k]^2
$$

It discards phase information and retains only energy per frequency bin. The primary domain for signal detection; bins whose power exceeds the local noise floor are declared detections.
