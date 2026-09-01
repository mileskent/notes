*Probability Theory* is the study of predicting [[Sample|Samples]] from [[Population]] ^e39c62

Futhermore, it is essentially applied [[Set Theory]] and [[Combinatorics]].
# Set Theory with Probability
General [[Set Theory]] applies to probability. There are also special sets within probability theory.
## Correspondance to Set Theory
In [[Probability Theory]], there is a correspondance between the following:

[[Venn Diagram|Venn Diagrams]] $\iff$ [[Set|Sets]] $\iff$ [[Probability|Probabilities]]

This is because, obviously Venn Diagrams correspond to Sets. But furthermore, probabilities also correspond to sets, because probabilities simply just exist within a special case of a [[Universe]] where the Universe is the [[Sample Space]] $S$ and a particular subset of that sample space is an [[Event]] $A$: $A \subset S$. 

$$
P(A) = \frac{|A|}{|S|}
$$
## Outcome
![[Outcome]]
## Event
![[Event]]
## Experiment
![[Experiment]]
## Sample Space
![[Sample Space]]
## Principle of Inclusion Exclusion
![[Principle of Inclusion-Exclusion for Probability]]

## Disjoint Events
![[Disjoint]]

# Combinatorics with Probability
In order to calculate probabilities, you usually need to determine the cardinality of the [[Event]] using [[Combinatorics]].

## Addition Rule
A special case of [[#Disjoint Events]].
$$
\begin{align}
A \cap B = \varnothing  
&\implies |A \cup B| = |A| + |B|\\
&\implies P(A \cup B) = P(A) + P(B)\\
\end{align}
$$

## Multiplication Rule
If a process has sequential stages where stage i has $c_i$ paths to stage i+1, then the number of paths from $c_0$ to $c_{n-1}$ is $\prod_{i=0}^{n-1} c_{i}$


## Permutation
![[Permutation]]

## Combination
![[Combination]]