# CodeChef LEBLOCKS
#DP #Implementation #Combo
- Given $n\leq 20$ blocks, each with length at most 10
- Each block is $A_i$ units long and has color $C_i$.
	- No three blocks have the same color.
- Order the blocks in some way
- Find the expected number of pairs $(i, j)$ s.t. $j-i = K$ and the color at index $i$ is equal to the color at index $j$
## Solution
- There are two ways for such pairs to exist: either they're from the same block or they're from different isochromatic blocks
- Let $dp_{c, k, L}$ be the number of ways to place $k$ blocks *not* of color $c$ to form a chain of length $L$.
	- $c$ will remain constant.
	- $dp_{c, k, L} += dp_{c, k+1, L+A_i}$ at each new index $i$.
- It's easy to then find the number of ways to place the blocks given that two isochromatic blocks are some distance away.
	- $dp_{c, k, L} \cdot k! \cdot (n-2-k)! \cdot X$ where $X$ is the number of valid pairs in this position
- It's even easier for values in the same block. Just $A_i-K$ for each one.