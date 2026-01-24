In [[Functional Analysis]], a *Lebesgue Space*, denoted by $L^p$, where $p > 0$, acts of [measurable](https://en.wikipedia.org/wiki/Measurable_function) [[Mathematics/SetTheory/Function]]s $f$, such that:
$$
L^p = \left\{f\ \ \bigg\rvert\ \int_{X} |f|^p\ d\mu < \infty\right\}
$$
* $L^p$ is the Lebesgue Space
	* $L$ stands for *Lebesgue*, and signals we are using the [[Lebesgue Integral]]
	* $p$ is the exponent of the Lebesgue Space and informs its flavor

| Space               | Space Type        | Geometry                             |
| ------------------- | ----------------- | ------------------------------------ |
| $L^p,\ p \in (0,1)$ | [[F-Space]]       | Non-convex, no norm                  |
| $L^p, p \geq 1$     | [[Banach Space]]  | Convex, has norm                     |
| $L^p,\ p=2$         | [[Hilbert Space]] | [[Inner Product]], Parallelogram Law |
* $\int_{X}\dots\ d\mu$ is a [[Lebesgue Integral]] and the environment of the expression
	* $X$ is the [[Region|Domain]] in which the functions exist
	* $\mu$ is the measure in $X$, e.g. in 1D space it would be length
* $|f|^p$ is the [[Transformation]]
* $\int_{X} |f|^p\ d\mu < \infty \iff f\in L^p$
