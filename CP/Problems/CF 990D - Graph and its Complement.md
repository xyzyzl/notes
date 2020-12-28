# CF 990D
#Graphs #Implementation
- $n$ nodes, create a graph $G$ with complement $H$.
- $G$ must have $a$ connected components
- $H$ must have $b$ connected components
- find a suiting $G$ or state that it doesn't exist
## Solution
- There's only a solution if one of $a$ or $b$ is 1
- If $a=1$, then link node $i$ to node $i+1$ for nodes $0$ to $n-a-1$.
	- Do the same if $b=1$.
- If both are $1$, then it's possible unless $n=2$ or $n=3$. It can be easily seen that these cases don't work but larger ones do
## Why I suck
- Didn't implement the $n=2$ or $n=3$ cases
- Also implemented a thing that didn't even work, got stuck in it, and then realized that what I did didn't actually work. 
	- It did pass the samples but the samples were extremely weak and I didn't really double check it before sending it in