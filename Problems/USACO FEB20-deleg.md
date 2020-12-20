# USACO feb20-deleg
#DP #Graphs #Tree-DP
## Problem Statement
- tree with $N$ nodes
- try to divide $N-1$ edges into $K$ sets of paths
	- find all $K$ such that this works
## Solution
- first note that $K | N-1$ must be true for all working $K$
	- thus we have at most $\sqrt N$ such numbers
	- for each node we find the number of nodes stemming from each edge leading out of the node
		- If you cannot group all of the ungrouped nodes converging around any node, this pairing is impossible.
