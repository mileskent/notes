---
date: 2026-05-31
---
A stencil is a [[Filter]] where every pixel's next value a [[fold]] of its neighbors.
* Examples
	* [[Box Blur]], [[Gaussian Blur]]
		* Each pixel is a weighted average of its neighbors
	* Conway's Game of Life
		* Each pixel is on or off based on different orientations of its neighbors
	* [[Jacobi Method]], [[Gauss-Seidel Method]]
		* Each pixel is a weighted average of its neighbors, where Jacobi is a [[Finite Impulse Response Filter|FIR Filter]] and Gauss-Seidel is an [[Infinite Impulse Response Filter|IIR Filter]]