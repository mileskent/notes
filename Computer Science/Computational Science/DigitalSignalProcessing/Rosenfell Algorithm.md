---
date: 2026-06-10
aliases:
---
The *Rosenfell Algorithm* is an [[Algorithm]] that maps the [[Power Spectrum]] output of an [[Fast Fourier Transform|FFT]] to a display that has fewer pixels than the spectrum has frequency bins ($k$), meaning that multiple bins get grouped into one pixel. Instead of taking the average of these bins, this algorithm chooses the max if the group is [[Monotonic Function|Monotonic]]. Otherwise it will use the min if the pixel index is even or max if the pixel index is odd.

# Motivation
TLDR: Average $\rightarrow$ Blurry $\rightarrow$ 😭, Rosenfell $\rightarrow$ Use Actual Frequencies / No Blurry $\rightarrow$ 😀

In order to faithfully represent the spectrum, we really want to make sure we represent peaks even if our resolution isn't very high. Average fails because it hides narrow peaks by blurring them; average is literally how [[Box Blur]] and [[Gaussian Blur]] work.
