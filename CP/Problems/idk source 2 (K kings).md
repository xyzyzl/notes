# idk source #2
#DP #Bitmasks
- Place $K$ chess kings on an $N \times N$ grid s.t. no two kings can attack
- $N \leq 9, K \leq N^2$.
## Solution
- Let $dp_{i, j, m}$ be the number of ways to put $j$ kings on the first $i$ rows s.t. the kings on the $i$-th row are put in pattern $m$. $m$ is a bitmask
- Then $$dp_{i, j, m} = \sum_{m = 0} ^ {2^n-1} dp_{i-1, j-|m|, m'}$$ where $m'$ is another suitable bitmask for the previous row and $|m|$ is the number of ones in $m$.
	- Remove cases where $m$ or $m'$ have adjacent bits or one of $m$ and $m'$, $m$ and $2m'$, or $2m$ and $m'$ have common bits
- Final answer is $$\sum_{m = 0} ^ {2^n-1} dp_{n, k, m}.$$
## Why I suck
- Forgot to remove invalid cases
- Accidentally did $dp_{i-1}$ instead of $dp_{i}$ somehow.