# CF Edu Round 104
Probably the most successful contest I've ever taken.
## A
The smallest number in the list will not be able to beat anyone, therefore we remove all instances of the smallest number
## B
I still can't prove this question, and I found it really hard for a B. This is trivial for even $n$, but not for odd $n$. Basically what I ended up doing was guessing that cats A and B would meet every $\frac{k-1}{\floor{\frac{n}{2}}}$ naps, and we just needed to add this to the total. Sorcery worked.
## C
This is just a complete graph. If $n$ is odd, then all edges can be directed such that indegree equals outdegree. But if $n$ is even, then one set of edges will need to remain undirected and we can direct the rest.
## D
haha wolfram go brrrrrr
## E
I had an interesting solution I didn't see very often. Basically for each step (2, 3, 4) we find the blocked-off predecessors. We then use range-minimum queries to find the minimum possible total cost $c_{i,j}$ for the previous steps assuming that we are on step $j$ and chose $i$ on the $j$th step.

Was a more annoying implementation but I still liked the question nonetheless.

This also turned out to be the official solution : )