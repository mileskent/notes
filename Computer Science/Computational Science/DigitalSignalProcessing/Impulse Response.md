---
date: 2026-05-27
---
In [[Digital Signal Processing]], *Impulse Response* is the output of a system when it is subjected to an [[Impulse]]. 

For example, the impulse response of a reverb filter would continuously fade the volume from the impulse over time. An echo filter would periodically repeat the impulse, while fading the volume over time. A gain filter would have no temporal effect like the aforementioned.

$h[n]$ is used to denote the impulse response of a system where 

$$
h[n] = T\{\delta[n]\}
$$

Impulse response is important in DSP because if a system in a [[Linear Time-Invariant System]], then knowing $h[n]$ means you know *everything* about the system, where $T$ is the system.

$$
T\{x[n]\} = x[n] * h[n]
$$