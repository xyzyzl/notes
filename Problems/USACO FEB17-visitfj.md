# Problem Statement
#Graphs #BFS
- $N \times N$ grid
- Edge between $(i, j)$ and four cardinally adj points if they exist, has cost $T$
- Each element of the grid has a cost $gd_{i,j}$, but only add cost on every third node reached
- FInd minimum cost to go from $(0, 0)$ to $(N-1, N-1)$.

# Solution
- Initialize $dist_{i,j}$
- Start BFS from $(0, 0)$ to the end
- Travel 3 units each time and see how much time it takes, add it if it gives a shorter path
- If we are under 3 units away from the end $(n-1, n-1)$ we can finish by just travelling to $(n-1, n-1)$
- This is definitely fast enough because $N \leq 100$.

## Takeaways
- Implementation had many holes because of overflow correction
	- Also type brackets in correctly (this mistake is embarassingly common)
- Make sure that there is termination condition for the BFS (otherwise it's just dead loop)
- Ensure that all desired conditions are met in order for the BFS to be processed.