*Context-Free Grammar* is the [[Formal Grammar]] defined by axioms of the form $N \rightarrow (N \cup \Sigma)^*$. That is, from a nonterminal to some string with some combination of terminal and/or nonterminals.
* Context-Free Grammar is [[Isomorphism|isomorphic]] to First-Order Polynomial [[Algebraic Data Type|Algebraic Data Types]]
* Context-Free Grammar is the most common type of Grammar for programming languages
* Contains nonterminals and terminals
	* Terminal characters have no production ability
	* Nonterminal characters must be morphed by a production rule to work towards a leaf state terminal character
* Production rules generate strings
* Production replaces a nonterminals with one of its options
* Production terminates when only terminal symbols remain
* We can evaluate Grammar membership via [[Parsing]] 

# Examples
## LL(1) No. 1
**Grammar**
* S $\rightarrow$ (S) | E
* E $\rightarrow$ {E} | c

## LL(1) No. 2
**Grammar**
* S $\rightarrow$ AB$
* A $\rightarrow$ xA
* A $\rightarrow$ B
* B $\rightarrow$ yzB
* B $\rightarrow$ z
