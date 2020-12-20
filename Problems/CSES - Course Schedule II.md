# CSES - Course Schedule II
#Graphs #Topo
## Problem Statement
- Find a topological ordering such that 1 appears as early as possible. Ties are broken by 2 appearing as early as possible, and so on.

## Solution
- Use a priority queue
	- Each time, pop off the smallest index. Keep a set of the indices or something and pop the smallest one
## Why did multiset not work?
- Returned the lex. min. topological sort as opposed to the one with smallest numbers appearing first. 
