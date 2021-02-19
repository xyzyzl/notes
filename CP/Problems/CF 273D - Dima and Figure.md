# CF 273D - Dima and Figure
## Problem Statement
- given $n, m$. construct an $n \times m$ grid
- want to color each square black or white such that the black squares
	- form a contiguous region
	- have Manhattan distance from $(x, y)$ to $(a, b)$ along *only black squares* be $|x-a|+|y-b|$
- find number of possible colorings. there must be at least one black square
## Solution
- clearly because it's counting it's most likely some math wrangling or DP
- after trying to do math it becomes very hard so it's probably DP
- we look at the two ends of the black region in the middle. we know that
	- the left end of each interval decreases until it might turn around, and then increases until the end. it does not necessarily need to decrease or increase but then it's monotonic
	- the right is the opposite. increasing and then decreasing in the manner previously described
- let $dp(i, l, r, dec_l, dec_r)$ be the number of ways with
	- first $i$ rows are filled in
	- the black interval on row $i$ is $[l, r]$
	- $dec_l = 1$ if $l$ has turned around and is starting to increase, and $0$ otherwise
	- $dec_r = 1$ if $r$ has turned around and is decreasing and $0$ otherwise
- we make transitions for each $i$
	- $dp(i, l, r, 0, 0) = \sum_{l \leq l' \leq r' \leq r} dp(i-1, l', r', 0, 0)$
	- $dp(i, l, r, 0, 1) = dp(l, r, 1, 0) = dp(l-1, r, 0, 0) + \sum_{l' \leq l \leq r' \leq r} dp(i-1, l', r', 1, 0)$
	- $dp(i, l, r, 1, 1) = dp(l-1, r+1, 0, 0) + dp(l-1, r, 0, 1) + dp(l, r+1, 1, 0) + \sum_{l' \leq l \leq r \leq r'} dp(i-1, l', r', 1, 1)$
	- this is $O(nm^4)$ but we can optimize to $O(nm^2)$ with prefix sums that we can compute during the DP transition.
	- we can also optimize memory (unnecessarily but it may be needed on future questions) by ignoring $i$ in our dp array