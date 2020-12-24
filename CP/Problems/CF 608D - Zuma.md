# CF 608D-Zuma
#DP #Range-DP
## Problem statement
- Have an array $a$ and want to erase every element
- Can only erase subarrays that are palindromes.
- Find minimum number of moves to erase every element
## Solution
- Let $dp_{i,j}$ be the minimum number of moves to erase the subarray $a[i;j]$. 
- Then $dp_{i,i} = 1$.
- Our other states are: $dp_{i,j} = min(1+dp_{i+1,j}, dp_{i+1,k-1}+dp_{k+1, j}, 1+dp_{i+2,j})$.
	1. $1+dp_{i+1,j}$ happens categorically, because we simply add $a_i$ to the palindrome $a[i+1;j]$.
	2. $dp_{i+1,k-1}+dp{k+1,j}$ happens if $a_i=a_k$ for $k \in [i+2,j]$; we divide the problem into $a[i;k]$ and $a[k+1;j]$, but we know that $a_i=a_k$ so it suffices to just solve $a[i+1;k-1]$. This is the main transition.
		- For cases where $a_i = a_{i+1}$, we have $1+dp_{i+2,j}$. This basically does the same thing, but $a[i;i+1]$ only takes one move to do so there is no use to calculate it.
- The final answer is $dp_{0,n-1}$.