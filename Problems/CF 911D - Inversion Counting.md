# CF 911D - Inversion Counting
## Problem Statement
- Permutation $a$ of size $n$, $m$ queries
- In each query
	- Reverse the order of a subarray $a[l;r]$
	- Find the parity of the number of inversions
## Solution
- First, find the number of inversions
- Then, notice that the inversion parity changes if you swap two adjacent numbers
	- Note that the inversion parity is equivalent to the parity of $\lfloor \dfrac{r-l+1}{2} \rfloor$.