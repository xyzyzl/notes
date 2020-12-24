# Sleepy Cow Sorting
#BIT #Greedy
## Problem Statement
- Given a permutation of the first $N$ positive integers $p_1,p_2,\ldots,p_N$
- In each operation you can move the number in index $1$ down to index $k$ and shift indices $2, 3, \ldots, k$ to $1, 2, \ldots, k-1$.
- Find the minimum number of operations to turn $p$ into a sorted array
## Solution
- Clearly the longest decreasing subarray ending at the end need not be moved
	- If there is a longer decreasing subarray that does not end at index $N$ then we will need to move all of it to reorder the values after the end of the subarray
- Let the longest decreasing subarray be $[l,n]$. Then, the total number of moves we will need to do is $l-1$.
- To find the distance, store an array $a$ and let $a_i = 1$ if the number $i$ does not need to be operated on
	- Set all $a_{p_j} = 1 \forall j \in [l,n]$.
	- Loop for $i$from $0$ to $l-1$. The total distance needed for each number $a_i$ is $\#\text{ remaining to be sorted} + \#\text{ already sorted numbers at most }a_i$.
		- The first value is $l-i-1$.
		- The second value can be found with binary index tree.