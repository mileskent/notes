---
date: 2026-03-02
---
A *Monotic Stack* is a [[Stack]] that forces its data to be [[Monotonic Function|Monotonic]]. In practice this means that when data is pushed onto the stack the breaks this property, all the data in the stack that is now is invalid is evicted until the new data can be pushed while maintaining the property. Some additional side effects might happen during this.

# Monotonically Increasing Stack
A Monotonic Stack where the ordering is non-strictly increasing.
# Monotonically Decreasing Stack
A Monotonic Stack where the ordering is non-strictly decreasing.
# Examples
Monotonic Stack is used in
* [[739. Daily Temperatures]]
	* [[739. Daily Temperatures#Monotonic Stack of Pairs Solution]]
	* [[739. Daily Temperatures#Monotonic Stack of Indices Solution]]
	