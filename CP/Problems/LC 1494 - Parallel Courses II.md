# LC 1494 - Parallel Courses II
## Problem Statement
- $n \leq 15$ courses (!!)
- $k \leq n$ courses can be taken per semester
- a bunch of edges
- find the minimum number of semesters needed to finish all $n$ courses
## Solution
- $n \leq 15$ (!!) motivates bitmask DP
- let $dp_{msk}$ be the number of semesters to finish a subset of the $n$ courses
	- take away the nodes with indegree 0 and recalculate
	- if this number is greater than $k$ take out groups of $k$ at a time and recalculate
- final answer is $dp_{2^n-1}$