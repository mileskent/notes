---
date: 2026-06-09
---
The FFT Shift post-processes the output frequency graph of the [[Fast Fourier Transform|FFT]] and centers 0 in the middle of the array, rather than at the beginning, making it easier to interpret. By default frequencies of zero are on the left, then positives, then negatives. 

$$
[k_0,\ \vec{k}_+,\ \vec{k}_-] \rightarrow [\vec{k}_-,\ k_0,\ \vec{k}_+]
$$

