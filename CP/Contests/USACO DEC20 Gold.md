# USACO Summary
1. Problem name: Replication, Method: BFS
	1. flirted around with some ideas, including that the only valid ending nodes for the initial robot were nodes such that $D_s \leq D_r$, where $D_s$ is the distance from a starting node and $D_r$ is the distance from a rock
	2. could not work around some implementation details, ran out of time and just went for the first 5 test cases
	3. overall score: 5/20
	4. **UPDATE 12/27**: I found a strategy for the implementation details I had missed in concept, and realized that this isn't something solely with coding my ideas but rather how to intelligently use BFS.
		1. This isn't bare implementation but rather a specific type of BFS that I'm rather unfamiliar with; so it's still more problem solving ability than how to code
2. Problem name: Bovine Genetics, Method: DP??
	1. not totally sure how to do what the question asked. tried a brute force but it didn't work so I just went for samples
	2. overall score: 2/20
	3. **UPDATE 12/26:** now I know the DP state but transitions seem a little bit hard... 
	4. **UPDATE 12/27:** now I got it. There are only two possible transitions: adding a new character to the current sequence or making a new sequence. 
		1. Adding a new character to the current sequence requires the characters to all be distinct. We only need to check the last character $k_2$ and the new character $S_i$ each time, so we store that in our DP state.
		2. Making a new sequence requires the first element of the previous sequence $k_0$ and the last element of the current sequence $k_2$ to be equal, and the new $k_0$ will be the first element $k_1$ of the current sequence.
		3. Therefore, we make a $dp_{i, k_0, k_1, k_2}$ and implement the previous two transitions.
		4. I originally overcomplicated the transitions, because I thought it was range/prefix DP. Turns out that I had just forgotten to include the characters into the DP states.
3. Problem name: Square Pasture, Method: sweepline
	1. Went for the first partial because it was very doable
	2. Tried to optimize for the second partial but there were some insurmountable implementation details
	3. Had some idea for an AC solution but again the same implementation issues persisted.
	4. overall score: 5/20
	5. **UPDATE 12/26** so I got it.
		1. Idea for the AC solution (which I had in contest) was iterating over left and right. I didn't know how to store the $y$-values in contest, which turned out to be using a set
		2. Implementing this turned out to be a challenge, also because `size_t` is actually *unsigned*; it's a very tiny brained move to go `x.size()-1` or something. Also note that you cannot compare a negative into to a `size_t`. Hard lesson learned.

Total score: **200**
Generally feel like the issue this time was more with implementation details