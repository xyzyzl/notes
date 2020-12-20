# IOI19-shoes
#Greedy #BIT
## Problem Statement
- $\dfrac{N}{2}$ pairs of shoes, for a total of $N$ shoes
- Rearrange shoes into a "valid arrangement"
	- for all $i$ shoes $2i$ and $2i+1$ are the same size
	- Shoe $2i$ is a left shoe, $2i+1$ a right shoe
- Swap two adjacent shoes in one move, find the min. number of moves to get a valid arrangement
## Solution
- For every pair of shoes, use swaps to move the shoes to the correct position.
	- Process the shoes in order from the leftmost to rightmost in terms of the leftmost shoe (not necessarily the left shoe).
	- Each time, move the rightmost shoe left. If the rightmost shoe is the left shoe, use another swap to move them into place.
	- Use a BIT to keep track of how many moves are needed, as this value is dynamic. Remove each pair of shoes after processing it. This is OK because (proof below).
- Proof that the greedy (with BIT) works:
	1. Feels right
	2. We only move the rightmost shoe of each pair to the leftmost shoe of each pair, so we will never need to come across any shoes we've already processed.