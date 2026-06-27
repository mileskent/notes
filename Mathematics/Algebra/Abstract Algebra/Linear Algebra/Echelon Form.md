---
date: 2026-01-11
---

A rectangular matrix is in **echelon form** if 
1. If there are any, all zero rows are at the bottom
2. The first non-zero entry (leading entry) of a row is to the right of any leading entries in the row above it
3. All elements below a leading entry are zero
![[Pasted image 20240821095448.png|450]] 
For **reduced row echelon form**
4. All leading entries, if any, are equal to 1.
5. Leading entries are the only nonzero entry in their respective column.

# Pivot
* A **Pivot** in a matrix A is a location in A that corresponds to a leading 1 in the RREF of A
* A **Pivot column** is the column of the pivot

# Free Variable
**Free variables** are the variables of the non-pivot columns
* Any choice of the free variables leads to a solution of the system
* If you have any free variables you do not have a unique solution]
![[Pasted image 20240821100548.png]]
