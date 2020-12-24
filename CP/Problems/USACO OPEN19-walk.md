# USACO open19-walk
#Graphs #MST
## Problem Statement
- $N \leq 7500$ cows into $K$ non-empty groups such that no two cows can interact between different groups without walking
- Cows $(x,y)$ with $x\leq y$ are willing to walk $(Ax+By) \pmod M$ miles to see each other
- Assign groups s.t. minimum number of miles any two cows are willing to walk to see each other is maximized
## Solution
- We have a complete graph with known edge weights, and want to find the minimum spanning tree.
	- Use $O(N^2)$ Prim.
	- The groups are connected by the minimum spanning tree, and removing $K-1$ edges creates $K$ connected components.
- It's optimal to remove the $K-1$ highest-weight edges in the MST.
	- Thus, the desired value is the $K-1$th largest edge in the tree.
	- This can be found by sorting the resulting edge weights retrieved from Prim.