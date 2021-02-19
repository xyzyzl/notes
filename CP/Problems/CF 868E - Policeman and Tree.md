# CF 868E
[Problem Statement](https://codeforces.com/contest/868/problem/e)

## Solution
- Let $dp_{e,in,out}$ be the smallest time if the policeman just traversed the edge $e$, there are $in$ criminals in the subtree in front of the policeman, and $out$ criminals in the other part of the tree.
- Start from $S$ and go to another edges. The final states will be the edges $S \to X$.
- If an edge $e$ leads to a leaf node, then all criminals at that leaf node will be captured
	- Therefore, we have $dp_{e',out,0}$ as the next state if $e'$ is the reverse edge of $e$.
- Then, iterate over all future $e_n$ and $in_n$ and find the maximum time to finish the state $dp_{e_n, in_n, in+out-in_n}$.
	- Return this maximum value as $dp_{e,in,out}$.
### This thing took 1.5 hours to code up
- Around 45 minutes was debugging incorrect input and wrong parentheses.
	- I actually forgot about 0 based vs 1 based indexing and also about surrounding an xor with parentheses. This caused a bunch of wrong answers that somehow took over an hour to find