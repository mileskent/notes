---
date: 2026-06-09
---
*Morphological dilation* is a sliding-window maximum nonlinear [[Filter]] over a [[Signal]]. For each sample, the output is the maximum value within a kernel of width $k$ centered on that sample:

$$
(f \oplus k)[n] = \max_{|i| \leq k/2} f[n + i]
$$

* Applied to a [[Power Spectrum]], dilation restores the spatial extent of broad structures that survived [[Morphological Erosion]]. Used as the second step in [[Morphological Opening]].
* This is a [[Stencil]] operation: each output depends only on a fixed neighborhood of $k$ surrounding inputs, with a nonlinear max reduction instead of a weighted sum.
