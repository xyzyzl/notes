# CF 101630J - Journey from Petersburg to Moscow
#Dijkstra 
## Problem Statement
- Given a graph with $n$ vertices and $m$ edges
- Want to find the shortest path given that only the $k$ heaviest edges count.
- $n \leq 3000, m \leq 3000, k < n$
## Solution
Assuming we don't have the $k$-heaviest-edges condition, we can find the shortest path quite easily. Similar to USACO dec19-pump and USACO dec13-mroute, we can iterate for every bottleneck edge $u \leftrightarrow v$. Assuming that $u \leftrightarrow v$ is the $k$-th heaviest edge, we can easily find the shortest path for the rest of the graph and add $k \cdot wt(u \leftrightarrow v)$ through Dijkstra's algorithm.

After this, we still need to run a vanilla Dijkstra over the original graph to capture any shortest paths with under $k$ edges.

### A lot of things
1. Check for int overflow.
2. We cannot check the sum $1 \to u + u \to v + v \to n$ for all edges $u \to v$, because this may not produce the correct cumulative shortest path. (WA)
3. **Remember to do the vanilla Dijkstra over the original graph to capture any short paths.** (WA)
	1. No, checking the edge length of the shortest path will not work. 
4. I coded up the Dijkstra wrong, so it wasn't optimized. For Dijkstra I *need* a visited array to ensure that we don't do the same shortest path check again. (TLE)
	1. The Dijkstra template has been updated accordingly. Oops.
5. priority_queue is also faster than set, which has been changed. But looping through the priority_queue in the wrong order makes the algorithm slower than set. (TLE)
	1. Must have `priority_queue<pii, vii, greater<pii> >` instead of just `priority_queue<pii>`. I thought I'd remembered this.