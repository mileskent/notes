---
date: 2026-06-09
---
*Morphological opening* is [[Morphological Erosion]] followed by [[Morphological Dilation]] with the same kernel width $k$. It is transitively also a nonlinear [[Filter]] applied to a [[Computer Science/Computational Science/DigitalSignalProcessing/Signal|Signal]].

$$
f \circ k = (f \ominus k) \oplus k
$$

* The net effect is that any spectral feature narrower than $k$ bins is removed; broader features are preserved. Applied to a [[Power Spectrum]], the result is a smooth estimate of the noise floor envelope which is the basis of the [[Automatic Noise Floor Spectrum Estimation in the Presence of Signals]]
* This is a [[Stencil]] operation: each output depends only on a fixed neighborhood of $k$ surrounding inputs, with an erosion then dilation instead of a weighted sum. The order of operations matters.
