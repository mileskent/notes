A *Syntax Tree* is the artifact [[Tree]] you get during the process of [[Parsing]] a [[Programming Language]]. 

It comes in two flavors. 
* Syntax Tree
	* [[Abstract Syntax Tree]]
	* [[Concrete Syntax Tree]] (Parse Tree)

![[Pasted image 20260830203217.png]]

Whereas a Parse Tree includes every token in the string being parsed, explicitly shows nonterminal production rules, and preserves all source syntax, an Abstract Syntax Tree merely preserves the minimal set of operations, variables, and control flow necessary to maintain the semantics of the expression.