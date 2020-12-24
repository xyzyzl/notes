# Empty String
#DP #Range-DP 
- Have a string $S$ of $n$ characters
- Can remove a pair of adjacent characters $S_i, S_j$ if $S_i=S_j$.
## Solution
- Let $dp_{i, j}$ be the number of ways to solve this problem for the substring $S[i;j]$.
- We know that if $S_i = S_k$ for some $i < k < j$, then we can add $dp_{i+1,k-1}$ and $dp_{k+1, j}$.
	- There are many ways to add the values in $dp_{i+1, k-1}$ and $dp_{k+1,j}$. 
	- The number of ways is $\binom{(j-i+1)/2}{(k-i+1)/2}$. This is because there are $\frac{j-i+1}{2}$ pairs to order and $\frac{k-i+1}{2}$ pairs that are in the first half.
	- Thus, $dp_{i,j} = dp_{i+1,k-1} + dp_{k+1,j} \forall k$ s.t. $S_i=S_k$.
- The base case is $dp_{i,i+1} = 1$ if $S_i = S_i+1$.
- The final answer is $dp_{0,n-1}$.