# Problem Statement
#DP #Range-DP 
- Farmer John has a string. In one step add a prefix or suffix to the front or the back of the current string
	- `ABC` can become `AABC` or `ABCC`.
	- Find the number of ways to create the given string with 1 or more steps
# Solution
- let $dp_{i,j}$ be the amount of ways to construct $S_{i,j}$
- clearly we can have a transition $dp_{i,j} = dp_{i,k} + dp_{k+1,j}$
	- all that remains is calculating the appropriate $dp_{i,k}$
	- fix the lengths of one of the substrings and try to search for prefixes and suffixes
	- add those into the transition if they apply
- remove the initial string $S$ because 0 operations were applied
- Total time $O(N^3)$, roughly.
## Issues
- I totally forgot about the **only prefixes and suffixes** part
- implementation details, including not finding length $i$ substrings and including all substrings (which is not the problem text, that would increase the time complexity and make the question significantly more difficult)