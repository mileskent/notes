Based on the [[Principle of Inclusion-Exclusion]], which relates to [[Cardinality]]. We can simply divide both sides by the cardinality of the [[Universe]] in order to get everything in terms of cardinality. See [[Probability Theory#Correspondance to Set Theory]]
$$
\begin{align}
P(A_1 \cup A_2 \cup \dots \cup A_n) &= \\
 \sum_{i=1}^{n} P(A_i) &- \\
 \sum_{1 \leq i < j \leq n} P(A_i \cap A_j) &+ \\
 \sum_{1 \leq i < j < k \leq n} P(A_i \cap A_j \cap A_k) &- \\
 \dots& \\ \\
 + (-1)^{n+1} P(A_1 \cap A_2 \cap \dots \cap A_n)&
\end{align}
$$