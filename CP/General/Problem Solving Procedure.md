# Problem Solving Procedure
## Analyzing the Method
- Read through the problem carefully and find things
- Work through the sample test data and try to solve the problem.
	- Sometimes the samples are trivial and there is nothing to work on, but still try to work on them
- Make observations on key properties that may propel to a solution
- Then read the question constraints and try to find a correct running speed for a possible algorithm
	- Sometimes question constraints literally don't exist
	- Sometimes questions become too hard when constraints are high but are easy when constraints are low.
- Think in all methods (not just one).
	- BFS vs DFS
	- If one method is too hard think of another one.
	- Charts are friends
- Use brute force code to create test files and analyze patterns during the contests
## Implementation
- Mostly need to write pseudocode during the analysis to speed the process up
	- Make a list of things you need to do in order to solve the problem
	- Also I've had a few times where I've had an idea and it just disappeared; just write the details down.
- Then also need to like find an appropriate DS or template algorithm to base your solution off of
- Then find a way to use this algorithm to solve the question.
	- Use methods from the algorithm, such as segmenttree.update() or smth
## Debugging
- General WA
	- Make debugging output at various stages w/ `cerr`
- **INT OVERFLOW**
	- Generally when you get a wrong submission first try `#define int long long` and try again
		- Please don't define any "int" things before `#define int long long` because they'll still be 32-bit integers
	- Or if that gives MLE, try to check the constraints and turn only what needs to be long long into long long
- LL overflow?
	- If it's an infinity variable: Set LLINF = 1e16 or 1e15 s.t. it doesn't nuke itself
- Negative numbers
	- In optimization problems: if values can be negative, initialize as -LL_INF; if they can't, initialize to 0.
- Indexing
	- Check if it is $0$-based or $1$-based indexing.
- Array size too small
	- Check the constraints for $N$ in the problem if errors such as RTE, WA, and TLE occur but the time complexity seems OK and there are confirmed to be no dead loops.
- Multiple test cases
	- `memset` may be slow if arrays are huge and the number of test cases is huge. consider using local vectors instead of global arrays in that case
	- Need to reset array every single test case w/ `memset` or use local vars