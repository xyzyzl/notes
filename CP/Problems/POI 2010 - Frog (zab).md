# POI 2010 - Frog (zab)
## Problem Statement
- A frog jumps from point $i$ to the $k$th closest point, ties are broken by the lower index
- Find the location of the frog $m$ seconds after
- $n$ points, $n \leq 10^6$
- $m \leq 10^{18}$
- $k < n$
## Solution
Time complexity: $O(n \log n)$ worst case

First, note that the design of the problem resembles that of a functional graph; each node leads to exactly one other node.

Through a two-pointer algorithm (capturing the range of the $k$ closest points to each $i$) we can find the (singular) edge for each node. Then, we use binary jumping to find the end node.

There's one caveat though, $m \leq 10^{18}$. However, it's worth noting that most of these $m$ jumps for a very large $m$ will be spent in a cycle. Thus, we just need to find the cycle size for each cycle. Although there will be some points that are not in cycles, we know that we are at most $n$ nodes away from a cycle. Therefore, we can calculate the position of the frog after $n$ jumps, and then calculate its movement along the cycle. All of the complete periods along the cycle can be ignored because they bring the frog back to where it was. We only need to calculate the last, incomplete period.

If $m \leq n$, then $m$ is small enough for us to calculate directly.

Note that fast I/O may be required to pass the question, as I/O takes out a lot of time. Generally it's a good idea to always implement fast I/O from the start.