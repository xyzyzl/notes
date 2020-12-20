# USACO jan19-time
#DP #Graphs
## Problem Statement
- $N$ cities, $M$ directed edges
- city $i$ -> $m_i \leq 1000$ money
- cost to travel to $T$ cities is $CT^2$.
- find maximum amount of profit
## Solution
- **observation:** only need to travel at most 1000 times because otherwise you will evidently get a negative profit
- therefore let $dp_{i,t}$ be the revenue when at city $i$ after time $t$
	- clearly $dp_{i,t} = max(dp_{i,t}, dp_{x,t-1}+m_i)$ for all $x$ such that $x \to i$ is an edge
- the end state is $dp_{0,t}$ for all $t$. Find the maximum profit ($dp_{0,t} - Ct^2$) among all $t \leq 1000$.