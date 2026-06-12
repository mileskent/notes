---
date: 2026-06-09
---
*Morphological closing* is [[Morphological Dilation]] followed by [[Morphological Erosion]] with the same kernel width $k$. It is transitively also a nonlinear [[Filter]] applied to a [[Computer Science/Computational Science/DigitalSignalProcessing/Signal|Signal]].

$$
f \bullet k = (f \oplus k) \ominus k
$$

* The net effect is that any spectral valley narrower than $k$ bins is filled; broader structures are preserved. The dual of [[Morphological Opening]].
* This is a [[Stencil]] operation: each output depends only on a fixed neighborhood of $k$ surrounding inputs, with a dilation then erosion instead of a weighted sum. The order of operations matters.
