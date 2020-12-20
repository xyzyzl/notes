# USACO JAN15-cowroute
#Graphs #Dijkstra
## Problem Statement
- $N \leq 1000$ series of edges, each following a directed route with $m \leq 100$ nodes and with a collective cost $c$
1. Find shortest path between nodes $A$ and $B$
2. Find the fewest number of edges to get from $A$ to $B$ with the shortest path

## Solution
- Store costs into an adjacency matrix, with the cost from any nodes $u$ to $v$ in a series $i$ such that $u$ is before $v$ being $c_i$.
	- Minimize the cost each time, and if two routes have the same cost, tiebreak by length of the path
- Use Dijkstra to find both the shortest path from $A$ to $B$ (traditionally) but also adding a parameter to tiebreak by shortest path length if the path weights are equal

### Issues in code
- Initially read the entire question wrong and forgot the entirety of part 2. 
- Different paths have different path lengths. I initially set path lengths to $1$ for every single path $u \rightarrow v$, even if the paths involved intermediates.
- Then, I calculated the overall shortest path length from $u$ to $v$ regardless of if it was part of the shortest path from $u$ to $v$.
- Fixing these errors gave AC