# Problem Statement
- $M \times N$ grid
- Find the largest $B$ such that the pattern can be drawn with $B \times B$ overlapping squares.
# Solution
- Binary search for $B$, clearly if $B$ works then $B-1$ works, so binary search is valid.
	- Now all we need to do is find if the configuration is valid
	- This can be done with 2D prefix sums (basically just the DP transition that we used in FEB18-paintbarn)
## How'd I screw this up??
- Originally did not actually do the prefix sums, but only did one iteration
- Then added the prefix sums, but did not use the correct array names when calculating the prefix sums
- Then wrote the prefix sums wrong, which made the calculated values all incorrect