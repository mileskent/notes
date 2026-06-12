---
date: 2026-06-09
aliases:
  - Lagrange Interpolation
---
*Lagrange polynomial interpolation* estimates the value of a [[Discrete-Time Signal]] in-between its integer [[Sampling|sample]] positions by constructing a [[Polynomial]] [[Mathematics/SetTheory/Function|Function]] that "connects the dots". 
* Cubic Polynomials are the default order that is commonly used for algorithms involving this method
* Higher order polynomials are capable of fitting a larger [[Windowing|Window]] of samples, and consequently cover a larger neighborhood of samples per function, e.g. a linear function would only cover a neighborhood between two samples whereas a cubic function might cover a neighborhood over several samples.
