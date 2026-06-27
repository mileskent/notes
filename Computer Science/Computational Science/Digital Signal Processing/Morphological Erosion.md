---
date: 2026-06-09
---
*Morphological erosion* is a sliding-window minimum nonlinear [[Filter]] over a [[Signal]]. For each sample, the output is the minimum value within a kernel of width $k$ centered on that sample:

$$
(f \ominus k)[n] = \min_{|i| \leq k/2} f[n + i]
$$

* Applied to a [[Power Spectrum]], erosion carves out any spectral peak narrower than $k$ bins, leaving only broad structures. Used as the first step in [[Morphological Opening]].
* This is a [[Stencil]] operation: each output depends only on a fixed neighborhood of $k$ surrounding inputs, with a nonlinear min reduction instead of a weighted sum.
