# USACO open20-exercise
#DP #NT
## Problem Statement
- $N$ cows, find the number $K$ such that there exists a permutation of the $N$ cows that requires $K$ steps to rereach identity.
## Solution
- For all primes $p$, try adding a cycle of length $p$
- Let $dp_{i, j}$ be the answer for the first $i$ primes and $j$ cows
	- clearly $dp_{i, j} = dp_{i-1, j}$ works. Just use all previous primes.
	- then add all new primes $p$ and prime powers $p^x$. Doing $p^x \cdot dp_{i-1}{j-p}$ works because everything in $dp_{i-1}$ has a lower prime power and is thus relatively prime to $p^x$.
- The final answer is $dp_{P, N}$ where $P$ is the total number of primes $\leq N$.