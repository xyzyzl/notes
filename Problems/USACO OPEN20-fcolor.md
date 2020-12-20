# open20-fcolor
#Graphs #DSU
- $N$ nodes, each with a color $c_i$.
- $M$ directed edges from $a$ to $b$, saying that $b$ admires $a$.
- If two nodes $i,j$ both admire a node $v$, then $c_i=c_j$.
- Find the lexicographically minimum sequence $c$ with the most colors
## Solution
- If two nodes $i,j$ both admire a node $v$, then it suffices to treat $i,j$ as a single node. Thus, all nodes that admire $i,j$ will now be stated to admire a single node $x$. The best way to do this is DSU.
	- Also need to merge the adjacency lists, which can be done with the DSU merge.
	- The node should be the smaller number.
	- Repeat as long as you have two nodes that admire another node
- At the end, everything in the same connected component should have the same color. This is just trivial processing to get to the answer.