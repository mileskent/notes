---
date: 2026-05-25
---
A **digital signal** is the result of [[Quantization|Quantizing]] the values of the codomain of a [[#Discrete-Time Signal]], creating a new signal where both the [[Domain]] and [[Codomain]] are discrete. It is typically can be denoted as $x[n]$, where $x$ is the function of the signal, and $n$ is the index. It can also be denoted as $\hat{x}[n]$ or $x_{q}[n]$ to distinguish it from its discrete-time counterpart, and to show that it has been quantized.

![[Pasted image 20260521160426.png|300]]

An example of a digital signal would be the final steps of the [[Analog-to-Digital Converter]] before it sends the final digital signal to the computer; it has to represent that signal in binary. Any means of representing all continuous values with finite digits of precision will lead to loss, so regardless of if you choose [[IEEE 754 Double]]s, or some kind of integer, you will be performing some level [[Quantization]] to the signal. The result is a signal with both discrete time and amplitude.