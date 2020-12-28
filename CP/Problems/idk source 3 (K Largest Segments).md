# idk source #3
#DP #prefix-sums
- Given an array $a$ of length $N$, find $K$ subarrays of length $M$ with the largest collective sum
## Solution
- Let $dp_{i, j}$ be the max. sum with first $i$ numbers and $j$ subarrays.
	- Add the $j$th subarray by doing $dp_{i, j} = max(dp_{i-1, j}, dp_{i-m, j-1} + \sum_{l = i-m+1}^i a_l)$
	- This can be found with prefix sums
- Final answer is $dp_{n, k}$.
## Why I suck
- I initially thought it was a greedy algorithm, but then I realized it had to be $K$ *contiguous* subarrays in the original array
	- Then I realized it was wrong, until I tried to think about subproblems again.
- Int. Overflow.
	- Printing out `%d` in C makes everything, even 64-bit integers, into 32-bit integers. Must do `%lld` instead.
- Didn't exclude any unreachable values.