# CSES - Distinct Values Queries
## Problem Statement
- Given an array of size $n \leq 200000$, find the number of distinct values in each range $[a,b]$ for $q \leq 200000$ queries.
	- The values can be as large as $10^9$.
## Solution
One solution would just be looping through each of the intervals and finding the relevant data. This would take $O(nq)$ time, which is too slow.

Clearly a BIT is desirable for range queries, but we cannot solve this question linearly even with a BIT.

We can have $x$ BITs, but this would have at least $O(x)$ memory and time. Using coordinate compression we can turn this into $n$ BITs, but that is still $O(nq\lg n)$. This is still too slow. Therefore, we must only use one BIT.

Using offline queries, we can rearrange our queries and process them in an order that speeds up the algorithm. Let's process queries in order of decreasing $a$-value. 

Add $i$ into the BIT, and remove the other instances of $x_i$ already in the BIT. If we do this each time, there is at most one other instance of $x_i$ currently in the array.

This turns it into a basic BIT question, which we solve normally.