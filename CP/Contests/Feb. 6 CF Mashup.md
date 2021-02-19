# Feb. 6 CF Mashup
## Problem A
#DP
## Problem B
No idea
## Problem C
#2-Pointers #Greedy 
This obviously is a 2-pointer problem. However, what the two pointers are is not clear. We can have the two pointers be $i, j$ for elements in the array, but we aren't sure how to iterate through the two arrays.

One incorrect way that is close the the real answer is to choose the larger element in each array. This is very simple, but breaks on cases where a tiny $a_i$ is followed by a huge $a_{i+1}$. In this case the $a_{i+1}$ will be placed much later than it meeds to. (This is what I originally thought of and it didn't work.)

Instead, we "bundle" each contiguous increasing segment into a group; that way, large and small numbers balance each other out. We treat these as intervals, and only consider the arith. mean of all numbers in this interval and do the same thing as previous. Now everything should be in a decreasing sequence. (I forgot to treat it as a mean originally, and then I remembered halfway but didn't update it originally)