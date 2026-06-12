---
date: 2026-06-09
---
A *threshold offset* is a fixed margin, expressed in dB, added above an estimated noise floor to set a detection threshold. A larger offset reduces false alarms at the cost of missing weaker targets.

# CFAR Threshold Offset

In [[Constant False Alarm Rate|CFAR]], the multiplier $\alpha$ corresponds to a threshold offset of

$$
\Delta = 10 \log_{10}(\alpha) \text{ dB}
$$
