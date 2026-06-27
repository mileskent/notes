---
date: 2026-06-09
---
A *hysteresis latch* is a [[Finite State Machine]] that asserts a binary output corresponding to when a value crosses a threshold, and holds that assertion for a configurable hold-off period after the value drops back below the threshold.
* Without hysteresis, a signal that hovers near the threshold causes rapid toggling between present and absent, called *chattering*. The hold-off period suppresses this by keeping the output asserted for a minimum duration after the last threshold crossing.
