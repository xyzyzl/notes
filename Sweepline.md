# Sweepline
## General idea
- The basic concept of algorithms is iterating ("sweeping")	from one end to another on a set of points. For example, if we know the $x$-values of specific points on a graph, we can sweep from left to right wrt $x$.
	- These are usually event points in order to speed up the process for higher $x$ values.
- Generally 4 steps
	1. Find events of interest
		1. Some of these events of interest will be active at a given time.
	2. Use some DS (usually a set) to enqueue and dequeue active points
	3. Find the answer from the active points
## Problems
- [[USACO MAR13-hillwalk]]