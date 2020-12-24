# CF 1408D - Searchlights
#Brute-force 
## Problem Statement
- $n$ robbers at coordinates $(a_1, b_1), (a_2, b_2), \dotsc, (a_n, b_n)$.
- $m$ lights at coordinates $(c_1, d_1), (c_2, d_2), \dotsc, (c_m, d_m)$.
- A light can see a robber if $a_i \leq c_j$ and $b_d \leq d_j$, in other words, the robber is below AND to the left of the light
- **All** robbers move either UP or RIGHT in a move
- Find the minimum number of moves until all robbers are safe
## Solution
- For each pair $(i, j)$ of criminals $i$ and searchlights $j$, find the maximum $x$ such that moving $x$ requires the criminal to move above the searchlight.
	- This $x$ is clearly $c_j - a_i$. The $y$ distance the criminal needs to move to be above the searchlight is $d_j - b_i + 1$.
	- Store all of these maximum $x$ values into an array, with $A_x = d_j - b_i + 1$. Thus, $A_i$ is the minimum vertical distance needed if all criminals make $i$ horizontal moves.
	- Take suffix maxima over $A_i$
	- Brute force over all $i$ from $1$ to $1000000$, trying to minimize $i+A_i$.
## Mistakes
- We can ignore pairs $(i, j)$ such that $c_j < a_i$. Otherwise the values in the array will be less than 0 and the code will RTE.
- Each time we set a value in the array, we maximize $A_x$ each time. If there are multiple $(i, j)$ with the same $x$ value, we take the maximum of all of them.
	- Not taking the maximum leads to WA.