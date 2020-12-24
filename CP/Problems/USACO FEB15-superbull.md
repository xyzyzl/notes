# USACO FEB15-superbull
#Graphs #MST
- Have $N$ teams, each team has ID $a_i$
- If teams $i,j$ play score is $a_i \text{ XOR } a_j$.
	- Each game has a winner who advances and a loser who is eliminated
- Find total maximum possible score if matches and winners chosen optimally
## Solution
- Make the $a_i \text{ XOR } a_j$ into the weight for an edge $i \to j$.
- This is a complete graph, so we can represent it with an adjacency matrix
- Use basic Prim to find the MST, which is representative of the games played.