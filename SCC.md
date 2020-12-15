# SCC Notes
- SCC = strongly connected component
	- Every node $u$ in an SCC must be able to be visited by all other nodes $v$ in the SCC
	- SCC graph becomes a DAG after merging all SCC
	- Can find SCC's with Tarjan in $O(n+m)$
- Example: CF999E
	- Given a graph, find the minimum number of directed edges needed to be added to make all edges reachable from node 1.
		- Create the SCC DAG
		- Find number of nodes in the SCC DAG with indegree zero. If node 1 is one of these nodes, subtract 1. Otherwise, the number of edges needed is the number of nodes in the SCC DAG with indegree zero.
## 2-SAT (WIP)
- We have $n$ boolean variables and $m$ constraints. Add true/false to variables such that all constraints are made.
	- 2-SAT is when there are up to two variables in each constraint
	- Solvable in linear time with SCC
	- Higher numbers of variabels are NP-Complete.
- Directed graph with each constraint becoming two edges.