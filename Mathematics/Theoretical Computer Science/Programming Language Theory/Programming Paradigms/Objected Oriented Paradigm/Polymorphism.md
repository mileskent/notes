---
date: 2026-01-23
---
# Dynamic Polymorphism
The [[Program]] determines which implementation of a [[Member Function]] to call at [[Runtime]].
* Dynamic Polymorphism results in runtime overhead
* The way this dynamic lookup is achieved varies by implementation:
	* Look up the appropriate [[Label]] in a [[vtable|vtable]]
	* [[Duck Typing]]
# Static Polymorphism
The [[Program]] determines which implementation of a [[Member Function]] to call at [[Compile-Time]].
* Static Polymorphism involves no [[Runtime]] overhead, but instead compile-time overhead, which is obviously better for performance
* Compile-time resolution depends on implementation:
	* [[Curiously Recurring Template Pattern]]
	* [[Function Overloading]]
	* [[Template]]s
