# USACO feb20-help
#Sweepline 
## Problem Statement
- $N$ segments on a 1D number line
- $i$th segment contains all reals $x$ s.t. $l_i \leq x \leq r_i \leq 2N$.
- Let the *union* of a set of segments be the total area of all segments in the set
- Let the *complexity* of a set be the number of contiguous regions in the set
- Find the sum of complexities over all $2^n$ sets.
## Solution
### Test Case 1
- Brute force over every segment
### In General
- Go through the segments in left-to-right order
- Every time we add a segment $[l_i, r_i]$, add all other subsets such that $l_i$ is the leftmost point in the union. 
	- Sweeping left to right, add 1 at the start of a segment and subtract 1 at the end of a segment. This can be modelled as a stack.
	- The answer for each segment added is $2^{n-\# \text{segments in stack}}$.