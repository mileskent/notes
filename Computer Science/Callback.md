---
date: 2026-01-23
---
A *Callback* is a [[Computer Science/Function|Function]] represented by its [[Function Pointer]] whose invocation is deferred to its [[Caller]], which treats it as a black box.
* The callback is often passed to a function at runtime
* All [[Higher-Order Function]]s utilize callbacks
* Facilitates modularity and decoupling

```mermaid
classDiagram
	class Src {
	- callback : *fn
	+ setCallback(callback : *fn)
	+ sendMessage()
	}
	class Interface {
	- Src src
	+ wrapperFunction()
	- specialFunction()
	}
	Interface --> Src : src.setCallback(callback)
```

```mermaid
sequenceDiagram
	participant Src
	participant Interface
	Interface ->> Src: src.setCallback(wrapperFn)
	Src -->> Interface: Invoke callback()
	Interface ->> Interface: wrapperFn()
	Interface ->> Interface: specialFn() called within wrapperFn
```
