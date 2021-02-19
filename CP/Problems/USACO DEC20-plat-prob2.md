# USACO DEC20-plat-prob2 - Spaceship
## Problem Statement
- given $N$ rooms labelled $1 \cdot N$, and an adjacency matrix showing which rooms have a door to which other rooms
- given $K$ buttons. if a button $i$ is pressed, it is deactivated until another button $j > i$ is pressed
	- press a button every time Bessie travels to another room, and when she starts
- given $Q$ queries of starting button, starting pos, ending button, and ending position
	- find the number of ways for Bessie to satisfy all such conditions
## First subtask
- bitmask DP on subsets of $K$ buttons and try to reach the end with the correct button
- literal instasolve
- interesting how the "first subtask" of this plat problem would've constituted a full problem 5 years ago
## Everything else
- DP with offline characteristics
-  let $dp_{i, j, k}$ be the number of ways to go from node $i$ to node $j$ with all buttons pressed $\leq k$
- use the $N$ nodes described, but also $2Q$ other nodes for query start and end
- $\forall$ intermediate nodes $x$, find the number of ways to go from $i \to x$ and then $x \to j$.
	- divide this into $i \to x$ and $x \to j$ components $L_i$ and $R_j$, respectively
	- if $i=x$ or $i$ is a query node with starting point $x$ then add $1$ to $L_i$
	- if $j=x$ or $j$ is a query node with ending point $x$ then add $1$ to $R_j$
	- then assume starting node of $i$ and another node $j \to x$. $i$ can be a start query node but $j$ must be a node in the $N$ main nodes
		- $L_i := L_i + dp_{i, j, k-1}$. we use $k-1$ because using $k$ would make a node $(x, k)$ impossible; we also cannot use anything $>k$ because that would break the invariant. we're adding the number of ways to go from $i \to j$ because $j \to x$ is only one edge and there's only 1 way to go there.
	- do the same with node $x \to i$ and ending node $j$
		- $R_j := R_j + dp_{i, j, k-1}$.
	- finally, $\forall$ nodes $i, j$, $dp_{i, j, k} = dp_{i, j, k} + L_i \cdot R_j$.
- output $dp_{start(q), end(q), k}$ for all queries $q$ at the end
## This took *very* long
- mostly finding the states for the larger subtasks because the first subtask bitmask DP state evidently did not work for larger $K$
- however there were a few bugs in my code, most apparently one where I used incorrect indexing
	- always check for $0$ or $1$ based indexing when debugging because sometimes I forget how the input works