# CF 1485E - Move and Swap
## Problem Statement
- $n$ vertices, each vertex 2 to $n$ has score $a_i$
	- all leaves are equidistant
- has a red and blue coin on vertex 1 initially\
- in each step:
	- move the red coin down to another child of the current node
	- move the blue coin to a node one more unit farther from the origin (doesn't need to be a child)
	- you can swap here if you want
- find the maximum score if you add $a_{blue}-a_{red}$ each time
## Solution
- let $dp_{i}$ be the max score up to the red node being node $i$ after some steps
- then we have two possibilities: swap or no swap
	- sort the $a$-values of every node distance $k$ away
	- if we don't swap we have $dp_i = dp_{par_{i}}+\max(a_i-a_{smallest_k}, a_{largest_k}-a_i)$
	- otherwise we have $dp_i = dp_{par_i}+|a_j-a_i|$. We can try to do this for cases $a_j \leq a_i$ and $a_j > a_i$ separately as we can maximize $a_j$ going up or down.
## Debug process
- logical errors made it so that we did not maximize $a_j$ going down, although we did going up