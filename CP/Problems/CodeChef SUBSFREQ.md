# Codechef SUBSFREQ
- Have a sequence $A_1$ to $A_n$ of $n$ numbers all $\in [1, n]$.
- In each subsequence, add the number with most frequency
- Find the number of subsequences where the number $i$ is chosen for all $1 \leq i \leq n$.
## Solution
- If all $A_i$ are distinct then we are immediately done; just sort by increasing order and the number $k$ appears $2^{n-k}$ times
- Otherwise we find the frequencies $F_x$ of each $x \in [1,n]$.
- Key observation here is that if we process in increasing order of frequency and decreasing order of number, the current number will be the one selected
	- Therefore we just find the number of subsequences including up to the current number
	- Let $c_x$ be the current desired frequency of $x$.
	- The number of desired sequences is, for all $l$, $$\dbinom{F_l}{i} \cdot \prod_{x | c_x < F_x} \sum_{j=1, j < c_x} \dbinom{F_x}{j},$$