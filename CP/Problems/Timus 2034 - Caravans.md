# Timus 2034 - Caravans
#Graphs #BFS 
## Problem Statement
- $n$ nodes in unweighted graph
- want to find the longest shortest distance between $r$ and a shortest path $s \to f$.
## Solution
1. Find shortest path from $r$ to all other nodes using BFS
2. Find shortest path from $s$ to all other nodes using BFS, but keep another parameter $d_3$ showing the shortest way to get to a node along the path $s \to v$ from $r$
3. Output $d_3[f]$.
## How I screwed up
BFS visited array should be updated every time the node is first seen, not the time that it first extends to other nodes. Not doing this could lead to MLE by adding many already visited nodes that claim to be unvisited, and then processing them multiple times. I don't understand how BFS works.