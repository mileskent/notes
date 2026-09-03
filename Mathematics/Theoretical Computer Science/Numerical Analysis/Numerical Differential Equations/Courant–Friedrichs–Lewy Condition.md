---
date: 2026-09-03
aliases:
  - CFL condition
  - CFL number
  - Courant-Friedrichs-Lewy condition
  - Courant number
---

A necessary condition for [[Convergent|Convergence]] of explicit [[Numerical Differential Equations|numerical solvers]] time-dependent [[Differential Equation]]s, and originally formulated specifically for hyperbolic [[Partial Differential Equation]]s. The principle is essentially that in order to record a snapshot of an propogating "wave" (wave is used loosely here), you must precisely time your snapshot to capture the object as it passes by; imagine that a racecar is passing by on a track and your are trying to take a picture as they cross the finish line. It is entirely possible that the timing of your photos is such that you have zero photos of race cars passing the finish line. The principle is a similar idea to [[Nyquist-Shannon Sampling Theorem]] or [[Aliasing]]. However, it is more about the binary: "is the object captured?", rather than the less contrained but equally encompassing, "is our sampling of the object representative of it?". A *CFL Violation*, is far more catastrophic than aliasing though, as it results in the total omission of information, rather than mere distortion.