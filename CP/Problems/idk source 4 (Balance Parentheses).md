# idk source 4
#DP #Range-DP 
- Given a string $S$ of length $n$ with square and curved brackets (`[`, `]`, `(`, `)`)
- Need to find the min. number of brackets that need to be added to balance the brackets
- `()`, `[]`, `([])` are balanced but `([)]` and `())(` aren't
## Solution
- let $dp_{i, j}$ be the minimum number of brackets needed for range $[i, j]$. 
- we know that $dp_{i, i} = 1$
- transitions are from lower length to higher length. $dp_{i, j} = \min_{i \leq k < j} (dp_{i, k} + dp_{k+1, j})$
	- If $S_i = S_j$ then $dp_{i, j} = dp_{i+1, j-1}$. If $i=j-1$, then this is $0$.
- final state is $dp_{0, n-1}$ (or $[1, n]$ if you used 1 based indexing)
### HOW I BECAME A CODING PRO
- originally thought that the question would be trivialized if it were just rounded / square brackets, which it would be
- then I thought it could've been a greedy except you don't know which ones to add a complement to, where, and how it would affect the total
- so I thought that it could be range DP, but then I didn't know how the transitions worked
	- after thinking it through again I figured out the transitions